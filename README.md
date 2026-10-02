# Projeto Machine Learning - IDEB

Previsão de risco de evasão escolar no Ensino Médio utilizando Machine Learning. Análise baseada nos microdados do IDEB/INEP (via Base dos Dados) para identificar fatores críticos de abandono e apoiar ações preventivas em escolas.

## 📊 Módulo Atual: Análise de Dados (`feature/analise`)
Este módulo foca na **Análise Exploratória de Dados (EDA)**. 
**Sobre os Dados:** Esta análise utiliza a base `ideb_ensino_medio.csv`, que contém os indicadores e métricas do Índice de Desenvolvimento da Educação Básica (IDEB) direcionados ao Ensino Médio, permitindo avaliar o desempenho escolar e identificar fatores de risco de evasão.

**O que foi feito nesta etapa:**
- Extração e carregamento dos microdados.
- Limpeza e tratamento inicial das bases.
- Visualização de variáveis e identificação de fatores preliminares que influenciam a evasão.

## 🚀 Como executar a análise?
1. Clone este repositório para a sua máquina ou abra o notebook diretamente no Google Colab.
2. Instale as dependências necessárias executando:
   ```bash
   pip install -r requirements.txt
2.5. É recomendado ter o Python instalado.

3. Abra e execute o notebook `1_analise_exploratoria_evasao.ipynb`.

### ⚠️ Atenção aos Dados: O notebook está configurado para ler a base ideb_ensino_medio.csv a partir do Google Drive.

Se for rodar no Colab, faça o upload do arquivo ideb_ensino_medio.csv (disponível neste repositório) para a sua pasta no Drive e verifique se o caminho no código corresponde ao seu:
CAMINHO = '/content/drive/MyDrive/machine_learning/ideb_ensino_medio.csv'

Alternativamente, altere a variável CAMINHO no código para ler o arquivo localmente.

Execute as células do arquivo 1_analise_exploratoria_evasao.ipynb.
