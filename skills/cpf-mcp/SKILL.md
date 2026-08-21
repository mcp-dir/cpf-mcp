---
name: cpf-mcp
description: Skill da REST API do CPF na MCP.AI: 2 endpoints em /api/cpf. Valida CPF (dígitos verificadores) e descobre processos judiciais por CPF, buscando por NOME no Diário (DJEN). Importante: CPF→nome não é dado público; informe o nome do titular (recomendado). Sem credencial. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# CPF — REST API skill

Você tem acesso à **CPF** REST API na MCP.AI.

> Valida CPF (dígitos verificadores) e descobre processos judiciais por CPF, buscando por NOME no Diário (DJEN). Importante: CPF→nome não é dado público; informe o nome do titular (recomendado). Sem credencial.

## Base URL

```
https://api.mcp.ai/api/cpf
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/cpf/processos \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cpf":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/cpf/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (2)

#### `cpf_processos`

DESCOBERTA por CPF: busca os processos da pessoa por NOME no Diário (DJEN), grátis. _(POST /api/cpf/processos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Sim | CPF (11 dígitos), com ou sem máscara. |
| `nome` | string | Não | Nome completo do titular (recomendado — CPF→nome não é público). |

#### `cpf_validar`

Valida os dígitos verificadores de um CPF (mod 11) e informa se há broker de identidade disponível. _(POST /api/cpf/validar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Sim | CPF (11 dígitos), com ou sem máscara. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_cpf` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
