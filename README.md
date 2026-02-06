🧠 ML-CS — Machine Learning Credit Scoring
👤 Autor: Davi Bezerra Fraga
🛠️ Tecnologias

Python 3.11.4 • Pandas • Scikit-learn • Jupyter Notebook

📌 Visão Geral

Este projeto implementa um modelo de Machine Learning supervisionado para Credit Scoring, com o objetivo de avaliar o risco de crédito de clientes e prever a probabilidade de inadimplência com base em dados financeiros, demográficos e comportamentais.

Os dados utilizados foram obtidos na plataforma Kaggle, amplamente reconhecida na comunidade de Data Science, tornando o projeto próximo de cenários reais utilizados por bancos e fintechs.

O foco é demonstrar um pipeline completo de Machine Learning, desde a preparação dos dados até a aplicação do modelo em novos clientes.

🎯 Objetivos do Projeto

📊 Automatizar a análise de risco de crédito

🧠 Utilizar Machine Learning para apoiar decisões financeiras

🔍 Identificar padrões relevantes nos dados

🚀 Demonstrar habilidades práticas em Data Science e ML

🔁 Pipeline de Machine Learning
1️⃣ Aquisição dos Dados

Dataset público extraído do Kaggle

Arquivos utilizados:

tabelatreinamento.csv — dados para treino do modelo

tabeladenovosclientes.csv — dados para simulação de novos clientes

2️⃣ Análise Exploratória dos Dados (EDA)

Análise da estrutura dos dados

Verificação de distribuições e padrões

Compreensão das variáveis relevantes para o score de crédito

3️⃣ Pré-processamento

Tratamento de variáveis categóricas

Codificação dos dados para uso em modelos supervisionados

Definição de features (variáveis independentes) e target (score de crédito)

4️⃣ Divisão dos Dados

Separação em treino (70%) e teste (30%)

Avaliação justa do desempenho do modelo

5️⃣ Modelagem

Treinamento de um Random Forest Classifier

Algoritmo escolhido pela robustez e bom desempenho em problemas de classificação

6️⃣ Avaliação do Modelo

Cálculo da acurácia no conjunto de teste

Análise do desempenho geral do modelo

7️⃣ Interpretação dos Resultados

Análise da importância das variáveis

Identificação dos fatores que mais influenciam o score de crédito

8️⃣ Aplicação em Novos Clientes

Uso do modelo treinado no arquivo tabeladenovosclientes.csv

Simulação de previsões em um cenário real de tomada de decisão

📈 Resultados

✔️ Modelo funcional para classificação de risco de crédito
✔️ Pipeline de Machine Learning organizado e reproduzível
✔️ Interpretação das variáveis mais relevantes
✔️ Aplicação prática em novos dados

Este projeto demonstra a capacidade de transformar dados brutos em insights acionáveis, habilidade essencial para áreas como Data Science, Machine Learning e Engenharia de Software.

📁 Estrutura do Repositório
├── ML-CS.ipynb                 # Notebook principal do projeto
├── tabelatreinamento.csv       # Dataset de treino
├── tabeladenovosclientes.csv   # Dataset para previsão
├── .gitignore
├── LICENSE
└── README.md

🚀 Como Executar o Projeto
# Clone o repositório
git clone https://github.com/Davibzf/Machine-Learning-Credit-Scoring

# Acesse a pasta
cd Machine-Learning-Credit-Scoring


Abra o notebook ML-CS.ipynb em um ambiente Jupyter e execute as células sequencialmente.

🌐 Links

🔗 Projeto no GitHub:
https://github.com/Davibzf/Machine-Learning-Credit-Scoring

💼 Portfólio:
https://github.com/Davibzf

📌 Observações Finais

Este projeto faz parte do meu portfólio profissional em Data Science e Machine Learning e pode servir como base para:

otimizações de modelos

testes com outros algoritmos

evolução para ambientes de produção
