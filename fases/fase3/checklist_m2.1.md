# Checklist M2.1: Paridade Funcional

## 1. Introdução

Este documento detalha o checklist de 20 itens para a métrica M2.1 (Paridade Funcional), conforme definido no [Plano de Execução da Fase 3](fase3.md#25-checklists-de-verificação-para-portabilidade-m2).

O objetivo é verificar a presença e o funcionamento correto das funcionalidades essenciais do Firefox nos quatro ambientes de teste.

## 2. Metodologia de Execução

Cada executor deve criar uma cópia deste documento para seu respectivo ambiente.

O processo consiste em verificar item por item se a funcionalidade está presente e operativa.

### Critérios de Pontuação
* **OK:** A funcionalidade existe no ambiente e funciona como esperado.
* **N/A (Não Aplicável):** A funcionalidade não se aplica a este ambiente (ex: "Mover Aba para nova janela" no Android). Itens marcados como N/A não contam contra a pontuação final.
* **FALHA:** A funcionalidade está visivelmente ausente ou apresenta um erro que impede seu uso.

### Registro de Resultados
Ao final, o executor deve somar o número total de itens marcados como 'OK' e registrar o total (ex: "19/20") na [Planilha Mestra](fase3.md#21-artefatos-de-coleta-e-divisão-de-tarefas). O link para o documento preenchido deve ser adicionado na coluna de evidências.

---

## 3. Checklist (Template)

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** *[Preencha: Windows / Linux / macOS / Android]*
**Executor:** *[Preencha seu nome]*

---

### Total: \_\_/20

**1. Gerenciamento de Conta e Sincronização (5 Itens)**
- [ ] **1.1 Login:** Consegue fazer login em uma conta Firefox.
- [ ] **1.2 Sinc. Favoritos:** Favoritos adicionados em outro dispositivo aparecem.
- [ ] **1.3 Sinc. Histórico:** Sites visitados em outro dispositivo aparecem.
- [ ] **1.4 Sinc. Senhas:** Senhas salvas em outro dispositivo são preenchidas.
- [ ] **1.5 Logout:** Consegue desconectar a conta do navegador.

**2. Navegação e Gerenciamento de Abas (5 Itens)**
- [ ] **2.1 Modo Privado:** Consegue abrir uma janela/aba de navegação privativa.
- [ ] **2.2 Reabrir Aba Fechada:** A função "Reabrir aba fechada" está presente.
- [ ] **2.3 Fixar Aba:** Consegue "Fixar Aba".
- [ ] **2.4 Mover Aba:** Consegue arrastar uma aba para uma nova janela.
- [ ] **2.5 Mudo de Aba:** Consegue silenciar o áudio de uma aba específica.

**3. Interação com Conteúdo Web (5 Itens)**
- [ ] **3.1 Reprodução de Mídia:** Reproduz vídeo no youtube.
- [ ] **3.2 Submissão de Formulário:** Consegue preencher campos de texto e submeter um formulário.
- [ ] **3.3 Download de Arquivo:** Consegue baixar um arquivo pdf e acessá-lo.
- [ ] **3.4 Zoom:** A função de zoom funciona corretamente.
- [ ] **3.5 Interação com Dropdown:** Menus dropdown em sites funcionam.

**4. Recursos Nativos do Navegador (5 Itens)**
- [ ] **4.1 Instalação de Extensão:** Consegue instalar "uBlock Origin" da loja de addons. (Desktop/Android).
- [ ] **4.2 Ferramenta de Captura:** A ferramenta nativa de captura de tela do Firefox funciona.
- [ ] **4.3 Gerenciador de Favoritos:** Consegue adicionar, nomear e deletar um favorito.
- [ ] **4.4 Gerenciador de Histórico:** Consegue visualizar e pesquisar o histórico.
- [ ] **4.5 Limpar Dados:** A função "Limpar dados de navegação" funciona.

---

## 4. Referências

* BROWSERSTACK. **Cross Browser Compatibility Testing Checklist**. Disponível em: <https://www.browserstack.com/guide/cross-browser-compatibility-testing-checklist>. Acesso em: 16 nov. 2025.
* MOZILLA. **Firefox browser features**. Disponível em: <https://www.firefox.com/en-US/features/>. Acesso em: 16 nov. 2025.
* TESTSIGMA. **Cross Browser Testing Checklist: The Do’s and Dont’s**. Disponível em: <https://testsigma.com/blog/cross-browser-testing-checklist/>. Acesso em: 16 nov. 2025.

---

## 5. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do template do checklist M2.1 | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 17/11/2025 | | |
| 1.1 | Adição da Seção 2 (Metodologia de Execução) | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 17/11/2025 | | |
