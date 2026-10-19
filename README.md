# Detecção de Fraudes em Compras

## 📋 Descrição

A detecção de fraudes em cartões de crédito é importante para proteger consumidores e instituições financeiras contra transações fraudulentas.

Neste projeto, são utilizadas técnicas de **Aprendizado de Máquina (Machine Learning)** para analisar transações e identificar padrões que possam indicar a ocorrência de fraude.

O projeto faz parte do estudo de classificação binária aplicado à detecção de fraudes, utilizando algoritmos de aprendizado supervisionado para distinguir transações legítimas de fraudulentas.

## 📊 Dataset

O conjunto de dados utilizado pertence à competição **IEEE-CIS Fraud Detection**, disponibilizada no Kaggle e associada à empresa Vesta.

O dataset contém informações sobre transações online, incluindo atributos relacionados aos valores das compras, dispositivos e informações de identidade.

Devido às limitações de processamento do ambiente utilizado, neste TDE foi selecionada uma **amostra de 10% dos dados**, preservando a proporção entre as classes por meio de amostragem estratificada.

- **Dataset:** [IEEE-CIS Fraud Detection — Kaggle](https://www.kaggle.com/c/ieee-fraud-detection/overview)
- **Descrição dos campos:** [Data Description](https://www.kaggle.com/c/ieee-fraud-detection/discussion/101203)

## 🎯 Objetivo

O objetivo deste trabalho é desenvolver modelos baseline de classificação binária para identificar se uma transação é:

- **Legítima:** transação não identificada como fraude.
- **Fraudulenta:** transação identificada como fraude.

Esta etapa tem como finalidade estabelecer resultados iniciais que poderão ser utilizados como referência para comparar e avaliar melhorias em etapas posteriores do projeto.

## 🧠 Metodologia

O desenvolvimento foi dividido nas seguintes etapas:

1. Carregamento e seleção dos atributos utilizados na análise.
2. Análise da distribuição das classes e identificação do desbalanceamento dos dados.
3. Seleção de uma amostra estratificada de 10% do conjunto de dados.
4. Divisão dos dados em conjuntos de treinamento e teste, na proporção de 80% e 20%, respectivamente.
5. Tratamento de valores ausentes, utilizando estatísticas calculadas a partir dos dados de treinamento.
6. Transformação das variáveis categóricas por meio de codificação one-hot.
7. Treinamento e avaliação dos modelos baseline.

## 🤖 Algoritmos utilizados

Foram utilizados dois algoritmos de classificação, com suas configurações padrão, sem aplicação de otimizações ou ajuste de hiperparâmetros nesta etapa.

- **Árvore de Decisão (Decision Tree):** modelo que realiza divisões sucessivas dos dados para produzir classificações.
- **Floresta Aleatória (Random Forest):** modelo que combina diversas árvores de decisão para realizar previsões.

## 📈 Métricas de avaliação

Para comparar os modelos, foram utilizadas as seguintes métricas:

- **Acurácia (Accuracy):** proporção total de previsões corretas.
- **Acurácia Balanceada (Balanced Accuracy):** média do desempenho de classificação por classe.
- **Precisão (Precision):** proporção das previsões de fraude que realmente correspondem a fraudes.
- **Recall:** proporção das fraudes reais identificadas pelo modelo.
- **F1-score:** média harmônica entre precisão e recall.
- **ROC-AUC:** avalia a capacidade de distinguir as classes em diferentes limiares de classificação.

Também foram utilizadas matrizes de confusão para analisar os acertos e erros de cada modelo.

Como o conjunto de dados apresenta desbalanceamento entre transações legítimas e fraudulentas, a análise considera métricas além da acurácia tradicional.

## 📊 Resultados do TDE 03

Os resultados obtidos na amostra de teste foram:

| Métrica | Árvore de Decisão | Floresta Aleatória |
|---|---:|---:|
| Acurácia balanceada | 0,6092 | 0,5639 |
| ROC-AUC | 0,6092 | 0,7982 |
| Acurácia | 0,9462 | 0,9667 |
| Precisão | 0,2389 | 0,6136 |
| Recall | 0,2470 | 0,1308 |
| F1-score | 0,2429 | 0,2156 |

A Floresta Aleatória apresentou maior ROC-AUC, acurácia e precisão. A Árvore de Decisão apresentou melhores resultados em acurácia balanceada, recall e F1-score.

Esses resultados mostram que o desempenho depende da métrica analisada. Em particular, o recall é importante neste problema porque indica a proporção de fraudes reais que o modelo consegue identificar.

Os modelos treinados nesta etapa constituem uma **baseline**, servindo como referência para experimentos e possíveis melhorias em etapas futuras do projeto.

## 🚧 Principais desafios

- **Desbalanceamento das classes:** as transações fraudulentas representam uma parcela menor dos dados.
- **Valores ausentes:** foi necessário definir estratégias de imputação para preparar os atributos.
- **Preparação dos dados:** as variáveis categóricas precisaram ser transformadas para utilização nos algoritmos.
- **Identificação de fraudes:** os modelos precisam distinguir transações fraudulentas das legítimas, considerando os diferentes tipos de erro.

## 🔗 Referências

- [IEEE-CIS Fraud Detection — Kaggle](https://www.kaggle.com/c/ieee-fraud-detection/overview)
- [Descrição dos campos do dataset](https://www.kaggle.com/c/ieee-fraud-detection/discussion/101203)
