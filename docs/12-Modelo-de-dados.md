# 12 — Modelo de Dados

## Entidade principal: Reclamação

Cada linha representa uma reclamação sintética ou devidamente anonimizada.

### Fluxo lógico

```text
RECLAMACAO_ORIGINAL
  complaint_id (PK)
  created_at
  complaint_text
  region (opcional)
  channel (opcional)
        |
        | 1:1 por complaint_id
        v
ANALISE_IA
  complaint_id (FK)
  category
  subcategory
  sentiment
  severity
  evidence
  rationale
  review_required
  model_name
  prompt_version
  processed_at
```

Para o MVP, as duas estruturas podem ser exportadas em um único CSV enriquecido. A separação lógica ajuda a preservar a origem e permite evoluir para tabelas distintas.

## Campos de saída da IA

- `category`: categoria principal.
- `subcategory`: subcategoria opcional.
- `sentiment`: positivo, neutro, negativo ou indeterminado.
- `severity`: baixa, media, alta ou indeterminada.
- `evidence`: trecho curto do texto que sustenta a classificação.
- `rationale`: justificativa concisa.
- `review_required`: booleano.
- `review_reason`: motivo da revisão, quando aplicável.
- `model_name`: modelo utilizado.
- `prompt_version`: versão do prompt.

## Granularidade

A granularidade do fato principal é uma reclamação por `complaint_id`. Indicadores devem contar IDs únicos para evitar duplicidade.
