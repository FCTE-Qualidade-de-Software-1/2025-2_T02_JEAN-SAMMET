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



## Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| ------ | ------------------------------------------------ | -------------------------------------------------------------- | ---------- | ------------------------------------------------------------ | --------------- |
| 1.0 | Criação e adição dos objetivos de medição  |[Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 14/10/2025 | | |
| 1.1 | Adição das questões e hipóteses de medição  |[Rodrigo Mattos de F. A. Bezerra](https://github.com/Rodrigomfab88) | 15/10/2025 | | |
