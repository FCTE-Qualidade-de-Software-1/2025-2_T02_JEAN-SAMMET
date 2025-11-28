# Guia Técnico de Coleta: Windows 11

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsáveis:** Rodrigo Mattos de F. A. Bezerra e Nayra Silva Nery
**Data:** 23/11/2025
**Versão:** 1.2

## 1. Objetivo

Este documento detalha os procedimentos técnicos para a coleta de todas as métricas definidas na Fase 3. Isso engloba as métricas de Eficiência como RAM, LCP e Benchmarks, além das métricas de Portabilidade, utilizando o Mozilla Firefox em ambiente **Windows 11**.

## 2. Pré-requisitos

Para executar este guia, o responsável deve garantir:

* **Software:** Mozilla Firefox instalado.
* **Permissões:** Acesso a uma conta com privilégios de **Administrador**, o que é obrigatório para leitura dos contadores de performance do sistema.
* **Terminal:** Prompt de Comando ou PowerShell configurado.
* **Ambiente:** O plano de energia do Windows deve estar configurado para **Alto Desempenho** e, caso seja um notebook, deve estar conectado à tomada.

## 3. Procedimento de Coleta: Eficiência (M1)

### 3.1. Métrica M1.1 - Consumo de Memória RAM

Para capturar o consumo de memória, utilizaremos a ferramenta nativa `typeperf`. O comando busca todos os subprocessos do Firefox e extrai a memória do Conjunto de Trabalho.

**Ferramenta:** Prompt de Comando em modo Administrador.

1.  **Preparação:**
    * Inicie o Firefox.
    * Prepare o cenário de teste, sendo Carga Leve ou Carga Pesada.
    * Aguarde 60 segundos para estabilização da memória.
    * Pressione a tecla Windows, digite **CMD**, clique com o botão direito e selecione **Executar como administrador**.

2.  **Execução:**
    * Execute o comando abaixo. Ele fará uma leitura instantânea de todos os processos do Firefox.
    ```cmd
    typeperf "\Process(firefox*)\Working Set - Private" -sc 1
    ```
    * *Nota:* Se o seu Windows estiver em português e der erro de contador não encontrado, consulte a seção Solução de Problemas abaixo.

3.  **Registro:**
    * O terminal retornará uma lista de valores separados por vírgula no formato CSV.
    * Como o Firefox usa múltiplos processos, você deve somar todos os valores numéricos retornados na última linha para obter o total.
    * A soma resultará no valor em Bytes. Converta para Megabytes dividindo por 1.048.576 e registre na Planilha Mestra.

### 3.2. Métrica M1.2 - Tempo de Carga (LCP)

A coleta é feita diretamente no navegador utilizando as Ferramentas de Desenvolvedor.

**Ferramenta:** Firefox DevTools acessível via F12.

1.  **Execução:**
    * Este passo deve ser repetido para os 10 sites padronizados.
    * Abra o site alvo.
    * Pressione a tecla **F12** ou a combinação **Ctrl + Shift + I** para abrir o DevTools.
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
    * *Nota:* Se o Firefox bloquear a colagem, digite `permitir colar` no console e tente novamente.

2.  **Registro:**
    * Anote o valor retornado em milissegundos.
    * Utilize a Ferramenta de Captura do Windows com **Win + Shift + S** para tirar um print da tela mostrando o console e o resultado.

### 3.3. Métrica M1.3 - Benchmarks

**Ferramenta:** Navegador Firefox.

**Regras de Ouro:**
* Feche outros aplicativos que consomem recursos, como Teams, Spotify ou jogos.
* Evite mover o mouse durante a execução dos testes gráficos.

1.  **Speedometer 3.0:**
    * Acesse o site `https://browserbench.org/Speedometer3.0/`.
    * Execute o teste 3 vezes, reiniciando o navegador completamente entre cada teste.
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
2.  Utilize o Firefox no Windows 11 para verificar cada item.
3.  Preencha com:
    * **[OK]** se o recurso funciona.
    * **[FALHA]** se apresentar erro ou comportamento inesperado.
    * **[N/A]** se o item for exclusivo de ambientes mobile ou touch.
4.  Verifique a integração com recursos nativos, como a Central de Ações para notificações e o Snap Layout para redimensionamento de janelas.
5.  Registre a contagem final na Planilha Mestra.

---

## 5. Solução de Problemas

* **Erro de Interface não encontrada ou Contador inválido no typeperf:**
    * Isso ocorre pois o Windows traduz os nomes dos contadores de performance baseados no idioma do sistema. Se o seu Windows está em Português Brasileiro, use o comando abaixo:
    ```cmd
    typeperf "\Processo(firefox*)\Conjunto de Trabalho - Particular" -sc 1
    ```
* **Acesso Negado:**
    * Certifique-se de que a janela do terminal exibe a palavra **Administrador** na barra de título.
* **Erro ao colar código no Console relativo ao LCP:**
    * O Firefox possui proteção contra Self-XSS. Digite `permitir colar` ou `allow pasting` no console para desbloquear a ação.

---

## 6. Histórico de Versões

| Versão | Descrição | Autor(es) | Data |
| :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico e definição dos comandos typeperf | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 |
| 1.1 | Correção de hyperlink errado | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 |
| 1.2 | Inclusão dos procedimentos para LCP, Benchmarks e Checklists | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |