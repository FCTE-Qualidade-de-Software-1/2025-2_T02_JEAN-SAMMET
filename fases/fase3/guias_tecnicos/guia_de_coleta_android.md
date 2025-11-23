# Guia Técnico de Coleta: Android

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsável:** Rodrigo Mattos de F. A. Bezerra
**Data:** 23/11/2025
**Versão:** 1.0

## 1\. Objetivo

Este documento detalha os procedimentos técnicos para a configuração do ambiente ADB (*Android Debug Bridge*) e a execução dos comandos para coleta de métricas de consumo de memória RAM (M1.1) do Mozilla Firefox em dispositivos **Android 14**.

## 2\. Pré-requisitos e Configuração Inicial

Para executar este guia, é necessário configurar a comunicação entre o PC e o Celular.

### 2.1. No Dispositivo Android (Celular)

1.  Acesse **Configurações \> Sobre o telefone**.
2.  Toque 7 vezes seguidas em **"Número da versão"** (ou "Número da compilação") até aparecer a mensagem "Você agora é um desenvolvedor".
3.  Volte para **Configurações \> Sistema \> Opções do Desenvolvedor**.
4.  Ative a chave **"Depuração USB"** (USB Debugging).

### 2.2. No Computador (Windows/Linux/Mac)

1.  Baixe o **SDK Platform-Tools** oficial do site do [Android Developers](https://developer.android.com/tools/releases/platform-tools).
2.  Extraia a pasta `platform-tools` em um local de fácil acesso.
3.  Abra o terminal dentro desta pasta.
4.  Conecte o celular via USB.
5.  No terminal, digite `adb devices`.
      * *Atenção:* Olhe para a tela do celular e autorize a conexão ("Sempre permitir").

## 3\. Procedimento de Coleta (Métrica M1.1)

### Passo 1: Preparação do Ambiente

1.  Abra o Firefox no celular.
2.  Prepare o cenário de teste conforme definido na [Fase 3](https://www.google.com/search?q=../fase3.md%2323-cen%C3%A1rios-de-teste-efici%C3%AAncia---m1) (Carga Leve ou Carga Pesada).
3.  Aguarde 60 segundos para estabilização.

### Passo 2: Execução do Comando

No terminal do computador, execute o comando abaixo para extrair o relatório de memória específico do pacote do Firefox:

```bash
adb shell dumpsys meminfo org.mozilla.firefox
```

### Passo 3: Interpretação e Registro

O terminal exibirá um relatório extenso. Role até encontrar a seção **"App Summary"**.

Exemplo de saída:

```text
App Summary
                       Pss(KB)
                        ------
           Java Heap:    12345
         Native Heap:    67890
                Code:     2048
               Stack:       52
            Graphics:    15000
       Private Other:     5200
              System:     3000
    
               TOTAL:   105535       TOTAL SWAP PSS:       500
```

1.  **Valor Alvo:** Identifique o valor na coluna **Pss(KB)** correspondente à linha **TOTAL**.
      * *Nota:* O PSS (Proportional Set Size) é a métrica mais precisa para o uso real de RAM por um app no Android.
2.  **Conversão:** O valor está em Kilobytes (KB). Divida por 1024 para obter Megabytes (MB).
3.  **Registro:** Insira o valor convertido na planilha oficial.
      * **Link:** [Planilha Mestra de Coleta de Dados (Google Sheets)](https://docs.google.com/spreadsheets/d/1pNws2Jl_TH-EQMOMho54TPvwczGSXf4ntVFK4Xa4p9Y/edit?usp=sharing)

-----

## 4\. Solução de Problemas 

  * **Erro `device unauthorized`:**
    O computador não tem permissão. Desconecte o cabo USB, revogue as autorizações de depuração USB nas opções do desenvolvedor do celular e conecte novamente.
  * **Erro `No process found for: org.mozilla.firefox`:**
      * O Firefox pode estar fechado. Abra o app.
      * Você pode estar usando uma versão Beta ou Nightly. Tente alterar o nome do pacote no comando para:
          * Beta: `org.mozilla.firefox_beta`
          * Nightly: `org.mozilla.fenix`

-----

## 5\. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico e detalhamento do `adb dumpsys` | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 | | |