# Guia Técnico de Coleta: Android

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsável:** Artur Mendonça Arruda
**Data:** 23/11/2025
**Versão:** 1.2

## 1. Objetivo

Este documento detalha os procedimentos técnicos para a configuração do ambiente ADB, conhecido como Android Debug Bridge, e a execução dos comandos para coleta de todas as métricas definidas na Fase 3. Isso inclui as métricas de Eficiência como RAM, LCP e Benchmarks, além das métricas de Portabilidade, utilizando o Mozilla Firefox em dispositivos com Android 14.

## 2. Pré-requisitos e Configuração Inicial

Para executar as coletas da métrica M1.1 de RAM e M1.2 de LCP, é necessário configurar a comunicação avançada entre o PC e o Celular.

### 2.1. No Dispositivo Android

1.  Acesse as **Configurações** e entre em **Sobre o telefone**.
2.  Toque 7 vezes seguidas em **"Número da versão"** ou **"Número da compilação"** até aparecer a mensagem confirmando que você agora é um desenvolvedor.
3.  Volte para **Configurações**, acesse **Sistema** e entre em **Opções do Desenvolvedor**.
4.  Ative a chave **"Depuração USB"**.
5.  **Configuração do Firefox:**
    * Abra o Firefox no celular.
    * Vá em **Configurações** e depois em **Sobre o Firefox**.
    * Toque 5 vezes no logotipo do Firefox até ativar o Menu de Depuração.
    * Volte para a tela principal de Configurações do Firefox, encontre a opção **"Depuração USB"** e ative-a.

### 2.2. No Computador

1.  Baixe o **SDK Platform-Tools** oficial do site do Android Developers.
2.  Extraia a pasta `platform-tools` em um local de fácil acesso.
3.  Abra o terminal dentro desta pasta.
4.  Certifique-se de ter o **Firefox Desktop** instalado no PC, pois ele é necessário para a métrica M1.2.
5.  Conecte o celular via USB.
6.  No terminal, digite `adb devices`.
      * *Atenção:* Olhe para a tela do celular e autorize a conexão marcando a opção **"Sempre permitir"**.

---

## 3. Procedimento de Coleta: Eficiência (M1)

### 3.1. Métrica M1.1 - Consumo de Memória RAM

**Ferramenta:** Terminal do Computador via adb shell.

1.  **Preparação:**
    * Abra o Firefox no celular.
    * Prepare o cenário, sendo Carga Leve com 10 abas leves ou Carga Pesada com 10 abas padronizadas.
    * Aguarde 60 segundos para estabilização sem tocar na tela.

2.  **Execução:**
    * No terminal do PC, execute o comando abaixo:
    ```bash
    adb shell dumpsys meminfo org.mozilla.firefox
    ```

3.  **Registro:**
    * Procure a seção identificada como **"App Summary"**.
    * Localize a linha **TOTAL** e a coluna **Pss** em Kilobytes.
    * Divida o valor por 1024 para obter o resultado em Megabytes.
    * Registre na Planilha Mestra.

### 3.2. Métrica M1.2 - Tempo de Carga (LCP)

**Ferramenta:** Firefox Desktop usando Depuração Remota via USB.

1.  **Preparação:**
    * Conecte o celular ao PC via USB.
    * No PC, abra o Firefox e digite na barra de endereço o comando `about:debugging`.
    * Na barra lateral esquerda, clique em **"Este Firefox"**. Dependendo da versão, pode aparecer o nome do seu dispositivo USB listado.
    * Clique em **"Conectar"** ao lado do seu dispositivo Android.

2.  **Execução:**
    * Deve-se repetir este passo para os 10 sites padronizados.
    * No celular, abra um dos sites da lista, como por exemplo o `youtube.com`.
    * No PC, na tela de depuração, localize a aba aberta e clique em **"Inspecionar"**.
    * Na nova janela que abrir, vá para a aba **Console**.
    * Cole e execute o seguinte código JavaScript:
    ```javascript
    const observer = new PerformanceObserver((list) => {
      const entries = list.getEntries();
      const lastEntry = entries[entries.length - 1];
      console.log("LCP:", lastEntry.startTime);
    });
    observer.observe({ type: "largest-contentful-paint", buffered: true });
    ```
    * *Nota:* Se o Firefox bloquear a colagem, digite `permitir colar` ou `allow pasting` e tente novamente.

3.  **Registro:**
    * Anote o valor retornado em milissegundos.
    * Tire um print da tela do PC mostrando o código e o resultado.

### 3.3. Métrica M1.3 - Benchmarks

**Ferramenta:** Navegador do Celular acessando os sites BrowserBench.

**Regras de Ouro:**
* Feche todos os outros aplicativos.
* Não toque na tela durante o teste.
* Garanta que o celular não está em modo de economia de energia.

1.  **Speedometer 3.0:**
    * Acesse o site `https://browserbench.org/Speedometer3.0/`.
    * Execute o teste 3 vezes, reiniciando o navegador entre cada teste.
    * Tire print do resultado final de cada execução.
    * Registre a **Mediana**, que é o valor do meio, na planilha.

2.  **JetStream 2:**
    * Acesse o site `https://browserbench.org/JetStream/`.
    * Execute o teste 3 vezes, reiniciando o navegador entre cada teste.
    * Tire print do resultado final.
    * Registre a **Mediana** na planilha.

---

## 4. Procedimento de Coleta: Portabilidade (M2)

### 4.1. Checklists Manuais M2.1 e M2.2

1.  Baixe os modelos de checklist definidos na Fase 3.
2.  Utilize o Firefox no Android para verificar manualmente cada item da lista.
3.  Preencha com:
    * **[OK]** se o recurso funciona ou existe.
    * **[FALHA]** se não funciona ou apresenta erro.
    * **[N/A]** se não se aplica ao contexto mobile.
4.  Registre a contagem final na Planilha Mestra e salve os arquivos Markdown preenchidos como evidência.

---

## 5. Solução de Problemas

* **Erro indicando dispositivo não autorizado no ADB:**
    * Desconecte o cabo, revogue as autorizações USB nas opções de desenvolvedor do celular e conecte novamente, aceitando o pop-up na tela do celular.
* **Firefox Desktop não encontra o celular na depuração:**
    * Verifique se a opção "Depuração USB" está ativada **dentro das configurações do próprio aplicativo Firefox no Android**, além das configurações do sistema.
* **Erro ao colar código no Console:**
    * O Firefox possui proteção contra Self-XSS. Digite `permitir colar` no console e dê Enter para desbloquear.

---

## 6. Histórico de Versões

| Versão | Descrição | Autor(es) | Data |
| :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico e detalhamento do ADB | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 |
| 1.1 | Troca de responsável e correção de hyperlink errado | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 |
| 1.2 | Inclusão dos procedimentos para LCP, Benchmarks e Checklists | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 27/11/2025 |