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



🧠 ML-CS — Machine Learning Credit Scoring
Autor: Davi Bezerra Fraga
O ML-CS (Machine Learning Credit Scoring) é um projeto de Machine Learning supervisionado desenvolvido para prever o score de crédito de clientes a partir de dados financeiros, demográficos e comportamentais estruturados.

# Desenvolver um sistema de prever scores de crédito com base em dados finaceiros e demográficos.
# Niveis Poor, Standard e Good
# 1. Importar as bibliotecas necessárias
import pandas as pd
# 2. Importar a Base de Dados de treinamento
tabela = pd.read_csv('tabelatreinamento.csv')
# 3. Analisar informações do banco de dados
display(tabela)
display(tabela.info())
id_cliente	mes	idade	profissao	salario_anual	num_contas	num_cartoes	juros_emprestimo	num_emprestimos	dias_atraso	...	idade_historico_credito	investimento_mensal	comportamento_pagamento	saldo_final_mes	score_credito	emprestimo_carro	emprestimo_casa	emprestimo_pessoal	emprestimo_credito	emprestimo_estudantil
0	3392	1	23.0	cientista	19114.12	3.0	4.0	3.0	4.0	3.0	...	265.0	21.465380	alto_gasto_pagamento_baixos	312.494089	Good	1	1	1	1	0
1	3392	2	23.0	cientista	19114.12	3.0	4.0	3.0	4.0	3.0	...	266.0	21.465380	baixo_gasto_pagamento_alto	284.629162	Good	1	1	1	1	0
2	3392	3	23.0	cientista	19114.12	3.0	4.0	3.0	4.0	3.0	...	267.0	21.465380	baixo_gasto_pagamento_medio	331.209863	Good	1	1	1	1	0
3	3392	4	23.0	cientista	19114.12	3.0	4.0	3.0	4.0	5.0	...	268.0	21.465380	baixo_gasto_pagamento_baixo	223.451310	Good	1	1	1	1	0
4	3392	5	23.0	cientista	19114.12	3.0	4.0	3.0	4.0	6.0	...	269.0	21.465380	alto_gasto_pagamento_medio	341.489231	Good	1	1	1	1	0
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
99995	37932	4	25.0	mecanico	39628.99	4.0	6.0	7.0	2.0	23.0	...	378.0	24.028477	alto_gasto_pagamento_alto	479.866228	Poor	1	0	0	0	1
99996	37932	5	25.0	mecanico	39628.99	4.0	6.0	7.0	2.0	18.0	...	379.0	24.028477	alto_gasto_pagamento_medio	496.651610	Poor	1	0	0	0	1
99997	37932	6	25.0	mecanico	39628.99	4.0	6.0	7.0	2.0	27.0	...	380.0	24.028477	alto_gasto_pagamento_alto	516.809083	Poor	1	0	0	0	1
99998	37932	7	25.0	mecanico	39628.99	4.0	6.0	7.0	2.0	20.0	...	381.0	24.028477	baixo_gasto_pagamento_alto	319.164979	Standard	1	0	0	0	1
99999	37932	8	25.0	mecanico	39628.99	4.0	6.0	7.0	2.0	18.0	...	382.0	24.028477	alto_gasto_pagamento_medio	393.673696	Poor	1	0	0	0	1
100000 rows × 25 columns

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 100000 entries, 0 to 99999
Data columns (total 25 columns):
 #   Column                    Non-Null Count   Dtype  
---  ------                    --------------   -----  
 0   id_cliente                100000 non-null  int64  
 1   mes                       100000 non-null  int64  
 2   idade                     100000 non-null  float64
 3   profissao                 100000 non-null  object 
 4   salario_anual             100000 non-null  float64
 5   num_contas                100000 non-null  float64
 6   num_cartoes               100000 non-null  float64
 7   juros_emprestimo          100000 non-null  float64
 8   num_emprestimos           100000 non-null  float64
 9   dias_atraso               100000 non-null  float64
 10  num_pagamentos_atrasados  100000 non-null  float64
 11  num_verificacoes_credito  100000 non-null  float64
 12  mix_credito               100000 non-null  object 
 13  divida_total              100000 non-null  float64
 14  taxa_uso_credito          100000 non-null  float64
 15  idade_historico_credito   100000 non-null  float64
 16  investimento_mensal       100000 non-null  float64
 17  comportamento_pagamento   100000 non-null  object 
 18  saldo_final_mes           100000 non-null  float64
 19  score_credito             100000 non-null  object 
 20  emprestimo_carro          100000 non-null  int64  
 21  emprestimo_casa           100000 non-null  int64  
 22  emprestimo_pessoal        100000 non-null  int64  
 23  emprestimo_credito        100000 non-null  int64  
 24  emprestimo_estudantil     100000 non-null  int64  
dtypes: float64(14), int64(7), object(4)
memory usage: 19.1+ MB
None
# 4. Filtra o Banco de dados para ML
# Transformar string [profissao, mix_credito, comportamento_pagamento] em números(Ml só trabalha com números)
from sklearn.preprocessing import LabelEncoder

codificador_profissao = LabelEncoder()
tabela["profissao"] = codificador_profissao.fit_transform(tabela["profissao"])

codificador_credito = LabelEncoder()
tabela["mix_credito"] = codificador_credito.fit_transform(tabela["mix_credito"])

codificador_pagamento = LabelEncoder()
tabela["comportamento_pagamento"] = codificador_pagamento.fit_transform(tabela["comportamento_pagamento"])
# separar os dados em treinamento e teste
y = tabela['score_credito']
x = tabela.drop(columns=['score_credito','id_cliente'])


from sklearn.model_selection import train_test_split

x_treino, x_teste, y_treino, y_teste = train_test_split(x, y, test_size=0.3, random_state=1)
# 5. Importar a ML
from sklearn.ensemble import RandomForestClassifier
modelo_arvore = RandomForestClassifier()
# 6. Treinar a ML
modelo_arvore.fit(x_treino, y_treino)
RandomForestClassifier()
In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook.
On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.
# 7. Testar a eficiencia da ML
from sklearn.metrics import accuracy_score
previsao_arvore = modelo_arvore.predict(x_teste)
print('{:.2f}'.format(accuracy_score(y_teste, previsao_arvore)*100))
82.27
# 8. Indentificar componentes fundamentais na análise de dados
colunas = list(x_teste)
importancias = pd.DataFrame(index=colunas, data=modelo_arvore.feature_importances_)
importancias = importancias * 100
print(importancias)
                                  0
mes                        4.004829
idade                      4.231293
profissao                  3.256220
salario_anual              5.058106
num_contas                 3.379307
num_cartoes                4.235155
juros_emprestimo           8.075964
num_emprestimos            2.881479
dias_atraso                6.497473
num_pagamentos_atrasados   4.573434
num_verificacoes_credito   4.872490
mix_credito                8.438513
divida_total              11.752558
taxa_uso_credito           5.035504
idade_historico_credito    7.533083
investimento_mensal        4.821275
comportamento_pagamento    2.367059
saldo_final_mes            5.443775
emprestimo_carro           0.708394
emprestimo_casa            0.720070
emprestimo_pessoal         0.695861
emprestimo_credito         0.719409
emprestimo_estudantil      0.698747
# 9. Implantar a ML em um ambiente de produção
tabelanova = pd.read_csv('tabeladenovosclientes.csv')

codificador_profissao = LabelEncoder()
tabelanova["profissao"] = codificador_profissao.fit_transform(tabelanova["profissao"])
codificador_credito = LabelEncoder()
tabelanova["mix_credito"] = codificador_credito.fit_transform(tabelanova["mix_credito"])
codificador_pagamento = LabelEncoder()
tabelanova["comportamento_pagamento"] = codificador_pagamento.fit_transform(tabelanova["comportamento_pagamento"])

tabelanova = tabelanova.drop(columns=['id_cliente'])

previsao_arvore = modelo_arvore.predict(tabelanova)
print(previsao_arvore)
['Good' 'Standard' 'Poor' 'Standard' 'Poor' 'Standard' 'Poor' 'Standard'
 'Standard' 'Standard']
