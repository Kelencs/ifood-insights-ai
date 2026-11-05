# Power BI — Plano do Relatório

## Objetivo

Criar um relatório gerencial baseado no CSV enriquecido pelo processamento Python/IA.

## Páginas sugeridas

### 1. Visão executiva
- Total de reclamações válidas.
- Percentual de sentimento negativo.
- Percentual de gravidade alta entre casos determinados.
- Distribuição por categoria.
- Evolução temporal, quando houver datas válidas.

### 2. Análise operacional
- Reclamações por categoria e subcategoria.
- Distribuição por região, somente se o campo existir e for confiável.
- Evolução por período.
- Tabela de reclamações para detalhamento.

### 3. Experiência do cliente
- Distribuição de sentimentos.
- Distribuição de gravidade.
- Exemplos de evidências.
- Taxa de registros encaminhados para revisão.

### 4. Recomendações
- Lista de padrões observados.
- Evidências associadas.
- Recomendação sugerida.
- Campo para status de acompanhamento, se for criado manualmente.

## Medidas DAX iniciais

Ajustar o nome da tabela e os campos ao importar os dados.

```dax
Total Reclamações =
DISTINCTCOUNT(Reclamacoes[complaint_id])
```

```dax
Reclamações Negativas =
CALCULATE(
    [Total Reclamações],
    Reclamacoes[sentiment] = "negativo"
)
```

```dax
% Sentimento Negativo =
DIVIDE(
    [Reclamações Negativas],
    CALCULATE(
        [Total Reclamações],
        Reclamacoes[sentiment] <> "indeterminado"
    )
)
```

```dax
Casos Gravidade Alta =
CALCULATE(
    [Total Reclamações],
    Reclamacoes[severity] = "alta"
)
```

```dax
Taxa de Revisão =
DIVIDE(
    CALCULATE(
        [Total Reclamações],
        Reclamacoes[review_required] = TRUE()
    ),
    [Total Reclamações]
)
```

## Regras de visualização

- Mostrar período e filtros ativos.
- Exibir denominador em percentuais.
- Não misturar `outros` com `indeterminado`.
- Não apresentar recomendações como causas comprovadas.
- Permitir detalhamento até a reclamação sintética de origem.
- Conciliar totais do relatório com o CSV enriquecido.

## Atualização

No MVP, atualizar o relatório manualmente após gerar o arquivo enriquecido. Automatização de refresh fica fora do escopo inicial.
