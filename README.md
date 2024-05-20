# Projeto Machine Learning para previsão de cancelamento de serviço de internet

**O propósito deste projeto é desenvolver um modelo de Machine Learning capaz de prever o cancelamento de serviço de internet 
e realizar a segmentação dos clientes que cancelaram o serviço com base em características e comportamentos semelhantes.**

## Previsão de Churn
O primeiro objetivo é criar um modelo capaz de prever quando um cliente está prestes a cancelar seu serviço de internet.

## Segmentação de Clientes
O segundo objetivo é agrupar os clientes que cancelaram o serviço de internet usando técnicas de clusterização. 
Ao identificar grupos de clientes com características e comportamentos semelhantes, poderemos desenvolver estratégias de marketing específicas para reter esses clientes

## Projeto
**Contexto**: Com a crescente competição entre os provedores de internet, manter os clientes existentes tornou-se uma prioridade vital para aumentar a receita. 
Diante desse cenário, entender o fenômeno do churn, ou seja, a taxa de cancelamento de serviços, é crucial. 
Os provedores buscam identificar quais clientes apresentam maior probabilidade de cancelar seus serviços, pois isso lhes permite antecipar tais movimentos e implementar 
estratégias eficazes de retenção.

Para o desenvolvimento do projeto, utilizamos o dataset Internet Service Provider Customer Churn disponível no site da 
[Kaggle](https://www.kaggle.com/datasets/mehmetsabrikunt/internet-service-churn/data).
Este conjunto de dados inclui variáveis essenciais que podem ajudar na identificação de padrões associados ao churn como: assinatura de TV, assinatura de pacotes de filmes, tempo de
assinatura, fatura média, contagem de falhas no serviço, etc.  

### Análise Exploratória de Dados
Para compreender os dados e as variáveis disponíveis, conduzimos uma análise exploratória detalhada.
Isso incluiu também a investigação das relações entre as variáveis preditoras e o target, utilizando testes de hipóteses adequados.
O notebook contendo esta etapa pode ser acessado [aqui](https://github.com/leticiadluz/ml_internet_provider_churn/blob/main/EDA.ipynb).

**O dataset limpo após a análise exploratória, pode ser acessado [aqui](https://github.com/leticiadluz/ml_internet_provider_churn/blob/main/df_churn_cleaned.csv)** 

### Aprendizado de máquina supervisionado (classificação)
Construímos seis modelos de Machine Learning utilizando três estimadores diferentes: KNN, SVC e XGBoost. Realizamos pré-processamento das variáveis, escolhendo as mais adequadas para cada estimador, além de otimização de hiperparâmetros. A métrica escolhida para a avaliação do modelo foi o recall. Ao otimizar o recall, garantimos que estamos minimizando a quantidade de falsos negativos, ou seja, estamos identificando o maior número possível de clientes em risco de churn.
O modelo final utilizou o estimador XGBoost e atingiu um recall de 0.94 nos dados de teste, demonstrando sua eficácia em identificar casos de churn.  
O notebook contendo esta etapa pode ser acessado [aqui](https://github.com/leticiadluz/ml_internet_provider_churn/blob/main/ML.ipynb).

### Aprendizado de máquina não supervisionado (clusterização)
Para entender melhor os padrões entre os clientes que cancelaram o serviço, realizamos uma análise de clusterização utilizando dois algoritmos: K-Means e DBSCAN.
Ambos os algoritmos, K-Means e DBSCAN, apresentaram escores de silhueta semelhantes, indicando desempenho comparável na definição dos clusters. No entanto, o K-Means identificou um número maior de clusters (k=6), enquanto o DBSCAN identificou um número menor, (k=3), sugerindo  que o K-Means apresenta uma capacidade maior de capturar a complexidade dos nossos dados. Além disto, o K-Means apresentou menor tempo de processamento, se mostrando mais adequado para lidar com conjuntos de dados de grande escala. 
Com base nisso, escolhemos o K-Means como nosso modelo de clusterização, pois além de ser computacionalmente eficiente, ele oferece uma segmentação mais detalhada dos dados.
Os resultados da clusterização podem ser acessados [aqui](https://github.com/leticiadluz/ml_internet_provider_churn/blob/main/clusterizacao.ipynb).

## Ferramentas utilizadas

* Google Colab
  
## Linguagem utilizada

* Python






.

