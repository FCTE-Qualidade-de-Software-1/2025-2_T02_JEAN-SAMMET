# Fase 1: Definição dos Requisitos de Avaliação de Qualidade

### Descrição Estruturada do Software Selecionado
O **Mozilla Firefox** é um navegador web de código aberto, multiplataforma, desenvolvido e mantido pela Mozilla Foundation. É amplamente utilizado em desktops e dispositivos móveis, sendo uma peça fundamental da infraestrutura digital global.

A escolha do Firefox para esta avaliação se justifica por três pilares centrais:
-   **Relevância global:** O navegador desempenha um papel crucial na promoção de um ecossistema digital aberto e competitivo.
-   **Desenvolvimento contínuo e comunidade ativa:** O Firefox possui um ciclo de desenvolvimento rápido e uma comunidade de contribuidores robusta, o que garante a disponibilidade de vasta documentação pública e dados de bugs, como os encontrados no Bugzilla.[1, 2]
-   **Diversidade de ambientes de execução:** Sua natureza multiplataforma permite a coleta de métricas concretas e comparáveis em diferentes sistemas operacionais, o que é essencial para a avaliação da característica de portabilidade.

Do ponto de vista técnico, a arquitetura moderna do Firefox é baseada em um modelo **multi-processo**, que isola a interface do navegador dos conteúdos web.[3] Essa separação, que utiliza componentes como o motor de renderização **Gecko** e o motor JavaScript **SpiderMonkey**, é projetada para melhorar a estabilidade e a segurança, mas introduz um *trade-off* com o consumo de recursos.[4]

---

### Classificação do Tipo de Produto
-   **Categoria:** Software aplicativo (navegador web).
-   **Natureza:** Multiplataforma, distribuído e de código aberto.
-   **Domínio:** Acesso à internet, produtividade e comunicação.

---

### Propósito da Avaliação e Uso Pretendido dos Resultados
-   **Propósito:** Avaliar como o Firefox mantém **eficiência** e **portabilidade** em diferentes plataformas e cenários de uso.
-   **Uso dos resultados:**
    -   Apoiar melhorias de desempenho.
    -   Garantir maior inclusão digital por meio do acesso a software livre de qualidade.
    -   Estabelecer métricas auditáveis para comparações futuras.

---

### Modelo de Qualidade (Descrição e Representação Gráfica)
O modelo de qualidade adotado é baseado na norma **ISO/IEC 25010**, adaptado às necessidades do Firefox. As características selecionadas são **Eficiência** e **Portabilidade**.

**Relação entre as características:**
-   Eficiência assegura que o navegador responda de forma rápida e com baixo consumo de recursos.
-   Portabilidade garante que esse desempenho seja mantido em diferentes sistemas operacionais e arquiteturas.

**Estrutura do Modelo de Qualidade**
Qualidade do Produto:
- Eficiência
    - Desempenho (tempo de resposta, consumo de CPU/memória)
    - Escalabilidade (múltiplas abas, uso de extensões)
- Portabilidade
    - Adaptabilidade (Windows, Linux, macOS, Android)

---

### Lista das Características Escolhidas e Critérios de Priorização
-   **Eficiência:**
    -   **Critério:** Impacto direto na experiência do usuário. Um navegador lento ou que consome muitos recursos leva à frustração e ao abandono do produto.
    -   **Aplicação:** Medir tempo de carregamento, inicialização e uso de recursos em diferentes cenários.

-   **Portabilidade:**
    -   **Critério:** Democratização do acesso, abrangência multiplataforma.
    -   **Aplicação:** Comparar instalação, atualização e compatibilidade em diferentes sistemas.

---

### Escopo, Profundidade e Objetos de Avaliação
-   **Escopo:** Avaliação de eficiência e portabilidade do Firefox em **Windows, Linux, macOS e Android**.
-   **Profundidade:** Métricas objetivas (tempo em milissegundos, uso percentual de CPU/memória, sucesso em instalação e atualização). Ferramentas como **Speedometer** [5] e **JetStream** [6] serão usadas para benchmarks de desempenho, e utilitários de sistema (`typeperf` no Windows [7], `top`/`vmstat` no Linux [8, 9]) para monitoramento de recursos.
-   **Objetos de avaliação:** Versão estável mais recente do Firefox em múltiplos ambientes, com e sem extensões.

---

### ODS Relacionados e Justificativa
-   **ODS 9 — Indústria, Inovação e Infraestrutura:**
    Avaliar a **eficiência** do Firefox contribui para compreender como a infraestrutura digital pode ser otimizada para inovação tecnológica inclusiva, alinhando-se à Meta 9.c de aumentar o acesso a tecnologias de informação .

-   **ODS 10 — Redução das Desigualdades:**
    Avaliar a **portabilidade** garante que o navegador funcione em hardware de baixo custo, promovendo inclusão digital e equidade no acesso à informação, em conformidade com a Meta 10.2 de promover a inclusão social e econômica de todos .

---

## Bibliografia

ISO. **ISO/IEC 25000:2014 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Guide to SQuaRE.** International Organization for Standardization, 2014. Disponível em: [https://www.iso.org/standard/64764.html](https://www.iso.org/standard/64764.html). Acesso em: 29 set. 2025.

ISO. **ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models.** International Organization for Standardization, 2011. Disponível em: [https://www.iso.org/standard/35733.html](https://www.iso.org/standard/35733.html). Acesso em: 29 set. 2025.

ISO. **ISO/IEC 25023:2016 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Measurement of system and software product quality.** International Organization for Standardization, 2016. Disponível em: [https://www.iso.org/standard/35746.html](https://www.iso.org/standard/35746.html). Acesso em: 29 set. 2025.

BrowserBench. **Browser Benchmarks: Speedometer, JetStream, MotionMark.** Disponível em: [https://browserbench.org/](https://browserbench.org/). Acesso em: 29 set. 2025. [10]

Mozilla. **Firefox Source Docs.** Documentação oficial da arquitetura e componentes do Firefox. Disponível em: [https://firefox-source-docs.mozilla.org/](https://firefox-source-docs.mozilla.org/). Acesso em: 29 set. 2025. [11]

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| ------ | ------------------------------------------------ | -------------------------------------------------------------- | ---------- | ------------------------------------------------------------ | --------------- |
| 1.0 | Criação e documentação inicial da fase 1 |(https://github.com/joao151104) | 29/09/2025 | | |
| 1.1 | Adição da bibliografia e do histórico de versões | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 29/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 29/09/2025 |
| 1.2 | Aprimoramento do documento com demilitação de escopo e justificativa das ODS's  | [Artur Mendonça Arruda](https://github.com/ArtyMend07) e [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 29/09/2025 |  |  |