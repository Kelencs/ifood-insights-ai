# 08 — Estratégia de Testes e Qualidade da IA

## Objetivo

Avaliar se a IA classifica reclamações de forma consistente, válida e útil, medindo erros em vez de presumir que as respostas estão corretas.

## Conjunto de referência (golden dataset)

Criar uma amostra de reclamações sintéticas rotuladas manualmente antes de executar o modelo. Cada exemplo deve conter:
- texto original;
- categoria esperada;
- sentimento esperado;
- gravidade esperada;
- justificativa do rótulo;
- indicação se exige revisão humana.

Os rótulos de referência devem ser definidos por critérios documentados. Casos ambíguos podem ter mais de uma interpretação aceitável ou ser marcados como indeterminados.

## Dimensões de avaliação

| Dimensão | Como avaliar |
|---|---|
| Categoria | Acurácia e matriz de confusão |
| Sentimento | Acurácia por classe e análise de erros |
| Gravidade | Concordância com rótulo de referência |
| Formato | Percentual de respostas JSON válidas |
| Evidência | Evidência realmente presente no texto |
| Incerteza | Casos ambíguos encaminhados para revisão |
| Recomendação | Relação com padrões observados e ausência de alegações sem suporte |

## Casos de teste

1. Reclamação direta e simples.
2. Texto com mais de um problema.
3. Texto com ironia ou sarcasmo.
4. Texto curto e ambíguo.
5. Texto sem reclamação identificável.
6. Texto com erro ortográfico ou abreviações.
7. Texto que menciona um problema sem expressar sentimento.
8. Texto que contém informação insuficiente para estimar gravidade.
9. Texto com instruções maliciosas embutidas — tratar como dado, nunca como instrução ao modelo.
10. Resposta da API malformada ou incompleta.

## Métricas

- Acurácia por categoria.
- Precisão e recall por classe.
- F1 macro para evitar que classes frequentes escondam erros nas classes menores.
- Taxa de JSON válido.
- Taxa de revisão humana.
- Taxa de evidências não suportadas.
- Custo e latência médios por registro, se mensuráveis.

## Metas iniciais

As metas abaixo são hipóteses para o protótipo e devem ser ajustadas conforme tamanho e dificuldade do conjunto de teste.

| Métrica | Meta inicial |
|---|---:|
| F1 macro de categoria | >= 0,85 |
| JSON válido | >= 0,98 |
| Registros com vínculo de origem preservado | 100% |
| Evidências sem suporte identificadas | 100% nos testes de controle |
| Casos ambíguos sinalizados | Avaliar por conjunto de referência |

Não declarar que o modelo atingiu uma meta sem executar e registrar os testes.

## Revisão humana

Casos de baixa confiança, ambíguos ou com potencial impacto relevante devem ser encaminhados para revisão. A pontuação de confiança do modelo, se usada, não deve ser tratada automaticamente como probabilidade calibrada.

## Registro de experimentos

Para cada execução, registrar:
- data/hora;
- identificador do conjunto de dados;
- provedor e modelo;
- versão do prompt;
- parâmetros relevantes;
- métricas;
- falhas conhecidas.
