# Resultados da Execução da Avaliação

## Plataforma Windows (Coleta 1)

## 1. Eficiência

### M1.1 - Consumo de RAM:

**Cenário de Carga Leve**

![Imagem 1](/assets/RAM-Leve.png)

- Totalizando um consumo médio de 2.763,1 MB.

**Cenário de Carga Pesada**

![Imagem 2](/assets/RAM-Pesada.png)

- Totalizando um consumo médio de 5.954,2 MB.

---

### M1.2 - Tempo de Carga (LCP):

![Imagem 3](/assets/LCP-Geral.jpg)

- Resultando em uma média do tempo do LCP de 1,41 segundos.

---

### M1.3 - Benchmarks:

**Speedometer3.0**

![Imagem 4](/assets/Speedometer.png)

![Imagem 5](/assets/Speedometer2.png)

![Imagem 6](/assets/Speedometer3.png)

**JetStream2**

![Imagem 7](/assets/JetStream.png)

![Imagem 8](/assets/JetStream2.png)

![Imagem 9](/assets/JetStream3.png)

- Nos Execução da Avaliação de **Eficiência** na plataforma Windows não foram feitas gravações, pois as gravações estavam influenciando nos resultados.

---

## 2. Portabilidade

### M2.1 - Paridade Funcional:

#### 3. Checklist

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Windows
**Executor:** Rodrigo M.

#### Total: 19/19

**1. Gerenciamento de Conta e Sincronização (5 Itens)**
- [OK] **1.1 Login:** Consegue fazer login em uma conta Firefox.
- [OK] **1.2 Sinc. Favoritos:** Favoritos adicionados em outro dispositivo aparecem.
- [OK] **1.3 Sinc. Histórico:** Sites visitados em outro dispositivo aparecem.
- [OK] **1.4 Sinc. Senhas:** Senhas salvas em outro dispositivo são preenchidas.
- [OK] **1.5 Logout:** Consegue desconectar a conta do navegador.
**Total 5/5**

**2. Navegação e Gerenciamento de Abas (5 Itens)**
- [OK] **2.1 Modo Privado:** Consegue abrir uma janela/aba de navegação privativa.
- [OK] **2.2 Reabrir Aba Fechada:** A função "Reabrir aba fechada" está presente.
- [OK] **2.3 Fixar Aba:** Consegue "Fixar Aba".
- [OK] **2.4 Mover Aba:** Consegue arrastar uma aba para uma nova janela.
- [OK] **2.5 Mudo de Aba:** Consegue silenciar o áudio de uma aba específica.
**Total 5/5**

**3. Interação com Conteúdo Web (4 Itens)**
- [OK] **3.1 Reprodução de Mídia:** Reproduz vídeo no youtube.
- [OK] **3.2 Download de Arquivo:** Consegue baixar um arquivo e acessá-lo.
- [OK] **3.3 Zoom:** A função de zoom funciona corretamente.
- [OK] **3.4 Interação com Dropdown:** Menus dropdown em sites funcionam.
**Total 4/4**

**4. Recursos Nativos do Navegador (5 Itens)**
- [OK] **4.1 Instalação de Extensão:** Consegue instalar "uBlock Origin" da loja de addons. (Desktop/Android).
- [OK] **4.2 Ferramenta de Captura:** A ferramenta nativa de captura de tela do Firefox funciona.
- [OK] **4.3 Gerenciador de Favoritos:** Consegue adicionar, nomear e deletar um favorito.
- [OK] **4.4 Gerenciador de Histórico:** Consegue visualizar e pesquisar o histórico.
- [OK] **4.5 Limpar Dados:** A função "Limpar dados de navegação" funciona.
**Total 5/5**

---

### M2.2 - Conformidade da UI

#### 3. Checklist

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Windows
**Executor:** Rodrigo M.

### Total: 12/15

**1. Convenções Nativas do SO (5 Itens)**
- [OK] **1.1 Controles de Janela:** (Desktop) Botões de Fechar, Minimizar e Maximizar seguem o padrão visual do SO (ex: "semáforo" no macOS, botões à direita no Windows/Linux).
- [OK] **1.2 Menus de Contexto:** O menu de clique-direito (ou toque longo) parece nativo do SO ou, pelo menos, é consistente com o resto da UI do Firefox.
- [OK] **1.3 Renderização de Fonte:** As fontes da UI do navegador (menus, barra de endereço) respeitam as configurações de renderização (ex: ClearType no Windows, anti-aliasing do macOS).
- [OK] **1.4 Notificações:** Notificações de sites (Web Push) são entregues através do sistema nativo de notificações do SO (Action Center, Notificações do macOS/Linux/Android).
- [OK] **1.5 Alertas/Prompts:** Caixas de diálogo (alertas JavaScript, prompts de senha) usam o estilo nativo do SO.
**Total 5/5**

**2. Adaptabilidade e Layout (5 Itens)**
- [OK] **2.1 Renderização HiDPI (Retina):** (Desktop/Mobile) Ícones, texto e UI estão nítidos e sem borrões em telas de alta resolução.
- [OK] **2.2 Redimensionamento (Desktop):** A UI do navegador (barras de ferramentas, painéis) se reajusta corretamente ao redimensionar a janela.
- [N/A] **2.3 Modo Paisagem (Mobile):** A UI se adapta corretamente ao girar o dispositivo para o modo paisagem, sem sobreposição de elementos.
- [OK] **2.4 Barra de Endereço:** A barra de endereço (megabar) se expande para sugestões sem cobrir conteúdo indevidamente.
- [N/A] **2.5 Menus Nativos (macOS):** (macOS) O navegador utiliza a barra de menu global no topo da tela, em vez de uma barra de menu dentro da janela.
**Total 3/5**

**3. Consistência Visual e Interação (5 Itens)**
- [OK] **3.1 Tema do SO:** O navegador alterna automaticamente entre o tema claro e escuro ao detectar a mudança no SO.
- [OK] **3.2 Animações da UI:** Animações (abrir nova aba, abrir menu) são fluidas e sem "engasgos" (jank).
- [OK] **3.3 Interação com Trackpad (Desktop):** O scroll de dois dedos e o gesto de "pinça para zoom" são suaves e responsivos.
- [N/A] **3.4 Gestos Nativos (Mobile):** O gesto de "puxar para recarregar" (pull-to-refresh) funciona em páginas web.
- [OK] **3.5 Aparência de Abas:** As abas têm aparência e comportamento consistentes com o design "Proton" do Firefox em todas as plataformas.
**Total 4/5**

---

## 3. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do documento e adição das coletas de dados das métricas  | [Rodrigo Mattos de F. A. Bezerra](https://github.com/Rodrigomfab88) | 26/11/2025 | | |
