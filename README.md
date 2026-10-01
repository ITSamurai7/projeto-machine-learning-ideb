# Projeto Machine Learning - IDEB

Previsão de risco de evasão escolar no Ensino Médio utilizando Machine Learning. Análise baseada nos microdados do IDEB/INEP (via Base dos Dados) para identificar fatores críticos de abandono e apoiar ações preventivas em escolas.

## 📊 Módulo Atual: Análise de Dados (`feature/analise`)
Este módulo foca na **Análise Exploratória de Dados (EDA)**. 

**O que foi feito nesta etapa:**
- Extração e carregamento dos microdados.
- Limpeza e tratamento inicial das bases.
- Visualização de variáveis e identificação de fatores preliminares que influenciam a evasão.

## 🚀 Como executar a análise?
1. Certifique-se de ter o Python instalado.
2. Instale as dependências do projeto:
   `pip install -r requirements.txt`
3. Abra e execute o notebook `1_analise_exploratoria_evasao.ipynb`.

## 🧪 Módulo: Protocolo Experimental e Baseline
Este módulo define **como os modelos serão avaliados** (protocolo experimental) e executa um **modelo de referência (baseline)** para prever o risco dos municípios, usando como métrica o recall da classe Alto Risco, justificado pelo custo do erro no domínio.

**O que foi feito nesta etapa:**
- **Preparação da base:** remoção dos registros com nota de Matemática ou rendimento ausentes (3.848 registros, 13,9%), pois a regra do alvo não pode ser avaliada neles. Restaram 23.921 registros, com 20,9% de Alto Risco.
- **Seleção de variáveis sem vazamento de dados:** ficam de fora as colunas que definem o alvo ou derivam dele (nota de Matemática, rendimento, aprovação, IDEB), as de valor único e os identificadores. Dois cenários foram avaliados:
  - **A (só contexto):** `ano`, `sigla_uf` e `populacao`.
  - **B (+ português):** o cenário A mais a nota de Língua Portuguesa, que funciona como limite superior de desempenho por ser muito correlacionada com a nota de Matemática.
- **Divisão treino/teste (80/20):** estratificada pelo alvo e **agrupada por município**, para que nenhum município apareça nos dois conjuntos. Semente fixa (`SEMENTE = 42`) para reprodutibilidade.
- **Métrica:** recall da classe Alto Risco (principal), com precisão, F2 e PR-AUC de apoio. Deixar de identificar um município em risco (falso negativo) é o erro mais custoso, e a acurácia foi descartada por causa do desbalanceamento das classes.
- **Baseline:** regressão logística com ponderação de classes, comparada a um classificador trivial (sempre "Estável"). Validação cruzada de 5 folds no treino e avaliação final única no teste.

- ## 🚀 Como executar o baseline?
1. Execute primeiro as etapas da EDA, pois o baseline usa a base e a variável `alerta_risco` criadas nelas.
2. Abra e execute o notebook `etapas-1_e_3_baseline.ipynb`, seguindo as células em ordem até a **Etapa 6** (seções 6.1 a 6.8).
