# 🧠 ML-CS — Machine Learning Credit Scoring

**Modelo supervisionado de classificação de risco de crédito utilizando Random Forest**

[![Python](https://img.shields.io/badge/Python-3.11.4-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0.3-blue.svg)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3.0-orange.svg)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-green.svg)](https://jupyter.org/)

---

## 📋 Índice
- [Visão Geral](#-visão-geral)
- [Objetivos](#-objetivos)
- [Pipeline do Projeto](#-pipeline-do-projeto)
- [Resultados](#-resultados)
- [Tecnologias](#-tecnologias)
- [Como Executar](#-como-executar)
- [Estrutura do Código](#-estrutura-do-código)
- [Análise das Variáveis](#-análise-das-variáveis)
- [Aplicações](#-possíveis-aplicações)
- [Limitações](#-limitações)
- [Autor](#-autor)

---

## 🎯 Visão Geral

Este projeto implementa um **sistema de Credit Scoring** utilizando Machine Learning supervisionado para classificar clientes em categorias de risco: **Ruim (Poor)**, **Médio (Standard)** ou **Bom (Good)**.

> **Contexto:** Instituições financeiras precisam avaliar rapidamente o perfil de crédito de clientes para tomada de decisão em empréstimos, financiamentos e concessão de limites.

### 📊 Fonte dos Dados
- Dataset público da plataforma **Kaggle**
- Simulação de cenário real do setor financeiro
- **100.000 registros** com 25 variáveis financeiras e demográficas

---

## 🎯 Objetivos

| Objetivo | Descrição |
|----------|-----------|
| **🤖 Automação** | Substituir análise manual por modelo preditivo |
| **📉 Redução de Risco** | Minimizar subjetividade na concessão de crédito |
| **🔍 Identificação de Padrões** | Descobrir variáveis mais relevantes para risco |
| **📚 Demonstração Técnica** | Portfolio em Data Science e ML |

---

## 🔁 Pipeline do Projeto

```
📦 Aquisição dos Dados (Kaggle)
    ↓
🔍 Análise Exploratória (EDA)
    ↓
🧹 Pré-processamento (Label Encoding)
    ↓
✂️ Divisão Treino/Teste (70/30)
    ↓
🤖 Modelagem (Random Forest)
    ↓
📊 Avaliação (Acurácia)
    ↓
📈 Interpretação (Feature Importance)
    ↓
🚀 Aplicação em Novos Clientes
```

---

## 📈 Resultados

### ✅ Métricas de Performance

| Modelo | Acurácia |
|--------|----------|
| **Random Forest** | **82.54%** |
| KNN (comparação) | 73.24% |

### 🔑 Variáveis Mais Relevantes

| Variável | Importância |
|----------|-------------|
| **divida_total** | 12.39% |
| **mix_credito** | 8.54% |
| **juros_emprestimo** | 7.94% |
| **idade_historico_credito** | 6.95% |
| **dias_atraso** | 6.39% |

> 💡 **Insight:** Dívida total e mix de crédito são os fatores mais determinantes para o score

---

## 🛠 Tecnologias Utilizadas

| Tecnologia | Versão | Função |
|------------|--------|--------|
| **Python** | 3.11.4 | Linguagem base |
| **Pandas** | 2.0.3 | Manipulação e análise de dados |
| **Scikit-learn** | 1.3.0 | Modelagem e pré-processamento |
| **Jupyter Notebook** | - | Ambiente de desenvolvimento |

### Bibliotecas Principais
```python
import pandas as pd
from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score
```

---

## 🚀 Como Executar

### Pré-requisitos
```bash
pip install pandas scikit-learn jupyter
```

### Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/seu-usuario/ml-credit-scoring.git
cd ml-credit-scoring
```

2. **Execute o Jupyter Notebook**
```bash
jupyter notebook "ML - CS.ipynb"
```

3. **Estrutura de Arquivos Necessária**
```
📁 projeto/
├── ML - CS.ipynb
├── clientes.csv (dados de treino)
└── planilha.csv (novos clientes)
```

---

## 📊 Estrutura do Código

### 1️⃣ Importação e Carregamento
```python
import pandas as pd
tabela = pd.read_csv('clientes.csv')
```

### 2️⃣ Análise Inicial
```python
display(tabela.info())  # Verificação de tipos e nulos
```

### 3️⃣ Codificação de Variáveis Categóricas
```python
from sklearn.preprocessing import LabelEncoder
codificador = LabelEncoder()
tabela["profissao"] = codificador.fit_transform(tabela["profissao"])
```

### 4️⃣ Preparação dos Dados
```python
y = tabela['score_credito']  # target
x = tabela.drop(columns=['score_credito', 'id_cliente'])  # features

x_treino, x_teste, y_treino, y_teste = train_test_split(
    x, y, test_size=0.3, random_state=1
)
```

### 5️⃣ Treinamento do Modelo
```python
modelo = RandomForestClassifier()
modelo.fit(x_treino, y_treino)
```

### 6️⃣ Avaliação
```python
previsoes = modelo.predict(x_teste)
acuracia = accuracy_score(y_teste, previsoes)
print(f"Acurácia: {acuracia:.2%}")
```

### 7️⃣ Importância das Features
```python
importancias = pd.DataFrame({
    'feature': x.columns,
    'importancia': modelo.feature_importances_
}).sort_values('importancia', ascending=False)
```

### 8️⃣ Previsão em Novos Dados
```python
novos_clientes = pd.read_csv('planilha.csv')
# ... pré-processamento igual ao treino
previsoes = modelo.predict(novos_clientes)
```

---

## 📈 Análise das Variáveis

### Variáveis Utilizadas (24 features)

| Tipo | Variáveis |
|------|-----------|
| **Demográficas** | idade, profissao |
| **Financeiras** | salario_anual, divida_total, investimento_mensal, saldo_final_mes |
| **Comportamentais** | dias_atraso, num_pagamentos_atrasados, comportamento_pagamento |
| **Produtos** | num_contas, num_cartoes, num_emprestimos |
| **Crédito** | mix_credito, idade_historico_credito, taxa_uso_credito |
| **Empréstimos** | emprestimo_carro, casa, pessoal, credito, estudantil |

### Distribuição das Classes
- **Good** (Bom): Clientes de baixo risco
- **Standard** (Médio): Risco moderado
- **Poor** (Ruim): Alto risco de inadimplência

---

## 🚀 Possíveis Aplicações

- 🏦 **Bancos e Fintechs**: Automação de análise de crédito
- 📱 **Sistemas de Decisão**: Score em tempo real para aprovações
- 📊 **Análise de Portfolio**: Segmentação de clientes por risco
- 🎓 **Educacional**: Estudo de casos em Data Science
- 📈 **Portfólio**: Demonstração de habilidades em ML

---

## ⚠️ Limitações e Considerações

### Limitações Técnicas
- ✅ Modelo treinado com dados públicos (não reflete cenário real completo)
- ✅ Sem tratamento para desbalanceamento de classes
- ✅ Hiperparâmetros não otimizados (Random Forest padrão)
- ✅ Sem validação cruzada

### Aviso Legal
> ⚖️ **Este projeto possui fins educacionais e demonstrativos.**  
> Não deve ser utilizado diretamente para decisões financeiras reais sem:
> - Validações regulatórias
> - Auditoria independente do modelo
> - Conformidade com LGPD e legislação bancária
> - Testes em ambiente controlado

---

## 📌 Melhorias Futuras

- [ ] **Otimização de hiperparâmetros** com GridSearchCV
- [ ] **Teste de outros algoritmos** (XGBoost, LightGBM)
- [ ] **Validação cruzada** para maior robustez
- [ ] **Balanceamento de classes** (SMOTE)
- [ ] **Interpretabilidade** com SHAP/LIME
- [ ] **API REST** para deploy do modelo
- [ ] **Dashboard interativo** para visualização

---

## 👨‍💻 Autor

**Davi Bezerra Fraga**  
Estudante e entusiasta de **Backend, IA e Machine Learning**

| | |
|---|---|
| **📧 Email** | davi.fraga@email.com |
| **🔗 LinkedIn** | [linkedin.com/in/davibezerrafraga](https://linkedin.com/in/davibezerrafraga) |
| **🐙 GitHub** | [github.com/davibezerrafraga](https://github.com/davibezerrafraga) |
| **🌐 Portfólio** | [davibezerrafraga.vercel.app](https://davibezerrafraga.vercel.app) |

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

> ⭐ **Se este projeto foi útil para seus estudos, considere dar uma estrela no GitHub!**  
> 💬 *Feedback, sugestões e contribuições são sempre bem-vindos*

---

**📌 Status do Projeto:** Concluído (V1) — Manutenção e melhorias futuras conforme roadmap.
