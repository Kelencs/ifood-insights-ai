# 02 — PRD: Product Requirements Document

## 1. Resumo

O iFood Insights AI é um protótipo de análise de reclamações que utiliza Python, Pandas e IA generativa para converter textos em registros estruturados. O Power BI será utilizado para explorar indicadores e padrões.

## 2. Contexto e oportunidade

Reclamações contêm sinais sobre fricções na jornada de delivery. A consolidação e classificação desses textos pode apoiar a identificação de temas recorrentes. O MVP testa um fluxo de análise assistida por IA sem integração com sistemas reais.

## 3. Usuários

- Gestor de operações: precisa identificar prioridades e acompanhar tendências.
- Analista de experiência do cliente: precisa explorar reclamações, categorias e sentimentos.

## 4. Necessidades dos usuários

- Importar uma base sem conhecimento técnico avançado.
- Saber se o arquivo está válido antes do processamento.
- Entender como cada reclamação foi classificada.
- Identificar registros incertos ou que precisam de revisão.
- Visualizar indicadores por período e categoria.
- Consultar recomendações ligadas a evidências observadas.

## 5. Escopo do MVP

### Incluído
- Leitura de CSV.
- Validação de colunas e registros.
- Remoção ou sinalização de duplicidades.
- Classificação por categoria.
- Análise de sentimento.
- Estimativa de gravidade com justificativa textual.
- Extração de palavras-chave ou tema.
- Indicação de incerteza/revisão humana.
- Geração de recomendações agregadas.
- Exportação de CSV/JSON.
- Dashboard Power BI com métricas descritivas.

### Excluído
- Integração com APIs ou bancos internos do iFood.
- Dados reais identificáveis de clientes, restaurantes ou entregadores.
- Resposta automática ao consumidor.
- Ações automáticas sobre pedidos, pagamentos ou entregadores.
- Login, perfis, permissões e hospedagem.
- Modelos preditivos ou causalidade inferida.

## 6. Fluxo principal

1. Usuário seleciona arquivo CSV.
2. Sistema valida estrutura e qualidade mínima.
3. Registros inválidos são reportados.
4. Registros válidos são enviados à IA em lotes controlados.
5. A IA retorna campos estruturados.
6. O sistema valida o schema e normaliza valores.
7. Registros incertos ou inválidos são marcados para revisão.
8. O processamento exporta arquivos enriquecidos.
9. Power BI atualiza a análise a partir dos arquivos.
10. Gestor interpreta os dados e decide ações.

## 7. Requisitos de experiência

- Mensagens claras para arquivo inválido, falha de API ou resultado incompleto.
- Exibição da quantidade de registros lidos, válidos, rejeitados e processados.
- Não ocultar classificações incertas.
- Diferenciar dados observados, inferências da IA e recomendações.
- Exibir aviso de que a análise é assistiva e requer validação humana.

## 8. Regras de negócio

- Cada reclamação válida deve manter um identificador único.
- Categorias devem pertencer a uma taxonomia controlada.
- Sentimento deve aceitar apenas `positivo`, `neutro`, `negativo` ou `indeterminado`.
- Gravidade deve aceitar `baixa`, `media`, `alta` ou `indeterminada`.
- A IA não deve inventar região, horário, causa ou informação não presente na entrada.
- Ausência de evidência deve ser representada como nulo/indeterminado, não como suposição.
- Recomendações agregadas devem apontar quais padrões ou registros as sustentam.

## 9. Requisitos de qualidade

- Saída estruturada validada por schema.
- Tratamento de exceções e falhas de API.
- Registro de versão do prompt e do modelo.
- Proteção de credenciais.
- Dados sintéticos ou anonimizados.
- Reprodutibilidade do processamento sempre que possível.

## 10. Dependências

- Arquivo CSV conforme dicionário de dados.
- Acesso a uma API de modelo de linguagem.
- Python e bibliotecas definidas no projeto.
- Power BI Desktop para construção do relatório.

## 11. Riscos principais

- Ambiguidade no texto pode gerar classificação incorreta.
- O modelo pode variar respostas entre execuções.
- Custos e limites de API podem restringir o volume.
- Dados sintéticos não representam necessariamente a distribuição real.
- Indicadores agregados podem induzir conclusões equivocadas se a amostra for enviesada.

## 12. Critério de aceite do produto

O fluxo ponta a ponta deve ser demonstrável com dados sintéticos, com validação de entrada, classificação estruturada, identificação de incerteza, exportação e visualização no Power BI. A qualidade deve ser medida em amostra de referência rotulada manualmente.
