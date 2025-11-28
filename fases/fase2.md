# Fase 2

## Introdução

O objetivo desta fase é definir [objetivos de medição](#11-objetivo-de-medição) e estabelecer [métricas](#13-métricas) para avaliar a qualidade do Mozilla Firefox, utilizando a abordagem GQM, que conecta metas de alto nível a métricas de avaliação. Os objetivos serão fundamentados nas [prioridades identificadas na Fase 1](../fases/fase1.md#22-priorização-das-características-com-o-método-moscow), com foco em [Eficiência de Desempenho](#1-eficiência-de-desempenho) e [Portabilidade](#2-portabilidade), [considerando os diversos pontos de vista](../fases/fase1.md#12-requisitante) e o contexto de uso em diferentes plataformas e dispositivos.

### 1. Eficiência de Desempenho

### 1.1 Objetivo de medição

|                       |                           |
|-----------------------|---------------------------|
| **Analisar** | Navegador FireFox         |
| **Do propósito de** | Avaliar                   |
| **Com respeito a** | Eficiência de desempenho  |
| **Do ponto de vista do**| Time de desenvolvimento   |
| **No contexto da** | Disciplina de Qualidade de Software |

### 1.2 Questões e Hipóteses de medição

- **Questão 1.1:** O Firefox oferece uma navegação rápida e responsiva, atendendo às expectativas do usuário final? ([Referente às Partes Interessadas - Usuários](../fases/fase1.md#13-partes-interessadas))

    - **Hipótese 1.1:** Em pelo menos 90% dos testes realizados, o Firefox carrega páginas em menos de 3 segundos e mantém o consumo médio de memória abaixo de 1 GB durante a navegação comum (até 10 abas abertas). A percepção de fluidez pelos usuários é superior a 90% nas avaliações de desempenho.

- **Questão 1.2:** O Firefox mantém desempenho estável e consistente entre diferentes sistemas operacionais e dispositivos? ([Referente à Subcaracterística - Uso de Recursos e Tempo de Resposta](../fases/fase1.md#21-modelo-de-qualidade-de-referência))

    - **Hipótese 1.2:** A variação de desempenho entre sistemas operacionais é inferior a 10% e o tempo de resposta médio permanece dentro dos limites aceitáveis (até 3,5 segundos). Em avaliações subjetivas, pelo menos 90% dos usuários relatam experiência semelhante de desempenho entre plataformas.

### 1.3 Métricas de Eficiência

- **M1.1: Consumo de Memória (RAM):** Medido em Gigabytes (GB), avalia a quantidade de memória que o navegador utiliza durante um cenário de uso padrão (ex: 5 a 10 abas abertas).
- **M1.2: Tempo de Carregamento de Página:** Medido em segundos (s), corresponde ao tempo decorrido desde a solicitação de uma página até sua renderização completa. 
- **M1.3: Pontuação em Benchmarks de Desempenho:** Utilização de ferramentas padronizadas da indústria para obter uma pontuação objetiva. 
    - **Speedometer 3.0:** Mede a responsividade de aplicações web complexas.
    - **JetStream 2.2:** Avalia o desempenho de JavaScript e WebAssembly em tarefas computacionalmente intensivas.
- **M1.4: Variação de Desempenho entre Plataformas:** Medida em percentual (%), calcula a diferença relativa nas pontuações de benchmark (M1.3) entre diferentes sistemas operacionais (Windows, macOS, Linux). 

### 2. Portabilidade

### 2.1 Objetivo de medição

|                       |                           |
|-----------------------|---------------------------|
| **Analisar** | Navegador FireFox         |
| **Do propósito de** | Avaliar                   |
| **Com respeito a** | Portabilidade             |
| **Do ponto de vista do**| Time de desenvolvimento   |
| **No contexto da** | Disciplina de Qualidade de Software |

### 2.2 Questões e Hipóteses de medição

- **Questão 2.1:** O Firefox mantém suas principais funcionalidades e qualidade de uso de forma consistente em diferentes plataformas e dispositivos? 

    - **Hipótese 2.1:** O Firefox preserva 100% das funcionalidades essenciais (favoritos, histórico, extensões, sincronização) em todas as plataformas. A diferença na pontuação média de satisfação entre versões desktop e mobile é inferior a 10%.

- **Questão 2.2:** O Firefox adapta corretamente sua interface e experiência de uso em diferentes dispositivos? 

    - **Hipótese 2.2:** O Firefox apresenta comportamento visual e funcional consistente em 95% dos dispositivos testados, sem distorções de layout ou falhas de interação. Pelo menos 90% dos usuários avaliam positivamente a adaptação da interface em diferentes tamanhos de tela.

## 2.3 Métricas de Portabilidade

Para responder às [questões da Portabilidade](#22-questões-e-hipóteses-de-medição) e validar as hipóteses, foram selecionadas as seguintes métricas quantitativas e qualitativas, alinhadas com a metodologia GQM.

As métricas de portabilidade avaliam a subcaracterística de [Adaptabilidade](../fases/fase1.md#21-modelo-de-qualidade-de-referência).

- **M2.1: Paridade Funcional entre Plataformas:** Medida em percentual (%), quantifica a proporção de funcionalidades essenciais disponíveis e consistentes em todas as plataformas suportadas (desktop e mobile).
- **M2.2: Conformidade da Interface do Usuário (UI):** Medida em percentual (%), avalia o grau em que a interface se adapta corretamente a diferentes resoluções de tela e segue as convenções de cada sistema operacional, com base em um checklist de verificação.

### 3. Níveis de Pontuação

Para garantir uma avaliação justa e precisa, os critérios de pontuação foram definidos considerando as limitações e capacidades de cada plataforma. Enquanto as métricas de tempo de resposta (LCP) e conformidade funcional (Portabilidade) possuem critérios universais — pois a expectativa do usuário é a mesma independente do dispositivo —, as métricas de consumo de recursos (RAM) e desempenho bruto (Benchmarks) possuem escalas adaptadas para diferenciar ambientes Desktop (alta capacidade energética e de hardware) de ambientes Mobile (foco em eficiência energética e arquitetura ARM).

Abaixo estão as escalas de pontuação para todas as métricas definidas:

#### M1.1 - Consumo de Memória (RAM)

| Nível | Pontuação | Desktop (Windows/Linux/macOS) | Mobile (Android) |
| :--- | :---: | :--- | :--- |
| **Excelente** | **4** | ≤ 600 MB | ≤ 250 MB |
| **Bom** | **3** | 601 MB – 1.0 GB | 251 MB – 400 MB |
| **Regular** | **2** | 1.01 GB – 2.0 GB | 401 MB – 600 MB |
| **Insatisfatório** | **1** | > 2.0 GB | > 600 MB |

#### M1.2 - Tempo de Carregamento (LCP)

| Nível | Pontuação | Tempo (Todos os ambientes) |
| :--- | :---: | :--- |
| **Excelente** | **4** | ≤ 2.0 s |
| **Bom** | **3** | 2.1 s – 3.0 s |
| **Regular** | **2** | 3.1 s – 4.0 s |
| **Insatisfatório** | **1** | > 4.0 s |

#### M1.3 - Benchmarks (Speedometer 3.0)

| Nível | Pontuação | Desktop | Mobile |
| :--- | :---: | :--- | :--- |
| **Excelente** | **4** | ≥ 15.0 | ≥ 4.0 |
| **Bom** | **3** | 10.0 – 14.9 | 2.5 – 3.9 |
| **Regular** | **2** | 5.0 – 9.9 | 1.5 – 2.4 |
| **Insatisfatório** | **1** | < 5.0 | < 1.5 |

#### M1.4 - Variação de Desempenho (Consistência)

| Nível | Pontuação | Variação (CV %) |
| :--- | :---: | :--- |
| **Excelente** | **4** | ≤ 10 % |
| **Bom** | **3** | 11 % – 15 % |
| **Regular** | **2** | 16 % – 20 % |
| **Insatisfatório** | **1** | > 20 % |

#### M2.1 - Paridade Funcional

| Nível | Pontuação | Cobertura Funcional |
| :--- | :---: | :--- |
| **Excelente** | **4** | 100 % |
| **Bom** | **3** | 95 % – 99 % |
| **Regular** | **2** | 85 % – 94 % |
| **Insatisfatório** | **1** | < 85 % |

#### M2.2 - Conformidade da Interface (UI)

| Nível | Pontuação | Conformidade (Checklist) |
| :--- | :---: | :--- |
| **Excelente** | **4** | ≥ 95 % |
| **Bom** | **3** | 85 % – 94 % |
| **Regular** | **2** | 70 % – 84 % |
| **Insatisfatório** | **1** | < 70 % |


## 4. Critérios de Avaliação e Julgamento

### 4.1 Consolidação dos Resultados

Cada métrica (M1.1 até M2.2) utiliza uma **escala de 1 a 4** definida na [Seção 3](#3-níveis-de-pontuação):

| Pontuação | Nível Qualitativo | Interpretação                               |
|:----------|:------------------|:--------------------------------------------|
| 4         | Excelente         | Supera ou iguala os valores-alvo, alta conformidade. |
| 3         | Bom               | Atende satisfatoriamente aos critérios.      |
| 2         | Regular           | Abaixo do esperado, com limitações.         |
| 1         | Insatisfatório    | Não atende aos critérios mínimos.           |

### 4.2 Índice de Qualidade por Característica

Para cada característica, calcula-se a média ponderada das métricas:

\[
IQ_c = \frac{\sum (P_i \times w_i)}{\sum w_i}
\]

- \(IQ_c\) = Índice de Qualidade da característica
- \(P_i\) = [Pontuação](#41-consolidação-dos-resultados) da métrica \(i\)
- \(w_i\) = Peso da métrica (igual a 1 se não houver ponderação)

### 4.3 Interpretação do Índice

O [Índice de Qualidade por Característica (IQc)](#42-índice-de-qualidade-por-característica) e o [Índice Global de Qualidade (IQG)](#44-índice-global-de-qualidade-iqg) são interpretados conforme a tabela:

| Intervalo | Nível          | Interpretação                               |
|:----------|:---------------|:--------------------------------------------|
| 3,5 – 4,0 | Excelente      | Desempenho e portabilidade excelentes.      |
| 2,5 – 3,4 | Bom            | Atende adequadamente aos critérios.         |
| 1,5 – 2,4 | Regular        | Limitações perceptíveis; requer otimização. |
| 1,0 – 1,4 | Insatisfatório | Não atende aos requisitos mínimos.           |

### 4.4 Índice Global de Qualidade (IQG)

O IQG consolida a avaliação das duas características priorizadas:

\[
IQG = \frac{IQ_{Eficiência} + IQ_{Portabilidade}}{2}
\]

Este índice avalia a **qualidade geral do Firefox** no [escopo definido](../fases/fase1.md#23-escopo-e-profundidade-da-avaliação), permitindo comparação entre versões e identificação de oportunidades de melhoria.

### 4.5 Critérios de Aceitação

O resultado final da avaliação, baseado no [IQG](#44-índice-global-de-qualidade-iqg) e interpretado conforme a [Seção 4.3](#43-interpretação-do-índice), segue estes critérios:

- **Aceito:** \(IQG \geq 2,5\)
- **Aceito com recomendações:** \(2,0 \leq IQG < 2,5\)
- **Rejeitado:** \(IQG < 2,0\)

## 5. Diagrama GQM

A Figura 1 apresenta a representação visual da hierarquia GQM (Goal-Question-Metric) adotada neste plano de medição. O diagrama ilustra como os Objetivos de Medição de alto nível ([Eficiência](#1-eficiência-de-desempenho) e [Portabilidade](#2-portabilidade)) são decompostos em Questões específicas para avaliação ([Seção 1.2](#12-questões-e-hipóteses-de-medição) e [Seção 2.2](#22-questões-e-hipóteses-de-medição)). Por sua vez, cada Questão é conectada às Métricas quantitativas ([Seção 1.3](#13-métricas) e [Seção 2.3](#23-métricas-de-avaliação)) que fornecerão os dados necessários para respondê-las. A estrutura evidencia os três níveis lógicos da abordagem GQM, sendo eles o Conceitual (Objetivos), Operacional (Questões) e Quantitativo (Métricas).

![Diagrama GQM do Projeto de Avaliação do Firefox](../assets/Diagrama-GQM.drawio.png)
**Figura 1** – Diagrama GQM representando a hierarquia de Objetivos, Questões e Métricas.

**Fonte:** Elaborado pelos autores [Artur Mendonça Arruda](https://github.com/ArtyMend07) e [Lucas Mendonça Arruda](https://github.com/lucasarruda9) (2025).

## 6. Declaração de Uso de Inteligência Artificial

Para elaborar este artefato, a equipe contou com o apoio de modelos de linguagem de grande escala (LLMs), em especial o **ChatGPT**, como ferramenta auxiliar. O objetivo foi obter diferentes perspectivas sobre a organização e o conteúdo do trabalho, complementando a análise feita pelos integrantes do projeto.

O uso da IA se concentrou em duas frentes principais:

1. **Confirmação de Requisitos:** Serviu como recurso adicional para garantir que todos os requisitos e critérios da Fase 2 do projeto estavam atendidos.
2. **Coerência e Clareza do Documento:** Auxiliou na revisão da lógica e fluidez do texto, ajudando a identificar pontos que poderiam ser ajustados para tornar o artefato mais claro e bem estruturado.

O ChatGPT atuou exclusivamente como ferramentas de validação e sugestão. Todo o conteúdo, a redação final e as decisões estratégicas foram produzidos e validados pelos integrantes da equipe.

## 7. Tabela de Contribuição

| Matrícula     | Integrante                                                       | Principais Contribuições                                                 | Comprovação                                                                                                                                                                                                                                                              | Contribuição |
| :------------ | :--------------------------------------------------------------- | :----------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- |
| `[231033737]` | **[Artur Mendonça Arruda](https://github.com/ArtyMend07)** | Defini as métricas, fiz a bibliografia e o diagrama GQM                  | [Métricas](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/2aac6e30dc0ae8dfd190b807c9d1c2f307bf9320), [Bibliografia](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/2aac6e30dc0ae8dfd190b807c9d1c2f307bf9320), [Diagrama GQM](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/5352bea09f49ce493e74948bb10371e8b3bf8f96), [Rastreabilidade da fase 1 e 2](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/52b0e95daa8f00dcec8cc2aad0a91fed352bc463) | `20%`        |
| `[221007608]` | **[Nayra Silva Nery](https://github.com/NayraNery127)** |                                                                          |                                                                                                                                                                                                                                                                          | `20%`        |
| `[231035141]` | **[João Filipe de Oliveira Souza](https://github.com/Joao151104)**|                                                                          |                                                                                                                                                                                                                                                                          | `20%`        |
| `[231035464]` | **[Lucas Mendonça Arruda](https://github.com/lucasarruda9)** | Adicionei a introdução, Objetivos de medição e Declaração IA             | [Introdução](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/325725f582c8805cf616b0bfa7fde9d5403219fc), [Objetivos de medição](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/805d714287eca545ca80ac06834581b188acc04d), [Declaração IA](https://github.com/FCTE-Qualidade-de-Software-1/2025-2_T02_JEAN-SAMMET/commit/d1ae9f64d0003ce1e5747d0ae8a96aa50f1c2350) | `20%`        |
| `[180108875]` | **[Rodrigo Mattos de F. A. Bezerra](https://github.com/Rodrigomfab88)** |                                                                          |                                                                                                                                                                                                                                                                          | `20%`        |
|               | **Total** |                                                                          |                                                                                                                                                                                                                                                                          | **100%** |

## 8. Referências

- BASILI, V. R. et al. **The Goal/Question/Metric Paradigm**. Fraunhofer IESE, 2003.
- BROWSERBENCH.ORG. **BrowserBench.org — Browser Benchmarks**. Disponível em: [https://browserbench.org/](https://browserbench.org/). Acesso em: 15 out. 2025.
- ISO/IEC. **ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models**. International Organization for Standardization, 2011.
- MARTINEZ, L., et al. **Assistant for the Evaluation of Software Product Quality Characteristics Proposed by ISO/IEC 25010 Based on GQM-Defined Metrics**. SEDICI, 2018.
- TESTSIGMA. **Portability Testing: Attributes, Checklists, and Examples**. Disponível em: [https://testsigma.com/blog/portability-testing/](https://testsigma.com/blog/portability-testing/). Acesso em: 15 out. 2025.
- VARGAS, S. A., et al. **Application of the Goal-Question-Metric (GQM) Method to Improve the Management of Software Projects**. SciELO, 2025.
- SOLLAMI, T.; AL-ZUBAIDI, L. **Software Quality Metrics and Evaluation Using GQM Approach**. International Journal of Computer Applications, 2019.
- GOOGLE. **Core Web Vitals**. Disponível em: [https://web.dev/articles/vitals](https://web.dev/articles/vitals). Acesso em: 24 out. 2025.
- GOOGLE. **Core Web Vitals report**. Disponível em: [https://support.google.com/webmasters/answer/9205520?hl=en](https://support.google.com/webmasters/answer/9205520?hl=en). Acesso em: 24 out. 2025.
- HACKER NEWS. **Speedometer 3.0 benchmark score interpretation**. Disponível em: [https://news.ycombinator.com/item?id=39671051](https://news.ycombinator.com/item?id=39671051). Acesso em: 24 out. 2025.
- ISO25000.COM. **ISO/IEC 25010 - Product quality model**. Disponível em: [https://iso25000.com/index.php/en/iso-25000-standards/iso-25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010). Acesso em: 24 out. 2025.
- NEURONVM. **Which Browsers Uses Less Memory?**. Disponível em: [https://neuronvm.com/blog/which-browsers-uses-less-memory/](https://neuronvm.com/blog/which-browsers-uses-less-memory/). Acesso em: 24 out. 2025.
- REDDIT. **What's a good speedometer 3 score?**. Disponível em: [https://www.reddit.com/r/browsers/comments/1cvtczu/whats_a_good_speedometer_3_score/](https://www.reddit.com/r/browsers/comments/1cvtczu/whats_a_good_speedometer_3_score/). Acesso em: 24 out. 2025.
- RESEARCHGATE. **Maintainability and Portability Evaluation of the React Native Framework Applying the ISO/IEC 25010**. Disponível em:([https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010](https://www.researchgate.net/publication/346166139_Maintainability_and_Portability_Evaluation_of_the_React_Native_Framework_Applying_the_ISOIEC_25010)). Acesso em: 24 out. 2025.
- WEBLOGIC. **Website Performance: Website Speed & Core Web Vitals Explained**. Disponível em: [https://www.weblogic.ie/website-performance/website-speed-core-web-vitals-explained-an-overview/](https://www.weblogic.ie/website-performance/website-speed-core-web-vitals-explained-an-overview/). Acesso em: 24 out. 2025.

## 9. Histórico de Versões

| Versão | Descrição                                       | Autor(es)                                                                                      | Data       | Revisor(es) | Data de Revisão |
| :----- | :---------------------------------------------- | :--------------------------------------------------------------------------------------------- | :--------- | :---------- | :-------------- |
| 1.0    | Criação e adição dos objetivos de medição       | [Lucas Mendonça Arruda](https://github.com/lucasarruda9)                                       | 14/10/2025 |             |                 |
| 1.1    | Adição das questões e hipóteses de medição     | [Rodrigo Mattos de F. A. Bezerra](https://github.com/Rodrigomfab88)                            | 15/10/2025 |             |                 |
| 1.2    | Adição das métricas, níveis e critérios        | [Artur Mendonça Arruda](https://github.com/ArtyMend07)                                         | 15/10/2025 |             |                 |
| 1.3    | Adição da Tabela de Contribuição e Referências  | [Artur Mendonça Arruda](https://github.com/ArtyMend07)                                         | 15/10/2025 |             |                 |
| 1.4    | Criação dos níveis de pontuação                 | [Nayra Nery](https://github.com/NayraNery127)                                                  | 15/10/2025 |             |                 |
| 1.5    | Criação dos Critérios de Avaliação             | [João Filipe de Oliveira Souza](https://github.com/Joao151104)                                | 15/10/2025 |             |                 |
| 1.6    | Arrumando objetivos                             | [Lucas Mendonça Arruda](https://github.com/lucasarruda9)                                       | 18/10/2025 |             |                 |
| 1.7    | Ajustes nas questões e hipóteses de medição     | [Rodrigo Mattos de F. A. Bezerra](https://github.com/Rodrigomfab88)                            | 18/10/2025 |             |                 |
| 1.8    | Criação e Adição do diagrama GQM                | [Artur Mendonça Arruda](https://github.com/ArtyMend07) e [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 23/10/2025 |             |                 |
| 1.9    | Adicionando declaração de Uso de IA             | [Lucas Mendonça Arruda](https://github.com/lucasarruda9)                                       | 23/10/2025 |             |                 |
| 1.10   | Adição dos comprobatórios das contribuições     | [Artur Mendonça Arruda](https://github.com/ArtyMend07)                                         | 23/10/2025 |             |                 |
| 1.11   | Adição de rastreabilidade do documento         | [Artur Mendonça Arruda](https://github.com/ArtyMend07)                                         | 23/10/2025 |             |                 |
| 1.12   | Adição de fontes que justificam níveis de pontuação e atualização da tabela de contribuições         | [Artur Mendonça Arruda](https://github.com/ArtyMend07)                                         | 24/10/2025 |             |                 |
| 1.13 | Refinamento dos níveis de pontuação com distinção entre Desktop e Mobile | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 | | |