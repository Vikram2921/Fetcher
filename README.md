# AegisAPI

**Enterprise AI-Native Windows API Client**

AegisAPI is a powerful, local-first API client built for developers and teams who need more than just request/response — it combines a full-featured request builder, visual workflow automation, load testing, and native AI assistance, all running offline on your machine.

---

## Features

### Request Builder
- All HTTP methods: GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS
- Body types: JSON, Form Data, URL Encoded, XML, Text, GraphQL, SPARQL, Binary
- Query params, headers, and pre-request JavaScript scripting
- HTTP version selection (1.1 / 2 / 3), SSL/TLS options, proxy, and redirect control
- Network latency simulation for realistic testing conditions

### Authentication
- Bearer Token, Basic Auth, API Key
- OAuth 2.0 (Authorization Code, Client Credentials, Password, Implicit, PKCE) with automatic token refresh
- AWS Signature (SigV4), Digest Auth, NTLM, mTLS (client certificate)
- Auth inheritance: collection → folder → request with override support

### Collections & Organization
- Hierarchical collections with unlimited folder nesting
- Collection-level headers, variables, and auth — inherited by all nested requests
- Save, rename, move requests freely across the tree

### Environments & Variables
- Multiple named environments, switchable at any time
- Secret variables (masked in UI and storage)
- Variable syntax: `{{env.key}}`, `{{vars.key}}`, `{{bucket.key}}`, `{{function.name}}`
- First-match resolution order: bucket → function → env → collection → bare fallback

### Workspace Bucket
- Pre-request prework items: set variables from hardcoded values, references, or functions
- Transformations: base64, URL encode/decode, trim, uppercase, lowercase
- Post-response extraction: pull values from response body, headers, or status code into the bucket
- Conditional execution with `runIf` JavaScript expressions
- Per-send (reset each time) or session (accumulate) mode

### Response Inspection
- Syntax-highlighted body: JSON tree view, XML, plain text, binary detection
- Full response headers, status code, final URL
- Detailed timings: DNS, TCP, TLS, TTFB, Transfer
- Test result display with pass/fail indicators

### Workflows (Visual Flow Editor)
- Drag-and-drop node-based workflow editor powered by React Flow
- Node types: Request, Action, Script, Assertion, Set Bucket, Loop, Fork, Goto
- Branch conditions: `on_success`, `on_failure`, `status_is`, `body_check`, `header_check`, `function_check`
- Loop types: variable-based (array iteration), range-based, static list
- Fork nodes for parallel branch execution
- Retry configuration per node with configurable delay and max attempts
- Breakpoints and step-by-step debugging with live execution timeline
- Access previous step results via `{{step1.body.path}}` syntax
- Triggers: manual, scheduled (interval), webhook (HTTP POST with optional secret)
- Full execution history per workflow

### Collection Runner
- Run entire collections, folders, or workflows in sequence
- Configuration: iterations, concurrency, delay, stop-on-error
- Data-driven runs via CSV/JSON data files
- Per-request test script execution
- Persistent run reports (up to 50 per collection)

### Simulation Runner (Load Testing)
- Virtual user (VU) based load simulation
- Ramp-up strategies: Immediate, Linear, Step
- Delay strategies: Fixed, Random, Think Time
- Real-time metrics: active VUs, RPS, throughput, avg/P95/P99 latency, error rate
- Per-second timeline snapshots and error breakdown
- Historical simulation reports (up to 50 per collection)
- AI-powered performance analysis

### AI Integration (Ollama)
- Local LLM via Ollama — no data sent externally
- Modes: Chat, Generate request, Explain response, Generate test scripts, Name suggestions, Workflow generation
- Context-aware per entity: request, workflow, simulation, runner
- Streaming responses with per-entity chat history

### Workspace Management
- Multiple isolated workspaces — each with its own collections, environments, workflows, history, settings, and cookies
- Switch workspaces to fully swap all state
- All data stored in user-selected folder — fully portable, no lock-in

### Function Library
- Define reusable JavaScript functions per workspace
- Call via `{{function.name}}` anywhere variables are resolved
- Access `context.bucket`, `context.env`, `context.request` inside functions

### GitHub Sync
- Link workspace to a GitHub repository
- Push and pull collections for team collaboration
- Audit logging for sync operations

### Cookie Management
- Per-workspace cookie jar with persistent storage
- View and edit cookies with full attribute support: domain, path, expiry, HttpOnly, Secure, SameSite
- Automatic cookie handling on requests

### Import
- Import collections from OpenAPI / Swagger specifications

### Themes
- Built-in dark and light themes
- Full custom theme creation with granular color control (backgrounds, panels, borders, accent, text, status colors)

### History
- Automatic capture of every request with full request + response data
- Browse, reopen, and rerun historical requests
- Retains up to 500 entries per workspace

---

## Getting Started

1. Launch AegisAPI
2. On first run, create or select a workspace folder — this is where all your data lives
3. Create a collection and add requests
4. Set up environments for different deployment targets
5. Use the Workflow editor to chain requests into automated flows
6. Configure AI by pointing to your local Ollama instance in Settings

---

## Data & Privacy

All data is stored locally in your chosen workspace folder. No telemetry, no cloud sync (unless you configure GitHub), no external API calls except the ones you explicitly make. AI features require a locally running [Ollama](https://ollama.com) instance — nothing is sent to third-party AI providers.

---

## License

See `LICENSE` file for details.
