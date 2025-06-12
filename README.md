# 📈 Markov Trading System

Sistema de trading algorítmico baseado em Cadeias de Markov para análise e predição de movimentos de preços no mercado financeiro.

## 🎯 Objetivo

Este projeto implementa uma estratégia de trading quantitativo que utiliza Cadeias de Markov para modelar e prever transições entre diferentes estados de mercado (Aumento, Diminuição, Estável).

A matriz de transição obtida durante o treinamento revela uma forte persistência nos estados do mercado, ou seja, há uma alta probabilidade de que movimentos de alta ou baixa sejam seguidos por movimentos na mesma direção. Essa característica indica a presença de um comportamento com **drift**, onde os estados passados influenciam os estados futuros, ainda que o mercado mantenha um certo grau de aleatoriedade. Apesar dessa dependência temporal identificada, a estratégia baseada nesse modelo apresentou desempenho negativo no período de teste, evidenciando que padrões probabilísticos por si só não garantem lucratividade. O projeto, portanto, explora a aplicabilidade de modelos estocásticos como ferramenta de análise, servindo como base para estratégias mais sofisticadas e robustas.


### Dependências Necessárias
```python
# pip install yfinance==0.2.58
```

## 📊 Funcionalidades

### 1. Coleta e Preparação de Dados
- Download automático de dados históricos via Yahoo Finance
- Cálculo de retornos com período personalizável
- Classificação de movimentos em três estados baseado em limites definidos

### 2. Modelagem com Cadeia de Markov
- Construção de matriz de transição de estados
- Treinamento com dados históricos
- Cálculo de probabilidades de transição entre estados

### 3. Estratégia de Trading
- Geração de sinais baseada em probabilidades de transição
- Lógica de compra/venda com threshold configurável
- Posicionamento automático (Long/Short/Neutro)

### 4. Análise de Performance
- Cálculo de métricas financeiras (Sharpe Ratio, Drawdown, Volatilidade)
- Visualizações interativas multi-painel
- Relatório detalhado de resultados

## 🚀 Como Usar

### Configuração de Parâmetros
```python
# Parâmetros principais
ticker = "BOVA11.SA"           # Ativo a ser analisado
p = 5                          # Período para cálculo de retorno
limite_superior = 0.0175       # Threshold para classificar como "Aumento"
limite_inferior = -0.0175      # Threshold para classificar como "Diminuição"
year_train = "2022"            # Ano para treinamento
year_test = "2023"             # Ano para teste
threshold = 0.6                # Confiança mínima para gerar sinal
```

## 📈 Visualizações

O sistema gera um dashboard interativo com 4 painéis:

1. **Performance Cumulativa** - Evolução da estratégia ao longo do tempo
2. **Sinais de Trading** - Pontos de entrada/saída no gráfico de preços
3. **Distribuição de Estados** - Frequência de cada estado no período de teste
4. **Drawdown** - Análise de perdas máximas consecutivas

### 📊 Resultados

![Dashboard Principal](https://github.com/joaoal1998/Cadeias-de-Markov/blob/main/resultados_markov.png)
*Dashboard completo com os 4 painéis de análise*

## 📋 Métricas Calculadas

- **Retorno Total**: Performance absoluta da estratégia
- **Volatilidade**: Desvio padrão anualizado dos retornos
- **Sharpe Ratio**: Relação risco-retorno ajustado
- **Maximum Drawdown**: Maior perda consecutiva
- **Número de Trades**: Quantidade de operações executadas

## ⚠️ Importantes Considerações

- **Backtesting**: Os resultados são baseados em dados históricos e não garantem performance futura
- **Custos de Transação**: Não incluídos nos cálculos (podem impactar significativamente os resultados)
- **Risco**: Trading algorítmico envolve riscos substanciais de perda de capital

## ⚖️ Disclaimer

Disclaimer: Esta ferramenta é apenas para fins educacionais e de pesquisa. Não constitui aconselhamento financeiro. Sempre consulte um profissional qualificado antes de tomar decisões de investimento. O autor não se responsabiliza por perdas decorrentes do uso deste sistema.

---
