# src/ — Código-fonte do AgroRisk AI

Esta pasta contém todo o código-fonte desenvolvido para o projeto AgroRisk AI, organizado em módulos por responsabilidade.

## Estrutura

| Pasta | Responsabilidade |
|-------|-----------------|
| `data/` | Pipeline de ETL: geração de dados simulados, feature engineering e carga no SQL |
| `sql/` | DDL, seed data, views e dicionário de dados do banco relacional |
| `ml/` | Notebooks e scripts de Machine Learning (EDA, modelagem, avaliação, predição) |
| `dashboard/` | Interface visual Streamlit com mapa de risco, alertas e relatórios |

## Fluxo de Execução Esperado

1. `src/data/generate_dataset.py` → gera dados simulados em `data/raw/`
2. `src/data/feature_engineering.py` → cria features e salva em `data/processed/`
3. `src/sql/01_schema.sql` + `02_seed_data.sql` → cria banco SQLite/MySQL
4. `src/data/load_to_sql.py` → ingere dados processados no banco
5. `src/ml/01_eda.ipynb` → análise exploratória
6. `src/ml/02_modelagem.ipynb` → treinamento de modelos (Random Forest, XGBoost)
7. `src/ml/03_avaliacao.ipynb` → validação estatística (matriz de confusão, F1, AUC-ROC, RMSE)
8. `src/ml/04_predict.py` → predição em novos registros usando modelo salvo em `ml/models/`
9. `src/dashboard/app.py` → visualização interativa em Streamlit

## Contexto do Projeto

Este código-fonte é a implementação técnica da solução AgroRisk AI, previamente planejada na Sprint 1 (repositório: https://github.com/HenriqueSanchesSilva/challenger-sprint-1). Na Sprint 1 foram definidas as personas, user stories, arquitetura, variáveis do dataset e a proposta de modelo preditivo. Nesta Sprint 2, o objetivo é transformar o planejamento em código funcional: ML treinado, banco SQL persistindo scores de risco e dashboard com alertas.

