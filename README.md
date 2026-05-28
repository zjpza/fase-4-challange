# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Administração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

## FIAP + SOMPO — Predição de Risco Operacional em Frotas Agrícolas

## 👨‍🎓 Integrantes: 
- <a href="https://github.com/HenriqueSanchesSilva">Henrique Sanches Silva</a> — RM 570527
- <a href="https://github.com/zjpza">João Pedro Zavanela Andreu</a> — RM 570231
- <a href="https://github.com/Kayckxz">Kayck Gabriel Evangelista da Silva</a> — RM 572331
- <a href="https://github.com/lhboschi">Luis Henrique Laurentino Boschi</a> — RM 571352
- <a href="https://github.com/Trickmelo">Patrick Borges de Melo</a> — RM 574030

## 👩‍🏫 Professores:
### Tutor(a)

- Sabrina Otoni

### Coordenador(a)

- André Godoi

## 📜 Descrição

Projeto desenvolvido no Challenge Sprint FIAP em parceria com a Sompo Seguros. Objetivo: identificar fatores que elevam a probabilidade de sinistros operacionais em frotas agrícolas e gerar alertas preventivos via Machine Learning.

A solução — chamada **AgroRisk AI** — consolida dados de sensores e telemetria (distância até corpos d'água, umidade do solo, declividade, condições climáticas e histórico de uso), processa-os em um banco SQL e alimenta modelos preditivos que classificam o nível de risco por equipamento ou região — do baixo ao crítico. O resultado é apresentado em dashboards com alertas para Operadores e Gestores de Frota, permitindo uma gestão de segurança reativa a preventiva.

Além disso, todo o histórico de risco é persistido e auditável pelo Analista da Seguradora, garantindo rastreabilidade e confiança nas decisões tomadas.

Tecnologias: Python, Pandas, Scikit-learn, SQLite/MySQL, Streamlit/Flask.

## 🔄 Evolução do Projeto

Este repositório é a continuação do trabalho iniciado na [Sprint 1](https://github.com/HenriqueSanchesSilva/challenger-sprint-1). Na primeira fase, o grupo estruturou o planejamento, definiu personas, user stories, arquitetura da solução e um dataset simulado inicial com 20 registros. Nesta Sprint 2 (Fase 4), o foco é a implementação técnica: banco de dados SQL, modelos preditivos treinados e dashboards funcionais.

### 📋 Resumo da Sprint 1 (Contexto)

| Entrega | Status |
|---------|--------|
| Personas (Operador, Gestora, Analista) | ✅ Definidas |
| User Stories (US-01 a US-09) | ✅ Mapeadas |
| Dataset simulado inicial | ✅ 20 registros em `data/dataset_simulado.csv` |
| Arquitetura da solução | ✅ Proposta com sensores IoT → Pipeline → ML → Dashboard |
| Modelo preditivo (proposta) | ✅ Random Forest / XGBoost com score 0-100 |
| Métricas de avaliação | ✅ Recall, F1-score, RMSE, AUC-ROC, Feature Importance |
| Apresentação em vídeo | ✅ [YouTube](https://youtu.be/yq4IOYdmpwk) |

### 🎯 User Stories Priorizadas para Esta Sprint

As seguintes User Stories da Sprint 1 são o foco de implementação nesta entrega:

- **US-01** (Operador): Receber alerta visual antes de entrar em área de alto risco
- **US-04** (Gestora): Visualizar em mapa o status de risco de cada equipamento
- **US-07** (Analista): Acessar histórico de alertas emitidos antes de um sinistro

### 📊 Estrutura de Dados (mantida da Sprint 1)

| Variável | Tipo | Descrição |
|----------|------|-----------|
| `id_registro` | int | Identificador único |
| `id_equipamento` | string | Código do equipamento (ex: EQ-MT-0023) |
| `tipo_equipamento` | string | Colheitadeira / Trator / Pulverizador |
| `data_hora` | datetime | Timestamp do registro |
| `latitude` / `longitude` | float | Coordenadas geográficas |
| `tipo_operacao` | string | Campo ou Transporte |
| `proximidade_agua_m` | int | Distância de rios/lagos (metros) |
| `precipitacao_mm` | float | Chuva nas últimas 24h |
| `umidade_solo_pct` | float | Umidade do solo em % |
| `tipo_solo` | string | Argiloso / Arenoso / Misto |
| `declividade_graus` | float | Inclinação do terreno |
| `temperatura_c` | float | Temperatura ambiente |
| `velocidade_vento_kmh` | float | Velocidade do vento |
| `visibilidade_m` | int | Visibilidade em metros |
| `horas_uso_equipamento` | int | Horas totais de uso |
| `dias_ultima_manutencao` | int | Dias desde última manutenção |
| `velocidade_operacao_kmh` | float | Velocidade atual |
| `carga_pct` | float | % de capacidade de carga |
| `nivel_combustivel_pct` | float | Nível de combustível |
| `historico_incidentes` | int | Incidentes nos últimos 12 meses |
| `score_risco` | int | Score calculado (0–100) |
| `nivel_risco` | string | Baixo / Médio / Alto / Crítico |
| `alerta_gerado` | bool | Se alerta foi emitido |

## 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>.github</b>: Nesta pasta ficarão os arquivos de configuração específicos do GitHub que ajudam a gerenciar e automatizar processos no repositório.

- <b>assets</b>: aqui estão os arquivos relacionados a elementos não-estruturados deste repositório, como imagens, logos e screenshots.

- <b>config</b>: Posicione aqui arquivos de configuração que são usados para definir parâmetros e ajustes do projeto.

- <b>document</b>: aqui estão todos os documentos do projeto que as atividades poderão pedir. Na subpasta "other", adicione documentos complementares e menos importantes.

- <b>scripts</b>: Posicione aqui scripts auxiliares para tarefas específicas do seu projeto. Exemplo: deploy, migrações de banco de dados, backups.

- <b>src</b>: Todo o código fonte criado para o desenvolvimento do projeto ao longo das 7 fases.
  - <b>src/data</b>: Dataset simulado de sensores e scripts de ETL (geração, feature engineering, ingestão SQL).
  - <b>src/sql</b>: Schema DDL, seed data e views para persistência de telemetria e scores de risco.
  - <b>src/ml</b>: Notebooks de análise exploratória, treinamento de modelos, avaliação estatística e script de predição.
  - <b>src/dashboard</b>: Interface visual com mapa de risco, alertas em tempo real e evolução temporal.

- <b>README.md</b>: arquivo que serve como guia e explicação geral sobre o projeto (o mesmo que você está lendo agora).

## 🏗️ Arquitetura da Solução

O fluxo de dados da Sprint 1 foi refinado para esta entrega. A arquitetura é dividida em camadas:

```
[Sensores IoT / APIs] → [Coleta / ETL] → [Banco SQL] → [Modelos ML] → [Dashboard / Alertas]
     (Entrada)            (src/data)        (src/sql)     (src/ml)      (src/dashboard)
```

| Camada | Função | Tecnologia |
|--------|--------|------------|
| Ingestão | Gerar e processar dados simulados | Python, Pandas |
| Persistência | Armazenar dados e scores de risco | SQLite |
| Inteligência | Treinar modelos e gerar predições | Scikit-learn |
| Visualização | Exibir mapa, alertas e relatórios | Streamlit |

## 🔧 Como executar o código

### Pré-requisitos
- Python 3.10+
- pip ou conda

### Passo a passo

1. Clone o repositório:
```bash
git clone https://github.com/zjpza/fase-4-challange.git
cd fase-4-challange
```

2. Instale as dependências:
```bash
pip install -r requirements.txt
```

3. Execute os scripts na ordem:
```bash
# 1. Gerar dados simulados (expandido a partir do dataset da Sprint 1)
python src/data/generate_dataset.py

# 2. Criar features de risco e normalizar
python src/data/feature_engineering.py

# 3. Criar banco de dados SQLite com schema completo
sqlite3 sompo.db < src/sql/01_schema.sql

# 4. (Opcional) Inserir dados de exemplo
sqlite3 sompo.db < src/sql/02_seed_data.sql

# 5. Carregar dados processados no banco
python src/data/load_to_sql.py
```

4. Treinar e avaliar modelos ML:
```bash
# EDA (Análise Exploratória)
jupyter notebook src/ml/01_eda.ipynb

# Treinamento dos modelos
jupyter notebook src/ml/02_modelagem.ipynb

# Avaliação estatística
jupyter notebook src/ml/03_avaliacao.ipynb

# Predição em novos dados
python src/ml/04_predict.py
```

5. Rodar o dashboard:
```bash
streamlit run src/dashboard/app.py
```

## 🗃 Histórico de lançamentos

* 1.0.0 - 26/05/2026
    * Sprint 2 — Fase 4: estrutura de dados, banco SQL, modelos ML, dashboards e documentação
* 0.2.0 - XX/XX/2026
    * Sprint 1 — Fase 2: planejamento, arquitetura inicial e definição de User Stories
* 0.1.0 - XX/XX/2026
    * Kickoff do projeto e formação do grupo

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/zjpza/fase-4-challange">FIAP + SOMPO — Predição de Risco Operacional</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>
