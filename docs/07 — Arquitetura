# 07 — Arquitetura da Solução

## Visão geral

```text
[CSV de entrada]
      |
      v
[Python + Pandas]
  - leitura
  - validação
  - limpeza
      |
      v
[API de IA]
  - categoria
  - sentimento
  - gravidade
  - evidências
  - incerteza
      |
      v
[Validação da resposta]
  - schema JSON
  - normalização
  - tratamento de erro
      |
      v
[CSV enriquecido / JSON]
      |
      v
[Power BI]
  - indicadores
  - filtros
  - tendências descritivas
      |
      v
[Análise e decisão humana]
```

## Componentes

### 1. Entrada CSV
Arquivo com identificador, data opcional, texto da reclamação e dimensões disponíveis e não identificáveis, como região ou canal fictícios.

### 2. Python e Pandas
Responsável por ler arquivos, validar colunas, normalizar campos, detectar registros vazios e preparar lotes para análise.

### 3. API de IA
Recebe apenas o texto necessário para a tarefa e retorna uma classificação estruturada. O modelo e a versão do prompt devem ser registrados.

### 4. Validação de saída
O sistema verifica se a resposta é JSON válido, se os valores pertencem às opções permitidas e se os campos obrigatórios existem. Respostas inválidas não devem ser silenciosamente aceitas.

### 5. Arquivos enriquecidos
A saída mantém o identificador original e acrescenta campos de classificação. Deve ser possível rastrear cada resultado até o registro de entrada.

### 6. Power BI
Consome os arquivos exportados e apresenta métricas descritivas. O relatório não deve sugerir causalidade quando os dados mostram apenas associação ou frequência.

## Decisão arquitetural do MVP

Usar arquivos CSV/JSON como armazenamento inicial. Isso reduz configuração e permite validar o fluxo. Um banco de dados só será considerado quando houver necessidade de múltiplos usuários, histórico persistente, atualização automatizada ou maior volume.

## Segurança

- Guardar a chave de API em variável de ambiente.
- Não incluir `.env` no Git.
- Não enviar dados pessoais à API.
- Utilizar dados sintéticos na demonstração.
- Restringir logs para evitar exposição de textos sensíveis.

## Limitações

- Atualização do Power BI será manual no MVP.
- Não há integração com sistemas de produção.
- Qualidade depende da clareza e representatividade da base.
- A IA pode errar; revisão humana é necessária.
