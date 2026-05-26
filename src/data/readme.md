# src/data
Dados brutos e processados do projeto.

- `raw/`: dados simulados dos sensores (CSV).
- `processed/`: dados apos engenharia de features (CSV).

Scripts:
- `generate_dataset.py`: gera dados simulados.
- `feature_engineering.py`: cria features de risco e normaliza.
- `load_to_sql.py`: carrega dados no banco SQL.
