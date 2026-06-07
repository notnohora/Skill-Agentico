# Guía de Configuración del Servidor MCP de Notion

Esta guía contiene las instrucciones exactas para registrar este Skill agéntico y ejecutarlo usando el servidor oficial de MCP para Notion.

## Requisitos Previos
1. Una cuenta de Notion (Plan gratuito).
2. Un Token de Integración Interna generado en [developers.notion.com](https://developers.notion.com/).
3. Una página compartida con la integración dentro de tu espacio de trabajo de Notion.

## Configuración del Entorno MCP

Añade el siguiente bloque de configuración en el archivo de configuración de tu entorno de IA (por ejemplo, `%APPDATA%\Claude\claude_desktop_config.json` para Claude Desktop o el archivo de configuración correspondiente en Cowork/Codex/OpenCode):

```json
{
  "mcpServers": {
    "notion": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-notion"
      ],
      "env": {
        "NOTION_TOKEN": "TU_INTEGRATION_SECRET_AQUI"
      }
    }
  }
}