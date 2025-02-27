# Classificação de Tipos de Arroz

## Considerações iniciais
Os algoritmos foram implementados usando a biblioteca do scikit-learn no Google Colaboratory. A importação dos dados foi realizada utilizando a biblioteca pandas.

## 📂 Estrutura do Projeto
- **Dataset**: Planilha Excel com amostras dos dois tipos de arroz.
- **Pré-processamento**: Divisão dos dados em treino (2/3) e teste (1/3), realizada aleatoriamente.
- **Modelo**: Implementação de árvore de decisão com critérios de **Gini** e **Entropia**.
- **Otimização**: Testes para encontrar a melhor profundidade da árvore (**max_depth**) e análise do impacto da escolha do critério.
- **Avaliação**: Comparação das métricas **Precisão**, **Recall** e **F1-score**.


## 🛠️ Implementação
### Bibliotecas Utilizadas
```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import classification_report
```
### Treinamento Inicial
O modelo foi treinado sem ajuste de hiperparâmetros, utilizando:
- **X_train, y_train**: Conjunto de treinamento
- **X_test, y_test**: Conjunto de teste
- **y_pred**: Previsões do modelo

### Ajuste da Profundidade da Árvore
Foi analisado o impacto do hiperparâmetro **max_depth**, variando de **1 até treeDepth** (profundidade máxima observada). Para cada valor de **max_depth**, foram coletadas as métricas de desempenho.

Gráficos comparativos foram gerados para ambos os critérios (**Gini** e **Entropia**), evidenciando que **a faixa ideal de max_depth está entre [1,5]**.

## 📊 Resultados e Conclusões
- Modelos com **max_depth entre [1,5]** tiveram melhor generalização.
- Para modelos mais complexos (**max_depth > 5**), o critério de **Entropia** superou o **Gini**.
- O impacto do custo computacional entre os critérios foi insignificante no contexto deste projeto.

## 🚀 Como Executar o Projeto
1. Instale as dependências:
   ```bash
   pip install pandas scikit-learn
   ```
2. Execute o script principal:
   ```bash
   python main.py
   ```

## 📌 Observações
A separação aleatória dos dados pode influenciar os resultados. Para reduzir esse efeito, os experimentos foram repetidos várias vezes, calculando médias das métricas.

## 📄 Referências
- Documentação do [Scikit-Learn](https://scikit-learn.org/stable/)
- Conceitos de **Árvores de Decisão** e **Critérios de Impureza**

---
📍 Projeto desenvolvido para análise e classificação de grãos de arroz. Feedbacks e contribuições são bem-vindos!

