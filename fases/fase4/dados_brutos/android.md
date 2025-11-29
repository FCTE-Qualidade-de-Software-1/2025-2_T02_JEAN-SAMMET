# Resultados da Execução da Avaliação

## Plataforma Android

**Executor:** Artur Mendonça Arruda

## 1. Eficiência

### M1.1 - Consumo de RAM:

**Evidência de Execução (Vídeo):** [Assistir Coleta de RAM no YouTube](https://youtu.be/LwG7ybLhyFA)

**Cenário de Carga Leve**

![Evidência RAM Leve](/assets/m1.1_leve_qualidade.png)

- Totalizando um consumo médio de **221,569 MB**.

**Cenário de Carga Pesada**

![Evidência RAM Pesada](/assets/m1.1_pesado_qualidade.png)

- Totalizando um consumo médio de **293,515 MB**.

### M1.2 - Tempo de Carga (LCP):

**Evidência de Execução (Vídeo):** [Assistir Coleta de LCP no YouTube](https://youtu.be/GD2c-ZWF6jU)

**Evidências de Coleta (Amostragem dos 10 sites)**

<details>
  <summary>Clique para expandir as evidências dos 10 sites</summary>

  * **Amazon:** ![Amazon](/assets/m1.2_amazon.png)
  * **Facebook:** ![Facebook](/assets/m1.2_facebook.png)
  * **G1:** ![G1](/assets/m1.2_g1.png)
  * **Magazine Luiza:** ![Magalu](/assets/m1.2_magazine_luiza.png)
  * **Mercado Livre:** ![MercadoLivre](/assets/m1.2_mercado_livre.png)
  * **Reddit:** ![Reddit](/assets/m1.2_reddit.png)
  * **Twitch:** ![Twitch](/assets/m1.2_twitch.png)
  * **Twitter:** ![Twitter](/assets/m1.2_twitter.png)
  * **Wikipedia:** ![Wikipedia](/assets/m1.2_wikipedia.png)
  * **YouTube:** ![YouTube](/assets/m1.2_youtube.png)

</details>

- Resultando em uma média do tempo do LCP de **1,85 segundos**.

### M1.3 - Benchmarks:

**Evidência de Execução (Vídeo):** [Assistir Benchmarks no YouTube](https://youtu.be/QU0Z0jzR_Gw)

#### Speedometer 3.0

**Tentativa 1 (3.06)**
![Resultado 1](/assets/speedometer_resultado_1.png)
![Detalhes 1](/assets/speedometer_detalhes_1.png)

**Tentativa 2 (4.47)**
![Resultado 2](/assets/speedometer_resultado_2.png)
![Detalhes 2](/assets/speedometer_detalhes_2.png)

**Tentativa 3 (4.69)**
![Resultado 3](/assets/speedometer_resultado_3.png)
![Detalhes 3](/assets/speedometer_detalhes_3.png)

- **Pontuação Representativa (Mediana): 4.47**

#### JetStream 2

**Tentativa 1 (67.572)**
![JetStream 1](/assets/jetstream_resultado_1.png)

**Tentativa 2 (70.962)**
![JetStream 2](/assets/jetstream_resultado_2.png)

**Tentativa 3 (77.335)**
![JetStream 3](/assets/jetstream_resultado_3.png)

- **Pontuação Representativa (Mediana): 70.962**

## 2. Portabilidade

### M2.1 - Paridade Funcional:

#### 3. Checklist

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Android 14 (One UI)
**Executor:** Artur Mendonça Arruda

#### Total: 17/19

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
- [FALHA] **2.5 Mudo de Aba:** Consegue silenciar o áudio de uma aba específica.
**Total 4/5**

**3. Interação com Conteúdo Web (4 Itens)**
- [OK] **3.1 Reprodução de Mídia:** Reproduz vídeo no youtube.
- [OK] **3.2 Download de Arquivo:** Consegue baixar um arquivo e acessá-lo.
- [OK] **3.3 Zoom:** A função de zoom funciona corretamente.
- [OK] **3.4 Interação com Dropdown:** Menus dropdown em sites funcionam.
**Total 4/4**

**4. Recursos Nativos do Navegador (5 Itens)**
- [OK] **4.1 Instalação de Extensão:** Consegue instalar "uBlock Origin" da loja de addons. (Desktop/Android).
- [FALHA] **4.2 Ferramenta de Captura:** A ferramenta nativa de captura de tela do Firefox funciona.
- [OK] **4.3 Gerenciador de Favoritos:** Consegue adicionar, nomear e deletar um favorito.
- [OK] **4.4 Gerenciador de Histórico:** Consegue visualizar e pesquisar o histórico.
- [OK] **4.5 Limpar Dados:** A função "Limpar dados de navegação" funciona.
**Total 4/5**

#### Evidências Visuais M2.1

| Item do Checklist | Evidência Visual | Descrição |
| :--- | :---: | :--- |
| **1.1 Login** | ![Conta](/assets/checklist_android/prova1.png) | Tela de conta Mozilla com usuário logado. |
| **1.2 Sinc. Favoritos** | ![Favoritos](/assets/checklist_android/prova2.png) | Lista de favoritos sincronizados. |
| **1.3 Sinc. Histórico** | ![Histórico](/assets/checklist_android/prova3.png) | Histórico sincronizado e organizado. |
| **1.4 Sinc. Senhas** | ![Sync](/assets/checklist_android/prova31.png) | Configurações de sincronização ativa. |
| **1.5 Logout** | ![Logout](/assets/checklist_android/prova4.png) | Tela que mostra navegador sem conta qualquer conectada. |
| **2.1 Modo Privado** | ![Contexto](/assets/checklist_android/prova32.png) | Pesquisa utilizando modo privado. |
| **2.2 Reabrir Aba** | ![Histórico](/assets/checklist_android/prova33.png) | Opção "Abas fechadas recentemente". |
| **2.3 Fixar Aba** | ![Coleções](/assets/checklist_android/prova7.png) | Recurso Coleções equivalente ao mobile. |
| **2.4 Mover Aba** | ![MvAba](/assets/checklist_android/prova30.png) | Imagem que mostra aba sendo arrastada. |
| **3.1 Rep. Mídia** | ![Youtube](/assets/checklist_android/prova9.png) | Vídeo reproduzindo no YouTube. |
| **3.2 Download** | ![Download](/assets/checklist_android/prova10.png) | Notificação de download concluído. |
| **3.2 Download** | ![Download_feito](/assets/checklist_android/prova11.png) | Resultado do download de imagem. |
| **3.3 Zoom** | ![Zoom](/assets/checklist_android/prova12.png) | Notificação de download concluído. |
| **3.4 Interação com Dropdown** | ![Dropdown](/assets/checklist_android/prova25.png) | Notificação de download concluído. |
| **4.1 Instalação Ext.** | ![Addons](/assets/checklist_android/prova13.png) | Instalação do uBlock Origin. |
| **4.3 Ger. Favoritos** | ![FavUI](/assets/checklist_android/prova15.png) | Gerenciador de favoritos (UI). |
| **4.4 Ger. Histórico** | ![Histórico](/assets/checklist_android/prova3.png) | Interface de histórico. |
| **4.5 Limpar Dados** | ![Limpeza](/assets/checklist_android/prova17.png) | Pop-up para excluir histórico. |

### M2.2 - Conformidade da UI (Checklist)

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Android 14 (One UI)
**Executor:** Artur Mendonça Arruda

#### Total: 11/15

**1. Convenções Nativas do SO (5 Itens)**
- [N/A] **1.1 Controles de Janela:** (Desktop) Botões de Fechar, Minimizar e Maximizar seguem o padrão visual do SO (ex: "semáforo" no macOS, botões à direita no Windows/Linux).
- [OK] **1.2 Menus de Contexto:** O menu de clique-direito (ou toque longo) parece nativo do SO ou, pelo menos, é consistente com o resto da UI do Firefox.
- [OK] **1.3 Renderização de Fonte:** As fontes da UI do navegador (menus, barra de endereço) respeitam as configurações de renderização (ex: ClearType no Windows, anti-aliasing do macOS).
- [OK] **1.4 Notificações:** Notificações de sites (Web Push) são entregues através do sistema nativo de notificações do SO (Action Center, Notificações do macOS/Linux/Android).
- [OK] **1.5 Alertas/Prompts:** Caixas de diálogo (alertas JavaScript, prompts de senha) usam o estilo nativo do SO.

**2. Adaptabilidade e Layout (5 Itens)**
- [OK] **2.1 Renderização HiDPI (Retina):** (Desktop/Mobile) Ícones, texto e UI estão nítidos e sem borrões em telas de alta resolução.
- [N/A] **2.2 Redimensionamento (Desktop):** A UI do navegador (barras de ferramentas, painéis) se reajusta corretamente ao redimensionar a janela.
- [OK] **2.3 Modo Paisagem (Mobile):** A UI se adapta corretamente ao girar o dispositivo para o modo paisagem, sem sobreposição de elementos.
- [OK] **2.4 Barra de Endereço:** A barra de endereço (megabar) se expande para sugestões sem cobrir conteúdo indevidamente.
- [N/A] **2.5 Menus Nativos (macOS):** (macOS) O navegador utiliza a barra de menu global no topo da tela, em vez de uma barra de menu dentro da janela.

**3. Consistência Visual e Interação (5 Itens)**
- [OK] **3.1 Tema do SO:** O navegador alterna automaticamente entre o tema claro e escuro ao detectar a mudança no SO.
- [OK] **3.2 Animações da UI:** Animações (abrir nova aba, abrir menu) são fluidas e sem "engasgos" (jank).
- [N/A] **3.3 Interação com Trackpad (Desktop):** O scroll de dois dedos e o gesto de "pinça para zoom" são suaves e responsivos.
- [OK] **3.4 Gestos Nativos (Mobile):** O gesto de "puxar para recarregar" (pull-to-refresh) funciona em páginas web.
- [OK] **3.5 Aparência de Abas:** As abas têm aparência e comportamento consistentes com o design "Proton" do Firefox em todas as plataformas.

#### Evidências Visuais M2.2

| Item do Checklist | Evidência Visual | Descrição |
| :--- | :---: | :--- |
| **1.2 Menu Contexto** | ![Contexto](/assets/checklist_android/prova18.png) | Menu de contexto ao pressionar link. |
| **1.3 Renderização** | ![Leitura](/assets/checklist_android/prova14.png) | Renderização de fontes no modo leitura. |
| **1.3 Renderização** | ![Confirmacao](/assets/checklist_android/prova34.png) | Prova da fonte ser igual do aparelho. |
| **1.4 Notificações** | ![Notif](/assets/checklist_android/prova8.png) | Notificação nativa (Controle de Mídia). |
| **1.5 Alertas/Prompts** | ![Permissoes](/assets/checklist_android/prova21.png) | Prompt nativo de permissões. |
| **2.1 Renderização HiDPI** | ![Mobile](/assets/checklist_android/prova5.png) | Renderização nítida em alta resolução. |
| **2.1 Renderização HiDPI** | ![Wiki](/assets/checklist_android/prova12.png) | Layout e fontes na Wikipédia. |
| **2.3 Modo Paisagem** | ![Paisagem](/assets/checklist_android/prova22.png) | Interface adaptada à rotação da tela. |
| **2.4 Barra Endereço** | ![Barra](/assets/checklist_android/prova23.png) | Barra oculta superior ao rolar. |
| **3.1 Tema do SO** | ![TemaClaroApp](/assets/checklist_android/prova26.png) | Firefox adaptado ao tema claro do sistema. |
| **3.1 Tema do SO** | ![TemaClaroSys](/assets/checklist_android/prova27.png) | Configuração do sistema confirmando o tema claro ativo. |
| **3.1 Tema do SO** | ![TemaEscuroApp](/assets/checklist_android/prova29.png) | Firefox adaptado automaticamente ao tema escuro. |
| **3.1 Tema do SO** | ![TemaEscuroSys](/assets/checklist_android/prova28.png) | Configuração do sistema confirmando o tema escuro ativo. |
| **3.4 Gestos Nativos** | ![Recarregar](/assets/checklist_android/prova24.png) | Gesto "Pull-to-refresh". |
| **3.5 Aparência Abas** | ![Coleções](/assets/checklist_android/prova7.png) | Design de abas/coleções. |
| **Geral (Menu)** | ![Menu](/assets/checklist_android/prova16.png) | Menu principal e ícones. |
| **Geral (Home)** | ![Home](/assets/checklist_android/prova6.png) | Tela inicial e atalhos. |

## 3. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do documento e adição das coletas de dados das métricas | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 | | |
| 1.1 | Inclusão das evidências visuais do checklist | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 | | |
| 1.2 | Correção das imagens e do item 3.2 da métrica 2.1 | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 | | |