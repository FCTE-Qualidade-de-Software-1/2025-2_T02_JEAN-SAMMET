# Guia Técnico de Coleta: macOS

**Artefato Vinculado:** [Fase 3: Plano de Execução da Avaliação](../fase3.md)
**Responsável:** João Filipe de Oliveira Souza
**Data:** 23/11/2025
**Versão:** 1.0

## 1\. Objetivo

Este documento detalha os procedimentos técnicos para a coleta de métricas de consumo de memória RAM (M1.1) do Mozilla Firefox em ambiente **macOS**, utilizando o **Monitor de Atividade** nativo para garantir a leitura correta da memória física em uso.

## 2\. Pré-requisitos

Para executar este guia, o responsável deve garantir:

  * **Software:** Mozilla Firefox Versão 143.0.3 instalada.
  * **Ferramenta:** Monitor de Atividade (Activity Monitor) — já instalado no macOS.

## 3\. Procedimento de Coleta (Métrica M1.1)

### Passo 1: Preparação do Ambiente

1.  Inicie o Firefox.
2.  Prepare o cenário de teste conforme definido na [Fase 3](../fase3.md) (Carga Leve ou Carga Pesada).
3.  Aguarde 60 segundos para estabilização.
4.  Abra o **Monitor de Atividade** (Command + Espaço \> Digite "Monitor de Atividade").

### Passo 2: Filtragem e Seleção

O Firefox no macOS utiliza múltiplos processos (Main, Web Content, GPU, Extension). Para medir o consumo total:

1.  Na barra superior do Monitor de Atividade, clique na aba **Memória**.
2.  No campo de busca (canto superior direito), digite: `firefox`.
3.  Certifique-se de que a visualização está mostrando todos os processos (Menu **Visualizar** \> **Todos os Processos**).
4.  Selecione **todas** as linhas listadas resultantes da busca (Clique na primeira linha, segure `Shift` e clique na última).

### Passo 3: Interpretação e Registro

Com todas as linhas do Firefox selecionadas, observe o painel inferior ou a soma das colunas.

1.  **Coluna Alvo:** Utilize a coluna **Memória** (que representa a Memória Real/Physical Footprint).
2.  **Cálculo:**
      * Se o Monitor de Atividade não exibir a soma automática da seleção no rodapé, some os valores dos 3 maiores processos listados (geralmente o "Firefox" principal e os maiores "CP Web Content").
      * *Alternativa via Terminal (Recomendada para precisão):* Se a soma manual for difícil, abra o Terminal e rode:
        ```zsh
        ps -A -o rss,comm | grep -i "firefox" | awk '{sum+=$1} END {print sum/1024 " MB"}'
        ```
3.  **Registro:** Insira o valor total (em MB) na planilha oficial.
      * **Link:** [Planilha Mestra de Coleta de Dados (Google Sheets)](https://docs.google.com/spreadsheets/d/1pNws2Jl_TH-EQMOMho54TPvwczGSXf4ntVFK4Xa4p9Y/edit?usp=sharing)

-----

## 4\. Solução de Problemas (Troubleshooting)

  * **Processos não aparecem:**
    Verifique se o filtro de busca está limpo antes de digitar "firefox" novamente e confirme se o menu **Visualizar** está em "Todos os Processos" e não "Meus Processos".
  * **Valores oscilando muito:**
    O macOS faz compressão de memória. Se a coluna "Memória Comprimida" estiver alta, considere registrar o valor de "Memória" + "Memória Comprimida" para uma visão mais justa do impacto no sistema, mas anote essa observação na planilha. Para este teste, o padrão é apenas a coluna **Memória**.

-----

## 5\. Histórico de Versões

| Versão | Descrição | Autor(es) | Data | Revisor(es) | Data de Revisão |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1.0 | Criação do guia técnico para Monitor de Atividade | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 23/11/2025 | | |
| 1.1 | Correção de hyperlink errado | [Artur Mendonça Arruda](https://github.com/ArtyMend07) | 26/11/2025 | | |