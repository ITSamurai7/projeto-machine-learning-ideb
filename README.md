# Projeto Machine Learning - IDEB

Previsão de risco de evasão escolar no Ensino Médio utilizando Machine Learning. Análise baseada nos microdados do IDEB/INEP (via Base dos Dados) para identificar fatores críticos de abandono e apoiar ações preventivas em escolas.

## 📊 Marco 1: Fluxo Consolidado (Dados, Pré-processamento e Baseline)
Este módulo contém a esteira completa inicial de dados, preparando o terreno para a modelagem preditiva avançada. O arquivo principal é o `01_fluxo_marco1_consolidado.ipynb`.

**O que foi desenvolvido nesta etapa:**
- **Parte 1 (Análise Exploratória):** Extração, limpeza inicial, criação da variável alvo (`alerta_risco`), visualização de distribuições, correlações e diagnóstico rigoroso de outliers (Regra de Tukey).
- **Parte 2 (Pré-processamento):** Documentação (Ficha Técnica), tratamento justificado de valores nulos (Tabela de Descartes), codificação de variáveis categóricas (`Dummy Variables`) e padronização de escalas (`StandardScaler`).
- **Parte 3 (Protocolo e Baseline):** Divisão dos dados em Treino (70%), Validação (15%) e Teste (15%) com `random_state=42` estrito (sem vazamento). Execução de um modelo de referência (Regressão Logística) avaliado prioritariamente pela métrica de **Revocação (Recall)**, visando minimizar os falsos negativos no contexto de evasão escolar.

## 🚀 Como executar o projeto?

1. Clone este repositório para a sua máquina ou abra o notebook diretamente no Google Colab.
2. Instale as dependências necessárias executando o comando abaixo no seu terminal:
   ```bash
   pip install -r requirements.txt
