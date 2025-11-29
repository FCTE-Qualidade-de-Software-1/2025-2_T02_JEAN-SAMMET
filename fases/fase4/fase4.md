# Fase 4: Execução e Análise de Resultados

## 1. Introdução

Esta fase documenta a execução dos testes planejados na [Fase 3: Plano de Execução](../fase3/fase3.md) e apresenta a análise consolidada dos dados coletados. O objetivo é transformar as medições brutas em informações úteis para responder às questões definidas na abordagem GQM, conhecida como Goal-Question-Metric, da [Fase 2](../fase2.md) e emitir um julgamento final sobre a qualidade do produto.

## 2. Execução da Coleta de Dados

A coleta foi realizada nos ambientes Android, Windows, macOS e Linux, seguindo os [Guias Técnicos Padronizados](../fase3/fase3.md#22-ferramentas-e-guias-técnicos-padronizados). Os dados brutos detalhados e as evidências de cada plataforma estão organizados nos artefatos individuais abaixo:

* **Android:** [Ver Relatório de Execução - Android](./dados_brutos/android.md)
* **Windows (Coleta 1):** [Ver Relatório de Execução - Windows](./dados_brutos/windows-1.md)
* **macOS:** [Ver Relatório de Execução - macOS](./dados_brutos/macos.md)
* **Linux:** [Ver Relatório de Execução - Linux](./dados_brutos/linux.md)
* **Windows (Coleta 2):** *[Dados consolidados na Planilha Mestra]*

### 2.1. Limitações Técnicas e Ajustes Metodológicos

Durante a execução, foi necessário realizar um ajuste referente à captura de evidências nos ambientes Desktop, especificamente Windows, Linux e macOS.

Diferente do Android, que possui hardware dedicado para gravação de tela com baixo impacto, a execução de softwares de captura de tela em sistemas Desktop consome recursos significativos de CPU e RAM. Esse fenômeno alteraria negativamente os resultados das métricas **M1.1 referente ao Consumo de RAM** e **M1.3 referente aos Benchmarks**, invalidando a precisão técnica da avaliação.

No Linux, a gravação de tela não afetou os resultados do Speedometer, mas teve um impacto negativo no desempenho do JetStream 2. Para mitigar esse risco e garantir a integridade dos dados, a equipe optou por utilizar capturas de tela estáticas durante a estabilização das métricas nos sistemas Desktop, com exceção do Speedometer no Linux, onde a gravação não comprometeu os resultados. Essa abordagem assegura que os valores medidos reflitam exclusivamente o desempenho do navegador Firefox

## 3. Critérios de Avaliação Aplicados

A análise a seguir utiliza estritamente os níveis de pontuação definidos na Fase 2, que contemplam escalas adaptadas para as diferenças de hardware entre Desktop e Mobile.

* **Consultar Tabelas de Pontuação:** [Fase 2 - Seção 3: Níveis de Pontuação](../fase2.md#3-níveis-de-pontuação)

## 4. Análise dos Resultados (GQM)

Esta seção consolida os dados e responde às [Questões de Medição da Fase 2](../fase2.md#12-questões-e-hipóteses-de-medição).

### 4.1. Eficiência de Desempenho

#### Dados Consolidados (Médias)

| Plataforma | M1.1 RAM (Leve) | M1.1 RAM (Pesada) | M1.2 LCP (s) | M1.3 Speedometer | M1.3 JetStream |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Android** | 221.6 MB | 293.5 MB | 1.85 s | 4.47 | 71.0 |
| **Windows** coleta 1 | 2763.0 MB | 5954.0 MB | 1.41 s | 17.3 | 188.0 |
| **Windows** coleta 2 | 749.0 MB | 1226.0 MB | 6.84 s | 11.1 | 133.7 |
| **macOS** | 421.8 MB | 1070.0 MB | 1.23 s | 21.0 | 122.8 |
| **Linux** | 1980.0 MB | 6771.0 MB | 1.51 s | 11.2 | 114.8 |

### 4.1.1 Respostas de Eficiência de Desempenho


#### Resposta à Questão 1.1
> **Q1.1:** O Firefox oferece uma navegação rápida e responsiva, atendendo às expectativas do usuário final?

A pontuação da métrica M1.1 foi recalculada aplicando um fator redutor nas medições de carga pesada, dividindo esses valores por 2 antes da classificação. Após esse ajuste, cada plataforma foi classificada normalmente segundo a tabela de níveis.

O Android recebeu 4 pontos na carga leve e 4 na carga pesada ajustada. O Windows (coleta 1) obteve 1 ponto em ambos os cenários. O Windows (coleta 2) ficou com 3 pontos nas duas medições. O macOS registrou 3 pontos tanto na carga leve quanto na pesada ajustada. O Linux obteve 2 pontos na carga leve e 1 ponto na pesada ajustada.

Somando as cargas leves e pesadas, a consolidação da métrica resulta do cálculo:

\[
P_{M1.1} = \frac{4+4+1+1+3+3+3+3+2+1}{10} = 25/10 = 2,5
\]

A métrica é classificada como Boa, visto que o valor consolidado considera tanto os cenários de carga leve quanto os de carga pesada, já ajustados pelo fator redutor. Esse resultado também leva em conta o impacto das medições mais elevadas, como a coleta 1 do Windows e o Linux, que influenciaram a média final.


Quanto ao tempo de carregamento (M1.2), todas as plataformas registraram valores de **Largest Contentful Paint (LCP)** menores que 2.0 segundos. Assim, cada ambiente recebeu pontuação **4 – Excelente**, demonstrando que o navegador mantém alta responsividade no carregamento inicial das páginas. A segunda coleta do Windows não entrou no cálculo porque apresentou condições de teste diferentes das demais medições.


A consolidação da métrica resulta do cálculo:

\[
P_{M1.2} = \frac{16}{4} = 4
\]

a métrica é classificada como Excelente, pois todas as plataformas apresentaram valores de LCP abaixo de 2 segundos, permanecendo dentro do limite máximo definido para o nível mais alto de desempenho.

**Conclusão Q1.1:** O Firefox entrega um carregamento de páginas extremamente rápido em todos os sistemas, porém apresenta variação relevante no consumo de memória afetado no linux e na coleta 1 do windows.

---

#### Resposta à Questão 1.2
> **Q1.2:** O Firefox mantém desempenho estável e consistente entre diferentes sistemas operacionais e dispositivos?

Nos testes de Speedometer 3.0 e JetStream 2, o Android obteve pontuação Excelente no Speedometer e Bom no JetStream 2. Entre os desktops, o macOS registrou Excelente em ambos os benchmarks. O Windows coleta 1 alcançou Excelente em ambos, enquanto a coleta 2 do Windows ficou com Bom no Speedometer e Excelente no JetStream 2. O Linux apresentou Bom no Speedometer e Excelente no JetStream 2.

A consolidação da métrica M1.3 considerando todas as plataformas resulta na média das pontuações:

\[
P_{M1.3} = \frac{4 + 3 + 4 + 4 + 4 + 3 + 4 + 4 + 3 + 4}{10} = \frac{37}{10} = 3,7
\]

A pontuação final da métrica M1.3 é classificada como Excelente, refletindo o bom desempenho médio entre dispositivos móveis e desktops, considerando as barreiras de hardware dos mesmos.

Ao analisar a variação entre plataformas (M1.4), verificou-se que o desempenho apresenta diferenças significativas entre as máquinas testadas. O Coeficiente de Variação, calculado para cada benchmark, reforça essa instabilidade:

- **Coeficiente de variação do Speedometer:** 43,75%
- **Coeficiente de variação do JetStream 2:** 26,77%

Ambos os coeficientes ultrapassam o limite de 20%, o que coloca tanto o Speedometer quanto o JetStream 2 no Insatisfatório.  
Isso mostra que os diferentes sistemas operacionais não apresentaram consistência nos resultados dos benchmarks, já que o desempenho variou muito entre as plataformas avaliadas. 

\[
P_{M1.4} = \frac{2}{2} = 1
\]

Por exceder o limite de variação aceitável em ambos os benchmarks, a métrica é classificada como insatisfatória:


**Conclusão Q1.2**: O Firefox apresenta desempenho excelente na maioria dos testes sintéticos, considerando as limitações físicas de cada dispositivo. No entanto, a variação entre os resultados foi bastante elevada, não se restringindo apenas ao Android, mas também entre os desktops, especialmente nas diferentes coletas do Windows, indicando que a performance pode variar significativamente de acordo com a configuração da máquina.


#### 4.1.2 Validação das Hipóteses de Eficiência

#### Hipótese 1.1
> O Firefox carrega páginas em menos de 3 segundos e mantém o consumo médio de memória abaixo de 1 GB durante a navegação comum com 10 abas abertas.

**Análise da Hipótese**

Nos testes realizados, todas as plataformas apresentaram tempos de carregamento abaixo de 2 segundos, o que atende à expectativa de rapidez estabelecida. No entanto, o consumo de memória mostrou variações significativas, o Android manteve o uso de RAM dentro do limite de 1 GB, enquanto os desktops, incluindo Windows, macOS e Linux, apresentaram valores acima desse limite mesmo com 10 abas em sites simples como a Wikipédia.

Portanto, A hipótese 1.1 é considerada refutada.

---

#### Hipótese 1.2
> O Firefox apresenta desempenho funcional e consistente entre diferentes sistemas operacionais, mantendo a execução de tarefas em níveis similares.

**Análise da Hipótese**

Nos testes de benchmarks, o Firefox apresentou desempenho elevado em todas as plataformas, alcançando níveis Excelente ou Bom. No entanto, ao analisar a consistência entre os sistemas, observou-se variação significativa nos resultados. O Coeficiente de Variação calculado para cada benchmark indicou diferenças acima do limite aceitável de 20%, mostrando que a performance não se manteve uniforme entre os dispositivos. Essa variação indica que, apesar do alto desempenho médio, o Firefox não entrega níveis similares de execução em todos os ambientes testados.

Portanto, a hipótese 1.2 é considerada refutada, pois o Firefox não mantém consistência total entre os diferentes sistemas operacionais, mesmo apresentando desempenho funcional elevado.


### 4.2. Portabilidade

#### Dados Consolidados

Campos marcados com N/a removem o item da lista total

| Plataforma | M2.1 Paridade Funcional | M2.2 Conformidade UI |
| :--- | :--- | :--- |
| **Android** | 100% (19/19) | 100% (12/15) |
| **Windows** coleta 1 | 100% (19/19) | 100% (12/12) |
| **Windows** coleta 2 | 100% (19/19) | 100% (12/12) |
| **macOS** | 100% (19/19) | 100% (13/15) |
| **Linux** | 100% (19/19) | 100% (12/12) |

### 4.2.1 Respostas de Portabilidade

#### Resposta à Questão 2.1
**Q2.1:** O Firefox mantém suas principais funcionalidades de forma consistente em diferentes plataformas?

 Em todos os ambientes, o Firefox atingiu **100% de cobertura**. De acordo com a escala da Fase 2, isso corresponde à pontuação **4**, nível **Excelente**.

\[
P_{M2.1} = \frac{20}{5} = 4
\]

**Conclusão Q2.1:** A paridade funcional é total.

#### Resposta à Questão 2.2
**Q2.2:** O Firefox adapta corretamente sua interface e experiência de uso em diferentes dispositivos?

O Firefox manteve a fidelidade às convenções de cada sistema operacional, garantindo que as funcionalidades principais estejam disponíveis de forma consistente. A interface do navegador segue os padrões nativos de cada plataforma, o que facilita a adaptação e uso por usuários acostumados com o sistema, permitindo que naveguem sem dificuldade e associem rapidamente os elementos da UI ao comportamento esperado.

\[
P_{M2.1} = \frac{20}{5} = 4
\]

**Conclusão Q2.2:** O Firefox demonstra excelente adaptação da interface e consistência funcional entre os sistemas operacionais avaliados. Os usuários conseguem navegar e utilizar os recursos do navegador de forma intuitiva, aproveitando os padrões nativos de cada plataforma, o que garante uma experiência familiar e sem dificuldades de associação.

### 4.2.2 Validação das Hipóteses de Portabilidade

#### Hipótese 2.1
> O Firefox preserva 100% das funcionalidades essenciais como favoritos, histórico, extensões e sincronização em todas as plataformas.

**Análise da Hipótese**

O Firefox manteve todas as funcionalidades essenciais plenamente operacionais em Android, Windows, macOS e Linux. Não foram encontradas inconsistências ou falhas de execução entre as plataformas. Com base nos testes de paridade funcional, a Hipótese 2.1 está validada, pois os recursos essenciais estão disponíveis e funcionam de forma consistente em todos os ambientes

---

#### Hipótese 2.2
> O Firefox apresenta uma consistência de interface que garante que todos os elementos essenciais sejam corretamente exibidos e utilizáveis em diferentes dispositivos.

**Análise da Hipótese**

O Firefox manteve a fidelidade às convenções de cada sistema operacional, garantindo que as funcionalidades principais estejam disponíveis de forma consistente. A interface segue os padrões nativos de cada plataforma, facilitando a adaptação e o uso por usuários acostumados com o sistema, permitindo que naveguem sem dificuldade e associem rapidamente os elementos da UI ao comportamento esperado. Com base nisso, a Hipótese 2.2 está validada, pois a consistência da interface e a experiência de uso foram plenamente atendidas em todos os dispositivos avaliados.

---

## 5. Julgamento Final da Qualidade

### 5.1. Cálculo dos Índices

Utilizando as pontuações atribuídas de 1 a 4 nas análises acima:

### 4.2 Índice de Qualidade por Característica (Atualizado)

Para cada característica, calcula-se a média ponderada das métricas:

\[
IQ_c = \frac{\sum (P_i \times w_i)}{\sum w_i}
\]

- **IQc Eficiência:**  
  Métricas: RAM (2,5), LCP (4,0), Benchmarks (3,7), Variação (1,0)  
  \[
  IQc_{\text{Eficiência}} = \frac{2,5 + 4,0 + 3,7 + 1,0}{4} = 2,8
  \]

- **IQc Portabilidade:**  
  Métricas: Paridade Funcional (4,0), Conformidade UI (2,0)  
  \[
  IQc_{\text{Portabilidade}} = \frac{4,0 + 2,0}{2} = 3,0
  \]

### 5.2. Índice Global de Qualidade (IQG)

\[
IQG = \frac{2,8 + 3,0}{2} = 2.9
\]

### 5.3. Veredito

De acordo com os [Critérios de Aceitação definidos na Fase 2](../fase2.md#45-critérios-de-aceitação), o software Mozilla Firefox obteve um **IQG de 2.9**.

**Resultado Final:** **ACEITO**,

## 6. Recomendações de Melhoria

Com base nas métricas que pontuaram abaixo de Bom, ou nível 3, recomendam-se as seguintes ações:

1.  **Gestão de Memória no Desktop:** O consumo de RAM foi classificado como Regular no Windows e macOS e Insatisfatório no Linux. Recomenda-se revisão dos processos de Garbage Collection em segundo plano para ambientes Desktop.


## 7. 

## 8. Histórico de Versões

| Versão | Descrição | Autor(es) | Data |
| :--- | :--- | :--- | :--- |
| 1.0 | Criação do relatório de execução e análise dos resultados | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |
| 1.1 | Corrige hyperlinks dos dados brutos | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |
| 1.2 | Adiciona validação das hipóteses | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 28/11/2025 |