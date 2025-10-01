# Fase 1: 

### Descrição Estrurada do Software Selecionado
O **Mozilla Firefox** é um navegador web de código aberto, multiplataforma, desenvolvido e mantido pela Mozilla Foundation. É amplamente utilizado em desktops e dispositivos móveis, sendo uma peça fundamental da infraestrutura digital global.

A escolha do Firefox para esta avaliação se justifica por três pilares centrais:
-   **Relevância global:** O navegador desempenha um papel crucial na promoção de um ecossistema digital aberto e competitivo.
-   **Desenvolvimento contínuo e comunidade ativa:** O Firefox possui um ciclo de desenvolvimento rápido e uma comunidade de contribuidores robusta, o que garante a disponibilidade de vasta documentação pública e dados de bugs, como os encontrados no Bugzilla.<a id="cite-1-2"></a>[[1]](#ref-1), [[2]](#ref-2)
-   **Diversidade de ambientes de execução:** Sua natureza multiplataforma permite a coleta de métricas concretas e comparáveis em diferentes sistemas operacionais.

Do ponto de vista técnico, a arquitetura moderna do Firefox é baseada em um modelo **multi-processo**, que isola a interface do navegador dos conteúdos web.<a id="cite-3"></a>[[3]](#ref-3) Essa separação, que utiliza componentes como o motor de renderização **Gecko** e o motor JavaScript **SpiderMonkey**, é projetada para melhorar a estabilidade e a segurança, mas introduz um *trade-off* com o consumo de recursos.<a id="cite-4"></a>[[4]](#ref-4)



### Requisitante Principal

- **Mozilla**: Possui autoridade direta sobre o Firefox, garantindo financiamento, definição de prioridades e direção do projeto. É o requisitante principal, pois encomenda e supervisiona o projeto, buscando que o navegador seja eficiente e acessível para todos.

### Partes interessadas

- **Usuários do navegador**: Impactam diretamente o desenvolvimento com feedback e uso contínuo. Esperam um navegador com um tempo de resposta curto, que consuma pouca memória e CPU e que funcione em diferentes dispositivos. Sua influência é preceptível nas decisões de desempenho e priorização de melhorias.  

- **Comunidade open source**: Contribui com código, testes e documentação, ajudando na evolução do Firefox. Buscam participar do desenvolvimento e implementar melhorias de eficiência e portabilidade. Influenciam diretamente o projeto por meio de sugestões e contribuições práticas.

- **Instituições que utilizam o Firefox**: Dependem do navegador e influenciam indiretamente. Esperam que o software funcione corretamente em seus sistemas, sem decidir funcionalidades.  

- **Parceiros comerciais**: Interessados em parcerias ou divulgação, buscam associar-se a um navegador bem avaliado e acessível. Influenciam de forma indireta, podendo sinalizar necessidades de portabilidade para uma maior divulgação, mas não impacta diretamente decisões do desenvolvimento.

Os usuários do navegador e a comunidade open source são as partes interessadas principais, pois influenciam diretamente no desenvolvimento e operação do produto, influenciando suas funcionalidades e qualidade. Já as instituições e parceiros comerciais influenciam de forma mais indireta, afetando decisões estratégicas, mas não o funcionamento em si do produto.


### Classificação do Tipo de Produto
O Firefox é um navegador de código aberto criado pela Mozilla Foundation, capaz de ser usado em diversas plataformas, como Windows, Linux e macOS. Trata-se de um software multiplataforma, distribuído e de código aberto, onde o domínio de atuação envolve o acesso à internet, produtividade e comunicação. O front-end do navegador é composto por XUL, HTML, CSS e JavaScript, enquanto o back-end utiliza linguagens como C++, Python e Rust.


#### Módulos Principais

O código-fonte do Firefox é organizado em diferentes diretórios, que representam componentes fundamentais da sua arquitetura.  
Os principais módulos do FireFox são:


- **browser/**  
  Contém o código do front-end do Firefox para a versão desktop.

- **browser/themes/**  
  Contém imagens e arquivos CSS usados para personalizar a aparência do navegador em diferentes sistemas operacionais (Windows, Linux, macOS).

- **layout/**  
  Implementa a árvore de renderização, que define o tipo e a posição dos objetos na interface do usuário, além de gerenciar operações sobre essa árvore.

- **js/src/**  
  Também chamado de SpiderMonkey, é o motor JavaScript do Firefox.

- **netwerk/**  
  Conhecida como Necko, é a biblioteca de rede do Firefox dentro do motor de renderização Gecko, responsável por implementar os protocolos de rede da web.





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



### Lista das Características Escolhidas e Critérios de Priorização
-   **Eficiência:**
    -   **Critério:** Impacto direto na experiência do usuário. Um navegador lento ou que consome muitos recursos leva à frustração e ao abandono do produto.
    -   **Aplicação:** Medir tempo de carregamento, inicialização e uso de recursos em diferentes cenários.

-   **Portabilidade:**
    -   **Critério:** Democratização do acesso, abrangência multiplataforma.
    -   **Aplicação:** Comparar instalação, atualização e compatibilidade em diferentes sistemas.


### Escopo, Profundidade e Objetos de Avaliação
-   **Escopo:** Avaliação de eficiência e portabilidade do Firefox em **Windows, Linux, macOS e Android**.
-   **Profundidade:** Métricas objetivas (tempo em milissegundos, uso percentual de CPU/memória, sucesso em instalação e atualização). Ferramentas como **Speedometer** e **JetStream** <a id="cite-5"></a>[[5]](#ref-5) serão usadas para benchmarks de desempenho, e utilitários de sistema (`typeperf` no Windows <a id="cite-6"></a>[[6]](#ref-6), `top` <a id="cite-7"></a>[[7]](#ref-7) e `vmstat` <a id="cite-8"></a>[[8]](#ref-8) no Linux) para monitoramento de recursos.
-   **Objetos de avaliação:** Versão estável mais recente do Firefox em múltiplos ambientes, com e sem extensões.


### Propósito da Avaliação e Uso Pretendido dos Resultados

- **Propósito:** O nosso propósito é avaliar a qualidade do software Firefox, um navegador multiplataforma de código aberto, e analisar com foco nas características de eficiência e portabilidade levando em consideração seu uso em diferentes plataformas e cenários.  

Os resultados dessa avaliação interessam toda a comunidade que utiliza o navegador Firefox, pois poderão ter acesso a informações relevantes sobre o desempenho da aplicação, sua capacidade de adaptação a diferentes sistemas operacionais e dispositivos, além de compreender possíveis limitações e oportunidades de melhoria. Dessa forma, a análise contribui tanto para usuários finais, que buscam uma experiência de navegação mais estável e otimizada, quanto para desenvolvedores e colaboradores do projeto, que poderão utilizar os resultados dessa avaliação para futuras evoluções do software.

- **Uso dos resultados:**  
  - **1. Apoiar melhorias de desempenho**: A avaliação da qualidade do Firefox permite identificar gargalos de processamento, uso de memória e tempo de resposta. Esses dados podem ser utilizados para otimizações futuras, garantindo que o navegador continue competitivo e adequado às necessidades dos usuários em diferentes dispositivos e sistemas operacionais. 
  - **2. Garantir maior inclusão digital por meio do acesso a software livre de qualidade**: Como o Firefox é um navegador de código aberto e multiplataforma, sua melhoria contínua contribui para ampliar o acesso a ferramentas digitais estáveis, seguras e de qualidade, independentemente do poder aquisitivo ou da plataforma utilizada, promovendo assim a democratização da tecnologia.  
  - **3. Estabelecer métricas auditáveis para comparações futuras**: A definição de critérios e métricas de eficiência e portabilidade permite acompanhar a evolução do navegador ao longo do tempo. Além disso, possibilita comparações transparentes com outros softwares similares, oferecendo um referencial técnico que apoia a tomada de decisões por parte da comunidade de desenvolvedores e usuários.  



### ODS Relacionados e Justificativa

-   **ODS 9 — Indústria, Inovação e Infraestrutura:**
    Avaliar a **eficiência** do Firefox contribui para compreender como a infraestrutura digital pode ser otimizada para inovação tecnológica inclusiva, alinhando-se à Meta 9.c de aumentar o acesso a tecnologias de informação.<a id="cite-9"></a>[[9]](#ref-9)

    ![imagem da Meta 9.c](assets/referencia-9.c.png)
    **Figura 1** – Meta 9.c do Objetivo de Desenvolvimento Sustentável 9.
    **Fonte:** ORGANIZAÇÃO DAS NAÇÕES UNIDAS NO BRASIL, [s.d.].

-   **ODS 10 — Redução das Desigualdades:**
    Avaliar a **portabilidade** garante que o navegador funcione em hardware de baixo custo, promovendo inclusão digital e equidade no acesso à informação, em conformidade com a Meta 10.2 de promover a inclusão social e econômica de todos.<a id="cite-10"></a>[[10]](#ref-10)

    ![imagem da Meta 10.2](assets/referencia-10.2.png)
    **Figura 2** – Meta 10.2 do Objetivo de Desenvolvimento Sustentável 10.
    **Fonte:** ORGANIZAÇÃO DAS NAÇÕES UNIDAS NO BRASIL, [s.d.].



## Bibliografia

ISO. **ISO/IEC 25000:2014 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Guide to SQuaRE.** International Organization for Standardization, 2014. Disponível em: [https://www.iso.org/standard/64764.html](https://www.iso.org/standard/64764.html). Acesso em: 30 set. 2025.

ISO. **ISO/IEC 25010:2011 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models.** International Organization for Standardization, 2011. Disponível em: [https://www.iso.org/standard/35733.html](https://www.iso.org/standard/35733.html). Acesso em: 30 set. 2025.

ISO. **ISO/IEC 25023:2016 — Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Measurement of system and software product quality.** International Organization for Standardization, 2016. Disponível em: [https://www.iso.org/standard/35746.html](https://www.iso.org/standard/35746.html). Acesso em: 30 set. 2025.

ORGANIZAÇÃO DAS NAÇÕES UNIDAS NO BRASIL. **ODS 9: Indústria, Inovação e Infraestrutura**. Nações Unidas Brasil, [s.d.]. Disponível em: https://brasil.un.org/pt-br/sdgs/9. Acesso em: 1 out. 2025.

ORGANIZAÇÃO DAS NAÇÕES UNIDAS NO BRASIL. **ODS 10: Redução das Desigualdades**. Nações Unidas Brasil, [s.d.]. Disponível em: https://brasil.un.org/pt-br/sdgs/10. Acesso em: 1 out. 2025.

## Referências Bibliográficas
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
| 1.0 | Criação e documentação inicial da fase 1 (ODS's ) |[João Filipe de Oliveira Souza](https://github.com/joao151104) | 29/09/2025 | | |
| 1.1 | Adição da bibliografia e do histórico de versões | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 29/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 29/09/2025 |
| 1.2 | Reestruturação do documento  | [Artur Mendonça Arruda](https://github.com/ArtyMend07) e [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 29/09/2025 |  |  |
| 1.3 | Adição de detalhes técnicos, relação entre as características, e da profundidade do projeto | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 30/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 30/09/2025 |
| 1.4 | Adição de hyperlinks das fontes | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 30/09/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 30/09/2025 |
| 1.5 |  |  | 30/09/2025 |  | 30/09/2025 |
| 1.6 | Adição de partes interessadas e classificação do tipo do produto | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 01/10/2025 |  |  |
| 1.7 | Adição das imagens e bibliografia das ODS's | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 01/10/2025 | [Lucas Mendonça Arruda](https://github.com/lucasarruda9) | 01/10/2025 |