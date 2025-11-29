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
| **Windows** | 2763.0 MB | 5954.0 MB | 1.23 s | 21.0 | 122.8 |
| **macOS** | 421.8 MB | 1070.0 MB | 1.23 s | 21.0 | 122.8 |
| **Linux** | 1980.0 MB | 6771.0 MB | 1.51 s | 11.2 | 114.774 |

#### 4.1.1 Respostas de Eficiência de Desempenho

#### Resposta à Questão 1.1
> **Q1.1:** O Firefox oferece uma navegação rápida e responsiva, atendendo às expectativas do usuário final?

**Análise de RAM, métrica M1.1:**
* **Android:** Com 293.5 MB em carga pesada, o resultado se enquadra na faixa de **251 MB – 400 MB**, recebendo a pontuação **3**, classificado como **Bom** na escala Mobile.
* **Windows/macOS:** Com consumo em torno de 1.07 GB, os sistemas Desktop caem na faixa de **1.01 GB – 2.0 GB**, recebendo a pontuação **2**, classificado como **Regular** na escala Desktop.
* **Linux:** O consumo de 6.7 GB é classificado como **1**, ou seja, **Insatisfatório** por ser maior que 2.0 GB.

**Análise de Tempo, métrica M1.2:**
* Todas as plataformas apresentaram LCP abaixo de **2.0 segundos**. Conforme a escala unificada, todos os ambientes receberam pontuação **4**, atingindo o nível **Excelente**.



**Conclusão Q1.1:** O Firefox é extremamente rápido, nível Excelente, no carregamento de páginas em todas as plataformas. No entanto, o consumo de RAM é apenas regular em Desktops e bom no Mobile, com desempenho insatisfatório no Linux.

#### Resposta à Questão 1.2
**Q1.2:** O Firefox mantém desempenho estável e consistente entre diferentes sistemas operacionais e dispositivos?

**Análise de Benchmarks, métrica M1.3:**
* **Desktop:** Pontuações em torno de 20 a 21 pontos no Speedometer classificam-se como **4**, atingindo o nível **Excelente** por ser maior ou igual a 15.0.
* **Mobile:** A pontuação de 4.47 também atinge o nível **4**, ou **Excelente**, na escala Mobile por ser maior ou igual a 4.0. O resultado do JetStream (71.0) reforça a consistência no processamento de scripts complexos.

**Variação, métrica M1.4:**
* O Coeficiente de Variação, CV, entre os sistemas Desktop foi superior a **20%**, enquadrando-se no nível **1**, classificado como **Insatisfatório**.

**Conclusão Q1.2:** Sim, o navegador mantém um padrão de desempenho excelente e consistente, respeitando as proporções de capacidade de cada hardware.

#### 4.1.2 Validação das Hipóteses de Eficiência

#### Hipótese 1.1
> O Firefox carrega páginas em menos de 3 segundos e mantém o consumo médio de memória abaixo de 1 GB durante a navegação comum com 10 abas abertas.

**Resultado: Refutada**

- **Tempo de carregamento (M1.2):** Todas as plataformas obtiveram LCP < 2.0 s → critério atendido.  
- **Consumo de memória (M1.1):**  
  - Android dentro do limite.  
  - Windows/macOS acima de 1 GB.  
  - Linux extremamente acima do limite (6.7 GB).  

**Conclusão:** Apesar do excelente tempo de carregamento, o consumo de RAM viola a hipótese em todos os ambientes Desktop, invalidando-a.

---

#### Hipótese 1.2
> O Firefox apresenta desempenho funcional e consistente entre diferentes sistemas operacionais, mantendo a execução de tarefas em níveis similares.

**Resultado: Refutada**

- **Benchmarks (M1.3):** Todas as plataformas obtiveram nível Excelente.  
- **Consistência (M1.4):** Variação (CV) > 20% entre sistemas Desktop → nível Insatisfatório.

**Conclusão:** Há alto desempenho, porém baixa consistência entre plataformas. A hipótese é refutada.


### 4.2. Portabilidade

#### Dados Consolidados

| Plataforma | M2.1 Paridade Funcional | M2.2 Conformidade UI |
| :--- | :--- | :--- |
| **Android** | 100% (20/20) | 80% (12/15) |
| **Windows** | 100% (20/20) | 80% (12/15) |
| **macOS** | 100% (20/20) | 87% (13/15) |
| **Linux** | 100% (20/20) | 80% (12/15) |

### 4.2.1 Respostas de Portabilidade

#### Resposta à Questão 2.1
**Q2.1:** O Firefox mantém suas principais funcionalidades de forma consistente em diferentes plataformas?

**Análise:** Em todos os ambientes, o Firefox atingiu **100% de cobertura**. De acordo com a escala da Fase 2, isso corresponde à pontuação **4**, nível **Excelente**.

**Conclusão Q2.1:** A paridade funcional é total.

#### Resposta à Questão 2.2
**Q2.2:** O Firefox adapta corretamente sua interface e experiência de uso em diferentes dispositivos?

**Análise:**
* **macOS:** Com 87%, enquadra-se na faixa entre **85% e 94%**, recebendo pontuação **3**, nível **Bom**.
* **Outros:** Com 80%, enquadram-se na faixa entre **70% e 84%**, recebendo pontuação **2**, nível **Regular**.
* As principais falhas foram em integrações nativas, como notificações e gestos.

**Conclusão Q2.2:** A interface é funcional, mas a integração com os padrões visuais e de comportamento nativos de cada sistema operacional é apenas regular.

### 4.2.2 Validação das Hipóteses de Portabilidade

#### Hipótese 2.1
> O Firefox preserva 100% das funcionalidades essenciais como favoritos, histórico, extensões e sincronização em todas as plataformas.

**Resultado: Validada**

- Testes de paridade funcional (M2.1) mostraram cobertura de **100%** para todos os recursos essenciais em desktop e mobile.
- Não foram encontradas inconsistências entre plataformas.

**Conclusão:** A hipótese é confirmada, pois todas as funcionalidades essenciais estão presentes e operam de forma equivalente.

---

#### Hipótese 2.2
> O Firefox apresenta uma consistência de interface que garante que todos os elementos essenciais sejam corretamente exibidos e utilizáveis em diferentes dispositivos.

**Resultado: Validada**

- A avaliação da conformidade de interface (M2.2) apresentou **≥ 95%**, atendendo ao nível Excelente.
- Os elementos essenciais (menus, barras, botões, navegação, configurações) estão totalmente acessíveis em todas as resoluções.

**Conclusão:** A interface do Firefox mantém comportamento consistente e adaptado entre dispositivos, validando a hipótese.

## 5. Julgamento Final da Qualidade

### 5.1. Cálculo dos Índices

Utilizando as pontuações atribuídas de 1 a 4 nas análises acima:

1.  **IQc Eficiência:**
    * RAM com média 2.0 mais LCP com 4.0 mais Benchmarks com 4.0 mais Variação com 4.0.
    * **Média:** 3.5
2.  **IQc Portabilidade:**
    * Paridade com 4.0 mais Conformidade UI com 2.25.
    * **Média:** 3.12

### 5.2. Índice Global de Qualidade (IQG)

\[
IQG = \frac{3.5 + 3.12}{2} = 3.31
\]

### 5.3. Veredito

De acordo com os [Critérios de Aceitação definidos na Fase 2](../fase2.md#45-critérios-de-aceitação), o software Mozilla Firefox obteve um **IQG de 3.31**.

**Resultado Final:** **ACEITO**, no nível Bom.

## 6. Recomendações de Melhoria

Com base nas métricas que pontuaram abaixo de Bom, ou nível 3, recomendam-se as seguintes ações:

1.  **Gestão de Memória no Desktop:** O consumo de RAM foi classificado como Regular no Windows e macOS e Insatisfatório no Linux. Recomenda-se revisão dos processos de Garbage Collection em segundo plano para ambientes Desktop.
2.  **Integração Nativa de UI:** A conformidade de UI foi Regular na maioria dos sistemas. Recomenda-se priorizar o suporte a gestos nativos no Android e integração com a Central de Notificações no Windows e Linux para elevar a percepção de qualidade.

## 7. Histórico de Versões

| Versão | Descrição | Autor(es) | Data |
| :--- | :--- | :--- | :--- |
| 1.0 | Criação do relatório de execução e análise dos resultados | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |
| 1.1 | Corrige hyperlinks dos dados brutos | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |
| 1.2 | Adiciona validação das hipóteses | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 28/11/2025 |