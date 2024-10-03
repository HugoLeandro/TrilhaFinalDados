# Relatório Detalhado de Análise Comparativa dos Meses de Junho e Julho de 2024

## Introdução
Este relatório apresenta uma análise detalhada dos dados coletados nas pesquisas de satisfação da comunidade Código Certo Coders nos meses de junho e julho de 2024. O objetivo principal é comparar os resultados entre os dois meses, identificando tendências, padrões e insights que possam auxiliar na tomada de decisões estratégicas para melhorar a satisfação e o engajamento dos membros da comunidade.


## Metodologia
Para realizar a análise comparativa, seguimos as etapas descritas abaixo:

### 1. Coleta e Preparação dos Dados

- **Importação das bibliotecas necessárias**: Utilizamos bibliotecas como ```pandas```, ```numpy```, ```matplotlib```, ```seaborn``` para manipulação e visualização de dados, além de bibliotecas de NLP e modelagem preditiva.

- **Carregamento dos dados**: Importamos os arquivos ```feedback_junho2024.csv``` e ```feedback_julho2024.csv```, adicionando uma coluna para   identificar o mês correspondente.

- **Pré-processamento:**

- Conversão de colunas para os tipos adequados.
- Tratamento de valores nulos.
- Reset dos índices após exclusões.


### 2. Análise de Sentimentos
- **Análise de comentários adicionais**: Apliquei técnicas de Processamento de Linguagem Natural (NLP) para analisar os comentários adicionais fornecidos pelos membros.

- **Classificação dos sentimentos**: Utilizamos o ```pysentimiento``` para classificar os comentários em positivo, negativo ou neutro.

### 3. Modelagem Preditiva

- **Codificação de variáveis categóricas**: Transformamos variáveis categóricas em numéricas utilizando ```LabelEncoder```.

- **Criação de novas features:**

    - **Média de satisfação**: Calculada a partir das respostas de satisfação em diferentes aspectos.
    - **Comprometimento em reuniões**: Variável binária indicando comprometimento com as reuniões do time.

- **Definição da variável alvo**: Identifiquei membros com risco de desengajamento baseado na média geral de satisfação.

- **Treinamento de modelos**: Utilizei o algoritmo Random Forest para prever o risco de desengajamento.

### 4. Análise de Correlação e Clusterização
- **Matriz de correlação**: Calculamos a correlação entre as variáveis para identificar relações significativas.

- **Clusterização (K-Means)**: Segmentamos os membros em clusters com características semelhantes para identificar grupos distintos dentro da comunidade.

### 5. Visualização dos Dados
Criei diversos gráficos (barras, dispersão, boxplots, heatmaps) para facilitar a interpretação dos dados e evidenciar padrões relevantes.

## Resultados
### 1. Análise de Sentimentos
Distribuição dos Sentimentos dos Comentários por Mês


```Mês	Sentimento	Número de Comentários
Junho	Positivo	39
Neutro	52
Negativo	9
Julho	Positivo	57
Neutro	47
Negativo	8
```

### Observações:

- **Junho**: Predominância de comentários neutros, seguido de positivos e alguns negativos.
- **Julho**: Aumento significativo nos comentários positivos, redução nos neutros e leve diminuição nos negativos.

### Visualização Gráfica

**Interpretação**:

- O aumento nos comentários positivos em julho indica uma melhoria na percepção dos membros sobre a comunidade.

- A estabilidade nos comentários negativos sugere que os pontos de insatisfação persistem e precisam ser abordados.

### 2. Modelagem Preditiva

**Avaliação do Modelo para Junho**

- Métricas de Avaliação:

```Métrica	Classe 0 (Sem Risco)	Classe 1 (Com Risco)
Precisão	100%	100%
Revocação	100%	100%
F1-Score	100%	100%
```

- Matriz de Confusão:

```Previsto 0	Previsto 1
Real 0	13	0
Real 1	0	7
```

- Importância das Variáveis:

```Variável	Importância (%)
Média de Satisfação	91.88
Horas Semanais Dedicadas	5.36
Sentimento do Comentário	2.08
Atualmente Sou	0.67
Comprometimento em Reuniões
```

**Avaliação do Modelo para Julho**

- Métricas de Avaliação:

```Métrica	Classe 0 (Sem Risco)	Classe 1 (Com Risco)
Precisão	100%	100%
Revocação	100%	100%
F1-Score	100%	100%
```

- Matriz de Confusão:

```Previsto 0	Previsto 1
Real 0	18	0
Real 1	0	5
```

- Importância das Variáveis:

```Variável	Importância (%)
Média de Satisfação	93.42
Horas Semanais Dedicadas	3.92
Sentimento do Comentário	2.22
Atualmente Sou	0.44
Comprometimento em Reuniões	0
```

## Observações:

- **A média de satisfação** é a variável mais importante para prever o risco de desengajamento.
- **Comprometimento em reuniões** não contribuiu significativamente para o modelo, possivelmente devido à falta de variabilidade na variável.
Os modelos apresentaram **acurácia de 100%**, indicando alto desempenho, mas é necessário cuidado com overfitting.


## 4. Clusterização dos Membros
Clusters Identificados em Junho

Clusters Identificados em Julho

Descrição dos Clusters:

- Cluster 0: Membros com alta satisfação e alta dedicação de horas semanais.
- Cluster 1: Membros com satisfação média e dedicação moderada.
- Cluster 2: Membros com menor satisfação e menor dedicação de horas semanais.
**Observações**:

- A clusterização ajuda a identificar grupos específicos de membros que podem requerer estratégias diferenciadas para aumentar o engajamento.

## 4. Comparações Adicionais Entre os Meses
Distribuição dos Sentimentos dos Comentários

Média de Satisfação por Mês

```Mês	Média de Satisfação
Junho	0.918873
Julho	0.934200
```

**Observação**: Houve um aumento na média de satisfação de junho para julho.

**Horas Semanais Dedicadas por Mês**

**Interpretação**: Os membros dedicaram mais horas semanais em julho, o que pode estar associado ao aumento da satisfação.

**Relação entre Horas Dedicadas e Satisfação**

**Observação**: Existe uma tendência de que membros que dedicam mais horas semanais possuem maior média de satisfação.


## 5. Conclusões e Recomendações

### Principais Descobertas

**Aumento na Satisfação**: Houve um aumento na média de satisfação dos membros de junho para julho.

**Melhora nos Sentimentos Positivos**: Os comentários positivos aumentaram em julho, indicando uma percepção mais favorável.

**Importância da Média de Satisfação**: Continua sendo a variável mais relevante para prever o risco de desengajamento.

**Participação em Workshops**: Embora adicionada ao modelo, não teve impacto significativo nas previsões.

### 6. Recomendações

**Investigar Comentários Negativos**: Apesar de estáveis, é importante abordar as áreas de insatisfação apontadas.

**Promover Engajamento**: Incentivar a participação ativa dos membros, já que maior dedicação está associada a maior satisfação.

**Avaliar Ações Implementadas**: Identificar quais medidas contribuíram para o aumento na satisfação e replicá-las ou aprimorá-las.

**Reavaliar a Estratégia de Workshops**: Considerar novas abordagens para que a participação em workshops tenha um impacto mais significativo.

## 7. Ações Futuras
**Coleta Contínua de Dados**: Manter o monitoramento regular para identificar tendências e mudanças.
**Análise Qualitativa**: Realizar uma análise aprofundada dos comentários para entender contextos e nuances.
**Customização de Intervenções**: Desenvolver ações direcionadas aos grupos identificados nos clusters, focando nas necessidades específicas.

## Referências
Bibliotecas Utilizadas:

```Pandas```
```NumPy```
```Matplotlib```
```Seaborn```
```NLTK```
```Scikit-learn```
```PySentimiento```

**Metodologias:**

Análise de Sentimentos
Modelagem Preditiva (Random Forest)
Engenharia de Features



## Nota de Agradecimento – Trilha Final Ciência de Dados

Gostaria de expressar meus sinceros agradecimentos a todos os membros da comunidade Código Certo Coders pela oportunidade de participar desta incrível jornada. A conclusão da Trilha Inicial é apenas o começo de uma trajetória cheia de aprendizados e descobertas.

O projeto desenvolvido para a Trilha Final busca realizar uma análise detalhada dos dados coletados nas pesquisas de satisfação realizadas em junho e julho de 2024. Com o uso da ciência de dados, pretendemos extrair insights valiosos que vão nos ajudar a moldar o futuro da comunidade, atendendo melhor às expectativas e necessidades de cada um.

Este trabalho só é possível graças ao apoio e participação de cada um de vocês. Obrigado por se engajarem e compartilharem seus feedbacks. Juntos, estamos construindo um espaço de aprendizado e colaboração que cresce a cada dia. Que este seja apenas o início de grandes conquistas!

