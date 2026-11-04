# 11 — Riscos, Privacidade e Uso Responsável

## Riscos

| Risco | Impacto | Mitigação |
|---|---|---|
| Classificação incorreta | Indicadores distorcidos | Conjunto de referência e revisão |
| Alucinação | Recomendação sem suporte | Exigir evidência e validar saída |
| Viés da amostra | Conclusões não representativas | Documentar origem e limitações |
| Indisponibilidade da API | Interrupção | Tratamento de erro e reprocessamento |
| Custo de API | Custo imprevisível | Lotes, limites e monitoramento |
| Vazamento de credencial | Acesso indevido | Variáveis de ambiente e `.gitignore` |
| Dados pessoais | Risco à privacidade | Dados sintéticos/anonimizados |
| Interpretação causal indevida | Decisão inadequada | Linguagem de hipótese e análise humana |

## Privacidade por padrão

- Utilizar dados inteiramente sintéticos na versão pública.
- Não incluir nome, telefone, endereço, número de pedido ou identificador pessoal.
- Se futuramente houver dados reais, obter autorização e aplicar minimização e anonimização antes de qualquer processamento.
- Não publicar arquivos que possam reidentificar pessoas.
- Verificar termos e políticas do provedor de IA antes de enviar qualquer dado.

## Segurança de credenciais

- Usar variável de ambiente para a chave da API.
- Manter `.env` fora do Git.
- Criar `.env.example` apenas com nomes de variáveis e valores fictícios.
- Nunca inserir chave em notebook, README, imagem ou arquivo PBIX.

## Limites de uso

A solução é um apoio analítico. Não deve:
- decidir compensações ou penalidades;
- avaliar individualmente o desempenho de entregadores ou restaurantes;
- inferir atributos sensíveis;
- tomar decisões sobre clientes;
- afirmar causas sem evidência.

## Transparência

Toda apresentação pública deve informar que:
- o projeto é independente;
- os dados são sintéticos;
- resultados são experimentais;
- não existe integração oficial com o iFood.
