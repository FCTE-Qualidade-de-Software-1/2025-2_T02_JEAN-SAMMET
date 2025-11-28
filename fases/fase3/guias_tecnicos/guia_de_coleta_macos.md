# Guia Técnico de Coleta: macOS

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsável:** João Filipe de Oliveira Souza
**Data:** 23/11/2025
**Versão:** 1.2

## 1. Objetivo

Este documento detalha os procedimentos técnicos para a coleta de todas as métricas definidas na Fase 3. Isso inclui as métricas de Eficiência como RAM, LCP e Benchmarks, além das métricas de Portabilidade, utilizando o Mozilla Firefox em ambiente **macOS**.

## 2. Pré-requisitos

Para executar este guia, o responsável deve garantir:

* **Software:** Mozilla Firefox instalado.
* **Ferramenta de RAM:** Monitor de Atividade, que já vem instalado no macOS, ou o Terminal.
* **Ambiente:** Certifique-se de que o computador está conectado à energia, evitando o modo de economia de bateria durante os testes.

## 3. Procedimento de Coleta: Eficiência (M1)

### 3.1. Métrica M1.1 - Consumo de Memória RAM

O Firefox no macOS utiliza múltiplos processos, como Main, Web Content e GPU. Para medir o consumo total com precisão, recomenda-se o uso do Terminal para somar todos os processos automaticamente.

**Ferramenta:** Terminal (Zsh).

1.  **Preparação:**
    * Inicie o Firefox.
    * Prepare o cenário de teste, sendo Carga Leve ou Carga Pesada.
    * Aguarde 60 segundos para estabilização.

2.  **Execução:**
    * Abra o Terminal, que pode ser encontrado via Spotlight com Command + Espaço.
    * Copie e execute o seguinte comando:
    ```zsh
    ps -A -o rss,comm | grep -i "firefox" | awk '{sum+=$1} END {print sum/1024 " MB"}'
    ```

3.  **Registro:**
    * O terminal retornará o valor total em Megabytes.
    * Registre o valor na Planilha Mestra.
    * *Nota:* Caso prefira usar a interface gráfica, abra o **Monitor de Atividade**, vá na aba Memória, filtre por `firefox`, selecione todas as linhas e some manualmente a coluna Memória.

### 3.2. Métrica M1.2 - Tempo de Carga (LCP)

A coleta é feita diretamente no navegador utilizando as Ferramentas de Desenvolvedor.

**Ferramenta:** Firefox DevTools acessível via Command + Option + I.

1.  **Execução:**
    * Este passo deve ser repetido para os 10 sites padronizados.
    * Abra o site alvo.
    * Pressione as teclas **Command + Option + I** para abrir o DevTools.
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
    * *Nota:* Se o Firefox bloquear a colagem, digite `allow pasting` no console e tente novamente.

2.  **Registro:**
    * Anote o valor retornado em milissegundos.
    * Utilize o atalho **Command + Shift + 3** para tirar um print da tela inteira, ou **Command + Shift + 4** para selecionar a área do console.

### 3.3. Métrica M1.3 - Benchmarks

**Ferramenta:** Navegador Firefox.

**Regras de Ouro:**
* Feche outros aplicativos pesados como Xcode, Photoshop ou Docker.
* Desative o modo "Não Perturbe" ou notificações que possam aparecer na tela e interferir no teste.

1.  **Speedometer 3.0:**
    * Acesse o site `https://browserbench.org/Speedometer3.0/`.
    * Execute o teste 3 vezes, reiniciando o navegador completamente com **Command + Q** entre cada teste.
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
2.  Utilize o Firefox no macOS para verificar cada item.
3.  Preencha com:
    * **[OK]** se o recurso funciona.
    * **[FALHA]** se apresentar erro ou comportamento inesperado.
    * **[N/A]** se o item for exclusivo de ambientes mobile ou touch.
4.  Atenção especial para itens de UI nativa do macOS, como a barra de menus no topo da tela e os botões de janela tipo semáforo.
5.  Registre a contagem final na Planilha Mestra.

---

## 5. Solução de Problemas

* **Processos não aparecem no Monitor de Atividade:**
    * Verifique se o menu **Visualizar** está configurado para "Todos os Processos" e não apenas "Meus Processos".
* **Valores oscilando muito na RAM:**
    * O macOS utiliza compressão de memória agressiva. O comando de terminal sugerido utiliza a métrica RSS, que é a memória real ocupada sem compressão, sendo o padrão mais justo para comparação com outros sistemas.
* **Erro ao colar código no Console:**
    * O Firefox possui proteção contra Self-XSS. Digite `allow pasting` no console para desbloquear a ação.

---

## 6. Histórico de Versões

| Versão | Descrição | Autor(es) | Data |
| :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico para Monitor de Atividade | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 |
| 1.1 | Correção de hyperlink errado | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 |
| 1.2 | Inclusão dos procedimentos para LCP, Benchmarks e Checklists | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |