# Resultados da Execução da Avaliação

## Plataforma Linux

## 1. Eficiência

### M1.1 - Consumo de RAM:

Para essa métrica, foi evitado faze vídeo, pois o OBS estava consumindo mais RAM durante a gravação, o que prejudicaria a medição real do consumo de memória.

**Cenário de Carga Leve**

![Imagem 1](/assets/linux_assets/ram_leve.png)

- Totalizando um consumo médio de 1.979 MB.

**Cenário de Carga Pesada**

![Imagem 2](/assets/linux_assets/ram_peasdo.png)

- Totalizando um consumo médio de 6.770 MB.

---

### M1.2 - Tempo de Carga (LCP):

A seguir, tem um vídeo mostrando a coleta da métrica 1.2, rodando o comando javascript no console de cada página listada na seção [2.4 Lista de Sites Padronizados](../fase3/fase3.md#24-lista-de-sites-padronizados) da [Fase 3](../fase3/fase3.md)

**Evidência de Execução (Vídeo):** [LCP](https://youtu.be/myw58ekH-ys)




Lista dos sites e suas respectivas LCPs em milissegundos:

1 - Youtube: 2012ms

2 - Amazon: 2326ms

3 - Facebook: 1301ms

5 - G1 Globo: 476ms

6 - Wikipedia: 834ms

4 - Mercado livre: 925ms

7 - Twitch: 1178ms

8 - Reddit: 818ms

9 - Magazine Luiza: 1538ms

10 - X: 3679ms

Total = 15,087s

Média = 15,087/10 = 1,509s


---

### M1.3 - Benchmarks:

**Evidência de Execução do speedometer 3.0:** [Assistir Benchmarks no YouTube](https://youtu.be/V0c8PsPOvjc)

#### Speedometer 3.0

**Teste 1 (11.1)**
![Resultado 1](/assets/linux_assets/speedometer1.png)
![Detalhe 1](/assets/linux_assets/detalhe1.png)


**Teste 2 (11.3)**
![Resultado 2](/assets/linux_assets/speedometer2.png)
![Detalhe 2](/assets/linux_assets/detalhe2.png)


**Teste 3 (11.2)**
![Resultado 3](/assets/linux_assets/speedometer3.png)
![Detalhe 3](/assets/linux_assets/detalhe3.png)


- **Pontuação Representativa (Mediana): 11.2**

#### JetStream 2

**Evidência de Execução do JetStream 2:** [Assistir Benchmarks no YouTube]()

**Teste 1 (93.799)**
![JetStream 1](/assets/linux_assets/jetstream1.png)

**Teste 2 (114.774)**
![JetStream 2](/assets/linux_assets/jetstream2.png)

**Teste 3 (114.929)**
![JetStream 3](/assets/linux_assets/jetstream3.png)

- **Pontuação Representativa (Mediana): 114.774**

---

## 2. Portabilidade

### M2.1 - Paridade Funcional:

#### 3. Checklist

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Linux
**Executor:** Lucas Mendonça Arruda


#### Total: 20/20

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

**3. Interação com Conteúdo Web (5 Itens)**
- [OK] **3.1 Reprodução de Mídia:** Reproduz vídeo no youtube.
- [OK] **3.2 Submissão de Formulário:** Consegue preencher campos de texto e submeter um formulário.
- [OK] **3.3 Download de Arquivo:** Consegue baixar um arquivo pdf e acessá-lo.
- [OK] **3.4 Zoom:** A função de zoom funciona corretamente.
- [OK] **3.5 Interação com Dropdown:** Menus dropdown em sites funcionam.
**Total 5/5**

**4. Recursos Nativos do Navegador (5 Itens)**
- [OK] **4.1 Instalação de Extensão:** Consegue instalar "uBlock Origin" da loja de addons. (Desktop/Android).
- [OK] **4.2 Ferramenta de Captura:** A ferramenta nativa de captura de tela do Firefox funciona.
- [OK] **4.3 Gerenciador de Favoritos:** Consegue adicionar, nomear e deletar um favorito.
- [OK] **4.4 Gerenciador de Histórico:** Consegue visualizar e pesquisar o histórico.
- [OK] **4.5 Limpar Dados:** A função "Limpar dados de navegação" funciona.
**Total 5/5**

---

## 3. Checklist (Template)

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Linux
**Executor:** Lucas Mendonça Arruda

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

Caso o item da checklist esteja em "N/a" ou "Falha" ele não aparecerá na tabela abaixo.
Abaixo estão as capturas de tela coletadas, organizadas por métrica.

#### Galeria M2.1 - Paridade Funcional

| Item do Checklist | Evidência Visual | Descrição |
| :--- | :---: | :--- |
| **1.1 Login / Perfil** | ![Conta](/assets/linux_assets/1-1_login.png) | Tela de conta Mozilla com usuário logado e sincronização ativa. |
| **1.2 Favoritos** | ![Favoritos]() | Lista de favoritos sincronizados exibida corretamente. |
| **1.3 Histórico** | ![Histórico](/assets/linux_assets/4-4_historico.png) | Histórico de navegação sincronizado |
| **2.1 Janela privativa** | ![privado](/assets/linux_assets/2-1_janela_privativa.png) | Tela mostrando aba em guia anônima no firefox. |
| **2.2 Reabrir aba fechada** | ![Aba fechada](/assets/linux_assets/2-2_reabir_aba.png) | Tela mostrando opção pra reabrir abas fechadas. |
| **2.3 Fixar aba** | ![Fixar aba](/assets/linux_assets/2-3_fixar_aba.png) | Tela mostrando uma aba fixada no firefox. |
| **2.4 Mover aba** | ![Mover aba](/assets/linux_assets/2-4_mover_aba.png) | Interface mostrando a aba movendo para uma nova janela |
| **2.5 Silenciar aba** | ![silenciar aba 1x](/assets/linux_assets/2-5_silenciar_audio.png),  ![silenciar aba 2](/assets/linux_assets/2-5-1_silenciar_audio2.png)| Aba silenciada. |
| **3.1 Mídia** | ![Youtube](/assets/linux_assets/3-1_video.png) | Reprodução de vídeo no YouTube. |
| **3.2 Submissão de formulário** | ![Formulário]() | Submissão de formulário |
| **3.3 Download** | ![Download](/assets/linux_assets/3-3_baixar_pdf.png) | Notificação visual de download de imagem. |
| **3.4 Zoom** | ![Zoom](/assets/linux_assets/2.3-3_Zoom.png) | Interface mostrando zoom. |
| **3.5 Dropdown** | ![Busca](/assets/linux_assets/3-5_dropdown.png) | Imagem contendo o dropdown do github. |
| **4.1 Extensões** | ![Addons](/assets/linux_assets/4-1_ublock.png) | Instalação da extensão uBlock Origin via menu de complementos. |
| **4.2 Captura de tela** | ![Captura](/assets/linux_assets/4-2_captura.png) | Sistema de captura de tela nativa do Firefox. |
| **4.3 Gerenciador de favoritos** | ![Gerenciador de favoritos 1](/assets/linux_assets/4-3_gerenciar_favoritos.png), ![Gerenciador de favoritos 2](/assets/linux_assets/4-3_gerenciar_favoritos2.png) | Tela mostrando opção de nomear, ver e excluir os favotitos |
| **4.4 Gerenciador de histórico** | ![Gerenciador de histórico](/assets/linux_assets/4-4_gerenciador_historico.png) | Sistema mostrando o histórico com a ferramenta de pesquisa |
| **4.5 Limpar Dados** | ![Limpeza](/assets/linux_assets/4-5_limpar_dados.png) | Pop-up nativo para seleção de intervalo de limpeza de histórico. |


#### Galeria M2.2 - Conformidade da UI

| Item do Checklist | Evidência Visual | Descrição |
| :--- | :---: | :--- |
| **1.1 Controle de janela** | ![Janela](/assets/linux_assets/2.1-1controle_janela.png) | O controle de janela do firefox é parecido com o do linux. |
| **1.2 Menu Contexto** | ![Contexto](/assets/linux_assets/2.1-2_toque_direito.png), ![Contexto2](/assets/linux_assets/2.1-2-1_toque_direito2.png) | Menu de contexto ao pressionar link. |
| **1.3 Renderização de fonte** | ![Fonte](/assets/linux_assets/2.1-3_fonte.png) | O controle de janela do firefox é parecido com o do linux. |
| **1.4 Notificações** | ![NotifSistema1](/assets/linux_assets/2.1-4_notificacao.png) | Central de notificações do Android exibindo alertas do sistema. |
| **1.5 Alerta nativo** | ![Alerta](/assets/linux_assets/2.1-5_alerta_nativo.png) | Integração com o gerenciador de permissões nativo do Android. |
| **2.1 Renderização** | ![Mobile]() | Busca carregado com viewport correto para mobile. |
| **2.2 Redimensionamento** | ![Redimensionamento](/assets/linux_assets/2.2-3_redimensionamento.png) | Interface mostrando o redimensionamento do firefox. |
| **2.4 Barra Dinâmica** | ![Barra](/assets/linux_a/assets/linux_assets/2.2-4_barra_endereco.png) | Barra de endereço oculta automaticamente ao rolar a página. |
| **3.1 Tema do Sistema operacional** | ![Tema](/assets/linux_assets/2.3-1_tema_so.png) | Interface mostrando o Tema adaptável. |
| **3.2 Animações de tela** | ![Animação](/assets/linux_assets/2.3-2_animacao.png) | Interface mostrando a animação de carregar uma página no firefox |
| **3.3 Interação com trackpad** | ![Trackpad](/assets/linux_assets/2.3-3_Zoom.png) | Interface mostrando zoom utilizando trackpad |
| **3.5 Aparência de abas** | ![Abas]() | Interface mostrando as abas com bordas arredondadas e com ícones. |


---
