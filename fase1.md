# Fase 1

### Descrição Estruturada do Software Selecionado
O **Mozilla Firefox** é um navegador multiplataforma, de código aberto, amplamente utilizado em desktops e dispositivos móveis.  
Sua escolha se justifica por:  
- Relevância global na promoção de um ecossistema digital aberto;  
- Desenvolvimento contínuo e comunidade ativa;  
- Diversidade de ambientes de execução que permitem métricas concretas e comparáveis.  

---


### Propósito da Avaliação e Uso Pretendido dos Resultados
- **Propósito:** Avaliar como o Firefox mantém eficiência e portabilidade em diferentes plataformas e cenários de uso.  
- **Uso dos resultados:**  
  - Apoiar melhorias de desempenho;  
  - Garantir maior inclusão digital por meio do acesso a software livre de qualidade;  
  - Estabelecer métricas auditáveis para comparações futuras.  

---
## Requisitante e partes interessadas


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

####  Módulos Principais

- **browser/**  
  Contém o código do front-end do Firefox para a versão desktop.

- **browser/themes/**  
  Contém imagens e arquivos CSS usados para personalizar a aparência do navegador em diferentes sistemas operacionais (Windows, Linux, macOS).

- **layout/**  
  Implementa a árvore de renderização, que define o tipo e a posição dos objetos na interface do usuário, além de gerenciar operações sobre essa árvore.

- **js/src/**  
  Também chamado de SpiderMonkey, é a engine de JavaScript e WebAssembly do Firefox.

- **netwerk/**  
  Conhecida como Necko, é a biblioteca de rede do Firefox dentro do motor de renderização Gecko, responsável por implementar os protocolos de rede da web.



#### Interfaces
---


### Modelo de Qualidade (Descrição e Representação Gráfica)
O modelo de qualidade adotado é baseado na ISO/IEC 25010, adaptado às necessidades do Firefox.  
Características selecionadas: **Eficiência** e **Portabilidade**.  

**Relação entre as características:**  
- Eficiência assegura que o navegador responda de forma rápida e com baixo consumo de recursos.  
- Portabilidade garante que esse desempenho seja mantido em diferentes sistemas operacionais e arquiteturas.  

**Estrutura do Modelo de Qualidade**  
Qualidade do Produto:
- Eficiência
    - Desempenho (tempo de resposta, consumo de CPU/memória)
    - Escalabilidade (múltiplas abas, uso de extensões)

- Portabilidade
    - Adaptabilidade (Windows, Linux, macOS, Android)

---

### Lista das Características Escolhidas e Critérios de Priorização
- **Eficiência:**  
  - Critério: impacto direto na experiência do usuário.  
  - Aplicação: medir tempo de carregamento, inicialização e uso de recursos em diferentes cenários.  

- **Portabilidade:**  
  - Critério: democratização do acesso, abrangência multiplataforma.  
  - Aplicação: comparar instalação, atualização e compatibilidade em diferentes sistemas.  

---

### Escopo, Profundidade e Objetos de Avaliação
- **Escopo:** Avaliação de eficiência e portabilidade do Firefox em Windows, Linux, macOS e Android.  
- **Profundidade:** Métricas objetivas (tempo em milissegundos, uso percentual de CPU/memória, sucesso em instalação e atualização).  
- **Objetos de avaliação:** Versão estável mais recente do Firefox em múltiplos ambientes, com e sem extensões.  

---

### ODS Relacionados e Justificativa
- **ODS 9 — Indústria, Inovação e Infraestrutura:**  
  Avaliar eficiência do Firefox contribui para compreender como a infraestrutura digital pode ser otimizada para inovação tecnológica inclusiva.  

- **ODS 10 — Redução das Desigualdades:**  
  Avaliar portabilidade garante que o navegador funcione em hardware de baixo custo, promovendo inclusão digital e equidade no acesso à informação.  


https://firefox-source-docs.mozilla.org/contributing/directory_structure.html

https://firefox--source--docs-mozilla-org.translate.goog/overview/gecko.html?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt&_x_tr_pto=tc