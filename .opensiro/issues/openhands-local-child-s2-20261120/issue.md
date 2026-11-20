# OpenHands Agent Canvas — opt-in local child-launch S2 coordination (OpenSiro roadmap)

**PLAN_ONLY · proposal-stage GO · research NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED**

**One-sentence proposal:** Explore an optional Canvas-local, developer-composed S2 decision owner that can prevent conflicting shared-workspace child launches at the exact `launch_child_conversation` admission and worktree-fallback boundary, rather than creating a generic controller.

**Canonical decision receipt:** [roadmap.md](roadmap.md) is authoritative for evidence pins, historical vector, selected target, P0/P1/P2, verdict and publication state.
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md) specifies original-native interfaces, Track A/B and future test obligations; this document is the Human issue draft.
**Working fork:** `opensiro-contributions/OpenHands` on `opensiro/meta`.
**Case:** `.opensiro/issues/openhands-local-child-s2-20261120/` (outside the initial 23 in Upstream #58).

## 1. Why Opensiro and central accepted VSM assessment

OpenSiro examines whether VSM-informed descriptions and constructible control functions can help developers build and reason about agent harnesses. This is a research hypothesis; neither saved engineering cost nor a need for the original maintainers to adopt VSM has been demonstrated.

### Central starting point — accepted Index, not the target

> **ACCEPTED HISTORICAL INDEX — not current-HEAD grades or proposed after-states**
>
> **S1=A · S2=— · S3=— · S3*=— · S4=— · S5=—**
>
> [Accepted OpenHands Index assessment](https://github.com/opensiro/vsm-harness-index/blob/a3fcf7c156ef4d1132680890bc11544681fd30c0/assessments/op/openhands.md), Index commit `a3fcf7c156ef4d1132680890bc11544681fd30c0`, assessment blob `272333e34c0ef2d59091e8b06371a3694edf9530`, review_ref `28464621d879e3e9b3ceeae9d70a71d96da6212d` (resolves), reviewed 2026-09-15; Profile 0.2.1 / Skills assessment procedure 0.3.1; exact original catalog identity verified.

**Repository-wide audit:** [OpenHands/OpenHands@d5d790823e468587e9e4d8517860ca8ef75aad6a](https://github.com/OpenHands/OpenHands/commit/d5d790823e468587e9e4d8517860ca8ef75aad6a) inspected as Agent Canvas (browser and frontend for first-party coding-agent sessions). Reviewed [README](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/README.md), [original ownership and AI contributor guidance](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/AGENTS.md), [agent-server adapter](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/api/agent-server-adapter.ts), [child launch](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts), [launch resolution](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/hooks/mutation/resolve-conversation-launch.ts), [child tests](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/__tests__/services/child-conversation-launch.test.ts), [package test/CI commands](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/package.json), MIT license, original Issues/PRs and current branch HEAD. The Agent Server/SDK, reusable extensions, automation backend, Cloud independent sandboxes, and maintainer workflow have separate owners; their decisions are not automatically Canvas's deployed autonomous control.

| Function / plain-language role | Historical Index state | Current source-backed owner/closure | Candidate / uncertainty and priority |
| --- | --- | --- | --- |
| **S1 · Operations** — primary coding-agent tasks | A | Canvas launches first-party coding agents through Agent Server; actual actions execute in the agent runtime, not the browser | Existing operating capacity; no new S1 constructor |
| **S2 · Coordination** — prevents interference among operations | — | [Local child launcher](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts) normally isolates worktrees but falls back to shared directory and warns about concurrent edits; no observed independent coordination actor | **P0** optional Canvas-local sibling-conflict admission and feedback constructor |
| **S3 · Inside-now management** — current capacity and commitments | — | Settings, agent profiles and child launches route operator instructions; no independent Canvas-wide commitments owner established | DEFER; launch-scoped S2 is not a global S3 |
| **S3* · Complementary audit** — independent corrective checking | — | Confirmation/security surfaces and PR state visibility do not establish a separate decision-making reviewer that blocks protected future operations | NO_TARGET in observed Canvas boundary; distinct future question only |
| **S4 · Outside-then adaptation** — prospective environment intelligence | — | Schedules/webhooks/configuration start or configure current runs, primarily through separately owned automation; no autonomous prospective feedback owner demonstrated in Canvas | NO_TARGET; no invented S4 controller |
| **S5 · Policy/identity** — legitimate ultimate authority | — | Parent/user selects tasks, permissions, backends and policies; maintainer governance is outside the deployed harness | NO_TARGET; parent authority respected |

**Interpretation:** `A` means autonomous agent owns the functional closure; `C` means the first-party path lets a developer compose autonomous function-specific ownership; `P` marks supported parent-governed S3/S4/S5 modes; `A(P)` and `C(P)` require evidence for an additional parent mode; `—` is bounded absence of material in-scope ownership path; `?` is unresolved evidence. These are **ownership categories, not quality ranks**, and `—` is neither a quality score nor a blanket feature request. Historical states are not current regrades.

**Priority rationale:** Unlike speculative new S3–S5 layers, the actual Canvas-local fallback from isolated `new_worktree` to `local_repo` shared directory supplies a distinctive concrete S2 interference point and first-party effect boundary. This makes S2 the strongest *architecturally constructible* research target, not necessarily the most desirable product improvement.

**Deliberate exclusions / methodology challenge:** External Agent Server decisions and multi-tab clients lack demonstrated shared atomic authority in Canvas, so no cross-client S2 ownership is claimed. Cloud children use independently isolated sandboxes. Product omission is not assumed intentional absent direct evidence; proposed actor remains subordinate to parent/user authority.

**Contributor / maintainer interests (OPTIONAL):** [AGENTS.md](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/AGENTS.md) documents repository boundaries and a human-only `HUMAN:` PR-description section, but does not endorse this S2 proposal. Maintainer preference on this proposal: NOT_STATED.

## 2. Selected construction hypothesis and operator outcome

**Target transition:** S2=— -> S2=C

**Function-specific disturbance:** OBSERVED source path: local `launch_child_conversation` may start a child in the parent's directory when scratch workspace has no commit or worktree creation fails; [source explicitly warns](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts) that two agents can conflict over the same files. A real-world collision or demand metric has not been measured.

**Proposed C capability (P0):** A Canvas-integrating developer could opt in to a separate sibling-workspace conflict decision owner that observes already active children for a particular local workspace and chooses `admit isolated`, `defer shared`, or `deny shared`, with a binding pre-launch/fallback effect and returned child status/termination feedback. This is one-function S2 composition, not S3 task priority or S5 delegation.

**Best native operator alternative:** Always use separate git worktrees where supported, or have the parent/host serialize child launches or decline shared fallback. The existing default warns of shared mode; simplest comparison is doing no new controller and applying parent-side serialization.

**Expected user benefit:** HYPOTHETICAL improvement: concurrent independent children avoid uncoordinated shared-directory edits while lawful isolated children still run; no tests, net benefit or avoided collisions have been observed.

**Architectural sufficiency argument:** The shipped local child-launch tool already has a validated action, source-native workspace identity, `new_worktree`/shared effect and result returned to the parent. The smallest missing complete path is a developer-composed S2 decision/reservation owner that can make a different interference decision and enforce it *before* both the first launch and its shared fallback, then consume observed completion/error to release a reservation and select again. Any single-frontend design must expressly exclude parallel tabs/other SDK clients until a genuine server-side lease exists.

## 3. Existing native work versus missing construction

**Track A — native coverage:** SHIPPED: [child launch](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts), [tool schema](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/constants/child-conversation.ts), [native tests](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/__tests__/services/child-conversation-launch.test.ts), replay ledger and parent feedback. ISSUE_ONLY: [#18768](https://github.com/OpenHands/OpenHands/issues/18768) team task board, [#18280](https://github.com/OpenHands/OpenHands/issues/18280) child wait/finish, [#18751](https://github.com/OpenHands/OpenHands/issues/18751) team charter. MERGED: [PR #16380](https://github.com/OpenHands/OpenHands/pull/16380) initial child tool. CLOSED UNMERGED: [PR #18268](https://github.com/OpenHands/OpenHands/pull/18268) sidebar nesting. None provides proof of shipped independent S2 admission ownership.

**Track B — independent on-top C construction:** Opt-in, local-only composition at `handleLaunchChildConversationAction`→`launchLocalChild`. Require bounded workspace identity and active-sibling observations; obtain an independently composed owner's revision-bound `admit/defer/deny`; check before operational launch and again if worktree-to-shared fallback is attempted, then consume source-native completion/error feedback. Enforce-mode missing/stale/revoked owner blocks only unsafe shared action. Disabled mode matches baseline.

| C-sufficiency requirement | Already present / proposed in original (A) | What still must be constructed (B) |
| --- | --- | --- |
| Sibling interference state and lawful decision | Workspace resolution, worktree/shared choice, parent metadata; no separate arbiter | Composable per-workspace S2 owner with current sibling status, finite reservations and distinct admit/defer/deny decisions |
| Protected launch/fallback effect and return | Canvas `launchConversation`, worktree fallback and `postClientToolResult` | Version/authority-bound pre-effect guard, mandatory fallback recheck and later completion/failure feedback; fail-closed unsupported concurrent client modes |

**Distinctness and falsifier:** A team-wide task board and waiting for completion are useful native work but neither alone gives an independently composed arbiter pre-effect authority over *this* fallback. If isolated worktrees plus a trivial host queue provide exactly the same protected outcome, or Canvas cannot enforce decisions across actual competing clients, the scoped C contribution is not established.

## 4. Priorities and minimum sufficient result

- **P0:** Optional Canvas-local S2 composed conflict arbiter at child launch and shared-fallback effect, returning observed child results to the arbiter and parent.
- **P1:** Verify same controlling Canvas instance, workspace identity, real active sibling status, authority/staleness/revocation behavior, and native regression tests for worktree/shared/Cloud/no-owner modes.
- **P2:** NONE; no implied team-board implementation, Agent Server-wide lease or second VSM function.

**Proposed C-sufficiency verdict:** PROPOSED_C_SUFFICIENT as a bounded source-grounded hypothesis for one controlling Canvas/local workspace; not proven across independent clients or implemented.

## 5. Proposed acceptance and stop gates

**Future positive test:** With two local child conversations sharing a workspace and a developer-supplied S2 actor, one launch is lawfully admitted while another is deferred or denied before `local_repo` effect; after the first child finishes the arbiter observes completion and permits the next, with parent result matching actual effect.

**Future negative test:** Missing/stale/revoked decision actor in enforce mode does not cause an unguarded shared child; an attempted worktree creation that fails triggers the second guard; Cloud and multi-tab/direct Agent Server modes are explicitly rejected or never claim shared-lease protection. Disabled guard retains baseline fallback and feedback.

**Proposed falsifier:** A native parent queue/strict worktree always yields equivalent task outcome, or any approved Canvas-local choice fails to prevent real same-workspace launch under the declared boundary; source mismatch in runtime ownership is a stop.

**Validation state:** NOT_RUN — only source and historical shipped tests inspected; no new tests executed or results claimed.

## 6. Independent paths

**Original-native contribution:** If independently authorized later, compare the simplest strict-worktree/no-shared-fallback fix before implementing an S2 arbiter. Reuse original #18768/#18280 rather than duplicate their scopes.

**Profile / Skills:** The accepted assessment is historical; any later ownership regrade belongs to the Index after independent executable evidence. No Profile/Skills methodology defect claimed.

**Domain fork:** The matching `opensiro-contributions/OpenHands` metadata branch is a research record; no product-branch prototype is authorized, and direct Cloud/SDK capabilities belong to their owners.

## 7. Cost hypothesis

Compare the unchanged worktree/serialized-parent alternative with a composed Canvas-local S2 arbiter on the same two-child workload. Include development, compatibility scope, testing, recovery and maintainer review. **Cost status: NOT_MEASURED** until a matched measurement exists; neither savings nor collision reduction is claimed today.

## 8. Decision / handoff

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

**Decision reason / next permitted step:** A source-native S2 closure hypothesis is coherent at the local Canvas child launch+fallback boundary and differs structurally from a passive warning or parent queue. The next legitimate task is an authorized, source-pinned two-child native experiment plus matched simplest-alternative comparison. This is not permission for product code changes or third-party publication. After this outside-cohort one-time restrictive fork bootstrap, further metadata revisions require an attributable owner RESUME; no new status-only Upstream PR.

**Agent/developer handoff:** [constructor-sufficiency.md](constructor-sufficiency.md) and [roadmap.md](roadmap.md) provide the technical obligations and canonical status.

**Rights and publication:** MIT [original license](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/LICENSE), [AGENTS.md](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/AGENTS.md) contributor and repository-boundary rules verified; no root CONTRIBUTING.md in observed tree, no inferred CLA/DCO grant, and human-only PR-description text cannot be supplied by AI. Correct parented fork; outside the initial 23's ACTIVE/ALLOW mandate, initial conservative `PAUSE/DORMANT` state. **DRAFT — NOT PUBLISHED**: no public fork GitHub Issue, original Issue/PR/comment, product branch write or Index grade update. Any outward action requires separate exact current-conversation owner approval.

**AI disclosure:** Prepared with AI assistance; tests NOT_RUN, cost NOT_MEASURED, no independent human quality review presumed.
