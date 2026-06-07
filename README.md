# Skill-Agentico

Este repositorio contiene la implementación de un agente de IA especializado en Sourcing y Talent Intelligence, diseñado para integrarse con Notion a través del Model Context Protocol (MCP). El objetivo del sistema es automatizar la lectura, evaluación y preclasificación de perfiles técnicos frente a vacantes específicas, consolidando los resultados en un entorno interactivo y operativo para equipos de reclutamiento.

## Estructura del Repositorio

*   `SUBMISSION.txt`: Archivo de metadatos de la entrega (enlaces a Loom, reporte final y métricas de tiempo).
*   `agent.md`: Configuración core del agente con matrices de evaluación estáticas para los roles activos.
*   `agent-custom.md`: Versión modular y paramétrica del skill, diseñada con placeholders adaptables para reutilizar la lógica en futuras vacantes.
*   `notion-mcp-setup.md`: Guía paso a paso para replicar la conexión del servidor MCP e integrar la clave secreta de Notion.

---

## Estrategia de Carga y Manejo de Límites

Para mitigar las restricciones físicas de la interfaz de usuario en cuanto al volumen de archivos adjuntos (límite de 20 documentos en Claude Desktop), se implementó una estrategia de **Procesamiento por Lotes (Batching)**:
*   **Lote 1:** Inicialización de la infraestructura base de datos en la página destino de Notion y procesamiento de los primeros 15 perfiles.
*   **Lote 2:** Ejecución de operaciones `append` sobre la base de datos existente para inyectar los 15 perfiles restantes, garantizando la persistencia de datos y evitando la duplicación de estructuras.

---

## Ejecución del Skill

Para ejecutar este agente en un entorno local compatible con MCP:
1. Asegure la conectividad del servidor siguiendo los pasos de `notion-mcp-setup.md`.
2. Cargue el archivo `agent.md` (o `agent-custom.md` modificado con sus nuevos parámetros) en el contexto de su cliente de IA junto con los documentos de las vacantes y candidatos.
3. Ejecute la instrucción de inicio para que el agente construya de manera autónoma el dashboard en el espacio de trabajo de Notion asignado.
