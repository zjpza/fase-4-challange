# src/dashboard
Interface visual do projeto AgroRisk AI.

## Objetivo

Desenvolver dashboards interativos que permitam a visualização dos níveis de risco por equipamento e região, acompanhamento de alertas em tempo real e filtragem por persona (operador, gestor, analista).

## Telas e Funcionalidades (a implementar na Sprint 2)

- **Mapa de Risco:** visualização geoespacial com localização de cada equipamento e cor indicativa do nível de risco (verde=baixo, amarelo=médio, laranja=alto, vermelho=crítico). Atende US-04 (Gestora).
- **Alertas em Tempo Real:** painel com alertas ativos, horário, equipamento e recomendação. Atende US-01 (Operador).
- **Evolução Temporal do Risco:** gráficos de linha mostrando histórico de score por equipamento ao longo do tempo. Atende US-05 (Gestora).
- **Histórico de Alertas:** tabela filtrável com todos os alertas emitidos por período. Atende US-07 (Analista).
- **Filtros por Persona:**
  - Operador: alertas simples, visuais, linguagem acessível
  - Gestor: mapa da frota, relatórios semanais, filtros por equipamento/região
  - Analista: histórico auditável, exportação de dados, score acumulado por apólice

## Arquivos (a criar na Sprint 2)

- `app.py`: aplicação principal em Streamlit com todas as telas.
- `index.html`: layout alternativo se optar por Flask + templates HTML.

## Para Executar

```bash
streamlit run src/dashboard/app.py
```

A aplicação será acessível em `http://localhost:8501`
