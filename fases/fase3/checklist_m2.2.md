# Checklist M2.2: Conformidade da UI

## 1. Introdução

Este documento detalha o checklist de 15 itens para a métrica M2.2 (Conformidade da UI), conforme definido no [Plano de Execução da Fase 3](fase3.md#25-checklists-de-verificação-para-portabilidade-m2).

O objetivo é verificar se a interface do Firefox se adapta corretamente às convenções visuais e de interação de cada sistema operacional.

## 2. Metodologia de Execução

Cada executor deve criar uma cópia deste documento para seu respectivo ambiente.

O processo consiste em verificar item por item se a interface se adapta e respeita as convenções do sistema operacional.

### Critérios de Pontuação
* **OK:** O elemento da UI é renderizado corretamente e é consistente com o SO ou com o design Proton.
* **N/A (Não Aplicável):** A convenção não se aplica a este ambiente (ex: "Menus Nativos (macOS)" no Windows). Itens marcados como N/A não contam contra a pontuação final.
* **FALHA:** O elemento da UI apresenta um bug visual (renderização), de layout ou de interação.

### Registro de Resultados
Ao final, o executor deve somar o número total de itens marcados como 'OK' e registrar o total (ex: "14/15") na [Planilha Mestra](fase3.md#21-artefatos-de-coleta-e-divisão-de-tarefas). O link para o documento preenchido deve ser adicionado na coluna de evidências.

---

## 3. Checklist (Template)

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** *[Preencha: Windows / Linux / macOS / Android]*
**Executor:** *[Preencha seu nome]*

---

### Total: \_\_/15

**1. Convenções Nativas do SO (5 Itens)**
- [ ] **1.1 Controles de Janela:** (Desktop) Botões de Fechar, Minimizar e Maximizar seguem o padrão visual do SO (ex: "semáforo" no macOS, botões à direita no Windows/Linux).
- [ ] **1.2 Menus de Contexto:** O menu de clique-direito (ou toque longo) parece nativo do SO ou, pelo menos, é consistente com o resto da UI do Firefox.
- [ ] **1.3 Renderização de Fonte:** As fontes da UI do navegador (menus, barra de endereço) respeitam as configurações de renderização (ex: ClearType no Windows, anti-aliasing do macOS).
- [ ] **1.4 Notificações:** Notificações de sites (Web Push) são entregues através do sistema nativo de notificações do SO (Action Center, Notificações do macOS/Linux/Android).
- [ ] **1.5 Alertas/Prompts:** Caixas de diálogo (alertas JavaScript, prompts de senha) usam o estilo nativo do SO.

**2. Adaptabilidade e Layout (5 Itens)**
- [ ] **2.1 Renderização HiDPI (Retina):** (Desktop/Mobile) Ícones, texto e UI estão nítidos e sem borrões em telas de alta resolução.
- [ ] **2.2 Redimensionamento (Desktop):** A UI do navegador (barras de ferramentas, painéis) se reajusta corretamente ao redimensionar a janela.
- [ ] **2.3 Modo Paisagem (Mobile):** A UI se adapta corretamente ao girar o dispositivo para o modo paisagem, sem sobreposição de elementos.
- [ ] **2.4 Barra de Endereço:** A barra de endereço (megabar) se expande para sugestões sem cobrir conteúdo indevidamente.
- [ ] **2.5 Menus Nativos (macOS):** (macOS) O navegador utiliza a barra de menu global no topo da tela, em vez de uma barra de menu dentro da janela.

**3. Consistência Visual e Interação (5 Itens)**
- [ ] **3.1 Tema do SO:** O navegador alterna automaticamente entre o tema claro e escuro ao detectar a mudança no SO.
- [ ] **3.2 Animações da UI:** Animações (abrir nova aba, abrir menu) são fluidas e sem "engasgos" (jank).
- [ ] **3.3 Interação com Trackpad (Desktop):** O scroll de dois dedos e o gesto de "pinça para zoom" são suaves e responsivos.
- [ ] **3.4 Gestos Nativos (Mobile):** O gesto de "puxar para recarregar" (pull-to-refresh) funciona em páginas web.
- [ ] **3.5 Aparência de Abas:** As abas têm aparência e comportamento consistentes com o design "Proton" do Firefox em todas as plataformas.

---

## 4. Referências

* BROWSERSTACK. **UI Testing: A Detailed Guide**. Disponível em: <https://www.browserstack.com/guide/ui-testing-guide>. Acesso em: 16 nov. 2025.
* TESTIM.IO. **UI Testing: A Complete Beginner’s Guide With Examples**. Disponível em: <https://www.testim.io/blog/user-interface-testing/>. Acesso em: 16 nov. 2025.
* FREECODECAMP. **Cross-Browser Compatibility Testing – Best Practices for Web Developers**. Disponível em: <https://www.freecodecamp.org/news/cross-browser-compatibility-testing-best-practices-for-web-developers/>. Acesso em: 16 nov. 2025.

---

## 5. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do template do checklist M2.2 | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 17/11/2025 | | |
| 1.1 | Adição da metodologia | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 17/11/2025 | | |