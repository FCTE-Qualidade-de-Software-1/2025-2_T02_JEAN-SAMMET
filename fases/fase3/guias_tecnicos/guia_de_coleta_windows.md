# Guia Técnico de Coleta: Windows 11

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsáveis:** Rodrigo Mattos de F. A. Bezerra e Nayra Silva Nery
**Data:** 23/11/2025
**Versão:** 1.0

## 1\. Objetivo

Este documento detalha os procedimentos técnicos para a coleta de métricas de consumo de memória RAM (M1.1) do Mozilla Firefox em ambiente **Windows 11**, utilizando a ferramenta nativa de monitoramento de performance `typeperf`.

## 2\. Pré-requisitos

Para executar este guia, o responsável deve garantir:

  * **Software:** Mozilla Firefox Versão 143.0.3 instalada.
  * **Permissões:** Acesso a uma conta com privilégios de **Administrador** (obrigatório para acesso aos contadores de performance).
  * **Terminal:** Prompt de Comando (CMD) ou PowerShell configurado.

## 3\. Procedimento de Coleta (Métrica M1.1)

### Passo 1: Preparação do Ambiente

1.  Inicie o Firefox.
2.  Prepare o cenário de teste conforme definido na [Fase 3](../fase3.md)(Carga Leve ou Carga Pesada).
3.  Aguarde 60 segundos para estabilização da memória.
4.  Abra o **Prompt de Comando (CMD)** como Administrador:
      * *Pressione a tecla `Win`, digite "CMD", clique com o botão direito e selecione "Executar como administrador".*

### Passo 2: Execução do Comando

Para capturar o consumo de memória, execute o comando abaixo. Ele busca todos os subprocessos do Firefox e extrai o "Working Set - Private" (Memória Física Privada) e o "Working Set" (Total).

```cmd
typeperf "\Process(firefox*)\Working Set - Private" "\Process(firefox*)\Working Set" -sc 1
```

**Parâmetros utilizados:**

  * `\Process(firefox*)`: Seleciona dinamicamente todas as instâncias ativas do processo Firefox (abas, renderizadores, extensões).
  * `-sc 1`: Define a contagem de amostras (*sample count*) para 1 (snapshot instantâneo).

### Passo 3: Interpretação e Registro

O terminal retornará uma saída em formato CSV (Comma Separated Values).

1.  **Soma dos Valores:** Como o Firefox utiliza arquitetura multiprocesso, o comando retornará múltiplos valores. O consumo real é a **soma** de todos os valores retornados na linha de dados.
      * *Dica:* Se houver muitos processos, copie a saída para o Excel para somar.
2.  **Registro:** Copie o valor total (em Bytes) e registre na planilha oficial.
      * **Link:** [Planilha Mestra de Coleta de Dados (Google Sheets)](https://docs.google.com/spreadsheets/d/1pNws2Jl_TH-EQMOMho54TPvwczGSXf4ntVFK4Xa4p9Y/edit?usp=sharing)

-----

## 4\. Solução de Problemas 

  * **Erro: "Interface não encontrada" ou "Contador inválido":**
    Isso pode ocorrer se o Windows estiver em português e não reconhecer os contadores em inglês. Tente substituir o comando por:
    ```cmd
    typeperf "\Processo(firefox*)\Conjunto de Trabalho - Particular" -sc 1
    ```
  * **Acesso Negado:**
    Certifique-se de que o terminal exibe "Administrador" na barra de título.

-----

## 5\. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico e definição dos comandos `typeperf` | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 | | |