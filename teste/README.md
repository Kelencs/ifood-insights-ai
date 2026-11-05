# Testes

Organização prevista:

- `test_data_validation.py`: validação de entrada.
- `test_output_schema.py`: schema e taxonomia da saída.
- `test_ai_classification.py`: avaliação com conjunto de referência.
- `fixtures/`: exemplos sintéticos para testes.

Separar testes determinísticos de avaliação de modelo. Testes de IA podem variar entre execuções e devem registrar modelo e versão do prompt.
