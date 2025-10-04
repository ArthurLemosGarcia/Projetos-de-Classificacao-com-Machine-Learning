# Projetos de Classificação com Machine Learning
Este repositório contém três projetos práticos que exploram e comparam diferentes algoritmos de classificação em Python, utilizando a biblioteca Scikit-learn. Cada projeto aborda um conjunto de dados e modelos diferentes, focando em tarefas como detecção de spam, reconhecimento de dígitos, classificação de imagens e análise de vinhos.

Projetos
Aqui está um resumo do que você vai encontrar em cada notebook:

Exercicio_Naive_Bayes.ipynb: Um comparativo de performance entre os classificadores k-Nearest Neighbors (kNN) e Naive Bayes.

ExerciciokNN.ipynb: Uma análise aprofundada do algoritmo kNN, testando diferentes métricas de distância e o impacto da normalização de dados.

Exercicio_Árvores_de_Decisão.ipynb: Uma comparação entre kNN e Árvores de Decisão para uma tarefa de classificação de imagens de cenas.

1. Comparativo kNN vs. Naive Bayes (Exercicio_Naive_Bayes.ipynb)
Este projeto foca em comparar a eficácia dos algoritmos kNN e Naive Bayes (especificamente Bernoulli Naive Bayes) em dois datasets distintos.

Objetivos
Testar diferentes métricas de distância para o kNN e encontrar a que gera a melhor acurácia.

Comparar o melhor modelo kNN com o Naive Bayes usando métricas como F1-Score, precisão e revocação.

Avaliar os modelos em tarefas de classificação de texto e de imagem (dígitos).

Datasets Utilizados
SMS Spam Collection: Um conjunto de dados de mensagens de texto (SMS) para classificar como "spam" ou "ham" (não spam).

Optical Recognition of Handwritten Digits (ORHD): Um conjunto de dados com imagens de dígitos escritos à mão (0 a 9) para classificação.

Metodologia
Divisão dos Dados: Ambos os datasets foram divididos em três conjuntos: Treino (70%), Validação (15%) e Teste (15%).

Classificação de Spam:

O texto foi transformado em vetores numéricos usando CountVectorizer.

O kNN foi treinado com diferentes métricas de distância (euclidean, manhattan, chebyshev, minkowski), e a melhor foi escolhida com base na acurácia no conjunto de validação.

O melhor kNN e o Naive Bayes foram retreinados com os dados de treino + validação e avaliados no conjunto de teste.

Reconhecimento de Dígitos:

As features dos dígitos foram normalizadas e binarizadas.

Um modelo Naive Bayes (Bernoulli) foi treinado e avaliado.

Um modelo kNN foi otimizado (buscando o melhor k e a melhor métrica) usando o conjunto de validação.

Os dois modelos foram comparados no conjunto de teste, analisando a acurácia e a matriz de confusão.

2. Análise do kNN com o Dataset Wine (ExerciciokNN.ipynb)
Este notebook explora exclusivamente o algoritmo kNN, analisando como diferentes configurações afetam sua performance na classificação do famoso dataset "Wine" da Scikit-learn.

Objetivos
Analisar o impacto de diferentes métricas de distância na acurácia do kNN.

Encontrar o valor ideal de k (número de vizinhos) para cada métrica.

Verificar a importância da normalização dos dados (StandardScaler) para o desempenho do modelo.

Dataset Utilizado
Wine: Conjunto de dados com 13 atributos químicos de vinhos de três classes (cultivares) diferentes.

Metodologia
Divisão dos Dados: O dataset foi dividido em Treino (60%) e Teste (40%).

Análise sem Normalização:

Foram testadas as métricas de distância euclidean, cityblock (Manhattan) e chebyshev.

Para cada uma, foi avaliada a acurácia para valores de k de 1 a 10, gerando um gráfico para visualizar o melhor k.

Análise com Normalização:

Os dados de treino e teste foram normalizados usando StandardScaler.

O mesmo processo de teste de métricas e busca pelo melhor k foi repetido nos dados normalizados.

3. Classificação de Cenas com kNN e Árvore de Decisão (Exercicio_Árvores_de_Decisão.ipynb)
Neste projeto, o objetivo é classificar imagens de quatro tipos de cenas diferentes (coast, forest, highway, street) usando os algoritmos kNN e Árvore de Decisão.

Objetivos
Extrair características visuais de imagens (cor e textura) para alimentar os modelos.

Realizar o ajuste de hiperparâmetros (tuning) para o kNN (k) e para a Árvore de Decisão (max_depth).

Comparar a performance final dos dois modelos otimizados na tarefa de classificação de cenas.

Dataset Utilizado
4scenes: Um conjunto de dados de imagens com quatro categorias de cenas.

Metodologia
Extração de Features: Para cada imagem, foram extraídas:

Estatísticas de Cor: Média e desvio padrão dos canais no espaço de cor HSV.

Textura: Média dos descritores de textura de Haralick.

Divisão dos Dados: O conjunto de features foi dividido em Treino (70%), Validação (15%) e Teste (15%).

Ajuste de Hiperparâmetros:

k-NN: A acurácia no conjunto de validação foi testada para valores de k de 1 a 30.

Árvore de Decisão: A acurácia foi testada para max_depth (profundidade máxima) de 1 a 30.

Gráficos foram gerados para visualizar a performance e selecionar os melhores hiperparâmetros.

Avaliação Final:

Os modelos foram retreinados com os melhores hiperparâmetros usando os dados de treino + validação.

A performance final foi medida no conjunto de teste, utilizando classification_report e matriz de confusão para uma comparação detalhada.
