# 14 — Decisões de Produto e Definition of Done

## Registro de decisões

### ADR-001 — CSV como armazenamento inicial
**Decisão:** utilizar CSV/JSON no MVP.  
**Motivo:** reduzir esforço de infraestrutura e acelerar validação.  
**Consequência:** atualização do Power BI inicialmente manual; sem concorrência multiusuário ou histórico transacional.

### ADR-002 — IA para classificação assistida
**Decisão:** utilizar API de modelo de linguagem para interpretar textos.  
**Motivo:** avaliar capacidade de compreender linguagem natural e devolver dados estruturados.  
**Consequência:** exige controle de custo, validação de schema e testes de qualidade.

### ADR-003 — Power BI para camada analítica
**Decisão:** usar Power BI para visualização e exploração.  
**Motivo:** separar processamento de linguagem e análise gerencial.  
**Consequência:** arquivo de saída precisa manter schema estável.

### ADR-004 — Dados sintéticos
**Decisão:** utilizar dados sintéticos no repositório público.  
**Motivo:** evitar exposição de dados pessoais ou proprietários.  
**Consequência:** os resultados demonstram funcionamento técnico, não desempenho real de operação.

## Definition of Ready (DoR)

Uma história está pronta para desenvolvimento quando:
- problema e valor estão descritos;
- critérios de aceite são verificáveis;
- dependências estão identificadas;
- dados e regras necessários estão definidos;
- dúvidas relevantes foram resolvidas.

## Definition of Done (DoD)

Uma entrega está concluída quando:
- atende aos critérios de aceite;
- possui testes relevantes;
- trata erros esperados;
- não expõe credenciais ou dados pessoais;
- está documentada;
- foi revisada;
- os resultados são reproduzíveis ou suas limitações estão descritas.

## Checklist de lançamento do MVP

- [ ] Base sintética documentada.
- [ ] Taxonomia versionada.
- [ ] Prompt versionado.
- [ ] Testes de IA executados.
- [ ] Métricas calculadas e registradas.
- [ ] CSV enriquecido validado.
- [ ] Dashboard conciliado com a base.
- [ ] README atualizado.
- [ ] Aviso de projeto independente visível.
