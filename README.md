# Sistemas-de-Apoio-Decisao---Projeto-Pratico-II---NFL
A análise aprofundada dos dados históricos do Draft da NFL oferece uma janela única para entender as dinâmicas de seleção. 

## 1. Contextualização
Este projeto explora dados históricos do Draft da National Football League (NFL) para identificar padrões e fatores que influenciam o processo de seleção de jogadores universitários. O Draft é um evento crucial para as equipes da NFL, buscando equilibrar a liga e reforçar elencos com novos talentos. A análise de dados permite entender tendências em posições valorizadas, faculdades que mais fornecem jogadores e a relação de atributos físicos e demográficos com as escolhas.

## 2. Conjunto de Dados
O conjunto de dados utilizado contém informações de diversos Drafts da NFL. As colunas principais focadas nesta análise incluem:

- draftTeam: Time da NFL que realizou a seleção.
- college: Faculdade de origem do jogador.
- position: Posição jogada pelo atleta.
- heightInches: Altura do jogador em polegadas.
- weight: Peso do jogador em libras.
- ageAtDraft: Idade do jogador na época do Draft.
- round: Rodada em que o jogador foi selecionado.\
O arquivo de dados utilizado é draft.xlsx, localizado em /content/drive/MyDrive/Colab Notebooks/.

## 3. Metodologia
A análise seguiu as seguintes etapas:

- Importação de Bibliotecas: Carregamento das bibliotecas Python necessárias para manipulação de dados, análise e visualização (pandas, numpy, seaborn, matplotlib, scikit-learn, etc.).
- Carregamento e Limpeza de Dados.
- Seleção das colunas de interesse.
- Conversão de colunas numéricas e tratamento de valores ausentes (NaN e 0).
- Remoção de linhas com dados faltantes para garantir um conjunto de dados completo para análise.

### Análise Descritiva:
- Identificação das posições, faculdades e times mais frequentes no Draft.
- Visualização das relações entre atributos físicos (altura, peso, idade, rodada) através de pairplots e boxplots.
- Análise da distribuição das posições por rodada.

### Agrupamento (Clustering):
- Preparação dos Dados: Seleção de atributos relevantes e aplicação de One-Hot Encoding para variáveis categóricas (position).
- Padronização dos Dados: Escalonamento dos atributos numéricos para que tenham média 0 e desvio padrão 1.
- Análise de Componentes Principais (PCA): Redução da dimensionalidade dos dados para facilitar o agrupamento, analisando a variância explicada pelos componentes.
- Determinação do Número de Clusters (Método Elbow e Análise de Silhueta): Utilização de técnicas para identificar o número ideal de grupos a serem formados. Foi definido o uso de 4 clusters.
- Aplicação do Algoritmo K-Means: Agrupamento dos jogadores nos 4 clusters identificados com base nos componentes principais.
- Análise da Silhueta: Avaliação da qualidade do agrupamento, medindo a coesão e separação dos clusters.

### Análises Gráficas dos Clusters:
- Mapa de Calor: Visualização comparativa dos perfis médios dos clusters em relação a atributos físicos e posições.
- Mapa de Radar: Comparação visual dos clusters em múltiplos atributos de forma simultânea.
- Gráficos de Barras Comparativos: Análise direta de atributos como rodada média e peso médio por cluster.
- Histogramas: Visualização da distribuição de peso dentro de cada cluster.
- Composição de Posições por Cluster: Gráfico de barras empilhadas mostrando a distribuição percentual das posições mais comuns em cada cluster.

### Análise Descritiva dos Clusters:
- Cálculo de estatísticas sumárias para os atributos numéricos por cluster.
- Identificação das posições mais frequentes em cada grupo.
- Análise da distribuição de idade e rodada do Draft por cluster.
- Exploração da relação entre a faculdade de origem e os clusters.

### 4. Principais Descobertas
Foram identificados 4 perfis distintos de jogadores no Draft da NFL com base em atributos físicos, posição e rodada de seleção.\
Os clusters se diferenciam principalmente em termos de altura, peso e as posições predominantes (jogadores mais leves e ágeis, jogadores de linha, Tight Ends e jogadores que combinam tamanho/força/agilidade).\
A análise da relação entre as faculdades mais representativas e os clusters sugere que algumas faculdades podem ter uma leve tendência a desenvolver jogadores que se encaixam em determinados perfis de cluster.

## 5. Estrutura do Código
O projeto está organizado em um notebook Jupyter (ou Google Colab) que executa as etapas da análise sequencialmente. Cada seção do notebook corresponde a uma etapa da metodologia, com células de código e texto explicativo.

## 6. Configuração e Uso
Para replicar esta análise, você precisará das seguintes bibliotecas Python instaladas:

- numpy
- pandas
- seaborn
- matplotlib
- plotly
- networkx
- scikit-learn
