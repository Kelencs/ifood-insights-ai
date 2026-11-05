# iFood Insights AI

**Plataforma experimental de análise de reclamações e inteligência operacional com IA generativa e Power BI.**

> Projeto independente de portfólio, inspirado em desafios comuns de operações de delivery. Não é uma solução oficial do iFood, não possui integração com sistemas do iFood e não utiliza dados internos ou dados pessoais reais.

## Problema

A análise manual de grandes volumes de reclamações pode consumir tempo e dificultar a identificação de padrões, prioridades e oportunidades de melhoria operacional.

## Solução proposta

O iFood Insights AI recebe uma base CSV de reclamações fictícias ou anonimizadas, valida os registros, utiliza IA generativa para classificar os textos e produzir análises estruturadas, e disponibiliza os resultados para exploração no Power BI.

## Fluxo do MVP

1. Importar uma base CSV.
2. Validar colunas obrigatórias e registros.
3. Processar reclamações com Python e Pandas.
4. Utilizar uma API de IA para classificar categoria, sentimento, gravidade e evidências.
5. Validar e exportar os resultados em CSV/JSON.
6. Conectar os dados processados ao Power BI.
7. Analisar indicadores e recomendações; decisões permanecem sob responsabilidade humana.

## Arquitetura inicial

```text
CSV de reclamações
       |
       v
Python + Pandas (validação e preparação)
       |
       v
API de IA (classificação estruturada)
       |
       v
CSV enriquecido / JSON
       |
       v
Power BI (indicadores e análise)
       |
       v
Decisão e acompanhamento pelo gestor
```

A primeira versão não exige banco de dados, aplicação web, autenticação ou integração com sistemas externos. Esses componentes podem ser avaliados em versões futuras, caso exista necessidade validada.

## Tecnologias previstas

- Python
- Pandas
- API de modelo de linguagem (Claude ou alternativa configurável)
- CSV e JSON
- Power BI
- Git e GitHub

## Estrutura do repositório

```text
ifood-insights-ai/
├── dados/                 # Bases fictícias e dados de exemplo
├── docs/                 # Documentação de produto e solução
├── examplos/             # Exemplos de entrada e saída
├── powerbi/              # Arquivos e documentação do relatório Power BI
├── src/                  # Código-fonte Python
├── teste/                # Testes funcionais e de qualidade da IA
└── README.md
```

## Documentação

- [Visão do produto](docs/01-product-vision.md)
- [PRD — Requisitos do produto](docs/02-prd.md)
- [Personas e jornada](docs/03-personas-e-jornada.md)
- [Requisitos funcionais e não funcionais](docs/04-requisitos.md)
- [Épicos e histórias de usuário](docs/05-user-stories.md)
- [Critérios de aceite](docs/06-criterios-de-aceite.md)
- [Arquitetura da solução](docs/07-arquitetura.md)
- [Estratégia de testes da IA](docs/08-testes-de-ia.md)
- [KPIs e métricas](docs/09-kpis-e-metricas.md)
- [Backlog e plano de entrega](docs/10-backlog-e-plano.md)
- [Riscos, privacidade e limitações](docs/11-riscos-e-privacidade.md)
- [Modelo de dados](docs/12-modelo-de-dados.md)
- [Dicionário de dados](docs/13-dicionario-de-dados.md)
- [Decisões de produto e Definition of Done](docs/14-decisoes-e-definition-of-done.md)
- [Prompt de classificação — versão inicial](docs/15-prompt-classificacao.md)
- [Plano do dashboard Power BI](powerbi/README.md)

## Como executar

O código ainda será implementado. Quando estiver disponível, as instruções de instalação, configuração da API e execução serão atualizadas aqui.

**Segurança:** nunca versione chaves de API, credenciais ou dados pessoais. Utilize variáveis de ambiente e arquivos locais ignorados pelo Git.

## Status

**Fase atual:** documentação e definição do MVP.  
**Próxima etapa:** criar a base sintética de reclamações e implementar validação e processamento.

## Uso responsável

As classificações e recomendações da IA são apoio à análise, não decisões automáticas. Resultados devem ser avaliados por pessoas, especialmente quando envolverem impacto sobre clientes, entregadores ou restaurantes.
