# 📊 Regressão 01 - Tarefa 02: Transformações em X e Y

Este projeto tem como objetivo explorar diferentes formas de modelar a variável de gorjetas (`tip`) no conjunto de dados `tips`, utilizando transformações nas variáveis independentes (X) e dependentes (Y) para melhorar o ajuste dos modelos de regressão.

## 🎯 Objetivo

- Investigar o impacto de transformações logarítmicas e polinomiais nas variáveis explicativas e dependentes.
- Melhorar o ajuste do modelo de regressão que relaciona o valor da gorjeta (`tip`) com o valor líquido da conta (`net_bill`).
- Comparar diferentes estratégias de modelagem usando métricas como **R²** e **RMSE**.
- Visualizar os modelos ajustados e interpretar seus coeficientes.

---

## 🗂️ Dados Utilizados

- Dataset: `tips` (carregado diretamente via seaborn).
- Variáveis criadas:
  - `net_bill` = `total_bill` - `tip`
  - `tip_pct` = `tip` / `net_bill`
  - `log_net_bill`, `log_tip_pct`, `log_total_bill`

---

## ⚙️ Principais Etapas

### 1. Regressão linear simples: `tip` ~ `net_bill`
- Modelo base simples.
- Coeficiente de determinação (R²): **~0.29**
- Transformação aplicada: nenhuma.

### 2. Regressão com transformação logarítmica: `tip` ~ `log(net_bill)`
- Aplicação do log na variável explicativa.
- R²: **~0.29** (mesmo do modelo anterior, sem ganho evidente).

### 3. Regressão de `tip_pct` ~ `log(net_bill)`
- Análise da porcentagem da gorjeta.
- Boa explicação da variação percentual.
- Visualização da curva suavizada com transformação.

### 4. Modelo polinomial de 2º grau: `tip` ~ `total_bill + total_bill²`
- Introdução de termo quadrático.
- R²: **~0.457**
- Não apresentou melhora significativa sobre o modelo linear simples.

### 5. Regressão com log da variável dependente: `log(tip)` ~ `total_bill`
- Transformação apenas em Y.
- R² ajustado: **~0.42**

### 6. Regressão log-log: `log(tip)` ~ `log(total_bill)`
- **Melhor ajuste** entre os modelos.
- R²: **~0.462**
- Permite interpretação em termos de elasticidade.
- **Modelo preferido** por explicar ~46% da variância com boa linearidade.

---

## 📈 Visualizações

- Gráficos de dispersão com curvas de regressão ajustadas.
- Comparação entre modelos lineares, logarítmicos e polinomiais.
- Avaliação de resíduos e melhoria no ajuste com transformações.

---

## 📌 Conclusão

O modelo com **log(tip_pct) em função de log(net_bill)** apresentou o melhor desempenho dentre os testados, com um R² de **~0.46**, indicando que aproximadamente 46% da variação da porcentagem da gorjeta pode ser explicada pelo log do valor líquido da conta.

### 🔎 Motivos do bom desempenho do modelo log-log:
- Transformações logarítmicas ajudam a **linearizar relações não lineares**.
- Redução do impacto de **outliers** e **heterocedasticidade**.
- A variável `tip_pct` representa uma **proporção**, que se comporta melhor quando transformada em log.

---

## 🛠️ Tecnologias Utilizadas

- Python 🐍
- Bibliotecas:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `statsmodels`
  - `sklearn`

---

## 📚 Referências

- Curso de Regressão Linear (EBAC)
- Documentação do seaborn: https://seaborn.pydata.org/
- StatsModels Documentation: https://www.statsmodels.org/



