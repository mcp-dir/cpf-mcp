# CPF

### CPF para Claude, ChatGPT e agentes de IA

Valida CPF (dígitos verificadores) e descobre processos judiciais por CPF, buscando por NOME no Diário (DJEN). Importante: CPF→nome não é dado público; informe o nome do titular (recomendado). Sem credencial.

- 📊 **2 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `CPF` e **URL** `https://api.mcp.ai/p_cpf`.

### Cursor

[➕ Instalar CPF no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=cpf&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9jcGYifQ==)

### VS Code (Copilot Chat)

[➕ Instalar CPF no VS Code](vscode:mcp/install?name=cpf&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_cpf%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_cpf
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Valide o CPF 000.000.000-00
Processos do CPF 000.000.000-00 (nome: João da Silva)
Esse CPF é válido?
```

---

## 2 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `cpf_validar` | Valida os dígitos verificadores de um CPF (mod 11) e informa se há broker de identidade disponível. |
| `cpf_processos` | DESCOBERTA por CPF: busca os processos da pessoa por NOME no Diário (DJEN), grátis. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_cpf`.


---

## Suporte

- 📧 [cpf@mcp.ai](mailto:cpf@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/cpf-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_cpf` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
