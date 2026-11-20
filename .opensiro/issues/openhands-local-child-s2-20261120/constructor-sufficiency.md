# OpenHands Agent Canvas — source-native S2 C-construction technical contract

**Canonical storage:** `opensiro-contributions/OpenHands@opensiro/meta:.opensiro/issues/openhands-local-child-s2-20261120/constructor-sufficiency.md`.
**Level 1 / Human decision Issue:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md) owns historical Index vector, six-function dispositions, P0/P1/P2, target, evidence and decisions.
**Stage:** PLAN_ONLY / HYPOTHESIS → PROPOSAL-STAGE → future independent VALIDATED capability; **DRAFT — NOT PUBLISHED**. No implementation, test pass or new Index grade.

## 1. Function-specific construction boundary and methodology checks

**Source and mode boundary:** [OpenHands/OpenHands@main:d5d790823e468587e9e4d8517860ca8ef75aad6a](https://github.com/OpenHands/OpenHands/commit/d5d790823e468587e9e4d8517860ca8ef75aad6a), Agent Canvas's browser-side `launch_child_conversation` client action in one local controlling Canvas runtime/workspace. The Agent Server/SDK owns the actual session service and API, OpenHands/automation owns scheduling, OpenHands/extensions owns reusable integrations; full multi-tab, Cloud, direct Agent Server clients, tests, examples and maintainer CI do not automatically participate in Canvas's in-scope S2 ownership. [Original AGENTS ownership map](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/AGENTS.md).

**Target transition:** S2=— -> S2=C

**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** Operational S1 coding agents execute potentially conflicting workspace edits. Candidate S2 must prevent sibling interference before Canvas dispatch/fallback while returning actual execution state. S3 priorities/whole-system commitments remain parent-side and are not substituted by S2 admission; S3* security/quality audit not implemented by this plan; S4 external prospective model choice not relevant; S5 user/backend/tool permission remains parent-owned. No accepted Index historical state is changed.

**Function witness:** The disturbance is two local children that may edit the same parent directory when worktree creation is impossible or fails. Today a parent action chooses requested isolation and Canvas applies hardcoded fallback. Proposed independent developer-composed S2 actor owns a bounded `admit isolated / defer shared / deny shared` anti-interference decision; Canvas enforces by withholding or launching via its existing source-native action, then returns actual start/completion/error feedback to the parent and actor. A supported single controlling Canvas instance is mandatory for this first constructor; it cannot confer global authority across tabs or Agent Server callers.

**Counterfactual owner test:** If the independently composed actor is absent while `launchConversation` and the fallback remain, Canvas still starts a conflicting shared sibling after default worktree failure. With an authorized actor, the missing function-specific difference is an actual state-dependent defer/deny versus admit decision tied to that same launch effect and later sibling status, not a logging wrapper.

**Possible methodological negative control:** A parent always using `worktree` or a sequential queue may fully avoid a real conflict without composing any S2 actor; that would falsify an incremental constructor need but not establish autonomous S2=C in Canvas. Any claim of Cloud/multi-tab global control would require a separately owned server lease/closure mechanism and new boundary evaluation.

**Contributor / maintainer priorities:** Original [AGENTS.md](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/AGENTS.md) assigns frontend vs Agent Server/automation ownership and reserves `HUMAN:` PR text to a human; original maintainers have not stated a preference for this constructor: NOT_STATED.

## 2. Source-pinned baseline and parallel native Track A / on-top Track B

**Original native workflow:** Parent agent requests `launch_child_conversation` using [client tool contract](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/constants/child-conversation.ts) and [Canvas handler](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts). `validateLaunchParams` checks target/isolation; `launchLocalChild` resolves parent working dir, selects default worktree, calls `launchConversation(... workspaceMode: new_worktree)`; scratch/unborn HEAD or worktree failure triggers shared `local_repo` fallback. `handleLaunchChildConversationAction` deduplicates replay by tool call and sends actual launched/error result using `postClientToolResult`; no distinct shared-workspace admission owner is shown.

**Closest existing solution:** Native isolated git worktrees and parent-level serialized launches, or an opt-in refusal to fall back to shared. This is cheaper than a new S2 actor, and the matched comparator in later experiments.

**Relevant original Issues/PRs:** [#18768](https://github.com/OpenHands/OpenHands/issues/18768) OPEN proposes team-shared task board (not pre-effect interference admission); [#18280](https://github.com/OpenHands/OpenHands/issues/18280) OPEN proposes wait-for-finish and cleanup (not currently shipped, potential feedback seam); [#18751](https://github.com/OpenHands/OpenHands/issues/18751) OPEN team orchestration; [PR #16380](https://github.com/OpenHands/OpenHands/pull/16380) MERGED introduced client child action; [PR #18268](https://github.com/OpenHands/OpenHands/pull/18268) CLOSED UNMERGED for sidebar nesting. These statuses were checked; unmerged code and Issue specifications are not treated as shipped.

| Required C link or operator outcome | Track A: shipped / original work | Track B: minimum original-native integration | Falsifier |
| --- | --- | --- | --- |
| Current sibling-workspace interference state and independent choice | `resolveConversationWorkingDir` plus parent metadata and fixed isolation/fallback; no independent S2 decision | Bounded developer-injected arbiter observes active child ids/current workspace and chooses `admit/defer/deny`, with authority/revision receipt | Parent queue/strict-worktree fully suffices, or actor has no legitimate discretionary choice |
| Binding launch and fallback effect | Existing `launchConversation` and fallback from `new_worktree` to shared `local_repo` | Guard before createChild and again before shared retry; never allow stale/missing/revoked enforce-mode actor to authorize shared collision | Guard runs after effect or cannot prevent it; another client bypasses the only claimed boundary |
| Returned outcome and next coordination decision | `postClientToolResult` gives initial child id/actual isolation/error; later child finish is not synchronous in default path | Observe actual child completion/termination through supported conversation-status service; release bounded workspace reservation and feed actor/parent before next admission | Reservation not reliably released or actor only gets launch notification without a feedback loop |

**On-top distinctness:** This is narrower than #18768's team task-board membership and #18280's child-response awaiting. A board status cannot be assumed to enforce admission at a shared fallback. The added S2 owner must really decide differently and affect the first-party Canvas dispatch. Browser-only atomicity is limited to the controller's observed scope, not distributed clients.

**Source ambiguity / rights blockers:** No executed multi-child real-workspace experiment, no independently verified active-sibling status data for every supported backend, and no cross-tab server lease. A root CONTRIBUTING.md is absent in the observed original tree; [AGENTS.md](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/AGENTS.md) governs AI behavior. These gaps are **NEEDS_EVIDENCE**, not claims of native tests or public publication authority.

## 3. Minimal complete S2 first-party C construction

**Required property:** A function-specific, first-party **Canvas-local** path lets a developer compose an autonomous anti-interference decision owner with lawful local child-admission options, protected real launch/fallback effects and later feedback. A passive event bus or replay dedupe is insufficient for C.

| Necessary native component / port | Existing file / API and evidence | Smallest proposed edit / developer integration | Owner, operational effect and feedback |
| --- | --- | --- | --- |
| Optional S2 choice at local child admission | [`handleLaunchChildConversationAction`](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts) and [tool action contract](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/constants/child-conversation.ts) | Compose a per-workspace decision owner after validation; read active children and bind a revision to `admit isolated/defer shared/deny shared`; never infer permission from unsupported provider | Developer-defined arbiter owns only conflict choice; Canvas enforces withholding/admission, parent receives decision receipt |
| Recheck before shared fallback | [`launchLocalChild`](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/services/child-conversation-launch.ts) lines 294–317 currently try `createChild("shared")` after failed worktree | Re-evaluate actor state immediately before fallback to local_repo; no unguarded retry with missing/stale/denied enforce-mode evidence; disabled mode retains exact native behavior | Canvas owns actual effect, arbiter chooses lawful coordination action, returned `isolation_note`/error reflects reality |
| Return of observed lifecycle state | Same handler's `reportLaunchResult` plus server-owned conversation/status APIs via [adapter](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/src/api/agent-server-adapter.ts) | Track actual started child and observe terminal completion/failure with bounded cleanup; release reserved workspace and return to actor/parent; no invented server endpoint | Child runtime owns actual completion; Canvas transports authoritative observation; composed arbiter may admit next sibling |

**Architectural C-sufficiency argument:** Three paths were considered: (A) no additional constructor—require worktrees/host serialization, cheapest and a strong falsifier; (B) opt-in single-Canvas pre-effect arbiter composed into the existing child-launch/fallback and feedback services, chosen as minimum possible first-party S2=C research hypothesis; (C) shared cross-tab/server-wide arbiter requiring separately owned SDK atomic lease, beyond this evaluation object. B could close the S2 function at the deliberately bounded single-controller local Canvas boundary if the active-sibling source, decision authority, guarded pre-effect, fallback recheck and later return all work together. Existing isolation and child status transport alone do not own that choice. No implementation or functional proof has been performed.

**Explicit non-goals:** No S3 global priorities/task board, independent S3* quality auditor, prospective S4 controller, invented S5 authority, Cloud sandbox scheduler, forced dependency on an unmerged PR, SDK-wide lock, cross-tab guarantee, product code patch or maintainer endorsement.

**Implementation dependency graph:** P1 identify supported workspace/sibling-state API and single-controller authority, check original issue/PR overlap, negative test actual worktree→shared fallback/unsupported multi-client mode → P0 inject optional arbiter, bind both pre-effects, return launch and completion feedback → native automated and real-workspace paired comparison → only then optional separate Index reassessment. Do not add second function as a hidden dependency.

## 4. Priorities, optional alternative and stopping rules

**P0 and P1:** P0 is a bounded optional S2=C builder tied to existing local Canvas client action; P1 is valid per-workspace status/authority with no cross-tab overclaim, fail-closed state and native two-child regression/effect tests. The receipt [roadmap.md](roadmap.md) is authoritative.

**P2:** NONE. New team-board S3 coordination or an SDK lease is a separate scope and requires new ownership evidence.

**Alternative path:** Prefer original worktree behavior and a host-level serialized queue if it protects the same task without an independent actor; a strict-fail instead of implicit shared fallback is a source-native repair proposal rather than automatically S2=C.

**Stop:** Stop/reject the narrow C hypothesis if an equivalent function-specific C already exists in current native source, if the actor's decision cannot legally gate the actual fallback or return real lifecycle feedback, if local controller authority is not enforceable or if the only useful fix is an ordinary isolation fallback bug repair. Maintainer adoption preference is separate from constructibility; parent PAUSE blocks further canonical metadata writes, not read-only analysis.

## 5. Future source-native acceptance — derive tests, do not copy a matrix

**Native test commands and entry points:** [Original package scripts](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/package.json) define `npm test` (Vitest), `npm run lint`, `npm run build`, and `npm run test:e2e` (Playwright). Scope most pertinent to [`__tests__/services/child-conversation-launch.test.ts`](https://github.com/OpenHands/OpenHands/blob/d5d790823e468587e9e4d8517860ca8ef75aad6a/__tests__/services/child-conversation-launch.test.ts); these commands are **NOT_RUN** in this research. A future implementer must use actual original dependency lock and test/CI rules.

**Positive functional closure:** In a real committed local Git repo with two active child tasks and the optional S2 actor, the arbiter observes the current workspace and admits an isolated child, but defers/denies a conflicting shared fallback *before* createChild shared action; after child finishes and state is observed, arbiter lawfully permits the next compatible sibling. The parent receives actual launched/deferred/failed result.

**Independent alternative (where applicable):** On matched active-sibling state, swapping two lawful composed policies must change a supported choice (e.g. defer vs reject shared) while leaving unchanged built-in client tool transport/effect and parent authority, proving an actual S2 actor instead of a fixed hardcoded guard.

**Negative authority and compatibility (where applicable):** Enforce mode with missing/stale/revoked decision blocks unsafe shared retry; unsupported multi-tab/multi-client mode must reject or narrow its protection claim; no-guard mode behaves as shipped, Cloud path not blocked by local-only controller, shared fallback returns explicit warning/error, cancellation/replay does not leak reservation.

**Matched native alternative:** The same two-child task with unchanged worktrees and serialized launches, measure correctness, completed tasks, collision avoidance, operator work and review/maintenance. Cost and incremental utility remain **NOT_MEASURED** until actually run.

| Proposed native case (all NOT_RUN) | Original-supported entry point | Expected real effect / return | Falsifier / stop |
| --- | --- | --- | --- |
| Competing local children after worktree failure | Mocked fallbacks in `__tests__/services/child-conversation-launch.test.ts` then real local runner | Distinct arbiter defer/deny prevents `createChild("shared")`; result explains protected nonlaunch | Shared child started before validated decision |
| Actor absent or stale; disabled mode | Same existing launcher native tests | In enforce mode fail-closed shared risk; disabled mode same fallback as baseline | Unsupported side effect or default-mode regression |
| Child terminal feedback and reservation recovery | Server conversation status through existing adapter/service | Real finish or failure releases reservation; next lawful child admitted | Only a one-time notification or never-cleared hold |

## 6. Proposal verdict, falsification, evidence ownership and handoff

**Proposal-stage decision:** GO

**Research disposition:** NEEDS_EVIDENCE

**Primary falsifier:** Existing native worktree/parent queue achieves equivalent S2 protection, or a composed Canvas-local arbiter has no lawful binding action at the actual launch and fallback boundary; multi-tab claims without a server-side lease would also falsify an overbroad scope.

**Validation state:** NOT_RUN

**Ownership of truth:** Profile defines VSM semantics, Skills owns assessment method, Index alone owns accepted/general grades, original OpenHands owns product/maintainer decisions, [roadmap.md](roadmap.md) is canonical for this research receipt and metadata state controls later writes.

**Cost status:** NOT_MEASURED

**Next permitted action:** Persist this plan-only four-file source-pinned case and restrictive owner-state event on the matched fork `opensiro/meta`; if an owner RESUME later permits follow-up, test source-native local two-child case against simplest comparator before proposing original product work. No native implementation or public fork/original Issue/PR/comment without separate owner approval.

**Human backlink:** [issue.md](issue.md) for user-operational need, decisions and exact pending-publication boundary.

**case receipt:** [roadmap.md](roadmap.md) for frozen Index/source/proposal-state fields.

**AI disclosure:** Prepared with AI assistance; native tests NOT_RUN, economic benefit NOT_MEASURED, and no original maintainer/human endorsement claimed. **DRAFT — NOT PUBLISHED** means no public fork GitHub Issue, no external third-party contact, no code or Index regrade.
