# CPF

### CPF for Claude, ChatGPT and AI agents

Validates CPF (check digits) and discovers lawsuits by CPF, searching by NAME in the official gazette (DJEN). Note: CPF→name is not public data; provide the holder's name (recommended). No credentials.

- 📊 **2 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `CPF`, URL `https://api.mcp.ai/p_cpf`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=cpf&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9jcGYifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=cpf&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_cpf%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_cpf
```

---

## 2 tools

| Tool | Description |
|---|---|
| `cpf_validar` | Valida os dígitos verificadores de um CPF (mod 11) e informa se há broker de identidade disponível. |
| `cpf_processos` | DESCOBERTA por CPF: busca os processos da pessoa por NOME no Diário (DJEN), grátis. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_cpf` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
