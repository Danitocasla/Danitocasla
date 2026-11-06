# Daniel Méndez

<details open>
<summary><b>🇦🇷 Español</b></summary>

Trabajo en la capa que une los datos del negocio con la automatización: bases legacy (ERPs, CRMs, SQL Server) convertidas en APIs, servidores MCP y pipelines que agentes y flujos de trabajo pueden usar de verdad.

Argentina.

## En qué trabajo

**Agentes sobre datos reales.** Servidores MCP que le dan a los LLMs acceso estructurado y de solo lectura a bases de ERP en producción: tools tipadas, entradas validadas y descubrimiento de esquema, en lugar de un modelo adivinando nombres de tablas.

**APIs sobre esquemas legacy.** Servicios en FastAPI y Flask sobre bases SQL Server que nunca fueron pensadas para consultarse. Multi-empresa, containerizados, de solo lectura donde importa.

**Automatización de procesos.** Stacks de n8n self-hosted con Postgres, Redis y una base vectorial, conectados a sistemas internos y expuestos por webhooks.

## Trabajo seleccionado

### [MCP-Tango](https://github.com/Danitocasla/MCP-Tango) — servidor Model Context Protocol para Tango Gestión
`TypeScript` · `@modelcontextprotocol/sdk` · `mssql`

Servidor MCP que expone la base contable de Tango Gestión a cualquier cliente MCP. Las tools de catálogo le permiten al agente descubrir el esquema antes de consultar; el mapa de tablas de Tango (comprobantes, clientes, vendedores, renglones, artículos) está codificado como conocimiento de dominio y no librado a lo que el modelo suponga.

- Arquitectura hexagonal — `@domain`, `@application`, `@infrastructure`, `@interface` — un caso de uso por tool
- Multi-empresa desde el diseño: cada empresa de Tango es una base distinta en el mismo servidor, así que toda consulta va calificada por esquema y validada contra una lista conocida de empresas
- El test de integración levanta el servidor por stdio contra datos vivos, igual que un cliente real

### [Tango-KPI](https://github.com/Danitocasla/Tango_Api) — API de KPIs financieros sobre Tango Gestión
`Python` · `FastAPI` · `pandas` · `SQLAlchemy` · `pyodbc`

API de analítica de solo lectura sobre el mismo ERP: facturación agrupada por día, mes o año, top de clientes, flujo de caja y saldos. `?empresa=` selecciona la base destino, así que sumar una segunda empresa no requirió cambios de esquema ni duplicar código.

### [CRM-API](https://github.com/Danitocasla/CRM-API) — API REST de CRM
`Python` · `Flask` · `SQLAlchemy` · `Docker`

API REST sobre la base de CRM de Electricidad Serrano (ecosistema ADN Serrano), desarrollada con TDD: **46 tests** que cubren cada endpoint.

- Autenticación JWT, rate limiting, protección CSRF y cabeceras de seguridad
- Consultas paginadas y filtrables, siempre parametrizadas
- Imagen Docker con el driver ODBC de SQL Server incluido

### [Stack de automatización](https://github.com/Danitocasla/AUTOMATIZACION)
`n8n` · `Postgres` · `Redis` · `Qdrant` · `ngrok`

Entorno de automatización self-hosted: n8n con persistencia en Postgres, Redis para colas, Qdrant como base vectorial para retrieval y un túnel para webhooks externos. Incluye backups y volúmenes persistentes, porque una automatización que pierde estado es peor que no tener automatización.

## Stack

| Área | Herramientas |
| --- | --- |
| Lenguajes | Python, TypeScript, SQL, JavaScript |
| Backend | FastAPI, Flask, SQLAlchemy, Flask-SQLAlchemy |
| Datos | SQL Server, pandas, ETL |
| IA y automatización | MCP SDK, n8n, Qdrant, OpenAI API |
| Ops | Docker, Docker Compose, Git |

## Contacto

- LinkedIn — [danielmendez77](https://www.linkedin.com/in/danielmendez77)

</details>

<details>
<summary><b>🇬🇧 English version</b></summary>

I work on the layer between business data and automation: legacy databases (ERPs, CRMs, SQL Server) turned into APIs, MCP servers and pipelines that agents and workflows can actually use.

Based in Argentina.

## What I work on

**Agents over real data.** MCP servers that give LLMs structured, read-only access to production ERP databases: typed tools, validated inputs and schema discovery, instead of a model guessing table names.

**APIs over legacy schemas.** FastAPI and Flask services on top of SQL Server databases that were never designed to be queried. Multi-company, containerized, read-only where it matters.

**Process automation.** Self-hosted n8n stacks with Postgres, Redis and a vector store, wired into internal systems and exposed through webhooks.

## Selected work

### [MCP-Tango](https://github.com/Danitocasla/MCP-Tango) — Model Context Protocol server for Tango Gestión
`TypeScript` · `@modelcontextprotocol/sdk` · `mssql`

An MCP server that exposes a Tango Gestión accounting database to any MCP client. Catalog tools let the agent discover the schema before querying; the Tango table map (invoices, customers, sellers, line items, articles) is encoded as domain knowledge rather than left to whatever the model assumes.

- Hexagonal architecture — `@domain`, `@application`, `@infrastructure`, `@interface` — one use case per tool
- Multi-company by design: each Tango company is a separate database on the same server, so every query is schema-qualified and validated against a known company list
- The integration test runs the server over stdio against live data, the way a real client would

### [Tango-KPI](https://github.com/Danitocasla/Tango_Api) — financial KPI API over Tango Gestión
`Python` · `FastAPI` · `pandas` · `SQLAlchemy` · `pyodbc`

Read-only analytics API over the same ERP: billing grouped by day, month or year, top customers, cash flow and balances. `?empresa=` selects the target database, so adding a second company required no schema changes and no code duplication.

### [CRM-API](https://github.com/Danitocasla/CRM-API) — CRM REST API
`Python` · `Flask` · `SQLAlchemy` · `Docker`

REST API over the CRM database of Electricidad Serrano (ADN Serrano ecosystem), built test-first: **46 tests** covering every endpoint.

- JWT authentication, rate limiting, CSRF protection and security headers
- Paginated, filterable queries, always parameterized
- Docker image with the SQL Server ODBC driver baked in

### [Automation stack](https://github.com/Danitocasla/AUTOMATIZACION)
`n8n` · `Postgres` · `Redis` · `Qdrant` · `ngrok`

Self-hosted automation environment: n8n with Postgres persistence, Redis for queues, Qdrant as a vector store for retrieval and a tunnel for external webhooks. Backups and persistent volumes included, because automation that loses state is worse than no automation.

## Stack

| Area | Tools |
| --- | --- |
| Languages | Python, TypeScript, SQL, JavaScript |
| Backend | FastAPI, Flask, SQLAlchemy, Flask-SQLAlchemy |
| Data | SQL Server, pandas, ETL |
| AI & automation | MCP SDK, n8n, Qdrant, OpenAI API |
| Ops | Docker, Docker Compose, Git |

## Contact

- LinkedIn — [danielmendez77](https://www.linkedin.com/in/danielmendez77)

</details>
