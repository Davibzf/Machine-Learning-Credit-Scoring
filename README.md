# 🧠 ML-CS — Machine Learning Credit Scoring
# Autor: Davi Bezerra Fraga  

# Tecnologias: Python • Pandas • Scikit-learn • Jupyter Notebook

## 📌 Visão Geral

O **ML-CS (Machine Learning Credit Scoring)** é um projeto de **Machine Learning supervisionado** desenvolvido para **prever o score de crédito de clientes** a partir de dados financeiros, demográficos e comportamentais estruturados.

O objetivo é simular um **sistema de análise de risco de crédito**, seguindo boas práticas utilizadas por **bancos e fintechs**, com foco em **precisão, avaliação correta e interpretabilidade dos modelos**.

---

## 🎯 Objetivos do Projeto

* Prever o **score_credito** de clientes em (Poor, Standard e Good) 
* Analisar fatores que influenciam o risco de crédito
* Aplicar métricas adequadas para avaliação
* Explainable AI (XAI)

---

## 📊 Variáveis Utilizadas

### 🔹 Perfil do cliente

* `idade`
* `profissao`
* `salario_anual`

### 🔹 Relacionamento financeiro

* `num_contas`
* `num_cartoes`
* `idade_historico_credito`

### 🔹 Empréstimos e crédito

* `num_emprestimos`
* `juros_emprestimo`
* `emprestimo_carro`
* `emprestimo_casa`
* `emprestimo_pessoal`
* `emprestimo_credito`
* `emprestimo_estudantil`

### 🔹 Comportamento financeiro

* `dias_atraso`
* `comportamento_pagamento`
* `investimento_mensal`
* `saldo_final_mes`

🎯 **Variável alvo (target):**

* `score_credito`

> ⚠️ A variável `id_cliente` é utilizada apenas como identificador e não deve ser usada diretamente no treinamento do modelo.

---

## 🧠 Metodologia

* `1. Importar as bibliotecas necessárias`
* `2. Importar a Base de Dados de treinamento`
* `3. Analisar informações do banco de dados`
* `4. Filtra o Banco de dados para ML`
* `5. Importar a ML`
* `6. Treinar a ML`
* `7. Testar a eficiencia da ML`
* `8. Indentificar componentes fundamentais na análise de dados`
* `9. Implantar a ML em um ambiente de produção`
---

## 🤖 Modelos de Machine Learning

* Random Forest Regressor

---

## 📈 Métricas de Avaliação

### 🔹 Regressão

* MAE (Mean Absolute Error)
* RMSE (Root Mean Squared Error)
* R² (Coeficiente de Determinação)

### 🔹 Classificação (opcional)

* Accuracy
---

## 🔍 Explainable AI (XAI)

O projeto utiliza técnicas de **Explainable AI** para tornar as decisões do modelo interpretáveis, como:

* Importância das features
* SHAP values

Essas técnicas permitem entender **quais fatores mais impactam o score de crédito**, algo essencial em sistemas financeiros.

---

## 🛠 Tecnologias Utilizadas

* Python
* Pandas
* Scikit-learn
* Jupyter Notebook

---

## 🚀 Possíveis Aplicações

* Análise de risco de crédito
* Sistemas de decisão financeira
* Simulações para fintechs
* Projetos acadêmicos
* Portfólio em Data Science / Machine Learning

---

## ⚠️ Aviso Legal

Este projeto possui **fins educacionais e demonstrativos**. Não deve ser utilizado diretamente para decisões financeiras reais sem validações regulatórias, auditoria de modelos e conformidade legal.

---

## 👨‍💻 Autor

**Davi Bezerra Fraga**
Projeto desenvolvido para estudos em **Machine Learning aplicado a crédito e finanças**.

---

⭐ Se este projeto te ajudou, considere deixar uma estrela!
