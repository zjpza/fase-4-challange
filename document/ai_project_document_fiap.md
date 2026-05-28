
<img src="../assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=30% height=30%>

# AI Project Document - Módulo 1 - FIAP

**_Os trechos em itálico servem apenas como guia para o preenchimento da seção. Por esse motivo, não devem fazer parte da documentação final_**

## Nome do Grupo

**AgroRisk AI — Grupo Sompo Sprint**

#### Nomes dos integrantes do grupo

| Nome | RM | GitHub |
|------|----|--------|
| Henrique Sanches Silva | RM 570527 | [@HenriqueSanchesSilva](https://github.com/HenriqueSanchesSilva) |
| João Pedro Zavanela Andreu | RM 570231 | [@zjpza](https://github.com/zjpza) |
| Kayck Gabriel Evangelista da Silva | RM 572331 | [@Kayckxz](https://github.com/Kayckxz) |
| Luis Henrique Laurentino Boschi | RM 571352 | [@lhboschi](https://github.com/lhboschi) |
| Patrick Borges de Melo | RM 574030 | [@Trickmelo](https://github.com/Trickmelo) |

**Tutora:** Sabrina Otoni | **Coordenador:** André Godoi

---

## Sumário

[1. Introdução](#c1)

[2. Visão Geral do Projeto](#c2)

[3. Desenvolvimento do Projeto](#c3)

[4. Resultados e Avaliações](#c4)

[5. Conclusões e Trabalhos Futuros](#c5)

[6. Referências](#c6)

[Anexos](#c7)

<br>

# <a name="c1"></a>1. Introdução

## 1.1. Escopo do Projeto

### 1.1.1. Contexto da Inteligência Artificial

O setor agrícola brasileiro é um dos maiores do mundo, com frotas de equipamentos que representam investimentos de R$ 500 mil a R$ 2 milhões por unidade. No entanto, esses equipamentos estão permanentemente expostos a riscos operacionais e ambientais (atolamentos, danos mecânicos, colisões, acidentes de transporte). A seguradoras enfrentam custos elevados de sinistros e não dispõem de sistemas inteligentes para prever e mitigar esses riscos antes que ocorram.

A aplicação de Inteligência Artificial no agronegócio tem crescido globalmente. Técnicas de Machine Learning supervisionado são utilizadas para cruzar dados de sensores IoT, condições climáticas, geolocalização e histórico de manutenção, permitindo a geração de scores de risco em tempo real. No Brasil, iniciativas como as da EMBRAPA e INMET fornecem dados abertos que podem ser integrados a soluções preditivas.

A Sompo Seguros, um dos maiores grupos seguradores do mundo, busca transformar sua atuação de reativa para preventiva, utilizando dados para reduzir a frequência e severidade de sinistros agrícolas. Este projeto atua nesse contexto, desenvolvendo uma solução de IA aplicada à gestão de risco operacional em frotas agrícolas.

### 1.1.2. Descrição da Solução Desenvolvida

O **AgroRisk AI** é um sistema de análise preditiva de risco para equipamentos agrícolas que cruza dados ambientais, operacionais e históricos para gerar alertas preventivos e recomendar ações antes que incidentes ocorram.

A solução consolida variáveis como proximidade de corpos d'água, umidade do solo, declividade do terreno, condições climáticas e histórico de uso dos equipamentos. Esses dados são processados em um banco SQL e alimentam modelos preditivos de Machine Learning que classificam o nível de risco em quatro categorias: Baixo, Médio, Alto e Crítico.

O sistema entrega valor para três personas principais:
- **Operador de Equipamento:** recebe alertas simples e visuais no celular com recomendações claras
- **Gestora de Frota:** visualiza em dashboard o status de risco de toda a frota em tempo real
- **Analista da Seguradora:** acessa histórico auditável de riscos e alertas para avaliação de sinistros

## <a name="c2"></a>2. Visão Geral do Projeto

## 2.1. Objetivos do Projeto

Os objetivos do projeto foram definidos para atender ao desafio proposto pela Sompo Seguros no Challenge Sprint FIAP:

1. **Identificar fatores que elevam a probabilidade de sinistros operacionais** em frotas agrícolas, cruzando variáveis ambientais (clima, solo, declividade, proximidade de água), operacionais (velocidade, carga, horas de uso) e históricas (manutenção, incidentes anteriores).

2. **Gerar alertas preventivos** que permitam aos operadores e gestores tomar decisões antes que ocorra o incidente, mudando o paradigma da gestão de seguros de reativa para preventiva.

3. **Persistir e auditar o histórico de risco** em um banco de dados SQL, garantindo rastreabilidade para o Analista da Seguradora e apoiando decisões de precificação e renovação de apólices.

4. **Desenvolver modelos de Machine Learning** capazes de classificar níveis de risco com métricas de validação estatística (matriz de confusão, F1-score, AUC-ROC, RMSE).

## 2.2. Público-Alvo

O público-alvo da solução é dividido em três personas principais, mapeadas a partir do entendimento do problema:

**Carlos, Operador de Colheitadeira (38 anos, Mato Grosso):**
- 12 anos de experiência operando equipamentos agrícolas
- Usa smartphone básico e não tem familiaridade com sistemas complexos
- Precisa de alertas simples, visuais e em linguagem acessível
- Principal dor: falta de informação sobre condições do solo antes de entrar em uma área

**Fernanda, Gestora de Frota Agrícola (44 anos, Cuiabá):**
- Gerencia frota de 15 equipamentos e 30 operadores
- Usa computador e aplicativos de gestão diariamente
- Precisa de visibilidade em tempo real e relatórios para justificar investimentos
- Principal dor: só descobre problemas após o incidente ocorrer

**Ricardo, Analista de Sinistros da Sompo (35 anos, São Paulo):**
- Avalia e aprova sinistros agrícolas
- Alto letramento digital e experiência com análise de dados
- Precisa de dados objetivos e histórico de comportamento de risco
- Principal dor: falta de dados objetivos no momento do sinistro

## 2.3. Metodologia

O projeto segue uma abordagem ágil baseada em sprints, com as seguintes etapas:

**Sprint 1 (Fase 2): Planejamento e Estruturação**
- Entendimento do problema com a Sompo Seguros
- Definição de personas e user stories
- Mapeamento de fontes de dados e variáveis
- Criação do dataset simulado inicial (20 registros)
- Proposta de arquitetura da solução e modelo preditivo
- Entrega da documentação e apresentação em vídeo

**Sprint 2 (Fase 4 — atual): Implementação Técnica**
- Expansão do dataset simulado com maior volume e variedade
- Implementação do banco de dados SQL (DDL, índices, constraints)
- Desenvolvimento do pipeline de ETL (geração, feature engineering, ingestão)
- Análise exploratória de dados (EDA) e engenharia de features
- Treinamento e avaliação de modelos de Machine Learning
- Desenvolvimento do dashboard com alertas em tempo real
- Validação estatística com métricas (matriz de confusão, F1-score, AUC-ROC, RMSE)

**Sprints Futuras:**
- Sprint 3: Refinamento do modelo, API funcional, integração completa
- Sprint 4: Testes, protótipo funcional para apresentação final

## <a name="c3"></a>3. Desenvolvimento do Projeto

## 3.1. Tecnologias Utilizadas

| Camada | Tecnologia | Justificativa |
|--------|-----------|---------------|
| Linguagem | Python 3.10+ | Amplamente utilizado em Data Science e ML, com grande comunidade |
| Manipulação de Dados | Pandas, NumPy | Bibliotecas padrão para ETL e análise de dados tabulares |
| Machine Learning | Scikit-learn | Framework robusto com algoritmos de classificação e regressão implementados |
| Visualização | Matplotlib, Seaborn | Bibliotecas para EDA e geração de gráficos estatísticos |
| Dashboard | Streamlit | Framework simples para criar interfaces web de dados com poucas linhas de código |
| Banco de Dados | SQLite (prototipação) / MySQL (produção) | SQLite para desenvolvimento local; MySQL para escalabilidade |
| ORM / Conexão | SQLAlchemy | Abstração para interação com o banco de dados |
| Ambiente | Jupyter Notebook | Iteração rápida em análise exploratória e modelagem |

## 3.2. Modelagem e Algoritmos

### Abordagem Híbrida: Classificação + Regressão

A solução adota uma abordagem com dois outputs principais:

**1. Score de Risco (Regressão):**
- Saída contínua de 0 a 100
- Representa a probabilidade ponderada de ocorrência de um incidente
- Gerado a cada novo registro de telemetria

**2. Classificação de Risco (Classificação):**
- Faixas: Baixo (0–25) / Médio (26–50) / Alto (51–75) / Crítico (76–100)
- Baseado no score calculado
- Dispara alertas quando nível ≥ Alto

### Algoritmos Escolhidos

Foram escolhidos **Random Forest** e **XGBoost** como algoritmos candidatos pela seguinte justificativa técnica:

- **Lidam bem com variáveis de tipos mistos** (numéricas e categóricas como tipo de solo e equipamento)
- **São robustos a dados faltantes**, situação comum em sensores IoT em áreas rurais
- **Permitem interpretabilidade via feature importance**, essencial para justificar alertas ao operador e ao analista da seguradora
- **Apresentam bom desempenho sem necessidade de grandes volumes de dados iniciais**, adequado para a fase de prototipação

### Features de Entrada

```python
features = [
    'precipitacao_mm',
    'umidade_solo_pct',
    'tipo_solo_encoded',
    'proximidade_agua_m',
    'declividade_graus',
    'horas_uso_equipamento',
    'dias_ultima_manutencao',
    'velocidade_operacao_kmh',
    'carga_pct',
    'historico_incidentes',
    'temperatura_c',
    'velocidade_vento_kmh'
]
```

### Saída Esperada do Modelo

```json
{
  "score_risco": 74,
  "nivel_risco": "Alto",
  "alerta": true,
  "recomendacao": "Solo saturado e proximidade de corpo d'água detectados. Recomenda-se suspender a operação no setor e aguardar 48h.",
  "fatores_principais": ["umidade_solo_pct", "proximidade_agua_m", "precipitacao_mm"]
}
```

## 3.3. Treinamento e Teste

### Conjunto de Dados

O dataset utilizado é simulado, construído com base em cenários reais de operação agrícola. As variáveis foram definidas a partir de fontes de dados identificadas:

| Fonte | Tipo de Dado |
|-------|-------------|
| Sensores IoT no equipamento | Velocidade, temperatura, carga, combustível |
| GPS embarcado | Localização, rota |
| INMET / Open-Meteo | Chuva, vento, temperatura, umidade |
| EMBRAPA / MapBiomas | Tipo de solo, declividade |
| Sistema interno (ERP) | Histórico de manutenção e incidentes |

O dataset inicial da Sprint 1 continha 20 registros com valores coerentes para cenários de baixo, médio, alto e crítico risco. Nesta Sprint, o dataset será expandido para treinamento e validação dos modelos.

### Métricas de Avaliação

| Métrica | Justificativa |
|---------|--------------|
| **Recall (classe Alto/Crítico)** | Prioriza evitar falsos negativos — um sinistro não previsto é mais custoso que um falso alarme |
| **F1-score** | Equilíbrio entre precisão e recall nas classificações |
| **RMSE / MAE** | Avaliação da regressão (score 0–100) |
| **AUC-ROC** | Decisão binária de emitir ou não o alerta |
| **Feature Importance** | Interpretabilidade para justificar alertas |

> Nota: as metas numéricas de cada métrica serão definidas após a EDA, com base na distribuição real dos dados expandidos.

### Validação

- Divisão treino/teste: 80/20 estratificada pela classe de risco
- Validação cruzada (cross-validation) para evitar overfitting
- Análise da matriz de confusão para identificar padrões de erro por classe

## <a name="c4"></a>4. Resultados e Avaliações

## 4.1. Análise dos Resultados

*(Esta seção será preenchida após a execução da Sprint 2, com as métricas reais dos modelos treinados.)*

Resultados esperados:
- Modelo de classificação capaz de distinguir corretamente os níveis de risco
- Score de risco que reflita a combinação ponderada das variáveis ambientais e operacionais
- Dashboard com visualização clara por equipamento e região
- Histórico de risco persistido e auditável no banco SQL

## 4.2. Feedback dos Usuários

*(Esta seção será preenchida após testes com usuários nas próximas sprints.)*

## <a name="c5"></a>5. Conclusões e Trabalhos Futuros

### Pontos Fortes
- Solução alinhada a um problema real do setor segurador
- Arquitetura modular que permite evolução incremental
- Escolha de algoritmos interpretáveis (Random Forest, XGBoost) que permitem justificar decisões
- Pipeline completo: desde a coleta dos dados até a visualização do risco

### Pontos a Melhorar
- Integração com APIs reais de clima (INMET) e solo (EMBRAPA)
- Expansão do dataset com dados reais de parceiros agrícolas
- Implementação de notificações push para o operador
- Modelo em produção com atualização contínua (online learning)

### Próximos Passos
- **Sprint 3:** Refinar o modelo com mais dados, desenvolver a API REST com FastAPI, e integrar com fontes externas de dados
- **Sprint 4:** Testes integrados, deploy em nuvem (AWS/Azure), e protótipo funcional para apresentação ao Festival NEXT

## <a name="c6"></a>6. Referências

- FIAP — Challenge Sprint Sompo Seguros 2024/2025
- Documentação do projeto da Sprint 1: https://github.com/HenriqueSanchesSilva/challenger-sprint-1
- Scikit-learn Documentation: https://scikit-learn.org/stable/
- INMET — Instituto Nacional de Meteorologia: https://www.inmet.gov.br/
- EMBRAPA — Empresa Brasileira de Pesquisa Agropecuária: https://www.embrapa.br/
- Open-Meteo API: https://open-meteo.com/
- XGBoost Documentation: https://xgboost.readthedocs.io/

# <a name="c7"></a>Anexos

### Anexo A — User Stories Mapeadas

| ID | Persona | User Story |
|----|---------|-----------|
| US-01 | Operador | Como operador, quero receber um alerta visual no celular antes de entrar em uma área de alto risco |
| US-02 | Operador | Como operador, quero ver uma recomendação clara em linguagem simples |
| US-03 | Operador | Como operador, quero registrar manualmente a ocorrência de um incidente |
| US-04 | Gestora | Como gestora, quero visualizar em um mapa o status de risco de cada equipamento em tempo real |
| US-05 | Gestora | Como gestora, quero receber relatórios semanais automáticos com indicadores de risco |
| US-06 | Gestora | Como gestora, quero filtrar o histórico por equipamento, operador ou região |
| US-07 | Analista | Como analista, quero acessar o histórico de alertas emitidos antes de um sinistro |
| US-08 | Analista | Como analista, quero consultar o score de risco acumulado por apólice |
| US-09 | Analista | Como analista, quero exportar dados consolidados de risco por região e tipo de equipamento |

### Anexo B — Diagrama de Arquitetura da Solução

Ver imagem anexa no repositório Sprint 1: `https://github.com/HenriqueSanchesSilva/challenger-sprint-1`
