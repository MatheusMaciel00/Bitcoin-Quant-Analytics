# Bitcoin-Quant-Analytics

# 📈 Bitcoin Algorithmic Trading & Analytics Pipeline

> **Projeto End-to-End de Dados:** Engenharia de Dados, Análise Quantitativa e Business Intelligence.

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow)
![SQL](https://img.shields.io/badge/Database-SQLite-lightgrey)

## 📋 Sobre o Projeto
Este projeto simula a rotina de um **Analista de Dados Quantitativos**. O objetivo foi construir um pipeline automatizado que extrai dados financeiros, executa um backtest de estratégia de trading (Mean Reversion) e disponibiliza os resultados em um Dashboard Executivo para tomada de decisão.

A solução cobre todo o ciclo de vida dos dados: **ETL -> Modelagem -> Armazenamento -> Visualização**.

---

## 🛠 Tech Stack (Ferramentas Utilizadas)
* **Python (Pandas, Numpy, YFinance):** Extração de dados (API), limpeza e cálculo de indicadores técnicos.
* **Vectorbt / Lógica Proprietária:** Motor de Backtesting e validação de estratégia.
* **SQL (SQLite):** Persistência dos dados de trades e histórico de capital (Data Warehousing leve).
* **Power BI:** Conexão via Driver ODBC para leitura do banco SQL e criação de Dashboard Interativo.
* **DAX:** Criação de medidas de performance (Win Rate, Drawdown, ROI).

---

## 📊 O Pipeline de Dados

1.  **Ingestão:** O script Python baixa dados históricos do Bitcoin (BTC-USD) via API do Yahoo Finance.
2.  **Processamento:** Cálculo de médias móveis e desvios padrão para identificar pontos de entrada/saída.
3.  **Backtest:** Simulação de 2 anos de operações com capital inicial de $10.000.
4.  **Carga (Load):** Os resultados (trades, lucro/prejuízo, data) são salvos automaticamente em um banco de dados `track_record_quant.db`.
5.  **Analytics:** O Power BI consome esse banco de dados para gerar relatórios dinâmicos.

---

## 📈 Resultados da Estratégia (Backtest)

### Dashboard Executivo
O painel abaixo demonstra a evolução patrimonial e métricas de risco da estratégia.

[INSIRA O SEU PRINT DO POWER BI AQUI]

### KPIs Principais:
* **Lucro Líquido:** +$600.00 (6% de Retorno no Período)
* **Win Rate:** 25% (Foco em Assimetria de Risco: Ganhos longos, perdas curtas)
* **Total de Trades:** 245 operações automatizadas.

---

## 🧠 Análise Crítica (Post-Mortem)
*Nota do Analista:*

Embora a estratégia tenha fechado no lucro, observou-se uma taxa de acerto (Win Rate) baixa de 25%. Isso ocorre devido à natureza de **Tendência (Momentum)** do Bitcoin. Estratégias de **Reversão à Média** (como a utilizada) tendem a sofrer em fortes tendências de alta, pois tentam vender o ativo enquanto ele continua subindo.

**Melhoria Proposta:** Para versões futuras, recomenda-se a implementação de um filtro de tendência (ex: Média Móvel de 200 períodos) para desligar o robô em fortes altas, ou migrar para uma estratégia de *Trend Following*.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
* Python 3.x
* Power BI Desktop
* Driver ODBC para SQLite

### Passo a Passo
1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/SEU-USUARIO/NOME-DO-PROJETO.git](https://github.com/SEU-USUARIO/NOME-DO-PROJETO.git)
    ```
2.  **Instale as dependências:**
    ```bash
    pip install pandas yfinance pandas_ta sqlalchemy
    ```
3.  **Gere os Dados:**
    Execute o arquivo `notebook.ipynb` ou o script principal. Ele criará o arquivo `track_record_quant.db` automaticamente.
4.  **Visualize:**
    Abra o arquivo `dashboard_investimentos.pbix`. Se necessário, ajuste o caminho do banco de dados na configuração ODBC.

---

## 📬 Contato
**Matheus**
[Seu LinkedIn aqui]
