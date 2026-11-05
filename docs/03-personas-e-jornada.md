# 03 — Personas e Jornada

## Persona primária: Gestor(a) de Operações

**Perfil:** responsável por acompanhar indicadores operacionais, identificar problemas recorrentes e coordenar iniciativas de melhoria.

**Objetivos**
- Entender quais problemas aparecem com maior frequência.
- Identificar variações por período, região ou categoria, quando esses campos existirem.
- Priorizar investigações.
- Acompanhar se as ações adotadas estão associadas a mudanças nos indicadores.

**Dores**
- Volume alto de textos livres.
- Categorização manual inconsistente.
- Dificuldade para consolidar informações.
- Relatórios que mostram números, mas não explicam os temas recorrentes.

**Necessidades**
- Visão executiva simples.
- Filtros e detalhamento.
- Recomendações justificadas por evidências.
- Transparência sobre incerteza e limitações.

## Persona secundária: Analista de Experiência do Cliente

**Perfil:** analisa manifestações e feedbacks para identificar fricções na jornada do cliente.

**Objetivos**
- Explorar reclamações por tema.
- Encontrar termos e situações recorrentes.
- Avaliar sentimento e gravidade.
- Investigar exemplos individuais que expliquem os indicadores.

**Dores**
- Triagem repetitiva.
- Textos com linguagem informal, abreviações e erros.
- Dificuldade de transformar achados em recomendações objetivas.

## Jornada principal

| Etapa | Ação | Necessidade | Resposta esperada |
|---|---|---|---|
| Preparação | Seleciona CSV | Saber se o arquivo serve | Validação e resumo |
| Importação | Carrega dados | Evitar perda de registros | Contagem de válidos e inválidos |
| Análise | Inicia processamento | Classificar textos | Resultados estruturados |
| Revisão | Consulta incertezas | Confiar no resultado | Sinalização de revisão |
| Exploração | Abre Power BI | Entender padrões | Indicadores e filtros |
| Priorização | Analisa recomendações | Decidir próximos passos | Evidências e hipóteses |
| Acompanhamento | Compara períodos | Avaliar evolução | Tendências descritivas |

## Momentos críticos da experiência

- O arquivo não possui as colunas esperadas.
- A reclamação está vazia ou é ininteligível.
- A API está indisponível ou excede limites.
- A resposta da IA não segue o formato esperado.
- A IA não possui evidências suficientes para classificar.
- A amostra é pequena demais para sustentar uma conclusão.

Nesses casos, o sistema deve comunicar a limitação e não preencher lacunas com suposições.
