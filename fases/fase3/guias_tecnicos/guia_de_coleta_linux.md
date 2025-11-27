# Guia Técnico de Coleta: Linux (Ubuntu)

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsável:** Lucas Mendonça Arruda
**Data:** 23/11/2025
**Versão:** 1.0

## 1\. Objetivo

Este documento detalha os procedimentos técnicos para a coleta de métricas de consumo de memória RAM (M1.1) do Mozilla Firefox em ambiente **Linux (Ubuntu)**, utilizando ferramentas de terminal (`ps`, `awk` e `top`) para garantir precisão diante da arquitetura multiprocesso do navegador.

## 2\. Pré-requisitos

Para executar este guia, o responsável deve garantir:

  * **Software:** Mozilla Firefox Versão 143.0.3 instalada (preferencialmente versão `.deb` ou `tar.gz`, mas `snap` também é suportado).
  * **Terminal:** Acesso ao terminal padrão do sistema (Bash/Zsh).

## 3\. Procedimento de Coleta (Métrica M1.1)

### Passo 1: Preparação do Ambiente

1.  Inicie o Firefox.
2.  Prepare o cenário de teste conforme definido na [Fase 3](../fase3.md) (Carga Leve ou Carga Pesada).
3.  Aguarde 60 segundos para estabilização da memória.
4.  Abra o Terminal.

### Passo 2: Execução do Comando

Devido à arquitetura multiprocesso, o Firefox cria várias instâncias. O comando abaixo lista todos os processos associados ao Firefox, extrai o uso de memória residente (RSS) de cada um e calcula a soma total automaticamente.

Copie e cole o seguinte comando no terminal:

```bash
ps -C firefox -o rss= | awk '{sum+=$1} END {print sum/1024 " MB"}'
```

**Explicação técnica:**

  * `ps -C firefox`: Seleciona todos os processos com o nome exato "firefox".
  * `-o rss=`: Exibe apenas a coluna *Resident Set Size* (Memória Física em uso), sem cabeçalho.
  * `awk ...`: Itera sobre cada linha, soma os valores e divide por 1024 para converter de Kilobytes (KB) para Megabytes (MB).

### Passo 3: Registro

1.  O terminal retornará um valor único (ex: `1450.5 MB`).
2.  Arredonde para duas casas decimais, se necessário.
3.  Registre o valor na planilha oficial.
      * **Link:** [Planilha Mestra de Coleta de Dados (Google Sheets)](https://docs.google.com/spreadsheets/d/1pNws2Jl_TH-EQMOMho54TPvwczGSXf4ntVFK4Xa4p9Y/edit?usp=sharing)

-----

## 4\. Solução de Problemas 

  * **O comando retorna "0 MB" ou vazio:**
    Isso pode acontecer se o nome do binário for diferente (comum em algumas distros ou versões Nightly). Tente substituir `firefox` por `firefox-bin`:

    ```bash
    ps -C firefox-bin -o rss= | awk '{sum+=$1} END {print sum/1024 " MB"}'
    ```

  * **Método Alternativo (top):**
    Se o script falhar, use o `top`:

    1.  Execute `top -b -n 1 | grep firefox`.
    2.  Identifique a coluna `RES`.
    3.  Some manualmente os valores dos processos listados.

-----

## 5\. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico e script de automação `ps/awk` | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 | | |
| 1.1 | Correção de hyperlink errado | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 | | |