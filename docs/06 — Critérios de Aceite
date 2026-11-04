# 06 — Critérios de Aceite (Gherkin)

Os cenários abaixo orientam os testes funcionais do MVP.

## US01 — Importar CSV

```gherkin
Funcionalidade: Importação de reclamações

Cenário: Importar arquivo válido
  Dado que o usuário possui um CSV com as colunas obrigatórias
  Quando selecionar o arquivo para processamento
  Então o sistema deve ler os registros
  E informar a quantidade total encontrada

Cenário: Importar arquivo sem coluna obrigatória
  Dado que o CSV não contém a coluna "texto_reclamacao"
  Quando o usuário tentar importar o arquivo
  Então o sistema deve rejeitar o arquivo
  E informar qual coluna está ausente
```

## US02 — Validar registros

```gherkin
Funcionalidade: Validação dos registros

Cenário: Reclamação sem texto
  Dado que um registro possui texto vazio
  Quando a validação for executada
  Então o registro deve ser marcado como inválido
  E não deve ser enviado à IA

Cenário: Registro válido
  Dado que um registro possui identificador e texto
  Quando a validação for executada
  Então o registro deve ser considerado elegível para análise
```

## US04 — Classificar categoria

```gherkin
Funcionalidade: Classificação por IA

Cenário: Classificação com evidência suficiente
  Dado que uma reclamação descreve claramente um problema
  Quando a IA analisar o texto
  Então deve retornar uma categoria da taxonomia permitida
  E apresentar uma evidência textual curta

Cenário: Texto ambíguo
  Dado que o texto não permite identificar o motivo
  Quando a IA analisar a reclamação
  Então deve retornar "outros" ou "indeterminado", conforme a regra definida
  E sinalizar necessidade de revisão
```

## US05 — Identificar sentimento

```gherkin
Funcionalidade: Análise de sentimento

Cenário: Sentimento negativo explícito
  Dado que a reclamação expressa insatisfação
  Quando a IA analisar o texto
  Então deve retornar "negativo"

Cenário: Sentimento não identificável
  Dado que o texto não expressa uma opinião clara
  Quando a IA analisar o texto
  Então deve retornar "indeterminado"
```

## US06 — Estimar gravidade

```gherkin
Funcionalidade: Estimativa de gravidade

Cenário: Atraso simples sem impacto adicional descrito
  Dado que o cliente relata um atraso
  E não descreve consequência adicional
  Quando a IA estimar a gravidade
  Então não deve classificar automaticamente como alta
  E deve justificar a classificação

Cenário: Risco ou impacto relevante explicitamente descrito
  Dado que a reclamação descreve impacto relevante
  Quando a IA estimar a gravidade
  Então deve considerar o critério de gravidade documentado
  E sinalizar revisão humana quando necessário
```

## US07 — Sinalizar incerteza

```gherkin
Funcionalidade: Revisão humana

Cenário: Baixa confiança ou evidência insuficiente
  Dado que a IA não possui evidência suficiente
  Quando retornar a análise
  Então deve marcar "revisao_humana" como verdadeiro
  E explicar o motivo da incerteza
```

## US08 — Gerar recomendações

```gherkin
Funcionalidade: Recomendações operacionais

Cenário: Padrão recorrente observado
  Dado que existe concentração de reclamações em uma categoria
  Quando o sistema gerar recomendações
  Então cada recomendação deve estar ligada ao padrão observado
  E distinguir hipótese de causa confirmada

Cenário: Amostra insuficiente
  Dado que há poucos registros para sustentar uma tendência
  Quando o sistema gerar recomendações
  Então deve informar a limitação da amostra
  E evitar apresentar uma conclusão como fato
```

## US09 — Dashboard

```gherkin
Funcionalidade: Indicadores no Power BI

Cenário: Visualizar base processada
  Dado que existe um arquivo enriquecido válido
  Quando o usuário atualizar o relatório
  Então os indicadores devem refletir os registros válidos
  E os totais devem ser conciliáveis com a base de origem
```
