# Machine Learning — Fase 2

**Pós Tech FIAP — Data Analytics**

Materiais, anotações e exercícios da Fase 2 do curso, dedicada a modelos de machine learning aplicados a problemas de classificação.

---

## Sobre a fase

A Fase 2 percorre o ciclo completo de um projeto de machine learning: da compreensão do problema de negócio até a interpretação dos resultados e a comunicação honesta das limitações do modelo. O foco está em **aprendizado supervisionado**, com ênfase em classificação binária.

---

## Conteúdo estudado

### 1. Análise exploratória de dados (EDA)

- Distribuição das variáveis, assimetria e histogramas
- Matriz de correlação de Pearson e identificação de multicolinearidade
- Detecção de outliers pela regra do intervalo interquartil (IQR)
- Verificação de valores faltantes, duplicatas e balanceamento de classes

### 2. Pré-processamento

- Separação treino/teste estratificada, feita **antes** de qualquer decisão baseada nos dados
- Padronização com `StandardScaler` para modelos baseados em distância
- Prevenção de vazamento de dados (*data leakage*) com `Pipeline` do scikit-learn
- Seleção de variáveis calculada exclusivamente sobre o conjunto de treino

### 3. Feature engineering

- Criação de variáveis derivadas com fundamentação no domínio do problema
- Transformações para corrigir assimetria (logarítmica)
- Avaliação do ganho real por validação cruzada — e o valor de documentar resultados negativos

### 4. Modelos de classificação

| Modelo | Família | Característica principal |
|---|---|---|
| **KNN** | Baseado em instâncias | Não assume forma funcional; sensível à escala e à dimensionalidade |
| **SVM (kernel RBF)** | Margem máxima | Capta fronteiras de decisão não-lineares |
| **Random Forest** | Ensemble de árvores | Captura interações automaticamente e fornece importância de variáveis |
| **Regressão Logística** | Linear | Modelo de referência, interpretável pelos coeficientes |

### 5. Ajuste de hiperparâmetros

- Busca em grade com `GridSearchCV`
- Validação cruzada estratificada e repetida (`RepeatedStratifiedKFold`)
- Regra de 1 erro-padrão: entre modelos estatisticamente equivalentes, escolher o mais simples

### 6. Avaliação de modelos

- Matriz de confusão e leitura de falsos positivos × falsos negativos
- Acurácia, precisão, recall e F1 — e em que situação cada métrica importa
- Curva ROC e AUC como medida de ordenação, independente do limiar de corte
- Ajuste do limiar de decisão como alavanca de negócio, não como ganho de desempenho
- Comparação contra baseline (classe majoritária) antes de declarar qualquer resultado

### 7. Interpretação dos resultados

- Importância por impureza (Gini) e seu viés em favor de variáveis contínuas
- Importância por permutação como medida mais confiável
- Distinção entre correlação, importância preditiva e causalidade

---

## Ferramentas

Python 3 · pandas · numpy · scikit-learn · matplotlib · seaborn · Jupyter Notebook

---

## Tech Challenge da fase

Aplicação prática de todo o conteúdo: classificação da qualidade de vinhos tintos a partir de características físico-químicas, comparando KNN, SVM e Random Forest em dois conjuntos de variáveis.

Principais aprendizados do projeto:

- Quatro medições (`alcohol`, `volatile acidity`, `sulphates`, `citric acid`) preservam o desempenho preditivo obtido com onze — redução direta de custo laboratorial
- Random Forest e KNN ficaram estatisticamente empatados; a escolha entre eles depende do custo do erro, não da métrica isolada
- Duplicatas na base inflavam as métricas em 4 a 9 pontos percentuais — quantificar a limitação vale mais que escondê-la

Repositório: `INSERIR_LINK_DO_TECH_CHALLENGE`

---

## Autora

Laura Garcias