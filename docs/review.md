# Product reset review

13 September 2026. Historical review of the original system at the source revision cited below. Current replacement requirements are owned by [product-idea.md](product-idea.md) and [prd.md](prd.md); the [candidate inventory](../README.md#compare-the-three-designs) records the current design comparison. Review, product brief and design only.

## Conclusion

The system is overcomplicated for the owner's actual task. The largest removable burden is Matrix: a second user surface, encryption/device lifecycle, Rust sidecar, native release pipeline, transport-specific storage, delivery synchronization and wake/recovery machinery. A browser UI alone is insufficient if that entire backend remains underneath it.

The second problem is behavioral. The team is implemented as a formal approval sequence around repeated full proposals. Long response allowances, procedural stage labels and stock announcements make real separate model invocations feel robotic. Research is already technically available through Codex, but a request-language gate makes it less available than the product brief promised.

These findings follow inspected source code. They are not proof of the root cause of every reported live failure.

## What changes

| Decision | Result |
|---|---|
| Replace the messenger channel | One private responsive web app is the complete everyday surface. |
| Remove transport-specific machinery | No Matrix rooms, verified devices, Rust encryption sidecar, messenger ingress/outbox or wake registration in the replacement. |
| Keep essential persistence | One durable run and ordered event stream; accepted work survives disconnect/restart and Stop rejects late responses. |
| Make discussion substantive | Separate agents with different assignments; focused objections and replies; full actual messages; one useful outcome. |
| Make research ordinary | Live search is available when needed, with shared cited evidence and no magic request phrase. |
| Simplify preferences | Preserve models/settings; manage routine provider refresh internally; show a contextual action only for a real selected-provider failure. |
| Replace the visual baseline | Fresh mobile-first prototype. Existing Matrix design approval is not reused. |

## Highest-priority evidence

1. **Transport coupling:** `src/godaddy/application-runtime.ts:131` composes the Matrix service, outbox and media path; `src/godaddy/registrar-runtime.ts:40` ties confirmed consultation messages to Matrix delivery. Simplification must cut this dependency, not restyle its settings page.
2. **Conversation ceremony:** `src/consilium/consensus-router.ts:164` sequences initial positions, candidate, specialist reviews, Critic and Head review. `src/consilium/consensus-prompts.ts:3` allows up to 32,000 characters; `src/matrix/bridge.ts:488` adds stage framing. Shorter substantive generated messages and addressed issue replies should replace the visible ritual, while truthful agreement tracking remains internal.
3. **Research mismatch:** `src/runtime/consultation-intake.ts:46` gates research on request wording; `src/runtime/codex-thread-client.ts:68` disables it by default and `:80` exposes a live-search configuration. Claude Critic remains tool-free. Shared targeted research preserves the provider choice while closing this gap.
4. **Readiness ceremony:** `src/godaddy/settings-runtime.ts:306` exposes several provider and Matrix operations; Claude discovery can probe many model/effort combinations (`src/godaddy/claude-code-process.ts:349`). Normal use should refresh the selected route, not require a complete catalog exercise.
5. **Specification drift:** the old architecture's newer MySQL amendments coexist with an earlier SQLite diagram. Voice code also exists alongside a product exclusion. A clean current brief and explicit unresolved evidence are necessary; code alone must not silently rewrite product scope.

References above are to source checkout `49c7ad9a0b3033e9437e79cd98ed5d35e71cfced`. See the [full product review](reviews/product.md) and [full architecture review](reviews/architecture.md) for supporting ranges, all product amendment/core-decision dispositions and the complete AD-01–AD-27 decision index. Those are evidence reports, not newly approved requirements.

## What must not be simplified away

Keep the exact model/provider/effort selection; private owner access; genuine separate agents and Critic; ordinary-processing consent and query minimization; complete submitted messages; honest consensus or explicit disagreement; durable acceptance; cancellation; session language; history/export/delete; current input capabilities unless their authority mismatch is explicitly reconciled.

Google login and AI subscription authorization are different. Provision provider access for deployment and refresh automatically where possible. A revoked grant can still require the owner. One contextual reconnect action is honest; an integration dashboard on every visit is unnecessary.

## Review discussion and disagreement

Two separately launched reviewers examined architecture and product behavior. They challenged each other through the lead reviewer; a third Critic reviewed the synthesis. The actual full exchange is retained locally in the ignored review-session directory. Its private transcript and host paths are not published here.

The key resolved tradeoff: removing Matrix must not remove persistence. One transactional run/event store is sufficient in the proposed single-owner architecture; browser delivery can read those canonical events directly, without a separate delivery outbox. Exactly-once model execution is not promised. A repeated uncommitted provider call must not become a repeated confirmed message.

The other resolved tradeoff: “login and work” is the ordinary path, with precise recovery for revoked selected-provider access. Quota exhaustion, connection trouble and revoked credentials require different messages. Unused providers remain silent.

## Evidence limits and next decision

The current GoDaddy app was identified read-only; the visible Preview revision differs from the reviewed checkout. Attempts to read the existing app's current sign-in/settings tab timed out, so no fresh effective-settings snapshot was obtained. Historical settings are explicitly dated in [model-settings.md](model-settings.md). Database identity/ownership was not verified and no GoDaddy resource was changed.

The outstanding owner decision is the whole-design choice among the three candidates in the current inventory. The later implementation must prove current settings, real research and agent exchanges, mobile interruption/recovery, and the exact GoDaddy data boundary. This review does not declare the old system broken in every case or the proposed backend already operational.
