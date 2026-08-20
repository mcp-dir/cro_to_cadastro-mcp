---
name: cro_to_cadastro-mcp
description: Skill da REST API do Conselho Regional de Odontologia TO: Cadastro na MCP.AI: 1 endpoint em /api/cro_to_cadastro. Conselho Regional de Odontologia TO: Cadastro, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Conselho Regional de Odontologia TO: Cadastro — REST API skill

Você tem acesso à **Conselho Regional de Odontologia TO: Cadastro** REST API na MCP.AI.

> Conselho Regional de Odontologia TO: Cadastro, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/cro_to_cadastro
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
curl -X POST https://api.mcp.ai/api/cro_to_cadastro/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"inscricao":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/cro_to_cadastro/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `cro_to_cadastro_consultar`

Conselho Regional de Odontologia TO: Cadastro, consulta em fonte oficial. _(POST /api/cro_to_cadastro/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `inscricao` | string | Sim | Parâmetro de consulta "inscricao". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_cro_to_cadastro` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
