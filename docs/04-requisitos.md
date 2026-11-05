# 04 — Requisitos Funcionais e Não Funcionais

## Requisitos funcionais

| ID | Requisito | Prioridade | Critério resumido |
|---|---|---|---|
| RF01 | Importar CSV | Must | Ler arquivo no formato documentado |
| RF02 | Validar estrutura | Must | Verificar colunas obrigatórias e tipos |
| RF03 | Validar registros | Must | Sinalizar texto vazio e campos inválidos |
| RF04 | Identificar duplicidades | Should | Sinalizar IDs ou textos duplicados conforme regra |
| RF05 | Classificar categoria | Must | Retornar categoria da taxonomia |
| RF06 | Classificar sentimento | Must | Retornar valor permitido |
| RF07 | Estimar gravidade | Must | Retornar nível e justificativa |
| RF08 | Identificar evidências | Must | Citar trecho curto do texto de origem |
| RF09 | Sinalizar incerteza | Must | Encaminhar casos ambíguos para revisão |
| RF10 | Gerar recomendações | Should | Relacionar recomendação a padrões observados |
| RF11 | Exportar resultados | Must | Gerar CSV/JSON validado |
| RF12 | Exibir indicadores no Power BI | Must | Apresentar medidas e filtros |
| RF13 | Filtrar por período/categoria | Should | Atualizar visuais conforme seleção |
| RF14 | Comparar períodos | Could | Comparação descritiva quando houver datas |

## Requisitos não funcionais

| ID | Requisito | Critério |
|---|---|---|
| RNF01 | Segurança | Chaves não podem ser salvas no repositório |
| RNF02 | Privacidade | Usar dados sintéticos ou anonimizados |
| RNF03 | Rastreabilidade | Registrar ID, modelo e versão do prompt |
| RNF04 | Robustez | Tratar timeout, limite e erro de API |
| RNF05 | Integridade | Não perder vínculo entre entrada e saída |
| RNF06 | Transparência | Distinguir observação, inferência e recomendação |
| RNF07 | Manutenibilidade | Separar validação, IA e exportação em módulos |
| RNF08 | Reprodutibilidade | Registrar parâmetros relevantes do processamento |

## Priorização MoSCoW

- **Must have:** importação, validação, classificação, saída estruturada, exportação e dashboard básico.
- **Should have:** recomendações agregadas, identificação de duplicidades e filtros adicionais.
- **Could have:** comparação avançada, interface web e armazenamento em banco.
- **Won't have no MVP:** integração real com iFood, automação de decisões e previsão de demanda/reclamações.
