# 01 — Visão do Produto

## Identificação

| Campo | Definição |
|---|---|
| Produto | iFood Insights AI |
| Tipo | MVP experimental para portfólio |
| Product Owner | Kelen Cristina Silva |
| Domínio | Experiência do cliente e operações de delivery |
| Usuários principais | Gestores de operações e analistas de experiência |
| Status | Em definição |

## Visão

Transformar reclamações textuais em informações estruturadas e rastreáveis que ajudem equipes de operações a identificar problemas recorrentes, investigar suas possíveis causas e priorizar oportunidades de melhoria.

## Problema

A leitura e categorização manual de reclamações pode ser demorada e inconsistente. Quando os registros estão dispersos em arquivos, torna-se mais difícil consolidar indicadores, comparar períodos e identificar temas recorrentes.

## Proposta de valor

O produto combina processamento de dados, IA generativa e Business Intelligence para:

- reduzir o esforço inicial de triagem;
- padronizar a categorização;
- revelar tendências e temas recorrentes;
- apoiar a priorização com evidências;
- facilitar o acompanhamento por meio de dashboards.

## Objetivo do MVP

Validar, em uma base sintética ou anonimizada, se uma solução simples consegue classificar reclamações com qualidade mensurável e disponibilizar os resultados em formato adequado para análise no Power BI.

## Não objetivos

- Representar uma ferramenta oficial do iFood.
- Acessar sistemas internos ou dados proprietários.
- Tomar decisões automaticamente.
- Prever eventos sem dados e validação apropriados.
- Substituir equipes de atendimento ou operações.

## Hipóteses a validar

1. Uma taxonomia objetiva permite classificar os principais motivos de reclamação.
2. A IA consegue sugerir categorias e atributos com qualidade suficiente para apoiar triagem.
3. Os resultados estruturados são úteis para análise gerencial no Power BI.
4. Recomendações acompanhadas de evidências são mais acionáveis que resumos genéricos.

## Premissas

- A primeira versão utilizará dados fictícios.
- O processamento será executado localmente.
- A integração com IA será feita por API, com chave protegida em variável de ambiente.
- O Power BI consumirá arquivos estruturados exportados pelo processamento.

## Critérios de sucesso do produto

O MVP será considerado promissor se:
- processar uma base de demonstração de ponta a ponta;
- apresentar métricas de qualidade em conjunto de teste rotulado;
- exportar dados consistentes;
- alimentar um relatório Power BI com filtros e indicadores verificáveis;
- documentar limitações, erros conhecidos e decisões humanas necessárias.
