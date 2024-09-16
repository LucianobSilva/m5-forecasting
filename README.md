# m5-forecasting

# Projeto de Previsão de Vendas com Séries Temporais

Este projeto realiza a previsão de vendas utilizando diferentes abordagens de modelos de séries temporais, incluindo **Exponential Smoothing**, **ARIMA**, e **Prophet**. O objetivo principal é analisar o desempenho de cada modelo e comparar as previsões com base em diferentes métricas de erro.

## Estrutura do Projeto

- `static_data/`: Contém os arquivos de entrada necessários para a análise.
- `Outputs/`: Diretório onde os arquivos de saída (como previsões e relatórios) são salvos.

## Instalação e Configuração

### 2. Criar Ambiente Virtual

```bash
python -m venv .env
.env\Scripts\activate # Windows
source .env/bin/activate #Bash/Linux
```

### 3. Instalar Dependências
pip install -r requirements.txt


## Como Executar o Projeto
1. Carregar os Dados
Os arquivos estáo localizados em :
https://www.kaggle.com/competitions/m5-forecasting-accuracy/code?competitionId=18599&sortBy=voteCount&excludeNonAccessedDatasources=true

Arquivos necessarios: 
- calendar.csv: Contém informações de datas e eventos.
- sales_train_evaluation.csv: Contém os dados históricos de vendas.

### 4. Análise basica de Exploratória de Dados (EDA)
Na etapa de EDA, é realizada a visualização básica dos dados de vendas, incluindo:

Distribuição de Vendas: Um histograma que mostra a densidade das vendas.
Vendas por Categoria (cat_id): Um gráfico de barras que exibe o total de vendas por categoria nos últimos 30 dias.

### 5. Modelagem de Séries Temporais
Três modelos principais de séries temporais foram usados para previsão:

Exponential Smoothing: Modelo que atribui mais peso às observações mais recentes.
ARIMA: Combina regressão e médias móveis para capturar padrões de longo prazo.
Prophet: Modelo aditivo desenvolvido pelo Facebook, que lida bem com efeitos sazonais.


Divisão de Dados:

- Treino: Dados até os últimos 30 dias.
Validação: Últimos 60 dias de vendas para validação das previsões.
Comparação de Modelos:
- Cada modelo foi avaliado utilizando RMSE (Root Mean Squared Error). As previsões de cada modelo foram comparadas visualmente com os dados reais, e os erros foram calculados.

### 7. Análise do Erro de Backtesting
Durante a validação do modelo de previsão, utilizei o método de Exponential Smoothing para prever as vendas diárias dos últimos 30 dias, comparando os resultados previstos com os dados reais. O modelo apresentou um erro de 2.31.

Comparação com outros modelos:

O erro de 2.31 foi calculado utilizando o backtesting e está sendo comparado com outros modelos de previsão, como ARIMA e Prophet. Por exemplo, o erro desses modelos foi maior, isso sugere que o Exponential Smoothing apresentou uma performance superior nesta aplicação específica.
Escala dos dados:

O valor de 2.31 significa que, em média, o modelo está errando por aproximadamente 2.31 unidades de vendas por dia.

<font color="Green">Conclusão:</font>.

O erro de 2.31 sugere que o modelo é relativamente preciso, especialmente em comparação com outras abordagens. Contudo, para uma avaliação completa, o erro deve ser analisado em conjunto com outras métricas e comparado com os resultados de modelos alternativos.


### 7. Resultados
O modelo Exponential Smoothing apresentou um erro médio de 2.31 unidades de vendas por dia, indicando uma boa precisão comparado aos demais modelos.

### Próximos Passos
Como estamos lidando com previsões diárias de vendas, é importante avaliar se esse erro é aceitável dado o volume de vendas diário. Por exemplo, se as vendas médias diárias forem em torno de 100 unidades, um erro de 2.31 seria considerado pequeno e o modelo estaria performando bem.

### Contribuições

Contribuições são bem-vindas! Se tiver sugestões ou melhorias, fique à vontade para abrir uma issue ou enviar um pull request.