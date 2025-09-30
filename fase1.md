# Fase 1: Definição dos Requisitos de Avaliação de Qualidade

### Descrição Estrurada do Software Selecionado
O **Mozilla Firefox** é um navegador web de código aberto, multiplataforma, desenvolvido e mantido pela Mozilla Foundation. É amplamente utilizado em desktops e dispositivos móveis, sendo uma peça fundamental da infraestrutura digital global.

A escolha do Firefox para esta avaliação se justifica por três pilares centrais:
-   **Relevância global:** O navegador desempenha um papel crucial na promoção de um ecossistema digital aberto e competitivo.
-   **Desenvolvimento contínuo e comunidade ativa:** O Firefox possui um ciclo de desenvolvimento rápido e uma comunidade de contribuidores robusta, o que garante a disponibilidade de vasta documentação pública e dados de bugs, como os encontrados no Bugzilla.<a id="cite-1-2"></a>[[1]](#ref-1), [[2]](#ref-2)
-   **Diversidade de ambientes de execução:** Sua natureza multiplataforma permite a coleta de métricas concretas e comparáveis em diferentes sistemas operacionais.

Do ponto de vista técnico, a arquitetura moderna do Firefox é baseada em um modelo **multi-processo**, que isola a interface do navegador dos conteúdos web.<a id="cite-3"></a>[[3]](#ref-3) Essa separação, que utiliza componentes como o motor de renderização **Gecko** e o motor JavaScript **SpiderMonkey**, é projetada para melhorar a estabilidade e a segurança, mas introduz um *trade-off* com o consumo de recursos.<a id="cite-4"></a>[[4]](#ref-4)

---

### Classificação do Tipo de Produto
-   **Categoria:** Software aplicativo (navegador web).
-   **Natureza:** Multiplataforma, distribuído e de código aberto.
-   **Domínio:** Acesso à internet, produtividade e comunicação.

---

### Propósito da Avaliação e Uso Pretendido dos Resultados
-   **Propósito:** Avaliar como o Firefox mantém **eficiência** e **portabilidade** em diferentes plataformas e cenários de uso.
-   **Uso dos resultados:**
    -   Apoiar melhorias de desempenho.
    -   Garantir maior inclusão digital por meio do acesso a software livre de qualidade.
    -   Estabelecer métricas auditáveis para comparações futuras.

---

### Modelo de Qualidade (Descrição e Representação Gráfica)
O modelo de qualidade adotado é baseado na norma **ISO/IEC 25010**, adaptado às necessidades do Firefox. As características selecionadas são **Eficiência** e **Portabilidade**.

**Relação entre as características:**
-   Eficiência assegura que o navegador responda de forma rápida e com baixo consumo de recursos.
-   Portabilidade garante que esse desempenho seja mantido em diferentes sistemas operacionais e arquiteturas.

**Estrutura do Modelo de Qualidade**
Qualidade do Produto:
- Eficiência
    - Desempenho (tempo de resposta, consumo de CPU/memória)
    - Escalabilidade (múltiplas abas, uso de extensões)
- Portabilidade
    - Adaptabilidade (Windows, Linux, macOS, Android)

---

### Lista das Características Escolhidas e Critérios de Priorização
-   **Eficiência:**
    -   **Critério:** Impacto direto na experiência do usuário. Um navegador lento ou que consome muitos recursos leva à frustração e ao abandono do produto.
    -   **Aplicação:** Medir tempo de carregamento, inicialização e uso de recursos em diferentes cenários.

-   **Portabilidade:**
    -   **Critério:** Democratização do acesso, abrangência multiplataforma.
    -   **Aplicação:** Comparar instalação, atualização e compatibilidade em diferentes sistemas.

---

### Escopo, Profundidade e Objetos de Avaliação
-   **Escopo:** Avaliação de eficiência e portabilidade do Firefox em **Windows, Linux, macOS e Android**.
-   **Profundidade:** Métricas objetivas (tempo em milissegundos, uso percentual de CPU/memória, sucesso em instalação e atualização). Ferramentas como **Speedometer** e **JetStream** <a id="cite-5"></a>[[5]](#ref-5) serão usadas para benchmarks de desempenho, e utilitários de sistema (`typeperf` no Windows <a id="cite-6"></a>[[6]](#ref-6), `top` <a id="cite-7"></a>[[7]](#ref-7) e `vmstat` <a id="cite-8"></a>[[8]](#ref-8) no Linux) para monitoramento de recursos.
-   **Objetos de avaliação:** Versão estável mais recente do Firefox em múltiplos ambientes, com e sem extensões.

---

### ODS Relacionados e Justificativa
-   **ODS 9 — Indústria, Inovação e Infraestrutura:**
    Avaliar a **eficiência** do Firefox contribui para compreender como a infraestrutura digital pode ser otimizada para inovação tecnológica inclusiva, alinhando-se à Meta 9.c de aumentar o acesso a tecnologias de informação.

-   **ODS 10 — Redução das Desigualdades:**
    Avaliar a **portabilidade** garante que o navegador funcione em hardware de baixo custo, promovendo inclusão digital e equidade no acesso à informação, em conformidade com a Meta 10.2 de promover a inclusão social e econômica de todos.

---

## Bibliografia

ISO. **ISO/IEC 25000:2014 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Guide to SQuaRE.** International Organization for Standardization, 2014. Disponível em: [https://www.iso.org/standard/64764.html](https://www.iso.org/standard/64764.html). Acesso em: 30 set. 2025.

ISO. **ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models.** International Organization for Standardization, 2011. Disponível em: [https://www.iso.org/standard/35733.html](https://www.iso.org/standard/35733.html). Acesso em: 30 set. 2025.

ISO. **ISO/IEC 25023:2016 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Measurement of system and software product quality.** International Organization for Standardization, 2016. Disponível em: [https://www.iso.org/standard/35746.html](https://www.iso.org/standard/35746.html). Acesso em: 30 set. 2025.

<a id="ref-1"></a>[[1]](#cite-1-2) THE BUGZILLA PROJECT. **Bugzilla**. Disponível em: [https://www.bugzilla.org/](https://www.bugzilla.org/). Acesso em: 30 set. 2025.

<a id="ref-2"></a>[[2]](#cite-1-2) MOZILLA. **Bug Writing Guidelines**. MDN Web Docs. Disponível em: [https://developer.mozilla.org/en-US/docs/Mozilla/QA/Bug_writing_guidelines](https://developer.mozilla.org/en-US/docs/Mozilla/QA/Bug_writing_guidelines). Acesso em: 30 set. 2025.

<a id="ref-3"></a>[[3]](#cite-3) MOZILLA. **Process Model**. Firefox Source Docs. Disponível em: [https://firefox-source-docs.mozilla.org/dom/ipc/process_model.html](https://firefox-source-docs.mozilla.org/dom/ipc/process_model.html). Acesso em: 30 set. 2025.

<a id="ref-4"></a>[[4]](#cite-4) MOZILLA. **Gecko Overview**. Firefox Source Docs. Disponível em: [https://firefox-source-docs.mozilla.org/overview/gecko.html](https://firefox-source-docs.mozilla.org/overview/gecko.html). Acesso em: 30 set. 2025.

<a id="ref-5"></a>[[5]](#cite-5) BROWSERBENCH. **Browser Benchmarks: Speedometer, JetStream, MotionMark**. Disponível em: [https://browserbench.org/](https://browserbench.org/). Acesso em: 30 set. 2025.

<a id="ref-6"></a>[[6]](#cite-6) MICROSOFT. **typeperf command**. Microsoft Learn. Disponível em: [https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/typeperf](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/typeperf). Acesso em: 30 set. 2025.

<a id="ref-7"></a>[[7]](#cite-7) THE LINUX MAN-PAGES PROJECT. **top(1) — Linux manual page**. Disponível em: https://man7.org/linux/man-pages/man1/top.1.html. Acesso em: 30 set. 2025.

<a id="ref-8"></a>[[8]](#cite-8) THE LINUX MAN-PAGES PROJECT. **vmstat(8) — Linux manual page**. Disponível em: https://man7.org/linux/man-pages/man8/vmstat.8.html. Acesso em: 30 set. 2025.

---

## Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| ------ | ------------------------------------------------ | -------------------------------------------------------------- | ---------- | ------------------------------------------------------------ | --------------- |
| 1.0 | Criação e documentação inicial da fase 1 (ODS's, ) |[João Filipe de Oliveira Souza](https://github.com/joao151104) | 29/09/2025 | | |
| 1.1 | Adição da bibliografia e do histórico de versões | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 29/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 29/09/2025 |
| 1.2 | Reestruturação do documento  | [Artur Mendonça Arruda](https://github.com/ArtyMend07) e [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 29/09/2025 |  |  |
| 1.3 | Adição de detalhes técnicos, relação entre as características, e da profundidade do projeto | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 30/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 30/09/2025 |
| 1.4 | Adição de hyperlinks das fontes | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 30/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 30/09/2025 |