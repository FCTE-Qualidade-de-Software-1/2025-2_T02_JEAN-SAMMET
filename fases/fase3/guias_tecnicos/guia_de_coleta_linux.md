# Guia Técnico de Coleta: Linux Ubuntu

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsável:** Lucas Mendonça Arruda
**Data:** 23/11/2025
**Versão:** 1.2

## 1. Objetivo

Este documento detalha os procedimentos técnicos para a coleta de todas as métricas definidas na Fase 3. Isso engloba as métricas de Eficiência como RAM, LCP e Benchmarks, além das métricas de Portabilidade, utilizando o Mozilla Firefox em ambiente **Linux Ubuntu**.

## 2. Pré-requisitos

Para executar este guia, o responsável deve garantir:

* **Software:** Mozilla Firefox instalado, preferencialmente versão `.deb` ou `tar.gz`, embora `snap` também seja suportado.
* **Terminal:** Acesso ao terminal padrão do sistema, como Bash ou Zsh.
* **Ambiente:** Certifique-se de que não há atualizações do sistema rodando em segundo plano, como `apt upgrade` ou `snap refresh`, durante os testes.

## 3. Procedimento de Coleta: Eficiência (M1)

### 3.1. Métrica M1.1 - Consumo de Memória RAM

Devido à arquitetura multiprocesso, o Firefox cria várias instâncias. O comando abaixo lista todos os processos, extrai o uso de memória residente, conhecida como RSS, e calcula a soma total automaticamente.

**Ferramenta:** Terminal do Linux.

1.  **Preparação:**
    * Inicie o Firefox.
    * Prepare o cenário, sendo Carga Leve ou Pesada.
    * Aguarde 60 segundos para estabilização.

2.  **Execução:**
    * Abra o terminal e execute o comando abaixo:
    ```bash
    ps -C firefox -o rss= | awk '{sum+=$1} END {print sum/1024 " MB"}'
    ```

3.  **Registro:**
    * O comando retornará o valor total em MB.
    * Registre este valor na Planilha Mestra.

### 3.2. Métrica M1.2 - Tempo de Carga (LCP)

Diferente do Android, no Linux a coleta é feita diretamente no navegador utilizando as Ferramentas de Desenvolvedor.

**Ferramenta:** Firefox DevTools acessível via F12.

1.  **Execução:**
    * Este passo deve ser repetido para os 10 sites padronizados.
    * Abra o site alvo.
    * Pressione **F12** para abrir o DevTools.
    * Clique na aba **Console**.
    * Cole e execute o seguinte código JavaScript:
    ```javascript
    const observer = new PerformanceObserver((list) => {
      const entries = list.getEntries();
      const lastEntry = entries[entries.length - 1];
      console.log("LCP:", lastEntry.startTime);
    });
    observer.observe({ type: "largest-contentful-paint", buffered: true });
    ```
    * *Nota:* Se o Firefox bloquear a colagem, digite `permitir colar` ou `allow pasting` e tente novamente.

2.  **Registro:**
    * Anote o valor retornado.
    * Tire um print da tela utilizando a tecla PrintScreen ou a ferramenta de captura do Ubuntu, mostrando o console e o site ao fundo.

### 3.3. Métrica M1.3 - Benchmarks

**Ferramenta:** Navegador Firefox.

**Regras de Ouro:**
* Feche outros programas pesados como VS Code, Spotify e Docker.
* Se estiver em um notebook, conecte o cabo de energia e ajuste o perfil de energia para **Desempenho**.

1.  **Speedometer 3.0:**
    * Acesse o site `https://browserbench.org/Speedometer3.0/`.
    * Execute o teste 3 vezes, reiniciando o navegador entre cada teste.
    * Tire print do resultado final.
    * Registre a **Mediana**, que é o valor do meio, na planilha.

2.  **JetStream 2:**
    * Acesse o site `https://browserbench.org/JetStream/`.
    * Execute o teste 3 vezes, reiniciando o navegador entre cada teste.
    * Tire print do resultado final.
    * Registre a **Mediana** na planilha.

---

## 4. Procedimento de Coleta: Portabilidade (M2)

### 4.1. Checklists Manuais M2.1 e M2.2

1.  Baixe os modelos de checklist definidos na Fase 3, nomeados como `checklist_m2.1.md` e `checklist_m2.2.md`.
2.  Utilize o Firefox no ambiente Desktop para verificar cada item.
3.  Preencha com:
    * **[OK]** se o recurso funciona.
    * **[FALHA]** se apresentar erro ou comportamento inesperado.
    * **[N/A]** se o item for exclusivo de ambientes mobile ou touch.
4.  Registre a contagem final na Planilha Mestra.

---

## 5. Solução de Problemas

* **Comando de RAM retorna "0 MB" ou vazio:**
    * Isso ocorre se o nome do processo for diferente, o que é comum em versões Nightly ou algumas distros. Tente substituir `firefox` por `firefox-bin`:
    ```bash
    ps -C firefox-bin -o rss= | awk '{sum+=$1} END {print sum/1024 " MB"}'
    ```
* **Erro ao colar código no Console relativo ao LCP:**
    * O Firefox possui proteção contra Self-XSS. Digite `allow pasting`, caso o sistema esteja em inglês, ou `permitir colar` no console para desbloquear.

---

## 6. Histórico de Versões

| Versão | Descrição | Autor(es) | Data |
| :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico e script de automação | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 |
| 1.1 | Correção de hyperlink errado | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 |
| 1.2 | Inclusão dos procedimentos para LCP, Benchmarks e Checklists | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |