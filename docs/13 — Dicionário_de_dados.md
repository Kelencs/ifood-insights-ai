# 13 — Dicionário de Dados

## CSV de entrada

| Campo | Tipo | Obrigatório | Descrição |
|---|---|---:|---|
| complaint_id | texto | Sim | Identificador sintético único |
| created_at | data/hora | Não | Data da reclamação |
| complaint_text | texto | Sim | Texto da reclamação |
| region | texto | Não | Região fictícia ou agregada |
| channel | texto | Não | Canal de origem fictício |

## CSV enriquecido

| Campo | Tipo | Obrigatório | Valores/regras |
|---|---|---:|---|
| complaint_id | texto | Sim | Preservar ID original |
| created_at | data/hora | Não | Preservar entrada |
| complaint_text | texto | Sim | Preservar texto sintético |
| category | texto | Sim | Taxonomia controlada |
| subcategory | texto | Não | Subcategoria opcional |
| sentiment | texto | Sim | positivo, neutro, negativo, indeterminado |
| severity | texto | Sim | baixa, media, alta, indeterminada |
| evidence | texto | Não | Trecho curto literal |
| rationale | texto | Não | Justificativa concisa |
| review_required | booleano | Sim | true/false |
| review_reason | texto | Não | Motivo da revisão |
| model_name | texto | Sim | Modelo utilizado |
| prompt_version | texto | Sim | Ex.: 0.1.0 |
| processed_at | data/hora | Sim | Momento do processamento |

## Taxonomia inicial

- `atraso_entrega`
- `pedido_incorreto`
- `qualidade_produto`
- `pagamento`
- `cancelamento`
- `atendimento`
- `outros`
- `indeterminado`

A categoria `outros` deve ser usada quando o tema é compreensível, mas não cabe nas categorias existentes. `indeterminado` deve ser usada quando não há informação suficiente para classificar.

## Regras

- Não criar categorias novas durante a execução sem controle de versão.
- Não inferir região ou horário a partir do texto.
- Preservar valores ausentes como nulos.
- Datas devem usar formato consistente, preferencialmente ISO 8601.
- Identificadores devem ser únicos.
