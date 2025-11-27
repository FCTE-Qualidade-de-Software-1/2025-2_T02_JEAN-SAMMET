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

#### Total: 20/20

**1. Gerenciamento de Conta e Sincronização (5 Itens)**
- [OK] **1.1 Login:** Consegue fazer login em uma conta Firefox.
- [OK] **1.2 Sinc. Favoritos:** Favoritos adicionados em outro dispositivo aparecem.
- [OK] **1.3 Sinc. Histórico:** Sites visitados em outro dispositivo aparecem.
- [OK] **1.4 Sinc. Senhas:** Senhas salvas em outro dispositivo são preenchidas.
- [OK] **1.5 Logout:** Consegue desconectar a conta do navegador.

**2. Navegação e Gerenciamento de Abas (5 Itens)**
- [OK] **2.1 Modo Privado:** Consegue abrir uma aba de navegação privativa.
- [OK] **2.2 Reabrir Aba Fechada:** A função de reabrir aba fechada ou histórico recente está acessível.
- [OK] **2.3 Coleções/Fixar:** Consegue salvar abas em Coleções equivalente mobile ao Fixar.
- [OK] **2.4 Mover Aba:** Consegue enviar uma aba para outro dispositivo conectado ou reorganizar a grade.
- [OK] **2.5 Reprodução em 2º Plano:** O áudio continua tocando se minimizar o app.

**3. Interação com Conteúdo Web (5 Itens)**
- [OK] **3.1 Reprodução de Mídia:** Reproduz vídeo no YouTube/Twitch.
- [OK] **3.2 Submissão de Formulário:** Teclado virtual abre corretamente e submete formulários.
- [OK] **3.3 Download de Arquivo:** Consegue baixar um arquivo e notifica na barra de status.
- [OK] **3.4 Zoom:** O gesto de pinça para zoom funciona suavemente.
- [OK] **3.5 Menus Mobile:** Menus com três linhas horizontais de sites responsivos funcionam ao toque.

**4. Recursos Nativos do Navegador (5 Itens)**
- [OK] **4.1 Instalação de Extensão:** Consegue instalar extensões pelo menu de Add-ons.
- [OK] **4.2 Modo Leitura:** O ícone de modo leitura aparece em artigos compatíveis.
- [OK] **4.3 Gerenciador de Favoritos:** Consegue adicionar e editar favoritos na interface mobile.
- [OK] **4.4 Histórico:** Acesso ao histórico é intuitivo.
- [OK] **4.5 Limpar Dados:** Opção de "Limpar dados privativos" ao sair ou no menu.


### M2.2 - Conformidade da UI (Checklist)

**Instrução:** Preencha 'OK', 'N/A' ou 'FALHA'.

**Ambiente:** Android 14
**Executor:** Artur Mendonça Arruda

#### Total: 12/15

**1. Convenções Nativas do SO (5 Itens)**
- [FALHA] **1.1 Gestos de Navegação:** Suporta gestos do Android corretamente.
- [OK] **1.2 Menu de Contexto:** O toque longo em links abre um menu consistente com o Material Design.
- [N/A] **1.3 Teclado Virtual:** O teclado abre com o layout correto dependendo do campo.
- [FALHA] **1.4 Notificações:** Downloads e mídias aparecem na barra de notificações do Android.
- [OK] **1.5 Permissões:** Solicita permissões usando o pop-up nativo do Android.

**2. Adaptabilidade e Layout (5 Itens)**
- [OK] **2.1 Renderização Mobile:** Sites carregam a versão mobile por padrão.
- [OK] **2.2 Modo Paisagem:** A UI se adapta ao girar a tela.
- [OK] **2.3 Barra de Endereço Dinâmica:** A barra se esconde ao rolar a página para baixo e reaparece ao subir.
- [OK] **2.4 Modo Escuro:** O app respeita a configuração de Modo Escuro/Claro do Android.
- [OK] **2.5 Ícone Adaptativo:** O ícone do app na home screen segue o padrão do tema.

**3. Consistência Visual e Interação (5 Itens)**
- [OK] **3.1 Feedback Tátil:** Há feedback visual ou tátil ao tocar em botões.
- [OK] **3.2 Animações:** As transições de abas são fluidas.
- [OK] **3.3 Grid de Abas:** A visualização de abas abertas é organizada e legível.
- [OK] **3.4 Pull-to-refresh:** Puxar o topo da página para recarregar funciona.
- [OK] **3.5 Acessibilidade:** O tamanho da fonte do navegador respeita o zoom de texto do sistema Android.

Abaixo estão as capturas de tela coletadas, organizadas por métrica.

#### Galeria M2.1 - Paridade Funcional

| Item do Checklist | Evidência Visual | Descrição |
| :--- | :---: | :--- |
| **1.1 Login / Perfil** | ![Conta](/assets/checklist_android/prova1.png) | Tela de conta Mozilla com usuário logado e sincronização ativa. |
| **1.2 Favoritos** | ![Favoritos](/assets/checklist_android/prova2.png) | Lista de favoritos sincronizados exibida corretamente. |
| **1.3 Histórico** | ![Histórico](/assets/checklist_android/prova3.png) | Histórico de navegação acessível e organizado por data. |
| **2.3 Coleções** | ![Coleções](/assets/checklist_android/prova7.png) | Criação de coleção de abas, recurso exclusivo da versão mobile. |
| **2.5 2º Plano** | ![Notif](/assets/checklist_android/prova8.png) | Áudio reproduzindo em segundo plano com controle via notificação. |
| **3.1 Mídia** | ![Youtube](/assets/checklist_android/prova9.png) | Reprodução de vídeo em andamento no YouTube. |
| **3.3 Download** | ![Download](/assets/checklist_android/prova11.png) | Notificação visual de download de imagem concluído com sucesso. |
| **3.3 Download Efetuado** | ![Busca](/assets/checklist_android/prova10.png) | Imagem instalada. |
| **4.1 Extensões** | ![Addons](/assets/checklist_android/prova13.png) | Instalação da extensão uBlock Origin via menu de complementos. |
| **4.2 Modo Leitura** | ![Leitura](/assets/checklist_android/prova14.png) | Artigo carregado com ícone de Modo Leitura disponível na barra. |
| **4.5 Limpar Dados** | ![Limpeza](/assets/checklist_android/prova17.png) | Pop-up nativo para seleção de intervalo de limpeza de histórico. |
| **4.5 Privacidade** | ![Privacidade](/assets/checklist_android/prova19.png) | Configurações de privacidade e limpeza de dados (Referência). |
| **Config. de Sync** | ![Sync](/assets/checklist_android/prova4.png) | Painel de configurações mostrando opções de sincronização de dados. |
| **Menu Principal** | ![Menu](/assets/checklist_android/prova16.png) | Menu principal do Firefox com todas as opções acessíveis. |
| **Tela Inicial** | ![Home](/assets/checklist_android/prova6.png) | Home screen com atalhos, favoritos e barra de pesquisa. |

#### Galeria M2.2 - Conformidade da UI

| Item do Checklist | Evidência Visual | Descrição |
| :--- | :---: | :--- |
| **1.2 Menu Contexto** | ![Contexto](/assets/checklist_android/prova18.png) | Menu de contexto ao pressionar link. |
| **1.4 Notificações** | ![NotifSistema](/assets/checklist_android/prova20.png) | Central de notificações do Android exibindo alertas do sistema. |
| **1.5 Permissões** | ![Permissoes](/assets/checklist_android/prova21.png) | Integração com o gerenciador de permissões nativo do Android. |
| **2.1 Renderização** | ![Mobile](/assets/checklist_android/prova5.png) | Busca carregado com viewport correto para mobile. |
| **2.1 Renderização** | ![Wiki](/assets/checklist_android/prova12.png) | Renderização de fontes e layout na página inicial da Wikipédia. |
| **2.2 Modo Paisagem** | ![Paisagem](/assets/checklist_android/prova22.png) | Adaptação correta da interface ao virar a tela. |
| **2.3 Barra Dinâmica** | ![Barra](/assets/checklist_android/prova23.png) | Barra de endereço oculta automaticamente ao rolar a página. |
| **2.4 Modo Escuro (UI)** | ![FavUI](/assets/checklist_android/prova15.png) | Interface de gerenciamento de favoritos adaptada ao Tema Escuro. |
| **3.4 Pull-to-Refresh** | ![Recarregar](/assets/checklist_android/prova24.png) | Interface reagindo ao gesto de puxar para recarregar a página. |

## 3. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do documento e adição das coletas de dados das métricas | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 | | |
| 1.1 | Inclusão das evidências visuais do checklist | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 | | |