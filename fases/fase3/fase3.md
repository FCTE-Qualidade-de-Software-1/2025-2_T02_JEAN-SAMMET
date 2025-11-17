# Fase 3: Plano de Execução da Avaliação

## 1. Introdução

Esta seção detalha o **Plano de Execução** da Fase 3 para a avaliação de qualidade do Mozilla Firefox. O propósito deste documento é definir o passo-a-passo metodológico, os ambientes, as ferramentas e os artefatos de coleta necessários para executar os testes definidos na [Fase 2](../fases/fase2.md).

Este plano servirá como um guia padronizado para todos os executores de teste da equipe, garantindo que os dados coletados na próxima fase sejam consistentes e comparáveis. A execução em si, a coleta de dados brutos e a análise dos resultados serão documentadas em um artefato separado, a **Fase 4: Execução e Análise de Resultados**, utilizando os métodos e artefatos aqui definidos.

---

## 2. Metodologia e Plano de Execução

O plano segue a metodologia GQM definida na [Fase 2](../fases/fase2.md#5-diagrama-gqm), focando nas características de Eficiência de Desempenho e Portabilidade, priorizadas na [Fase 1](../fases/fase1.md#22-priorização-das-características-com-o-método-moscow).

### 2.1. Artefatos de Coleta e Divisão de Tarefas

Para centralizar a coleta de dados da Fase 4, a equipe utilizará uma Planilha Mestra. A divisão de tarefas de execução está definida conforme a tabela abaixo:

* **Artefato Principal:** [Planilha Mestra de Coleta de Dados (Google Sheets)](https://docs.google.com/spreadsheets/d/1pNws2Jl_TH-EQMOMho54TPvwczGSXf4ntVFK4Xa4p9Y/edit?usp=sharing)
* **Objeto de Teste:** Firefox Versão 143.0.3, em uma instalação limpa.

| Executor | Papel de Execução |
| :--- | :--- |
| **Artur Mendonça Arruda** | Windows (Coleta 1) |
| **Lucas Mendonça Arruda** | Linux |
| **João Filipe de Oliveira Souza** | macOS |
| **Rodrigo Mattos de F. A. Bezerra**| Android |
| **Nayra Silva Nery** | Windows (Coleta 2) |

### 2.2. Ferramentas e Ambientes de Teste Padronizados

Cada executor será responsável por configurar seu ambiente e utilizar as ferramentas padronizadas listadas abaixo para garantir a consistência dos dados.

| Ambiente | Executor(es) | Ferramentas de Coleta para M1.1 (RAM) | Ferramentas de Coleta para M1.2 (LCP) | Ferramentas de Coleta para M1.3 (Bench) |
| :--- | :--- | :--- | :--- | :--- |
| **Windows 11** | Artur M. / Nayra S. | `typeperf`, executado via Prompt Admin | Firefox DevTools, especificamente o Painel Rede | Sites Oficiais, como o BrowserBench |
| **Linux (Ubuntu)**| Lucas M. | `top` executado em modo batch ou `vmstat` | Firefox DevTools, especificamente o Painel Rede | Sites Oficiais, como o BrowserBench |
| **macOS** | João Filipe S. | Monitor de Atividade | Firefox DevTools, especificamente o Painel Rede | Sites Oficiais, como o BrowserBench |
| **Android** | Rodrigo M. | `adb shell dumpsys meminfo` | Firefox DevTools, usando Depuração Remota | Sites Oficiais, como o BrowserBench |

O requisito crítico para **Windows** é que a ferramenta `typeperf` deve ser executada a partir de um prompt de comando como **Administrador** ou por um usuário no grupo "Performance Log Users". Esta exigência é necessária para que o sistema operacional permita o acesso aos contadores de processo.

### 2.3. Cenários de Teste (Eficiência - M1)

Procedimentos detalhados para a coleta das métricas de eficiência definidas na [Fase 2](../fases/fase2.md#13-métricas-de-eficiência).

**M1.1 - Consumo de RAM:**
Para medir o consumo de memória, o utilitário `typeperf` no Windows será configurado para capturar três contadores específicos do processo Firefox: `\Process(firefox)\Private Bytes`, que é essencial para identificar vazamentos de memória; `\Process(firefox)\Working Set`, que representa o impacto total na RAM; e `\Process(firefox)\Working Set - Private`, referente ao uso exclusivo de RAM.

O teste será duplicado para dois perfis de uso:

1.  **Cenário de Carga Leve:**
    * Abrir o Firefox em uma instalação limpa.
    * Carregar 10 abas com sites de baixo recurso, como artigos de texto simples ou páginas de busca puras.
    * Aguardar 60 segundos para estabilização.
    * Utilizar a ferramenta do SO, conforme a [Seção 2.2](#22-ferramentas-e-ambientes-de-teste-padronizados), para capturar o consumo de memória, seja o `Working Set` ou `RES`.
2.  **Cenário de Carga Pesada:**
    * Reiniciar o Firefox.
    * Carregar os 10 sites padronizados definidos na [Seção 2.4](#24-lista-de-sites-padronizados-m11-e-m12), fazendo login onde indicado.
    * Aguardar 60 segundos para estabilização.
    * Utilizar a ferramenta do SO para capturar o consumo de memória.

**M1.2 - Tempo de Carga (LCP):**
A medição do tempo de carregamento focará na métrica Largest Contentful Paint, ou LCP. Esta é a métrica padrão da indústria para medir a velocidade de carregamento percebida pelo usuário.

1.  Abrir o Firefox em uma instalação limpa.
2.  Abrir o DevTools (F12) e navegar até o Painel "Rede" (Network).
3.  Marcar a opção **"Desabilitar Cache"**.
4.  Carregar cada um dos 10 sites padronizados da [Seção 2.4](#24-lista-de-sites-padronizados-m11-e-m12).
5.  Para cada site, anotar o tempo do LCP na aba "Temporização".
6.  Calcular a média dos 10 resultados e registrar na [Planilha Mestra](#21-artefatos-de-coleta-e-divisão-de-tarefas).

**M1.3 - Benchmarks:**
Para avaliar o desempenho sintético bruto, dois benchmarks padronizados serão executados. O teste deve ser executado em um navegador recém-aberto para garantir que não haja interferência de outros processos.

1.  Reiniciar o Firefox (instalação limpa).
2.  Acessar e executar: `https://browserbench.org/Speedometer3.0/`
3.  Registrar a pontuação final na [Planilha Mestra](#21-artefatos-de-coleta-e-divisão-de-tarefas) e salvar um screenshot como evidência.
4.  Reiniciar o Firefox.
5.  Acessar e executar: `https://browserbench.org/JetStream/`
6.  Registrar a pontuação final na [Planilha Mestra](#21-artefatos-de-coleta-e-divisão-de-tarefas) e salvar um screenshot como evidência.

### 2.4. Lista de Sites Padronizados (M1.1 e M1.2)

Para garantir que os testes de "Carga Pesada" (método [M1.1](#m11-consumo-de-ram)) e "LCP" (método [M1.2](#m12-tempo-de-carga-lcp)) sejam comparáveis entre os executores, todos deverão utilizar a seguinte lista de 10 sites.

* `https://www.youtube.com` (logado e reproduzindo um vídeo 1080p)
* `https://www.amazon.com.br` (em uma página de produto)
* `https://www.facebook.com` (logado, no feed principal)
* `https://www.mercadolivre.com.br` (em uma página de busca)
* `https://g1.globo.com` (na página principal)
* `https://pt.wikipedia.org` (em um artigo principal)
* `https://www.twitch.tv` (na página principal, com stream ao vivo)
* `https://www.reddit.com` (no feed principal)
* `https://www.magazineluiza.com.br` (em uma página de produto)
* `https://twitter.com` (logado, no feed principal)

**Justificativa da Seleção:** Esta lista foi escolhida para fornecer uma visão holística do uso real da web. Ela combina:
* **Mídia Pesada**, como YouTube e Twitch: Foco intenso em streaming de vídeo e scripts de reprodução.
* **Aplicações Web**, como Facebook, Twitter e Reddit: Alto uso de JavaScript para *infinite scroll* e atualização de conteúdo dinâmico.
* **E-commerce**, como Amazon, Mercado Livre e Magazine Luiza: Carregamento de centenas de imagens, rastreadores e scripts de interação complexos.
* **Portais de Notícias**, como o G1: Mistura de anúncios, vídeos e texto.
* **Linha de Base Estática**, como a Wikipedia: Serve como um controle leve, focado em renderização de texto e imagens simples.

### 2.5. Checklists de Verificação para Portabilidade (M2)

Os procedimentos detalhados para as métricas [M2.1 e M2.2](../fases/fase2.md#23-métricas-de-portabilidade) serão gerenciados em arquivos `.md` separados para manter a organização.

Cada executor deverá criar uma cópia dos templates abaixo, preenchê-los para seu ambiente específico e, em seguida, registrar o resultado total, por exemplo "19/20", e o link para o arquivo preenchido na [Planilha Mestra](#21-artefatos-de-coleta-e-divisão-de-tarefas).

* **[Template: Checklist M2.1 - Paridade Funcional (20 Itens)](./checklists/checklist_m2.1.md)**
* **[Template: Checklist M2.2 - Conformidade da UI (15 Itens)](./checklists/checklist_m2.2.md)**

### 2.6. Riscos e Mitigações Planejados

Esta seção identifica riscos potenciais para a validade da coleta de dados e suas respectivas mitigações.

* **Risco 1: Inconsistência na medição de RAM (M1.1).**
    * *Descrição:* Diferentes ferramentas e momentos de coleta podem gerar valores díspares.
    * *Mitigação:* Padronização rigorosa das ferramentas (conforme [Seção 2.2](#22-ferramentas-e-ambientes-de-teste-padronizados)), uso de cenários fixos (definidos na [Seção 2.3](#m11-consumo-de-ram)) e coleta de dados duplicada no ambiente Windows, especificamente a Coleta 1 por Artur e a Coleta 2 por Nayra, para validação cruzada.

* **Risco 2: Variação de Rede (M1.2).**
    * *Descrição:* A velocidade da internet de cada executor pode afetar o LCP.
    * *Mitigação:* O foco na média de [10 sites padronizados](#24-lista-de-sites-padronizados-m11-e-m12) ajudará a diluir anomalias de rede. Adicionalmente, a métrica LCP é mais resiliente a flutuações de rede do que o "Page Load Time" completo.

* **Risco 3: Diferenças de Hardware.**
    * *Descrição:* O hardware, como CPU e RAM, de cada executor impactará diretamente M1.1 e M1.3.
    * *Mitigação:* Esta não é uma falha, mas sim uma variável controlada. O objetivo da métrica [M1.4 (Variação de Desempenho)](../fases/fase2.md#13-métricas-de-eficiência) é justamente capturar essa diferença. A coleta será focada em *benchmarks*, que normalizam o desempenho, e não em valores absolutos de CPU.

---

## 3. Tabela de Contribuição

Esta tabela reflete as contribuições para a elaboração deste **Plano de Execução (Fase 3)**.

| Matrícula | Integrante | Principais Contribuições | Comprovação | Contribuição |
| :--- | :--- | :--- | :--- | :--- |
| `[231033737]` | **[Artur Mendonça Arruda](https://github.com/ArtyMend07)** | | | 30% |
| `[221007608]` | **[Nayra Silva Nery](https://github.com/NayraNery127)** | | | |
| `[231035141]` | **[João Filipe de Oliveira Souza](https://github.com/Joao151104)**| | | |
| `[231035464]` | **[Lucas Mendonça Arruda](https://github.com/lucasarruda9)** | | | |
| `[180108875]` | **[Rodrigo Mattos de F. A. Bezerra](https://github.com/Rodrigomfab88)** | | | |
| | **Total** | | | **30%** |

---

## 4. Declaração de Uso de Inteligência Artificial


## 5. Referências

* MICROSOFT. **typeperf**. Microsoft Learn. Disponível em: <https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/typeperf>. Acesso em: 16 nov. 2025.
* TECHRADAR. **The best web browsers 2024: Find the fastest and most secure browser**. Disponível em: <https://www.techradar.com/best/browser>. Acesso em: 16 nov. 2025.
* WEB.DEV. **Largest Contentful Paint (LCP)**. Disponível em: <https://web.dev/articles/lcp>. Acesso em: 16 nov. 2025.
* BROWSERBENCH. **Speedometer 3.0**. Disponível em: <https://browserbench.org/Speedometer3.0/>. Acesso em: 16 nov. 2025.
* WEBKIT. **JetStream 2.2**. Disponível em: <https://browserbench.org/JetStream/>. Acesso em: 16 nov. 2025.

---

## 6. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do plano de execução  | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 16/11/2025 | | |
| 1.1 | Definição dos artefatos, ferramentas e divisão de tarefas | [Artur Mendonça Arruda](https://github.com/ArtyMend07)| 16/11/2025 | | |
| 1.2 | Detalhamento dos cenários de teste e riscos | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 16/11/2025 | | |
| 1.3 | Adição da seção de Sites Padronizados e da seção de Links de Checklists | [Artur Mendonça Arruda](https://github.com/ArtyMend07)| 16/11/2025 | | |