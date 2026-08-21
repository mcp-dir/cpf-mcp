# Ferramentas

CPF expõe 2 ferramentas (todas somente leitura).

### 1. `cpf_validar`
**Input**: `cpf`

Valida os dígitos verificadores de um CPF (mod 11) e informa se há broker de identidade disponível.

### 2. `cpf_processos`
**Input**: `cpf`, `nome` (opcional)

DESCOBERTA por CPF: busca os processos da pessoa por NOME no Diário (DJEN), grátis.

## Prompts de exemplo

```
Valide o CPF 000.000.000-00
Processos do CPF 000.000.000-00 (nome: João da Silva)
Esse CPF é válido?
```
