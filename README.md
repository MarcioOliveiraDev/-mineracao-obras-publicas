# Modelo de Suporte à Decisão para Obras Públicas com Base em Mineração de Dados

Este repositório contém os artefatos do projeto final da disciplina **IN1144 - Mineração de Dados**, do Centro de Informática da Universidade Federal de Pernambuco (CIn-UFPE).

## 📋 Sobre o Projeto

O objetivo deste trabalho é desenvolver um modelo preditivo capaz de identificar obras públicas com alta probabilidade de paralisação antes mesmo do início da execução física. O estudo utiliza dados governamentais para auxiliar na tomada de decisão e mitigar o desperdício de recursos públicos.

**Problema:** Paralisação de obras públicas financiadas com recursos federais.
**Abordagem:** Classificação supervisionada para prever a classe `target_vai_paralisar`.

## 👥 Autores (Grupo Obras)

* Anderson Felinto
* Bezaleel Lira da Silva
* Marcio Oliveira de Brito
* Saulo Henrique do Nascimento
* Thaylor Vieira Martins

## 🛠 Tecnologias e Ferramentas

* **KNIME Analytics Platform:** Para todo o fluxo de ETL, mineração e avaliação.
* **Algoritmos:** Regressão Logística, Árvore de Decisão (Decision Tree), JRip (Indução de Regras) e PART.

## 📊 Metodologia e Dados

As bases de dados foram extraídas de fontes públicas (Agosto/22 a Abril/25):
1.  **TCU (Tribunal de Contas da União):** Dados principais das obras.
2.  **Portal da Transparência:** Dados de convênios (vigência).
3.  **IBGE:** Dados geográficos e biomas.

### Principais Descobertas
O modelo baseado em **Indução de Regras (JRip)** apresentou o melhor desempenho para a classe minoritária (obras que paralisam), fornecendo regras interpretáveis para gestão, como por exemplo:

> SE `duração_vigência` >= 67 meses E `execução_financeira` entre 9.6% e 37.6% -> Alta chance de paralisação (Lift 2.408).

## 📂 Estrutura do Repositório

* `docs/`: Artigo completo (PDF) e Apresentação (PPTX).
* `workflow/`: Arquivo `.knwf` exportado do KNIME para reprodução do experimento.
* `results/`: Planilhas com análise univariada, comparação de métricas e imagens das árvores de decisão geradas.

## 🚀 Como executar (Reproducibilidade)

1.  Instale o [KNIME Analytics Platform](https://www.knime.com/).
2.  Baixe o arquivo `.knwf` localizado na pasta `workflow/` deste repositório.
3.  No KNIME, vá em `File` > `Import KNIME Workflow...` e selecione o arquivo baixado.
4.  Caso necessário, reconecte os nós de leitura de arquivo (`Excel Reader` ou `CSV Reader`) apontando para os dados na pasta `data/`.

---
*Projeto desenvolvido no semestre 2025.1*
