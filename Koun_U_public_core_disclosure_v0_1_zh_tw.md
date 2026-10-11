---
title: "Koun-U 語義總域與生命週期理論：公開核心披露稿"
subtitle: "Koun Architecture、C/W 生命週期、AGI、Neural-CTR 與意識候選理論"
author: "Shu Koun / 朱庫文"
version: "Public Core Disclosure v0.1"
public_date: "2026-10-11"
canonical_source: "Koun-U Semantic Domain and Lifecycle, Canonical Baseline v0.4"
canonical_source_date: "2026-08-18"
canonical_source_sha256: "05d63b4f4ad5db3395fdf6862251060946df0e8710083284b66f080190bd2125"
language: "zh-TW"
status: "PUBLIC CORE DISCLOSURE"
keywords:
  - Koun-U
  - KounGraph
  - Koun Architecture
  - Koun-SET
  - Koun-SWT
  - Koun-Bridge
  - Koun-SLT
  - Lifecycle Disposition Closure
  - AGI
  - consciousness
  - Neural-CTR
  - TSSR
---

# Koun-U 語義總域與生命週期理論

## 公開核心披露稿

**作者：Shu Koun / 朱庫文**  
**公開版本：Public Core Disclosure v0.1**  
**公開日期：2026-10-11**  
**依據主線：Koun-U Canonical Baseline v0.4，2026-08-18**  
**主線 SHA-256：`05d63b4f4ad5db3395fdf6862251060946df0e8710083284b66f080190bd2125`**

---

## 文件定位

本文是 Koun-U 理論的公開核心披露稿，用於在網路上形成一份可閱讀、可引用、可校驗、具有時間戳記意義的公開記錄。它不是完整主線手稿的摘要替代品，也不是一份只含宣傳口號的簡介；其目的，是以相對穩定的篇幅公開 Koun-U 的主要對象、基本操作、生命週期模組、計算架構、形式結果、AGI 架構、神經與意識候選理論，以及第一條可接觸人類資料的 Neural-to-CTR 經驗路線。

本文以 Canonical Baseline v0.4 為依據，保留其核心術語與主張狀態。完整定義、全部 schema、fixture、歷史台帳、版本治理與審計，仍以完整 canonical source 為準。

本文是一份公開披露記錄，不構成任何法域中的法律意見，也不保證單憑公開上傳即可自動產生特定的專利、學術或法律優先權效果。

---

# 摘要

Koun-U 是一套把語義對象、生成式計算、活動實現、歷史、懸持、釋放、提交、重播、挑戰與重開放入同一總域的理論。其核心不是把所有領域壓成一個大模組，而是建立一條可追蹤的架構：從 `Node` 與 KounGraph 出發，經過 Graph-Flux、Koun Minimal Kernel 與 Koun Architecture，進入 C/W 生命週期，再由 Koun-SET、Koun-SWT、Koun-Bridge、Koun-SLT 與 Lifecycle Disposition Closure 管理結果如何形成、何時保持未決、何時有權釋放、何時完成提交、如何重播，以及新證據出現時如何保留歷史地重開。

Koun-U 的統一主張是：

> 語義事件不能只由最終輸出決定。其 object identity、形成歷史、候選結構、owner、permission、witness、release path、commitment、replay 與 reopen surface，都可能改變合法 query 的答案。

因此，相同文字、相同數值或相同外顯行為，不必等同於相同語義事件。Koun-U 同時承認外延結果的重要性，但拒絕把外延結果當成全部。

Koun Architecture 是一種多中心、歷史敏感、生命週期原生的語義計算架構。它允許傳統 bytes、files、records、programs、events 與 signals 經由 Conservative Data Ingress 保守進入 Koun substrate；原始 carrier 不必先經過「共振」才能存在，而較高階的語義身份、概念模式與 query-relative equivalence，則可由 relation、matching、共同激活、basin convergence 與 crystallization 形成。

在 AGI 與人類認知方向，Koun 將智能理解為完整生命週期能力，而不只是產生答案的能力。系統必須能生成候選、合法懸持、拒絕、釋放、提交、重播、重開，並維持 provenance、responsibility 與 identity continuity。

在人腦與意識方向，Koun v0.4 建立 KT-Neuro、Conscious Transition Regime、W-ConsMind-5、Neural-to-CTR realization、Trajectory-Sensitive Structural Realization 與 KT-CH1--KT-CH20。它提出一套結構、功能與動力候選理論：意識相關現象可能由 target-bound、時間延展、多尺度、可受擾、可重入、歷史敏感、自我回返、記憶耦合且保留反事實路徑的 transition regime 實現。v0.4 進一步把該候選壓成可接觸人類 EEG、MEG、iEEG 與 fMRI 資料的 Neural-to-CTR empirical bridge，但目前仍未取得 Koun-specific human empirical support，感質映射也仍是待檢驗假說。

---

# 一、Koun-U 的核心正面主張

1. **語義事件具有歷史厚度。** 最終輸出不足以完全決定事件身份。
2. **一切 object-level 對象共享 `Node` carrier。** Relation、event、trace、rule、action、agent、packet 與 lifecycle view 是 refinement、role 或 bundle，而不是平行本體。
3. **Program 與 data 不是永恆本體。** 它們共享 object carrier，其差異由 execution context 中的 role assignment 產生。
4. **Graph 不等於 Flux。** Graph 是可重訪的結構支持；Flux 是當前被激活、帶 context 與 bias 的活動實現。
5. **合法未決是一等狀態。** 不提交不必被還原成失敗、空值或能力不足。
6. **Release 不等於 Commit。** 條件滿足、取得釋放權與完成責任型提交是不同事件。
7. **Reopen 不等於 Rollback。** 修正必須保存 prior commitment、challenge、scope change、responsibility delta 與 supersession history。
8. **Shared semantics 是 query-relative equivalence，而不是 private-state identity。**
9. **Koun 的反發散目標不是所有路徑得到同一答案。** 每個有界 branch 必須取得 typed、owner-bound、trace-bearing disposition。
10. **Closure 不等於 success。** `blocked`、`refused` 或 `withheld` 可形成合法閉包，但必須另行評估 resolution quality。
11. **Koun Architecture 在邏輯上多中心。** 它不要求唯一 global interpretation、唯一 active branch 或唯一 semantic center；具體部署仍可中央化、分散化或混合化。
12. **歷史可以成為運算對象。** Event、conflict、challenge 與治理更新不只是外部 log，而可被 reify、query、replay 與再次參與生成。
13. **AGI 是生命週期能力，而不只是 surface capability。**
14. **人類高階語義活動可以被當作 Koun semantic machine 的候選 realization。**
15. **意識是一類 target-separated、時間延展、多尺度、可受擾、可重入、歷史敏感的 transition regime 候選。**
16. **感質不由單一 report、endpoint 或 complexity scalar 決定。** Koun 以 TSSR 作為主要工作假說，要求 trajectory geometry、counterfactual reachability、self-return、body/valence relation 與 history continuity 進入 mapping。

---

# 二、全書統一骨架

```text
Node
  -> Relation / Bundle / Event / Trace
  -> Graph / Flux
  -> Koun Minimal Kernel
  -> Koun Architecture
  -> C/W lifecycle foundation
  -> Koun-SWT / Koun-Bridge / Koun-SET / Koun-SLT
  -> Lifecycle Disposition Closure
  -> Cross-layer semantic governance
  -> AGI / human cognition / neuro / consciousness / math / society
```

Koun-U 採用 `One Concept, One Canonical Home` 原則：同一對象可以在不同章節被解釋、應用或投影，但 canonical definition、owner 與 claim status 必須唯一。

---

# 三、Object Kernel：Node、Role、Relation 與 History

## 3.1 唯一 object primitive

Koun Minimal Kernel 的唯一 object primitive 是：

```text
Node
```

以下對象不是新的 object ontology，而是 `Node` 的 refinement、role、bundle 或 lifecycle view：

```text
BundleNode
RelationNode
EventNode
TraceNode
WitnessNode
RuleNode
ActionNode
AgentNode
WState
ReleaseEnvelope
CReadyView
SETPackageView
CState
SLTPacket
```

型別化關係寫成：

$$
\Gamma \vdash n : \tau @ o
$$

其中：

- $n$ 是 node identity；
- $\tau$ 是 refinement 或 execution role；
- $o$ 是 canonical owner；
- $\Gamma$ 是 context、scope、query、guard、permission 與 policy。

因此：

```text
shared carrier != identity of roles
role equality != node identity
node identity != semantic equivalence
```

## 3.2 最小生成關係

KounGraph 使用元層生成關係：

$$
\operatorname{associate}\subseteq Nodes\times Nodes\times Nodes
$$

可讀為：在指定規則與 context 下，$A$ 與 $B$ 可以生成或支持 $C$。具體 generation event 可以被 reify 成 object-level event node，但 meta-level legality relation 不與具體 event identity 合併。

## 3.3 Structural identity 與 semantic equivalence

兩個對象即使在某個 query 下回答相同，也不必是同一 object：

$$
x \neq y,
\qquad
x \approx_Q y
$$

`identity` 保留 object history、source 與 version；`equivalence` 則相對於 matching regime 或 query family。這是 KounGraph 對「同一」問題的核心區分。

## 3.4 歷史內嵌

Koun 的離散變化優先使用 versioned generation，而不是 silent overwrite：

```text
old object
  -> UpdateEvent
  -> new object
  -> Supersedes(new, old)
```

過去對象可以不再是 current focus，但不因此從 historical existence 中消失。

---

# 四、Koun Minimal Kernel

## 4.1 最小組態

跨模組最小組態：

$$
\Sigma = \langle G,X,\Gamma,H,\beta\rangle
$$

| 成分 | 作用 |
|---|---|
| $G$ | typed node graph；current 與 historical object support |
| $X$ | finite active request、branch 與 focus surface |
| $\Gamma$ | context、owner route、scope、query、guard、permission、policy |
| $H$ | append-only transition 與 trace surface |
| $\beta$ | finite step、generation、branch、reflection、replay、reopen 與 flow budgets |

Operational judgment：

$$
\Gamma;\Sigma\vdash op(i)\Downarrow\langle r,\Sigma'\rangle
$$

其中 $r:TransitionResult<O>$。任何基本 operation 都不得 silent-return `None`。

## 4.2 八個 primitive operation families

```text
Structural / active kernel
  1. Generate
  2. Execute

Observational kernel
  3. Assess

Lifecycle kernel
  4. Withhold
  5. Release
  6. Commit
  7. Replay
  8. Reopen
```

最低 signatures：

```text
Generate(a, b, generation_rule, context)
  -> TransitionResult<NodeRef>

Execute(ExecutableNodeView, ActivationRequest, ExecutionGrant?, Sigma)
  -> TransitionResult<CandidateEvent>

Assess(target, criterion, query, scope, horizon, tolerance?)
  -> TransitionResult<AssessmentReport>

Withhold(candidate, WGuard, potential_accounting, review_contract)
  -> TransitionResult<WStateRef>

Release(WStateView, WCertRole, ReleaseCondition, scope)
  -> TransitionResult<ReleaseEnvelopeRef>

Commit(SETCommitInput, witness, trace, governance)
  -> TransitionResult<SETPackageViewRef>

Replay(package_or_trace, query, horizon, exposure_policy)
  -> TransitionResult<ReplaySurfaceRef>

Reopen(CStateView, ReopenReason, ChallengeRecord?, scope)
  -> TransitionResult<ReopenedWStateRef>
```

## 4.3 每個 operation 的最低獨特作用

| Operation | 不可偷換的最低 effect |
|---|---|
| `Generate` | new identity 或 version formation |
| `Execute` | active transition 與 candidate formation |
| `Assess` | 在不默認改變 lifecycle posture 的情況下形成 report |
| `Withhold` | 形成合法 W-side posture |
| `Release` | 建立帶 permission 的 W-to-C boundary |
| `Commit` | 形成 responsibility-bearing C posture |
| `Replay` | query-bounded reconstruction of formation history |
| `Reopen` | prior-preserving C-to-W transition |

## 4.4 Reify

`Reify` 可由 `Generate` 構造，因此不是第九個 independent primitive：

```text
Reify(event_or_relation, type_tag, trace_policy)
  := Generate(descriptor, event_or_relation, reification_rule, context)
     + typed source / trace closure
```

但對 history-sensitive profile 而言，Reify 的義務不可省略，否則 execution、challenge、conflict 與 governance update 會退化為系統外 log。

## 4.5 Kernel invariants

```text
KMK-INV1  Node is the sole object primitive.
KMK-INV2  associate is meta-level; events may be reified.
KMK-INV3  Role equality is not node identity.
KMK-INV4  Every operation returns typed TransitionResult.
KMK-INV5  Discrete change is versioned generation, not silent overwrite.
KMK-INV6  Participation capability is not side-effect authority.
KMK-INV7  Assessment does not imply permission or commitment.
KMK-INV8  Release is not commit.
KMK-INV9  Reopen preserves prior CState and is not rollback.
KMK-INV10 Reflection is stratified and budgeted.
KMK-INV11 Cross-owner operations preserve owner reports and refs.
KMK-INV12 Reified events retain source and trace closure.
KMK-INV13 Semantic equivalence does not perform identity merge.
KMK-INV14 Continuous material needs a discrete audit/certificate surface before SET commit.
```

---

# 五、Graph、Flux、Continuous Semantics 與 Resonance

## 5.1 Graph 與 Flux

```text
Graph
  = stable, revisitable, addressable support

Flux
  = active, contextual, locally realized process
```

一個最低循環：

```text
Graph
  -> Activate
  -> Flux realization
  -> CandidateEvent
  -> Cryst or Withhold
  -> Graph / Trace update
  -> future Activate
```

Graph 不等於執行；可能路徑不等於實際路徑；structure 不等於 activation。

## 5.2 Continuous configuration

有限支持 continuous configuration 可寫成：

$$
\Xi=\langle\Gamma,X,a,W,C,B,\tau\rangle
$$

其中：

- $\Gamma$ 是有限候選支持；
- $X$ 是連續語義狀態；
- $a$ 是 activation field；
- $W$ 是 triadic generation strength；
- $C$ 是 context field；
- $B$ 是 history、policy 或 attention bias；
- $\tau$ 是 bounded audit trace。

候選動力：

$$
\dot x_\gamma=f_\gamma(X,a,W,C,B,\tau)
$$

$$
\dot a_\gamma=g_\gamma(X,a,W,C,B,\tau)
$$

$$
\dot W_{\alpha\beta\to\gamma}
=p_{\alpha\beta\to\gamma}(X,a,W,C,B,\tau)
$$

## 5.3 Dynamical equivalence 與 semantic basin

$$
\Xi_0\approx^{\pi_{sem}}_{dyn}\Xi'_0
\iff
\pi_{sem}(\omega(\Xi_0))
=
\pi_{sem}(\omega(\Xi'_0))
$$

$$
\mathcal B(A)
=
\{\Xi_0\mid\pi_{sem}(\omega(\Xi_0))=A\}
$$

Dynamical equivalence 不等於 structural identity，也不等於 lifecycle commit。

## 5.4 Semantic Resonance

Semantic resonance 不是 raw data 存在的條件，也不是新的物理力。它是：

> 多個既有 carrier、node、structure 或 active state，在指定 context、matching regime 或 continuous dynamics 下，形成穩定共同識別或高階 semantic pattern 的可選機制。

```text
carrier existence
  -> structural embedding
  -> matching / co-activation / basin convergence
  -> recognized semantic pattern
  -> optional crystallization
```

---

# 六、Koun Architecture 與五層資料存在方式

Koun Architecture 的正式定位：

> Polycentric, History-Sensitive, Lifecycle-Native Semantic Architecture.

它在邏輯上允許多個 active center、owner、branch、perspective 與 local convergence center；但不強制具體部署一定是完全分散式。

## 6.1 D0 到 D4

### D0：Raw Carrier

```text
bytes
scalar
string
signal
external reference
raw file
raw packet
```

Raw carrier 不需要先經 resonance 才存在。

### D1：Addressable Object

```text
stable_id
carrier_ref
encoding
source_ref
integrity_anchor
import_event
```

Path、filename、memory address 與 row offset 只是 locator 或 view，不自動等於 identity。

### D2：Structured Semantic Object

```text
Node
RelationNode
FieldNode
ValueNode
schema
decode trace
source relation
```

解析產生 structure，但不得摧毀 raw source。

### D3：Role- and Context-Bound Semantic Object

同一 object 可以在不同 execution event 中承擔：

```text
Value
Rule
Action
Trigger
Guard
Target
Context
Witness
Agent
```

Object identity 不等於 current role。

### D4：Recognized / Crystallized Semantic Pattern

高階 pattern 可由 matching、co-activation、history、basin convergence 或 human confirmation 形成，但不能 identity-merge source records。

---

# 七、Conservative Data Ingress

Koun Architecture 不要求資料從零出生在 Koun world。傳統資料可以保守導入：

```text
CaptureRawCarrier
  -> EstablishStableIdentity
  -> DecodeStructuredView
  -> GenerateRelations
  -> AssignContextRoles
  -> OptionalRecognitionOrResonance
  -> LifecycleRouting
  -> ExportAndRoundtripValidation
```

## 7.1 Raw round trip

在 immutable custody 與 deterministic codec 的條件下：

$$
ExportRaw(ImportRaw(x))=x
$$

這是 `CDI-TH1` 的 paper-level conservativity result，不是整體架構正確性定理。

## 7.2 JSON worked example

傳統資料：

```json
{
  "name": "Alice",
  "age": 30
}
```

最低導入：

```text
RawPayloadNode P0
ImportedObjectNode AliceRecord
Field_name
Field_age
Value_Alice
Value_30
```

關係：

```text
DecodedFrom(AliceRecord, P0)
HasField(AliceRecord, Field_name)
HasValue(Field_name, Value_Alice)
HasField(AliceRecord, Field_age)
HasValue(Field_age, Value_30)
```

更新為 `age = 31` 時：

```text
Value_30
UpdateEvent_E1
Value_31
Supersedes(Value_31, Value_30)
GeneratedBy(Value_31, E1)
```

不得 silent overwrite。

## 7.3 CDI invariants

```text
CDI-INV1  Raw carrier is preserved or external custody is disclosed.
CDI-INV2  Import does not fabricate unknown provenance.
CDI-INV3  Decoded view does not replace source identity.
CDI-INV4  Path, name and offset do not become stable identity by default.
CDI-INV5  Role assignment does not change object identity.
CDI-INV6  Recognition does not identity-merge source objects.
CDI-INV7  Update creates version and supersession trace.
CDI-INV8  Import success is not semantic commit.
CDI-INV9  Export declares query and loss profile.
CDI-INV10 Round-trip claims declare their query family.
CDI-INV11 Central runtime does not absorb canonical owner verdicts.
CDI-INV12 Resonance is not promoted to raw existence condition.
```

---

# 八、C/W 生命週期與四個 owner modules

## 8.1 C-side 與 W-side

`C` 與 `W` 不是「正確／錯誤」二分。

```text
C-side
  = 在明示 scope、query、witness、permission 與 governance 下，
    已形成可承擔、可重播、可挑戰的 commitment posture。

W-side
  = 候選、衝突、未決、保護潛能或證據不足被合法保留，
    並具有 guard、trace、review、release 或 refusal contract。
```

## 8.2 六個治理動詞

```text
withhold
refuse
release
commit
replay
reopen
```

它們不是全部同級的 machine primitive，但共同構成 reader-facing governance grammar。

## 8.3 四模組分工

| 模組 | Canonical responsibility |
|---|---|
| Koun-SWT | W-side legality、WStateWF、guard、potential、trace、refusal、suspension、release readiness |
| Koun-Bridge | W-to-C permission boundary、ReleaseEnvelope、CReadyView、release trace、reopen handoff |
| Koun-SET | candidate execution、package、commit、QLinkAlignment、replay、public witness |
| Koun-SLT | owner binding、query binding、module-boundary conservation、lifecycle coordination、LBC |

---

# 九、Koun-SWT：合法懸持

`WState` 不是普通 ambiguity，也不是 `Option.None`。

最低內容包括：

```text
candidate or potential set
admissibility
protected potentials
WGuard
WTrace or trace debt
scope
owner
review trigger
release / refusal / suspension conditions
```

## 9.1 W0 到 W6

| 類別 | 含義 |
|---|---|
| W0 | raw suspension；尚未合法化 |
| W1 | admissible multipotential；已識別多潛勢 |
| W2 | guarded withholding |
| W3 | traceable withholding |
| W4 | Bridge-facing withholding；可釋放或重開 |
| W5 | self-indexed withholding；主體性研究地平線 |
| W6 | agentive withholding；AGI 研究地平線 |

## 9.2 Refusal 與 Suspension

```text
Refusal
  = 有理由、有 owner、有下一步或終止條件的合法 verdict。

Suspension
  = 暫停當前路徑，但必須保存原因、review trigger 與 resume condition。
```

它們都不等於 drift 或 silent failure。

---

# 十、Koun-Bridge：Release 不是 Commit

Bridge 的任務是擁有轉換，不是擁有真理。

```text
WStateView
  -> eligibility / permission assessment
  -> ReleaseEnvelope
  -> CReadyView
  -> SETCommitInput
```

重要區分：

```text
condition satisfied
  != permission granted

ReleaseEnvelope
  != CState

CReadyView
  != committed result
```

Bridge 必須保存 release trace。Raw WState 不得直接進入 SET commit。

---

# 十一、Koun-SET：Commit、Package、Replay 與 QLinkAlignment

SET 不接受裸答案作為完整 semantic event。最低 package 必須能承載：

```text
extensional result
scope
witness
trace / provenance
governance
release trace when Bridge-sourced
replay surface
challenge entrypoint
```

## 11.1 CommitPackage、SETPackageView 與 CState

```text
CommitPackage
  = commit-event bundle role

SETPackageView
  = bounded canonical checker-facing view

CState
  = post-commit lifecycle state
```

三者可共享 carrier，但不能 identity-merge。

## 11.2 QLinkAlignment

`QLinkAlignment` 要求：extensional result、provenance、governance、witness 與 release trace 在同一 query/scope surface 上相互對齊。

Verdict family 包括：

```text
aligned
partially_aligned
scope_mismatch
exposure_blocked
```

它不是普通 intersection，也不是「所有欄位都有值」就算通過。

## 11.3 Replay

Replay 是 query-bounded reconstruction，不是全宇宙重演：

```text
finite-horizon
witness-bounded
registry-bounded
query-indexed
```

---

# 十二、Koun-SLT：Boundary Conservation 與 Lifecycle Coordination

SLT 不成為大總包，也不吸收 SET、SWT 或 Bridge 的 owner semantics。

它負責：

```text
object owner binding
query owner binding
trace owner binding
projection discipline
module-boundary conservation
cross-module invariants
Lifecycle Boundary Checker
```

核心不變式包括：

```text
No raw WState commit
Release trace survival
QLinkAlignment visibility
Reopen is not rollback
Prior commitment preservation
No silent failure
Evidence maturity remains scoped
```

---

# 十三、Lifecycle Disposition Closure

## 13.1 Closure target

Koun 的 closure 不是「所有路徑得到同一答案」，而是：

> 每個被激活、well-formed、資源有界的 request 或 branch，必須在當前 scope、query 與 horizon 下取得 typed、owner-bound、trace-bearing lifecycle disposition。

合法 disposition class：

```text
c_final
w_stable
typed_handoff
typed_defect
```

可能的 disposition：

```text
committed
withheld
refused
suspended
stable_horizon_withholding
release_ready
needs_witness
scope_limited
reopen_required
blocked
invalid
malformed
silent_loop_detected
oscillation_without_progress
budget_exhausted
continuous_certificate_missing
```

## 13.2 Progress measure

Obligation vector：

```text
omega := <
  unresolved_query_debt,
  protected_potential_debt,
  witness_debt,
  trace_debt,
  owner_binding_debt,
  scope_debt,
  handoff_debt
>
```

Budget vector：

```text
beta := <
  remaining_steps,
  generation_budget,
  branch_budget,
  reflection_budget,
  replay_budget,
  reopen_budget,
  flow_window_budget
>
```

令 $\alpha$ 為 active residue：

$$
\mu(\Sigma,b)
=
\left\langle
\|\beta\|_1,
\|\omega\|_1,
\alpha
\right\rangle
\in\mathbb N^3
$$

每個 non-disposition step 必須滿足：

$$
\mu(\Sigma',b')<_{lex}\mu(\Sigma,b)
$$

否則形成 `silent_loop_detected`。

## 13.3 LDC-TH1

在有限 initial surface、有限 budgets、typed totality、progress-or-dispose、strict decrease、owner/type preservation、有限 branch generation 與 bounded reopen 等假設下，任何 maximal run 必須在有限步內抵達 well-formed `DispositionBundle`，且沒有 untyped active residue。

主張狀態：

```text
[PAPER-THM]
manuscript proof present
not [MECH-THM]
not global termination theorem
```

## 13.4 Closure 不等於 success

```text
resolved
lawfully_deferred
justified_refusal
recoverable_failure
unrecoverable_failure
vacuous_disposition
```

必須與 closure existence 分欄報告。對所有 request 無條件回傳 `blocked` 的系統即使閉包，也不是 task-adequate。

---

# 十四、History-Sensitive Semantic Computation

對 extensional query：

$$
\pi_{ext}(\Sigma_1)=\pi_{ext}(\Sigma_2)
\Rightarrow
Q(\Sigma_1)=Q(\Sigma_2)
$$

對 history-sensitive query，可能存在：

$$
\pi_{ext}(\Sigma_1)=\pi_{ext}(\Sigma_2)
$$

但：

$$
Q(\Sigma_1)\neq Q(\Sigma_2)
$$

因此，是否可以抹除 history 必須由 `QuerySensitivityProfile` 與 `QueryAdequacyProfile` 明示。選擇過弱的 query 來宣稱原本重要的差異不存在，構成 `query_laundering`。

---

# 十五、Semantic Sealing、Query Admissibility 與 Responsibility

## 15.1 Commit 不等於 Seal

```text
PublicEncapsulation
  = 將 private realization 封裝成可傳遞 artifact。

SemanticSealing
  = 把已提交或制度化內容升格成不需要再 challenge、replay 或 reopen。
```

```text
Commit != Seal
CState != UnchallengeableTruth
QLinkAlignment pass != absolute finality
```

## 15.2 Query Admissibility

問題本身也要型別化。可能 verdict：

```text
well_formed
underspecified
scope_inconsistent
perspective_mixed
self_intervening
counterfactual_unanchored
owner_missing
unanswerable_under_current_observation
malformed
```

但 admissibility gate 本身也可能被權威濫用，因此必須可 version、replay、challenge 與 appeal。

## 15.3 Responsibility Trace Continuity

責任不是守恆標量。它可以：

```text
retain
split
share
delegate
narrow
contest
supersede
discharge_with_reason
mark_unresolved
```

但 prior attribution 不得無痕消失：

$$
PriorAttributions
\subseteq
ReachableCurrentAttributions
\cup
TypedTransformations
\cup
ExplicitUnresolved
$$

---

# 十六、Koun-AGI

Koun-AGI 的核心主張：

> AGI 不是答案機器，而是能承擔完整語義生命週期的架構候選。

最低責任平面：

```text
Transition / Execution
Equivalence / Abstraction
Dynamical Regulation
Convergence Assessment
Lifecycle Governance
Replay / Reopen / Self-Revision
```

最低能力：

```text
ExecutionCapability
EquivalenceCapability
WithholdingCapability
ConvergenceAssessmentCapability
ReleaseDiscipline
CommitDiscipline
ReplayCapability
ReopenCapability
```

重要 surfaces：

```text
AGIEvent
AGIResultBundle
NCII
SemanticRuntimeStore
EgressSurface
AGIEval
```

AGI result 不能只是 answer string；公開回答、行動、委派與覆寫必須帶 exposure、authorization、challenge、reopen 與 responsibility surface。

---

# 十七、人類語義活動映射

## 17.1 Mapping problem

$$
\Phi^{HSA}_{S,Q,h}:
\mathcal H^{sem}_{p,[t_0,t_1]}
\rightharpoonup
\mathcal K_{S,Q,h}
$$

映射不是 neuron-to-node identity，而是有限時間窗、明示尺度與 query 下的 functional-structural realization。

## 17.2 七項保存義務

```text
HSA-M1  Content Preservation
HSA-M2  Alternative-Structure Preservation
HSA-M3  Temporal-Order Preservation
HSA-M4  Memory / History Preservation
HSA-M5  Commitment-Posture Preservation
HSA-M6  Perspective / Ownership Preservation
HSA-M7  Reopenability Preservation
```

若一個 mapping 只能把所有心理活動事後改名為 Generate、Assess 或 Commit，而不能保存上述差異，也不能排除錯誤 mapping，它就只有描述性，沒有解釋力。

## 17.3 Private Realization、Public Encapsulation、Query Equivalence

```text
PrivateRealization
  -> PublicEncapsulation
  -> InterpretationAmbiguityView
  -> query-relative shared semantics
```

不同主體對形式對象 `1` 的學習史、聯想、身體狀態與感質可能不同，但在算術 query 下可以等價：

$$
R_A(1)\neq R_B(1),
\qquad
R_A(1)\approx_{Q_{arith}}R_B(1)
$$

共享語義是等價，不是私人狀態同一。

---

# 十八、KT-Neuro：人腦的候選承載與機制族

KT-Neuro 把人腦看作多尺度、隨機、可塑、離散與連續混合的 carrier，而不是把單一神經元直接等同 semantic Node。

## 18.1 多尺度

```text
N0  molecular / receptor
N1  synapse / dendrite / axon
N2  neuron
N3  assembly / microcircuit
N4  mesoscale circuit / region
N5  whole-brain network
N6  brain-body-environment loop
```

每個 neural node claim 必須聲明尺度、時間窗、relation type 與 measurement projection。

## 18.2 Activation、Propagation、Gating

候選機制包括：

```text
continuous membrane dynamics
discrete spike events
population dynamics
excitation / inhibition
delays
neuromodulation
gating
attention routing
stochastic dynamics
```

Activation 不等於單一布林開關；Trigger、biophysical guard 與 semantic permission 也不得混合。

## 18.3 Plasticity

```text
first-order transition
  改變活動

second-order transition
  改變未來 transition 參數

third-order transition
  改變如何改變參數的規則
```

包括 short-term plasticity、LTP/LTD、STDP、intrinsic plasticity、homeostatic scaling、metaplasticity 與 structural plasticity。

## 18.4 Memory

```text
encoding
stabilization
reactivation
replay
cellular consolidation
systems consolidation
retrieval
reconsolidation
supersession / interference / forgetting
```

```text
reactivation != replay
replay != conscious recollection
retrieval != read-only operation
forgetting != necessarily deletion
```

---

# 十九、意識候選理論

## 19.1 Target separation

Koun 強制區分：

```text
Level / capacity
Episode presence
Content
Access
Report
Flexible action
Self-index
Memory / history continuity
Phenomenal structure
```

因此：

```text
unresponsiveness != unconsciousness
content != access
access != report
report != phenomenal presence
self-model != qualia
```

## 19.2 W-ConsMind-5

| Historical condition | Current reading |
|---|---|
| 張力內聚性 | differentiated metastable coordination |
| 責任鏈可追溯性 | causal and source traceability |
| 干涉容錯性 | controlled multiplicity under conflict |
| 語義主位感 | multicomponent self-index / self-encapsulation |
| 開放記憶場 | reactivatable and revisable memory coupling |

它們是 graded hypothesis family，不是意識充分條件。

## 19.3 KounConsciousnessCandidate

```text
KounConsciousnessCandidate := {
  target_bindings,
  temporal_window,
  carrier_scales,
  ctr_profile,
  counterfactual_transition_space,
  local_convergence_profile,
  global_withholding_profile,
  self_encapsulation_profile,
  memory_continuity_profile,
  phenomenal_invariant_profile,
  neural_realization_refs,
  measurement_projection_refs,
  competing_models,
  uncertainty,
  evidence_status
}
```

正面候選：

> 意識相關現象由一類 target-bound、時間延展、多尺度、可受擾、可重入、歷史敏感的 transition regime 實現；該 regime 能形成局部內容穩定，保留與 target 相關的反事實替代路徑，維持可修正的 self-index 與 memory continuity，並把感覺、行動、來源與未來路徑折返到同一主體性邊界。

主張狀態：`[EMP-HYP]`。

---

# 二十、Conscious Transition Regime

CTR 的核心候選 properties：

```text
differentiated coordination
reentrant sustainment
metastable repertoire
perturbational differentiation
selective availability
history sensitivity
self-return
memory continuity
```

Target-specific regimes：

```text
CTR-Level
CTR-Content<c>
CTR-Access<c,Q>
CTR-Self<c,s>
```

CTR 不等於一般複雜動力。Recurrence、metastability 或 complexity 單獨存在都不足以支持 consciousness candidate。必須同時聲明 target binding、selective availability、self-return、memory continuity、null models 與 phenomenal mapping eligibility。

---

# 二十一、Neural-to-CTR realization

$$
\mathcal R_{\mathrm{N2CTR}}:
\mathcal N^{\sigma}_{[t_0,t_1]}
\times Q
\rightharpoonup
\mathrm{CTRProfile}_Q
$$

最低 record：

```text
NeuralCTRRealizationRecord := {
  neural_scales,
  temporal_window,
  measured_state_variables,
  effective_connectivity_refs,
  recurrence_and_delay_profile,
  gating_and_routing_profile,
  metastability_and_repertoire,
  perturbation_response,
  memory_and_plasticity_coupling,
  self_index_proxies,
  counterfactual_task_surface,
  observation_projection,
  causal_interventions,
  null_models,
  ctr_components_supported,
  ctr_components_unresolved
}
```

Correlation map 不等於 mechanistic realization。真正提升需要 target-specific intervention、counterfactual model 與 alternative-regime comparison。

---

# 二十二、Phenomenal Mapping 與 TSSR

## 22.1 問題形式

$$
\mathcal M_{phen}:
\mathcal H_C/\sim_{phen}
\rightharpoonup
\mathcal P
$$

其中 domain 不是單一 endpoint，而是 time-extended history 或 transition regime。

## 22.2 Primary working stance

v0.3 起，Koun 採用：

# Trajectory-Sensitive Structural Realization

其工作主張：

> Phenomenal character 由 self-encapsulated、counterfactually structured、時間延展的 transition trajectory 所實現；其可比較結構由 trajectory 的 relational geometry、local transition curvature、retained alternatives、return paths、body/valence relation 與 history continuity 決定，而不是由單一 endpoint、report 或 scalar complexity 決定。

$$
\mathcal M_{\mathrm{TSSR}}:
\mathcal H_C/\sim_{\mathrm{TSSR}}
\rightharpoonup
\mathcal P
$$

## 22.3 PhenomenalInvariantProfile

```text
trajectory relations
counterfactual reachability
local transition curvature
self-return structure
binding and segmentation
body / valence structure
history continuity
retained and excluded alternatives
admissible transformations
predicted equivalences
predicted discriminations
intervention surface
```

TSSR 是可反駁的 phenomenal hypothesis，不是已驗證的 qualia identity。

---

# 二十三、Koun-specific predictions

既有 KT-CH1--KT-CH16 包括 perturbational repertoire、unresponsiveness dissociation、content recurrence without report、selective access transition、same-report history sensitivity、self-index dissociation、open-memory update、scale-and-projection、targeted perturbation、cross-substrate invariance，以及 TSSR 相關的 counterfactual basin、self-return、trajectory geometry 和 memory continuity 預測。

v0.4 新增：

```text
KT-CH17 Endpoint-Matched Trajectory Separability
KT-CH18 Trajectory Increment over Endpoint
KT-CH19 Delayed Memory and Reopen
KT-CH20 Cross-Paradigm and Cross-Modal Transfer
```

核心風險命題：

> 當 stimulus、report、correctness、confidence 與 late endpoint 被匹配時，不同 formation history 仍應具有可重現的 neural trajectory；trajectory features 應對 delayed memory、source attribution、confidence revision 或 reopen behavior 提供 held-out 增量預測。

若沒有增量預測力，相關 HSSC、CTR 或 TSSR 主張必須削弱或退役。

---

# 二十四、v0.4 Neural-to-CTR empirical bridge

## 24.1 Stage-oriented measurement view

$$
Y_i(t)
=
\langle E_i(t),L_i(t),G_i(t),A_i(t),H_i(t),K_i(t)\rangle
$$

| 變量 | 工作含義 |
|---|---|
| $E(t)$ | early sensory evidence |
| $L(t)$ | local recurrent integration |
| $G(t)$ | global availability、routing 或 maintenance |
| $A(t)$ | alternative occupancy 與 competition |
| $H(t)$ | history、reentry 與 persistence |
| $K(t)$ | report/action commitment readiness |

這些是 measurement coordinates，不是 canonical lifecycle objects。

## 24.2 Target-oriented NeuralCTRState

$$
Z(t)
=
\langle C(t),B(t),R(t),G(t),M(t),S(t)\rangle
$$

| 變量 | 含義 |
|---|---|
| $C(t)$ | target content differentiation |
| $B(t)$ | competing alternatives 與 withheld potential |
| $R(t)$ | recurrent sustainment |
| $G(t)$ | selective availability 與 access gating |
| $M(t)$ | memory trace 與 history continuity |
| $S(t)$ | self-return 與 source-binding proxy |

候選動力：

$$
\tau_C\dot C=-C+f_C(I_C,R,G,B)
$$

$$
\dot M=-\lambda_M M+\eta_{CR}CR+\eta_{GC}GC+\eta_{CB}CB
$$

$$
\dot S=-\lambda_S S+\eta_{GM}GM+\eta_C C+\eta_{CB}^{S}CB
$$

這些是可由 neural mass、recurrent network 或 probabilistic state-space model 實現的功能座標，不是六個固定腦區。

## 24.3 Endpoint vs trajectory

Endpoint projection 可以包括：

```text
report
accuracy
confidence
terminal content readout
terminal access readout
late-window amplitude
reaction time
```

Trajectory features 可以包括：

```text
path length
path curvature
alternative occupancy
conflict integral
recurrence integral
access integral
temporal-generalization stability
memory-update proxy
self-return proxy
perturbation response
```

增量條件：

$$
\operatorname{Perf}
\left(M_{trajectory}\mid E,H\right)
>
\operatorname{Perf}
\left(M_{endpoint}\mid E\right)
$$

## 24.4 Human-data routes

```text
KCTR-OBS-01
  public-data reanalysis route
  EEG / MEG / iEEG / fMRI

KCTR-INT-01-MEDH
  prospective matched-endpoint, divergent-history experiment
```

MEDH 主要比較：

```text
Direct history
  early evidence directly supports final answer

Conflict history
  early evidence supports multiple candidates,
  later evidence resolves to the same final answer
```

在匹配 final choice、accuracy、confidence、reaction time 與 late neural endpoint 後，比較 reopen probability、confidence revision、source memory、source misattribution、later priming 與 counterevidence response。

目前經驗成熟度仍為 `C-E0`；synthetic artifact 只驗證分析契約可執行，不是人類證據。

---

# 二十五、形式化路線

Koun v0.4 將形式化分為六層：

```text
F0 Representation
F1 Protocol
F2 Invariant
F3 Theorem
F4 Model
F5 Empirical operationalization
```

建議 proof packages：

```text
Koun.Core
Koun.Lifecycle
Koun.LDC
Koun.Lowering
Koun.Query
Koun.Responsibility
Koun.CDI
Koun.Consciousness.Schema
```

重要區分：

```text
DescriptiveModel
NormativeProtocol
ComplianceTheorem
EmpiricalHypothesis
```

第一條真正有力的形式化，不只是重證自然數嚴格下降不會無限下降，而是構造一個非平凡 scheduler 或 importer，證明它真的滿足 LDC 或 CDI 的 assumptions。

---

# 二十六、主張狀態語法

| 標籤 | 含義 |
|---|---|
| `[DEF]` | 定義 |
| `[NORMATIVE-SPEC]` | owner-bound MUST / MUST NOT rule |
| `[PAPER-THM]` | 有條件且具有 manuscript proof 的紙上定理 |
| `[FORMAL-CONJ]` | 尚待證明的形式猜想 |
| `[MECH-THM]` | proof assistant kernel 已接受 |
| `[ARTIFACT-CHECKED]` | 有限 schema、fixture 或 checker 結果 |
| `[EMP-HYP]` | 經驗假說 |
| `[EMP-SUPPORTED]` | 有明示範圍的經驗支持 |

局部 checker PASS、synthetic PASS、paper proof、Lean kernel proof 與 human empirical support 是不同狀態，不得互相偷升。

---

# 二十七、目前已建立與尚未建立的內容

## 已建立

- Koun object kernel、Graph-Flux 與 Minimal Kernel；
- C/W state axis 與六治理動詞；
- SET、SWT、Bridge、SLT 的 owner-bound lifecycle；
- LDC 的有界 disposition closure paper theorem；
- Koun Architecture、D0--D4 data ontology 與 Conservative Data Ingress；
- HSSC、query sensitivity、query adequacy 與 responsibility continuity；
- Koun-AGI application architecture；
- KT-Neuro 多尺度 carrier、activation、gating、plasticity、memory 與 replay scaffold；
- consciousness target separation、W-ConsMind-5、CTR、Neural-to-CTR、TSSR；
- KT-CH1--KT-CH20；
- v0.4 Neural-to-CTR empirical bridge、synthetic routes 與 preregistration drafts；
- 多個 bounded local artifacts 與 fixture suites。

## 尚未建立

- 全套 Koun 的 proof-assistant mechanization；
- 非平凡 runtime instance 對 LDC assumptions 的完整 proof；
- CDI extension conservativity 的 mechanized proof；
- accepted independent external rerun of the complete v0.4 bridge；
- Koun-specific preregistered human empirical result；
- 已驗證的 Neural-to-CTR realization；
- TSSR 對 phenomenal character 的必要性或充分性；
- Koun 相對競爭意識理論的穩定增量解釋優勢；
- 跨載體 phenomenal equivalence result。

---

# 二十八、公開核心主張登記

為便於網路引用，本文將核心主張壓縮為以下登記：

```text
KU-CORE-01
Semantic events may differ despite identical extensional outputs.

KU-CORE-02
Node is the sole object primitive; roles and lifecycle objects are refinements or views.

KU-CORE-03
Program and data share carrier; their operational distinction is context-bound role assignment.

KU-CORE-04
Graph and Flux are distinct: stored structure is not active realization.

KU-CORE-05
Koun Minimal Kernel consists of Generate, Execute, Assess, Withhold, Release, Commit, Replay and Reopen, with Reify as a protected derived macro.

KU-CORE-06
Lawful withholding is a first-class lifecycle disposition.

KU-CORE-07
Release and Commit are irreducibly distinct lifecycle events.

KU-CORE-08
Reopen preserves prior commitment and is not Rollback.

KU-CORE-09
Lifecycle closure targets typed responsibility posture, not universal normal-form equality.

KU-CORE-10
Shared semantics is query-relative equivalence, not private-state identity.

KU-CORE-11
Koun Architecture is polycentric, history-sensitive and lifecycle-native.

KU-CORE-12
Conventional data can enter Koun conservatively without requiring semantic resonance for raw existence.

KU-CORE-13
Higher-order semantic recognition may arise through relation, matching, co-activation, basin convergence and crystallization.

KU-CORE-14
AGI competence includes withholding, release, commit, replay, reopen and responsibility continuity.

KU-CORE-15
Human semantic activity is a candidate realization of Koun lifecycle structure when content, alternatives, history, commitment, perspective and reopenability are preserved.

KU-CORE-16
Consciousness-related phenomena are modeled as target-separated, time-extended, multiscale, perturbable, reentrant and history-sensitive transition regimes.

KU-CORE-17
Same report does not entail same conscious or cognitive episode.

KU-CORE-18
TSSR proposes that phenomenal character depends on trajectory-sensitive relational structure rather than endpoint or report alone.

KU-CORE-19
Endpoint-matched but history-divergent trials should remain neurally separable and predict delayed memory, source attribution, confidence revision or reopen behavior.

KU-CORE-20
No artifact, paper proof or synthetic result may be promoted into human or phenomenal evidence without a separate evidence event.
```

---

# 二十九、建議引用格式

## 中文

> Shu Koun（朱庫文），《Koun-U 語義總域與生命週期理論：公開核心披露稿》，Public Core Disclosure v0.1，2026-10-11。依據《Koun-U 語義總域與生命週期總論》Canonical Baseline v0.4，2026-08-18。

## English

> Shu Koun. *Koun-U Semantic Domain and Lifecycle Theory: Public Core Disclosure*. Public Core Disclosure v0.1, 2026-10-11. Based on *Koun-U Semantic Domain and Lifecycle, Canonical Baseline v0.4*, 2026-08-18.

---

# 三十、版本關係與校驗

```text
Public document:
  Koun-U Public Core Disclosure v0.1

Public date:
  2026-10-11

Canonical source:
  Koun-U Canonical Baseline v0.4

Canonical source date:
  2026-08-18

Canonical source SHA-256:
  05d63b4f4ad5db3395fdf6862251060946df0e8710083284b66f080190bd2125
```

本公開核心稿若與完整 canonical source 發生細節差異，以完整 canonical source 的 canonical definition、owner、claim status 與 frozen artifact 為準。未來的形式化、實作、外部重跑或經驗結果，應建立新的 superseding version，而不應無痕改寫已公開版本。

---

# 結語

Koun-U 的核心不是宣稱所有問題都已被解答，而是提出一套統一的語義計算與生命週期架構：對象可以被生成、激活、封裝與重新使用；候選可以被合法懸持；釋放與提交具有不同權限；結果必須可重播、可挑戰、可重開；歷史與責任不能無痕消失；跨主體共享不要求私人狀態同一；智能與意識的候選模型必須暴露其尺度、映射、失敗條件與經驗風險。

它試圖把「語義如何存在、計算如何發生、智能如何承擔、意識如何被建模」放進同一條可分層、可檢查、可形式化、可實作、可被反駁的研究路線中。
