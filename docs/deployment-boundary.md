# Deployment boundary

Design/review only, 13 September 2026. No GoDaddy changes were made.

The existing authenticated GoDaddy dashboard identified **Personal AI Consulting Group**, app ID `wy2v0putg6`, hostname `wy2v0putg6.c35.airoapp.ai`, source `Ingwarski/personal-ai-consulting-group-godaddy`, branch `main`, Node.js 22. The visible Preview tab showed commit `72265acf8b61d8b7f0954f0fdc29b5442a6b7cb5`, inactive Preview and an out-of-sync notice. This is Preview evidence, not a fresh verification of the Published commit or a diagnosis of its runtime.

The reviewed local checkout is `49c7ad9a0b3033e9437e79cd98ed5d35e71cfced`, on `codex/matrix-connection-20260906`, four commits ahead of its tracked remote at initial inspection. Its clean state does not prove deployment. The old checkout and its Git references were not changed.

The user permits erasure of this app and its database to use the replacement. Their later scope answer keeps this task at review, product brief and design. Therefore erasure is deferred until the replacement phase; it is not required to deliver this design.

Before the eventual reset, the implementer must read the current model settings without exporting conversation content, verify the selected provider grants can be recovered or reauthorized, and identify the database and exact tables owned solely by this application. This review did not inspect a database identifier or prove that every attached table belongs to this app. No executable DROP statement or deletion command is provided because that boundary is unverified.

Other GoDaddy apps, their data, shared/unidentified tables, domains and credentials are outside scope. If attachment or ownership is ambiguous, stop that deletion and ask about the exact ambiguous resource. Do not interpret an app attachment as ownership of everything in a database.

Before publishing the replacement, validate the actual Node runtime, persistent jobs and storage, restart/redeploy behavior, authenticated browser streaming or polling, provider access, logs and recovery within this app. A successful build or health endpoint alone is insufficient.
