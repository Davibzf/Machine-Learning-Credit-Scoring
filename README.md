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

O **ML-CS (Machine Learning Credit Scoring)** é um projeto de **Machine Learning supervisionado** desenvolvido para prever o score de crédito de clientes a partir de dados financeiros, demográficos e comportamentais estruturados.

> **Contexto:** Instituições financeiras precisam avaliar rapidamente o perfil de crédito de clientes para tomada de decisão em empréstimos, financiamentos e concessão de limites.

### 📊 Fonte dos Dados
- Dataset público da plataforma **Kaggle**
- Simulação de cenário real do setor financeiro
- **100.000 registros** com 25 variáveis
- Classes alvo: **Poor** (Ruim), **Standard** (Médio), **Good** (Bom)

---

## 🎯 Objetivos

| Objetivo | Descrição |
|----------|-----------|
| **🤖 Automação** | Substituir análise manual por modelo preditivo |
| **📉 Redução de Risco** | Minimizar subjetividade na concessão de crédito |
| **🔍 Identificação de Padrões** | Descobrir variáveis mais relevantes para risco |
| **📚 Demonstração Técnica** | Portfólio em Data Science e ML |

---

## 🔁 Pipeline do Projeto

```
📦 Aquisição dos Dados (tabelatreinamento.csv)
    ↓
🔍 Análise Exploratória (info(), display())
    ↓
🧹 Pré-processamento (LabelEncoder para variáveis categóricas)
    ↓
✂️ Divisão Treino/Teste (70% treino, 30% teste)
    ↓
🤖 Modelagem (RandomForestClassifier)
    ↓
📊 Avaliação (accuracy_score: 82.27%)
    ↓
📈 Interpretação (feature_importances_)
    ↓
🚀 Aplicação em Novos Clientes (tabeladenovosclientes.csv)
```

---

## 📈 Resultados

### ✅ Acurácia do Modelo

| Modelo | Acurácia |
|--------|----------|
| **Random Forest** | **82.27%** |

### 🔑 Variáveis Mais Relevantes

| Variável | Importância |
|----------|-------------|
| **divida_total** | 11.75% |
| **mix_credito** | 8.44% |
| **juros_emprestimo** | 8.08% |
| **idade_historico_credito** | 7.53% |
| **dias_atraso** | 6.50% |

> 💡 **Insight:** Dívida total e mix de crédito são os fatores mais determinantes para o score de crédito

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
jupyter notebook "ML-CS.ipynb"
```

3. **Estrutura de Arquivos Necessária**
```
📁 projeto/
├── ML-CS.ipynb
├── tabelatreinamento.csv (dados de treino)
└── tabeladenovosclientes.csv (novos clientes para previsão)
```

---

## 📊 Estrutura do Código

### 1️⃣ Importação e Carregamento
```python
import pandas as pd
tabela = pd.read_csv('tabelatreinamento.csv')
```

### 2️⃣ Análise Inicial
```python
display(tabela)
display(tabela.info())  # Verificação de tipos e estrutura
```

### 3️⃣ Codificação de Variáveis Categóricas
```python
from sklearn.preprocessing import LabelEncoder

codificador_profissao = LabelEncoder()
tabela["profissao"] = codificador_profissao.fit_transform(tabela["profissao"])

codificador_credito = LabelEncoder()
tabela["mix_credito"] = codificador_credito.fit_transform(tabela["mix_credito"])

codificador_pagamento = LabelEncoder()
tabela["comportamento_pagamento"] = codificador_pagamento.fit_transform(tabela["comportamento_pagamento"])
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
from sklearn.ensemble import RandomForestClassifier
modelo_arvore = RandomForestClassifier()
modelo_arvore.fit(x_treino, y_treino)
```

### 6️⃣ Avaliação
```python
from sklearn.metrics import accuracy_score
previsoes = modelo_arvore.predict(x_teste)
acuracia = accuracy_score(y_teste, previsoes)
print(f"{acuracia*100:.2f}%")  # 82.27%
```

### 7️⃣ Importância das Features
```python
colunas = list(x_teste)
importancias = pd.DataFrame(
    index=colunas, 
    data=modelo_arvore.feature_importances_ * 100
)
print(importancias)
```

### 8️⃣ Previsão em Novos Dados
```python
tabelanova = pd.read_csv('tabeladenovosclientes.csv')

# Aplicar mesma codificação
tabelanova["profissao"] = codificador_profissao.fit_transform(tabelanova["profissao"])
tabelanova["mix_credito"] = codificador_credito.fit_transform(tabelanova["mix_credito"])
tabelanova["comportamento_pagamento"] = codificador_pagamento.fit_transform(tabelanova["comportamento_pagamento"])

tabelanova = tabelanova.drop(columns=['id_cliente'])
previsoes = modelo_arvore.predict(tabelanova)
print(previsoes)
```

---

## 📈 Análise das Variáveis

### Variáveis Utilizadas (24 features)

| Categoria | Variáveis |
|-----------|-----------|
| **Demográficas** | idade, profissao |
| **Financeiras** | salario_anual, divida_total, investimento_mensal, saldo_final_mes |
| **Comportamentais** | dias_atraso, num_pagamentos_atrasados, comportamento_pagamento |
| **Produtos** | num_contas, num_cartoes, num_emprestimos |
| **Crédito** | mix_credito, idade_historico_credito, taxa_uso_credito, juros_emprestimo |
| **Empréstimos** | emprestimo_carro, emprestimo_casa, emprestimo_pessoal, emprestimo_credito, emprestimo_estudantil |

### Distribuição das Classes
- **Good** (Bom): Clientes de baixo risco
- **Standard** (Médio): Risco moderado
- **Poor** (Ruim): Alto risco de inadimplência

---

## 🚀 Possíveis Aplicações

- 🏦 **Bancos e Fintechs**: Automação de análise de crédito
- 📱 **Sistemas de Decisão**: Score em tempo real para aprovações
- 📊 **Análise de Portfólio**: Segmentação de clientes por risco
- 🎓 **Educacional**: Estudo de casos em Data Science
- 📈 **Portfólio**: Demonstração de habilidades em ML

---

## ⚠️ Limitações e Considerações

### Limitações Técnicas
- ✅ Modelo treinado com dados públicos (não reflete cenário real completo)
- ✅ Sem tratamento para desbalanceamento de classes
- ✅ Hiperparâmetros não otimizados (Random Forest padrão)
- ✅ Sem validação cruzada
- ✅ LabelEncoder aplicado separadamente para novos dados (pode causar inconsistências)

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
- [ ] **Persistência do modelo** com joblib/pickle
- [ ] **Salvar codificadores** para consistência em produção

---

## 👨‍💻 Autor

**Davi Bezerra Fraga**  
Estudante e entusiasta de **Backend, IA e Machine Learning**

| | |
|---|---|
| **📧 Email** | davibezerrafraga@gmail.com |
| **🔗 LinkedIn** | [https://www.linkedin.com/in/davizf/](https://www.linkedin.com/in/davizf/) |
| **🐙 GitHub** | [https://github.com/Davibzf](https://github.com/Davibzf) |
| **🌐 Portfólio** | [davibezerrafraga.vercel.app](https://davibezerrafraga.vercel.app) |

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

> ⭐ **Se este projeto foi útil para seus estudos, considere dar uma estrela no GitHub!**  
> 💬 *Feedback, sugestões e contribuições são sempre bem-vindos*

---

**📌 Status do Projeto:** Concluído (V1) — Manutenção e melhorias futuras conforme roadmap.
