# 🛒 Análise Exploratória — Dados de Vendas (Food Delivery)
 
## 📄 Resumo
 
Este projeto realiza uma análise exploratória completa sobre um dataset de histórico de pedidos de delivery de alimentos. O objetivo é responder perguntas de negócio por meio de análise de dados, abrangendo volume de pedidos, métricas financeiras, eficiência logística, satisfação do cliente e comportamento de cancelamentos.
 
Os dados foram obtidos no [Kaggle](https://www.kaggle.com) e a análise foi desenvolvida em Python com foco em **Análise Descritiva**, **Feature Engineering** e **Visualização de Dados**.

---
 
## 🛠️ Tecnologias Utilizadas
 
| Ferramenta | Uso |
|---|---|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Linguagem principal |
| `pandas` | Manipulação e limpeza de dados |
| `matplotlib` | Visualizações base |
| `seaborn` | Gráficos estatísticos |
| `numpy` | Operações numéricas |
| `TextBlob` | Análise de sentimentos em reviews |
| Google Colab | Ambiente de desenvolvimento |
---
 
## 📁 Estrutura do Projeto
 
```
📦 dados-vendas/
 ┣ 📓 DadosVendas.ipynb       # Notebook principal com toda a análise
 ┣ 📄 dadosvendas.py          # Script exportado do notebook
 ┗ 📊 order_history_kaggle_data.csv  # Dataset de pedidos
```
 
---
 
## 📌 Contexto
 
O dataset contém registros de pedidos de um serviço de delivery, incluindo informações de:
 
- Data e hora do pedido
- Distância de entrega
- Tempo de preparo (KPT) e tempo de espera do entregador
- Valores financeiros: subtotal, descontos e total
- Avaliações e reviews dos clientes
- Status e motivos de cancelamento/rejeição
- Localização (cidade e subzona)
 
---
 
## 💡 Etapas da Análise
 
### 1. 🧹 Limpeza e Preparação dos Dados
 
- **Conversão de datas** — coluna `Order Placed At` convertida de string para `datetime`
- **Limpeza da coluna de distância** — remoção do sufixo `km`, tratamento de valores `<1` (substituídos por `0.5`) e conversão para `float`
- **Padronização de strings** — remoção de espaços extras e capitalização consistente nas colunas `City` e `Subzone`
- **Tratamento de nulos nos descontos** — valores ausentes substituídos por `0` antes de operações matemáticas
 
### 2. ⚙️ Feature Engineering
 
Novas variáveis criadas a partir da data do pedido:
 
| Nova Coluna | Descrição |
|---|---|
| `Order Time` | Hora formatada (HH:MM:SS) |
| `Order Date` | Data do pedido |
| `Order Hour` | Hora do pedido (inteiro) |
| `Order Month` | Nome do mês |
| `Order Day of Week` | Nome do dia da semana |
| `Desconto Total` | Soma de todos os tipos de desconto |
