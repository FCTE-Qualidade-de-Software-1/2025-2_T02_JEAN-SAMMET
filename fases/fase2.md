# Fase 2

## Introdução

O objetivo desta fase é definir objetivos de medição e estabelecer métricas para avaliar a qualidade do Mozilla Firefox, utilizando a abordagem GQM, que conecta metas de alto nível a métricas de avaliação. Os objetivos serão fundamentados nas prioridades identificadas na [Fase 1](fase1.md), com foco em Eficiência de Desempenho e Portabilidade, considerando a perspectiva do usuário final e o contexto de uso em diferentes plataformas e dispositivos.



## Objetivos de Medição

Os objetivos de medição serão criados com base nas prioridades do Firefox, considerando suas subcaracterísticas e mantendo a perspectiva do usuário final em diferentes sistemas operacionais e dispositivos, tanto desktop quanto mobile.  

Eficiência de Desempenho: O objetivo é medir a eficiência e desempenho do Firefox, avaliando o uso de recursos e o tempo de resposta do navegador, de forma que o usuário final perceba rapidez e eficiência ao realizar tarefas comuns.  

Portabilidade: O objetivo é medir a portabilidade do Firefox, analisando a adaptabilidade do navegador, garantindo que ele mantenha suas funcionalidades e desempenho de maneira consistente para o usuário final em diferentes ambientes e plataformas.

## Questôes e Hipóteses de Medição

### 1. Eficiência de Desempenho

- Questão 1.1: O Firefox oferece uma navegação rápida e responsiva, com tempos de carregamento e uso de recursos adequados às expectativas do usuário final?

- Hipótese 1.1: Em pelo menos 85% dos testes realizados, o Firefox carrega páginas em menos de 3 segundos e mantém o consumo médio de memória abaixo de 1 GB durante a navegação comum (até 10 abas abertas). A percepção de fluidez pelos usuários é superior a 80% nas avaliações de desempenho.

- Questão 1.2: O Firefox mantém desempenho estável e consistente entre diferentes sistemas operacionais (Windows, Linux, macOS) e dispositivos (desktop e mobile)?

- Hipótese 1.2: A variação de desempenho entre sistemas operacionais é inferior a 15% e o tempo de resposta médio permanece dentro dos limites aceitáveis (até 3,5 segundos). Em avaliações subjetivas, pelo menos 80% dos usuários relatam experiência semelhante de desempenho entre plataformas.

### 2. Portabilidade

- Questão 2.1: O Firefox mantém suas principais funcionalidades e qualidade de uso de forma consistente em diferentes plataformas e dispositivos?

- Hipótese 2.1: O Firefox preserva 100% das funcionalidades essenciais (favoritos, histórico, extensões, sincronização) em todas as plataformas. A diferença na pontuação média de satisfação entre versões desktop e mobile é inferior a 10%.

- Questão 2.2: O Firefox adapta corretamente sua interface e experiência de uso às diferentes resoluções de tela e modos de interação (toque, mouse, teclado) entre dispositivos?

- Hipótese 2.2: O Firefox apresenta comportamento visual e funcional consistente em 95% dos dispositivos testados, sem distorções de layout ou falhas de interação. Pelo menos 85% dos usuários avaliam positivamente a adaptação da interface em diferentes tamanhos de tela.

## Métricas de Avaliação

Para responder às questões e validar as hipóteses, foram selecionadas as seguintes métricas quantitativas e qualitativas, alinhadas com a metodologia GQM.

### 1\. Métricas de Eficiência de Desempenho

As métricas para esta característica focam em **Uso de Recursos** e **Tempo de Resposta**.

  - **M1.1: Consumo de Memória (RAM):** Medido em Gigabytes (GB), avalia a quantidade de memória que o navegador utiliza durante um cenário de uso padrão (ex: 5 a 10 abas abertas).
  - **M1.2: Tempo de Carregamento de Página:** Medido em segundos (s), corresponde ao tempo decorrido desde a solicitação de uma página até sua renderização completa.
  - **M1.3: Pontuação em Benchmarks de Desempenho:** Utilização de ferramentas padronizadas da indústria para obter uma pontuação objetiva.
      - **Speedometer 3.0:** Mede a responsividade de aplicações web complexas.
      - **JetStream 2.2:** Avalia o desempenho de JavaScript e WebAssembly em tarefas computacionalmente intensivas.
  - **M1.4: Variação de Desempenho entre Plataformas:** Medida em percentual (%), calcula a diferença relativa nas pontuações de benchmark (M1.3) entre diferentes sistemas operacionais (Windows, macOS, Linux).

### 2\. Métricas de Portabilidade

As métricas de portabilidade avaliam a subcaracterística de **Adaptabilidade**.

  - **M2.1: Paridade Funcional entre Plataformas:** Medida em percentual (%), quantifica a proporção de funcionalidades essenciais disponíveis e consistentes em todas as plataformas suportadas (desktop e mobile).
  - **M2.2: Conformidade da Interface do Usuário (UI):** Medida em percentual (%), avalia o grau em que a interface se adapta corretamente a diferentes resoluções de tela e segue as convenções de cada sistema operacional, com base em um checklist de verificação.

## Tabela de Contribuição

| Matrícula | Integrante | Principais Contribuições | Comprovação | Contribuição |
| :--- | :--- | :--- | :--- | :--- |
| `[231033737]` | **Artur Mendonça Arruda** | | | `20%` |
| `[Matrícula]` | **Nome do Integrante** | | | `%` |
| `[Matrícula]` | **Nome do Integrante** | | | `%` |
| `[Matrícula]` | **Nome do Integrante** | | | `%` |
| `[Matrícula]` | **Nome do Integrante** | | | `%` |
| | **Total** | | | **100%** |

## Referências

  - BASILI, V. R. et al. **The Goal/Question/Metric Paradigm**. Fraunhofer IESE, 2003.
  - BROWSERBENCH.ORG. **BrowserBench.org — Browser Benchmarks**. Disponível em: [https://browserbench.org/](https://browserbench.org/). Acesso em: 15 out. 2025.
  - ISO/IEC. **ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models**. International Organization for Standardization, 2011.
  - MARTINEZ, L., et al. **Assistant for the Evaluation of Software Product Quality Characteristics Proposed by ISO/IEC 25010 Based on GQM-Defined Metrics**. SEDICI, 2018.
  - TESTSIGMA. **Portability Testing: Attributes, Checklists, and Examples**. Disponível em: [https://testsigma.com/blog/portability-testing/](https://testsigma.com/blog/portability-testing/). Acesso em: 15 out. 2025.
  - VARGAS, S. A., et al. **Application of the Goal-Question-Metric (GQM) Method to Improve the Management of Software Projects**. SciELO, 2025.

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| ------ | ------------------------------------------------ | -------------------------------------------------------------- | ---------- | ------------------------------------------------------------ | --------------- |
| 1.0 | Criação e adição dos objetivos de medição  |[Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 14/10/2025 | | |
| 1.1 | Adição das questões e hipóteses de medição  |([https://github.com/Rodrigomfab88](https://github.com/Rodrigomfab88)) | 15/10/2025 | | |
| 1.2 | Adição das seções de Métricas, Níveis de Pontuação e Critérios de Avaliação. | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 15/10/2025 | |  |
| 1.3 | Adição da Tabela de Contribuição e Referências. | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 15/10/2025 |  | |
