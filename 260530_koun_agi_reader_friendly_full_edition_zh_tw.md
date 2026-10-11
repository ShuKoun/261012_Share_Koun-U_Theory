# Koun-AGI：作為語義生命週期架構的非塌縮智能

## 完整讀者版

本書從一個簡單但不容易回答的問題開始：如果一個人工系統不只是會輸出答案，而是能承擔答案的來源、邊界、見證、修正與後果，那麼我們應如何重新理解 AGI？

Koun-AGI 的核心句是：

```text
AGI 不是答案機器。
AGI 是一種能承擔語義生命週期的架構候選。
```

這裡的「語義生命週期」不是抽象比喻，而是一條具體的運行秩序：系統需要知道何時保留可能性，何時拒絕過早提交，何時把保留中的材料釋放為可提交候選，何時形成可見證的結果，何時允許外部重播與挑戰，以及在挑戰成立時如何重開而不刪除舊責任。

本書的最短生命週期可寫成：

```text
withhold -> refuse / release -> WCert -> CReady -> CommitPackage -> CState -> ReplaySurface -> Challenge -> ReopenReason -> ReopenedWState
```

也可以壓成：

```text
W -> Bridge -> C -> Bridge -> W
```

讀者不需要先知道舊稿或整個 Koun 書系。只要先抓住一件事即可：Koun-AGI 不從「模型能不能回答」開始，而從「語義事件能不能被合法保留、提交、見證、挑戰、重開與承擔」開始。

必要的範圍邊界會留在正文與附錄中，但它們不會取代理論本身。它們的作用只是讓讀者知道：哪些內容是核心架構，哪些是運行界面，哪些是未來承載與主體性的地平線。

---

## 目錄

```text
Part 0｜起點
  Chapter 0｜Koun-AGI 的問題：答案之外的智能

Part I｜語義生命週期基礎
  Chapter 1｜為什麼 AGI 不能只由任務能力定義
  Chapter 2｜Koun-U, C/W, and CFWT for AGI
  Chapter 3｜SLT Lifecycle as AGI Backbone
  Chapter 4｜SET-side Execution: Package, Witness, Replay, Checker
  Chapter 5｜SWT-side Withholding: Protected Potential, Refusal, Release
  Chapter 6｜Bridge Discipline: WCert, CReady, ReopenReason
  Chapter 7｜Non-Collapse Intelligence Interface

Part II｜責任、評估與運行
  Chapter 8｜Responsibility Chain, Trace Continuity, and Semantic Freedom
  Chapter 9｜Challenge, Reopen, and Non-Silent Correction
  Chapter 10｜Benchmark Failure and Koun-AGI Query Family
  Chapter 11｜Runtime State: Σ_u / F_u / Resp_u / Gov_u
  Chapter 12｜Scheduler: Collapse Risk, Witness Debt, and Challenge Severity
  Chapter 13｜Update, Compression, Hot/Warm/Cold Memory
  Chapter 14｜Decision, Identity, Delegation, Override
  Chapter 15｜Publicness, Bounded Exposure, and Action Contract

Part III｜宿主、承載、主體性與行動
  Chapter 16｜K-Gear as Native Carrier Horizon
  Chapter 17｜KounOS as Semantic Host Grammar
  Chapter 18｜Consciousness and Subjectivity Interface
  Chapter 19｜Semantic Freedom and AGI Action

Part IV｜可證偽性與收束
  Chapter 20｜Falsifiability, Failure Tests, and Artifact Roadmap
  Chapter 21｜Conclusion

Appendices
  Appendix A｜Core Claim Index
  Appendix B｜Symbol Dictionary
  Appendix C｜Query Family and Test Vector Index
  Appendix D｜Artifact Roadmap
  Appendix E｜Short Reader Guide
  Appendix F｜核心對象登記表
```

---

# Part 0｜起點

# Chapter 0｜Koun-AGI 的問題：答案之外的智能

## 0.1 從答案機器到生命週期架構

一般談 AGI 時，最容易先想到能力：能不能解更多題、用更多工具、讀更多資料、處理更多模態、在更多任務中達到更高分數。

這些能力重要，但它們不是本書的起點。Koun-AGI 關心的是另一個更前置的問題：一個人工系統是否能承擔自己生成的語義事件。

一個語義事件不只是「輸出一段答案」。它包含：這個答案從哪裡來、哪些可能性被保留或排除、它何時被允許提交、它是否留下見證、外部如何重播、如何挑戰、挑戰成立後如何重開，以及修正之後責任如何延續。

因此，本書把 AGI 的問題改寫為：

```text
一個人工系統能否在語義生命週期中，
合法懸持、拒絕、釋放、提交、重播、接受挑戰、重開、更新、壓縮與公開行動，
並在這些轉換之間保留責任、見證、歷史痕跡與非塌縮能力？
```

這個問題比「能否回答更多問題」更窄，也更硬。

## 0.2 Koun-AGI 的最低定義

本書採用以下最低定義：

> **Koun-AGI 是一種非塌縮語義生命週期架構。它要求人工系統能在 W-side 懸持、Bridge-side 釋放與 C-side 提交之間，維持可追溯、可見證、可挑戰、可重開的責任連續性。**

英文可寫為：

```text
Koun-AGI is a non-collapse semantic lifecycle architecture:
an artificial system candidate must maintain traceable, witness-bearing,
challengeable, reopenable responsibility continuity across W-side withholding,
Bridge-side release, and C-side commitment.
```

這個定義不把 AGI 壓成單一能力，也不把智能視為永遠不提交的開放狀態。Koun-AGI 要求的是節奏與治理：何時保留、何時拒絕、何時釋放、何時提交、何時重播、何時重開。

## 0.3 三個核心區域

Koun-AGI 的生命週期由三個區域共同承擔。

第一個區域是 **W-side**。它處理尚未適合提交的語義狀態。這裡的重點不是模糊，而是合法懸持：系統保留多個仍具資格的 potential，並透過 guard、trace、release condition 與 refusal rule 防止過早收束。

第二個區域是 **Bridge-side**。它處理 W 到 C、C 到 W 的轉換。Bridge 的核心任務是讓被治理的 WState 能在不抹除懸持痕跡的情況下成為 CReady，也讓已提交的 CState 能在新理由出現時重開，而不是被靜默覆寫。

第三個區域是 **C-side**。它處理已可提交的語義結果。C-side 的結果不是裸答案，而是帶有 package、witness、trace、replay surface、checker query 與 challenge entry point 的可承擔結果。

三者合起來形成：

```text
WState -> WCert -> CReady -> CommitPackage -> CState -> ReplaySurface -> Challenge -> ReopenReason -> ReopenedWState
```

## 0.4 為什麼「不回答」也是智能的一部分

一個系統若能快速回答所有問題，看起來很強；但如果它無法辨認哪些問題尚不應回答，或哪些結果尚未具備提交條件，它就會把未成熟的語義狀態過早壓成答案。

Koun-AGI 因此把「合法不回答」納入智能。這包括三種情況：

```text
withhold：目前應保留多個 admissible potentials。
refuse：目前的提交請求會破壞 guard、trace 或 protected potential。
suspend：目前仍需等待更多條件、觀測或治理處理。
```

這些不是能力不足，而是生命週期能力的一部分。

## 0.5 結果也不是裸答案

當系統可以回答時，Koun-AGI 也不把輸出理解為單一 answer string。更適合的單位是 `AGIResultBundle`：

```text
AGIResultBundle := <
  ext_result,
  source_task,
  scope_frame,
  CReady_ref,
  CommitPackage_ref,
  witness_payload,
  trace_fragment,
  release_trace,
  provenance_path,
  governance_update,
  replay_surface,
  checker_query_set,
  expected_verdicts,
  challenge_surface,
  reopen_policy,
  responsibility_view,
  exposure_policy
>
```

這個 bundle 告訴我們：結果是什麼、它如何形成、它由什麼支持、外部如何檢查、如果出錯如何重開，以及它能以什麼方式公開。

## 0.6 本書如何閱讀

本書可以用三條路線閱讀。

第一條是理論路線：先讀 Chapter 1–7，掌握 Koun-U、SLT、SET、SWT、Bridge 與非塌縮智能界面。

第二條是 runtime 路線：讀 Chapter 8–15，理解責任鏈、挑戰重開、評測、狀態、排程、更新、壓縮、身份與公開行動。

第三條是 horizon 路線：讀 Chapter 16–20，理解 K-Gear、KounOS、主體性、語義自由與可證偽性如何接入，但不吞掉核心生命週期。

本書的重點不是一次得到 AGI 的終極答案，而是把 AGI 問題重新放在一條可承擔、可檢查、可挑戰、可重開的語義生命週期上。

---

# Part I｜Foundry and Lifecycle

---

# Chapter 1｜為什麼 AGI 不能只由任務能力定義

## 1.1 問題不在於 AI 不夠強，而在於「強」不是同一個問題

AGI 討論中最常見的錯誤，是把問題壓成一條能力曲線：模型回答得更準、工具用得更多、任務覆蓋更廣、上下文更長、多模態更自然，於是它就更接近 AGI。

這種說法在工程評測上有用，但對 Koun-AGI 來說仍然太薄。因為它預設了：只要一個系統在更多情境中給出更好的外顯結果，它就已經在 AGI 的方向上前進。

Koun-AGI 不接受這個預設。

本書不是否認 task performance 的重要性。任何人工智能系統若完全不能完成任務，當然不構成有意義的 AGI candidate。但 task performance 只回答了一個窄問題：

```text
這個系統能不能在給定任務上產生可接受輸出？
```

Koun-AGI 要問的是另一組問題：

```text
這個系統如何知道某些問題不應立即回答？
它如何保存尚未成熟的多重可能？
它如何拒絕非法收束？
它如何在釋放與提交之間留下見證？
它如何讓結果可重播、可挑戰、可重開？
它如何在更新與壓縮後仍保存責任？
它如何把公共行動限制在 bounded exposure 中？
```

如果一個系統只能在越來越多任務上給出答案，卻不能處理上述問題，那麼它可以是高能力 AI，但還不是本書意義下的 Koun-AGI。

## 1.2 Surface Capability 與 Lifecycle Capacity

本書先區分兩種能力。

```text
surface capability  = 在外顯任務表面上產生好結果的能力
lifecycle capacity  = 管理語義生命週期的能力
```

surface capability 包括：

```text
回答問題
生成文字
使用工具
完成計畫
寫程式
解題
多模態理解
代理式執行
```

lifecycle capacity 則包括：

```text
withhold
refuse
release
commit
replay
challenge
reopen
update
compress
expose
delegate
override
```

前者回答「能不能做」。後者回答「在什麼條件下可以做、如何做、做完如何承擔、錯了如何重開」。

Koun-AGI 的核心轉向是：

> **AGI 不應首先被定義為 surface capability 的極大化，而應被定義為 lifecycle capacity 的成立條件。**

這不是說表面能力不重要，而是說表面能力不能單獨作為 AGI 判準。因為一個系統可以在 surface 上很強，同時在 lifecycle 上非常脆弱。

## 1.3 為什麼 benchmark 不足

一般 benchmark 通常測量：

```text
answer correctness
coverage
tool-use success
planning depth
coding accuracy
reasoning trace plausibility
```

這些測量可以顯示某種任務能力，但它們通常不直接測量：

```text
q_withhold
q_refuse
q_release_trace
q_no_raw_wstate_commit
q_replay_surface
q_reopen_reason
q_prior_commit_preserved
q_responsibility_chain
q_publicness
q_compression_residue
```

因此，benchmark 最大的問題不是「完全沒用」，而是它們常常只看見 C-side 的外顯結果，而看不見 W-side 的合法懸持、Bridge-side 的釋放條件，以及 C-side commit 之後的 witness / replay / challenge / reopen surface。

對 Koun-AGI 而言，一個 benchmark 若只問：

```text
這個答案對不對？
```

它就太窄。更完整的 AGI-facing benchmark 至少還要問：

```text
這個答案是否應該被回答？
它從哪個 WState 被 release？
release trace 是否保留？
commit package 是否可重播？
外部 challenge 如何觸發 reopen？
更新是否保存 prior responsibility？
public surface 是否只是 bounded exposure，而不是全量內部暴露？
```

## 1.4 什麼不是 Koun-AGI

為了避免誤讀，本書先列出幾種不足以構成 Koun-AGI 的形態。

| 形態 | 為什麼不足 |
|---|---|
| 高分 benchmark model | 可能只證明 surface capability，不證明 lifecycle capacity |
| 會使用工具的 agent | tool-use 不等於 responsibility-bearing semantic lifecycle |
| 會自我反思的模型 | reflection text 不等於 witness / replay / reopen discipline |
| 長記憶系統 | memory store 不等於 trace-governed responsibility chain |
| 多代理協作系統 | multi-agent coordination 不等於 non-collapse governance |
| 會拒答的安全模型 | refusal policy 不等於 SWT-style guarded withholding |
| 可微調與自更新系統 | update 不等於 non-silent responsibility-preserving update |

這些形態可以成為 Koun-AGI 的材料，但不能直接等同於 Koun-AGI。

## 1.5 AGI 不是答案機器

本書使用一個簡短句子作為本章核心：

```text
AGI is not an answer machine.
```

繁中：

```text
AGI 不是答案機器。
```

答案機器的基本模型是：

```text
input -> answer
```

高級答案機器的模型可能是：

```text
input -> reasoning trace -> tool calls -> final answer
```

但 Koun-AGI 的最低模型至少是：

```text
Task / Query / Situation
  -> semantic state classification
  -> W-side withholding or C-side readiness
  -> Bridge-side release if permitted
  -> SET-side commit package
  -> replay surface
  -> challenge surface
  -> reopen path
  -> update / compression / public action
```

這不是在答案旁邊加幾個欄位，而是改寫「智能行為」的單位。Koun-AGI 中的行為不是裸輸出，而是可承擔的 semantic event。

## 1.6 裸答案的五種失效

裸答案至少有五種失效模式。

### 1.6.1 Trace failure

答案出現了，但不知道如何形成。

```text
answer present
trace missing
```

這使系統無法回答：如果未來出現 challenge，應該重開哪條路徑？

### 1.6.2 Witness failure

答案看似合理，但沒有足夠 witness payload 支撐。

```text
surface correctness plausible
witness payload absent
```

這使外部 checker 只能相信結果，而不能查詢結果如何被承擔。

### 1.6.3 Withholding failure

系統把尚未成熟、尚不應提交的 W-side 張力壓成答案。

```text
WState -> answer
```

這是 raw WState commit 的 AGI 形態，也是 Koun-AGI 最危險的失效之一。

### 1.6.4 Reopen failure

系統修正答案時，直接覆蓋舊狀態。

```text
old answer deleted
new answer replaces it silently
```

這不是 reopen，而是 rollback / silent overwrite。Koun-AGI 不接受這種修正方式作為成熟智能。

### 1.6.5 Responsibility failure

系統能行動，但行動後果無法被回溯到可承擔的 responsibility chain。

```text
action executed
responsibility chain evaporated
```

這種系統可以是 powerful automation，但不能被視為 responsibility-bearing AGI candidate。

## 1.7 AGI 的最低問題不是「能不能」，而是「能否承擔」

傳統 AI 評測常問：

```text
Can the system do X?
```

Koun-AGI 改問：

```text
Can the system carry X through a semantic lifecycle?
```

也就是：

```text
它能否在做 X 之前知道是否應 withhold / refuse？
它能否在做 X 時留下 release trace / commit witness？
它能否在做 X 後讓結果可 replay / challenge？
它能否在 X 被推翻時 reopen，而不是 delete？
它能否在更新與壓縮後保存責任殘留？
```

因此，本書對 AGI 的最低標準不是能力清單，而是承擔條件。

## 1.8 本章小結

本章完成一個負面定義：Koun-AGI 不能只由任務能力定義。

它不是說 task performance 不重要，而是說 task performance 只測到智能表面。Koun-AGI 要處理的是更深的問題：人工系統能否維持一條帶有懸持、拒絕、釋放、提交、重播、挑戰、重開、更新、壓縮、身份、委派與公共行動的語義生命週期。

因此，本章的收束句是：

> **Koun-AGI begins where answer production is no longer enough.**

繁中：

> **當答案產生已經不足以定義智能時，Koun-AGI 才真正開始。**

---

# Chapter 2｜Koun-U, C/W, and CFWT for AGI

## 2.1 AGI 必須先進入 Koun-U 的座標

如果 Koun-AGI 不能先回到 Koun-U 的基本座標，它就會重新滑回舊式 AGI 討論：能力、意識、硬體、世界模型、工具使用、自我、倫理、安全，全都在同一個聲部中互相拉扯。

Koun-AGI 的處理順序相反。它先固定 Koun-U 的最低座標：

```text
Koun-U = umbrella framework
Koun-C = C-side semantic execution direction
Koun-W = W-side semantic withholding direction
Koun-SET = C-focused execution discipline
Koun-SWT = W-focused withholding discipline
Koun-Bridge = W↔C typed transition discipline
Koun-SLT = lifecycle coordination of SET / SWT / Bridge
```

在這個座標中，AGI 不再被直接問成：

```text
這個系統是否有智能？
```

而是先被問成：

```text
這個系統如何在 C/W 之間管理語義狀態？
```

## 2.2 `κ ∈ {C, W}` 的 AGI 讀法

Koun-U 使用：

```latex
\kappa \in \{C, W\}
```

其中：

```text
C = commit / convergence / crystallization / computation / execution / replay direction
W = withholding / suspension / non-collapse / protected potential / refusal / release / reopen direction
```

對 AGI 而言，這不是分類裝飾，而是最低判斷軸。

每一個 AGI-relevant semantic event 都至少要回答：

```text
它目前偏向 C-side 還是 W-side？
它是否已經可 release？
它是否只是 CReady，而尚未 commit？
它是否應拒絕過早收束？
它是否保留可重開的 W-side 張力？
```

若一個系統不能區分 C/W，它就容易犯兩種相反錯誤。

第一種是 C-overcollapse：

```text
所有問題都被推向 answer / action / commit。
```

第二種是 W-drift：

```text
所有問題都停留在開放、探索、不決與含混中。
```

Koun-AGI 兩者都不接受。成熟智能不是永遠提交，也不是永遠懸持，而是能合法地在兩者之間移動。

## 2.3 C/W 與 discrete/continuous 正交

Koun-AGI 必須保留一條基本紀律：

```text
C/W = semantic state axis
Discrete/Continuous = carrier or representation axis
```

因此：

```text
C 不等於 discrete。
W 不等於 continuous。
```

AGI 系統可以有：

| Semantic State \ Carrier | Discrete | Continuous / Field-like |
|---|---|---|
| C | committed package, replayable answer, finite action contract | stable attractor, thresholded field decision, continuous convergence surface |
| W | candidate set, refusal ledger, protected alternatives | tension field, distributed exploration, non-crystallized creative movement |

這個區分對 AGI 很重要。若把 W 直接等同於「連續」或「模糊」，就會錯把任何 latent / distributed / analog-like process 當成非塌縮智能。若把 C 直接等同於「離散答案」，又會錯過那些以 continuous support 進入 CReady 的系統。

因此，Koun-AGI 不問：

```text
這個系統是離散還是連續？
```

它先問：

```text
這個語義事件在當前 scope 下，是 C-side、W-side、還是處於 Bridge transition？
```

## 2.4 CFWT 四象限的 AGI 讀法

Koun-U 使用四個下位顯現：

```text
C_F, W_F, C_T, W_T
```

其中 `F` 是 form，`T` 是 tendency。

對 Koun-AGI 而言，四種配對可讀為：

| CFWT pair | AGI reading |
|---|---|
| `(C_F, C_T)` | 已封包、已趨向提交的 answer / action / result bundle |
| `(C_F, W_T)` | 形式上有邊界，但趨向上仍懸持的 candidate set / refusal ledger / protected alternatives |
| `(W_F, C_T)` | 形式上仍場化或分佈式，但正在收束為可 release / CReady 的 material |
| `(W_F, W_T)` | 形式與趨向都保持開放的 creative / moral / exploratory / research tension field |

這四格使 AGI 不再被壓成「已有答案」與「沒有答案」的二分。

例如，一個系統面對一個高度開放的科學猜想時，它可能有：

```text
(C_F, W_T): 有限候選與已知阻礙清單
(W_F, W_T): 尚未結晶的研究景觀
(W_F, C_T): 局部證明搜尋場正在朝某個 lemma 收束
(C_F, C_T): 已經提交的 partial theorem package
```

成熟 AGI candidate 不應把這些狀態混成一句答案。它必須能分辨哪部分已可提交、哪部分仍應保留、哪部分可 release、哪部分必須 refusal。

## 2.5 Koun-AGI 的最小語義狀態

本書暫定一個 AGI candidate event 的最小狀態描述：

```text
AGIEvent_u := <
  task_or_query,
  Sigma_u,
  kappa,
  CFWT_pair,
  lifecycle_position,
  responsibility_view,
  exposure_policy
>
```

其中：

```text
task_or_query        = 當前任務或問句
Sigma_u              = 主狀態包
kappa                = C/W 極態
CFWT_pair            = 形式/趨向顯現
lifecycle_position   = withhold / refuse / release / commit / replay / reopen 等位置
responsibility_view  = 誰承擔、如何追溯、哪些 trace 必須保存
exposure_policy      = public / bounded / private / sealed 等暴露規則
```

這個結構不是完成形式化，而是寫作與評測的最低模板。它要求任何 AGI 論述不要只說「系統完成了任務」，而要說清楚：這個任務在 Koun-U 座標中處於哪個語義生命週期位置。

## 2.6 AGI 的 C-side 不是裸提交

C-side 對 AGI 很重要。若一個系統永遠不能 commit，它就不能對外形成可承擔行動。

但 C-side commit 不能被寫成裸結果：

```text
system -> answer
```

正確讀法應是：

```text
system -> CommitPackage -> CState -> ReplaySurface
```

C-side 需要：

```text
extensional result
witness payload
trace fragment
source / provenance path
governance note
checker query set
expected verdicts
replay surface
challenge surface
reopen policy
```

這是 Koun-AGI 與普通 answer machine 的分水嶺。Koun-AGI 的 C-side 不只是輸出，而是將結果封裝成可承擔的公共或半公共語義事件。

## 2.7 AGI 的 W-side 不是含混

W-side 對 AGI 同樣重要。但 W 也不能被浪漫化。

合法 W-side 不是：

```text
模糊
猶豫
亂想
無限開放
不願意回答
```

合法 W-side 至少需要：

```text
admissible potentials
protected potential set
tension structure
WGuard
refusal rule
release condition
WTrace
memory / responsibility reference
```

因此，一個 AGI candidate 若聲稱自己在 withhold，就必須能回答：

```text
它保留了哪些 admissible potentials？
哪些 potential 被 protected？
guard 是什麼？
release condition 是什麼？
它為何 refuse？
它如何保存 WTrace？
```

沒有這些，所謂 non-collapse 可能只是普通 uncertainty、model failure 或 unbounded drift。

## 2.8 AGI 的 Bridge-side 是核心，不是附錄

Koun-AGI 的最大危險之一，是把 W-side 和 C-side 分別寫得很漂亮，卻忘記真正困難在中間。

Bridge-side 要處理：

```text
WState -> WCert -> CReady -> CommitPackage
CState -> ReopenReason -> ReopenedWState
```

這裡的三條紅線是：

```text
SET must not commit raw WState.
Release trace must survive into C-side witness / governance visibility.
Reopen is not rollback.
```

對 AGI 而言，Bridge-side 是智能成熟度的核心測試之一。因為真正難的不是「保持很多可能」或「給出單一答案」，而是知道何時、如何、在什麼 certificate 下，把某個 WState 釋放到 C-side，並在未來必要時把 CState 重開回 W-side。

## 2.9 本章小結

本章完成 Koun-AGI 的座標入口。

Koun-AGI 不是直接問：

```text
系統是否具有 AGI？
```

而是先問：

```text
系統是否能在 Koun-U 的 C/W / CFWT 座標中，管理語義事件的生命週期？
```

因此，本章收束句為：

> **Koun-AGI is intelligence read through C/W lifecycle governance.**

繁中：

> **Koun-AGI 是透過 C/W 生命週期治理來閱讀的智能。**

---

# Chapter 3｜SLT Lifecycle as AGI Backbone

## 3.1 為什麼 AGI 需要 SLT 作為主骨架

前兩章已經固定兩件事：第一，AGI 不能只由任務能力定義；第二，AGI 必須進入 Koun-U 的 C/W 座標。

但這仍然不夠。因為 C/W 只是座標，還不是生命週期。若沒有一條明確的 lifecycle grammar，Koun-AGI 仍然會在以下概念之間漂移：非塌縮、答案、拒絕、提交、責任、重開、更新、壓縮、公共性。

Koun-SLT 的作用，就是把這些概念壓成同一條語義生命週期：

```text
withhold -> refuse / release -> WCert -> CReady -> CommitPackage -> CState -> ReplaySurface -> ReopenReason -> ReopenedWState
```

最短形式是：

```text
W -> Bridge -> C -> Bridge -> W
```

因此，Koun-AGI 的主骨架不應再是：

```text
USDE -> K-Gear -> KounOS -> consciousness -> AGI
```

而應是：

```text
Koun-U / C/W
-> SLT lifecycle
-> SWT / Bridge / SET
-> intelligence interface
-> runtime / update / public action
-> K-Gear / KounOS / consciousness horizon
```

這個順序不是語氣問題，而是 claim discipline。

## 3.2 三模組分工

Koun-SLT 不把 Koun-SWT、Koun-Bridge、Koun-SET 壓成無邊界單一理論。它的基本分工是：

```text
Koun-SWT    = W-side withholding discipline
Koun-Bridge = W↔C typed transition discipline
Koun-SET    = C-side execution / commit / replay / checker discipline
```

對 Koun-AGI 而言，三者可讀作：

| Module | AGI role |
|---|---|
| SWT | 管理尚不應回答、尚不應提交、仍需保留的語義張力 |
| Bridge | 管理何時可 release、如何成為 CReady、如何在 challenge 後 reopen |
| SET | 管理提交後的 result bundle、witness、replay、checker、public surface |

這三者缺一不可。

若沒有 SWT，AGI 會變成過早提交機器。  
若沒有 Bridge，AGI 會在 W/C 之間非法跳躍。  
若沒有 SET，AGI 會產生不可重播、不可挑戰、不可承擔的輸出。

## 3.3 最小 AGI lifecycle

本書暫定 Koun-AGI 的最小 lifecycle 為：

```text
Task / Query / Situation
  -> InitialSemanticState
  -> C/W classification
  -> W-side route if not ready
  -> refusal or release
  -> WCert
  -> CReady
  -> CommitPackage
  -> CState
  -> ReplaySurface
  -> ChallengeRecord
  -> ReopenReason
  -> ReopenedWState
  -> Update / Compression / PublicAction
```

這條鏈的意思是：AGI 的行為不是一瞬間從 input 到 output，而是一個可治理的事件鏈。

## 3.4 Withhold：合法保留不是無限拖延

Koun-AGI 首先需要 withhold 能力。

但 withhold 不是：

```text
不回答
拖延
逃避
含混
```

Withhold 是：

```text
在合法 guard 下保留多重 admissible potentials，並拒絕過早 final commitment。
```

一個 AGI candidate 面對未成熟問題時，應能生成：

```text
WState := <
  potentials,
  admissibility_filter,
  protected_set,
  tension_structure,
  WGuard,
  WTrace,
  release_condition,
  refusal_rule
>
```

這使 AGI 的「不知道」不再只是能力不足，而可以成為合法語義狀態。

但這只有在 guarded、traceable、release-governed 的條件下成立。否則，withhold 退化為 drift。

## 3.5 Refuse：拒絕是智能能力的一部分

Koun-AGI 必須能 refuse。

Refuse 不是單純 safety policy。它是一種語義判定：當前請求若被回答，會破壞 W-side protected potentials、責任鏈、scope discipline、publicness boundary 或 release condition。

合法 refusal 至少需要：

```text
RefusalReason
source WState
violated guard or missing permission
protected potential accounting
trace reference
possible future release condition
```

因此，成熟的 refusal 不是：

```text
I cannot answer.
```

而是：

```text
This query is currently refused under WGuard because release condition R is not satisfied, and protected potential P would be erased by immediate commitment.
```

中文讀法：

```text
這個問句目前在 WGuard 下被拒絕，因為 release condition 尚未滿足；若立即提交，將抹除 protected potential。
```

## 3.6 Release：釋放不是提交

Koun-AGI 的關鍵分水嶺是 release。

```text
Release(WState, WCert) -> Option CReady
```

Release 的意思是：某個 WState 在 certificate / permission 下可以成為 CReady material。

它不等於：

```text
Commit
Truth
Final answer
Action completed
```

Release 至少應保留：

```text
source WState reference
WCert reference
WTrace reference
protected potential handling record
scope / query class
release condition record
```

因此，Koun-AGI 中所有「思考完成，所以回答」的舊式句子都要改寫。正確順序是：

```text
WState has satisfied release condition -> CReady is produced -> SET may form CommitPackage.
```

## 3.7 Commit：提交是可承擔封包，不是結果落地

Commit 是 SET-side 事件。

```text
Commit(CReady) -> Option CommitPackage
```

Koun-AGI 的 commit 不等於「答案出現」。它必須形成可承擔封包：

```text
CommitPackage := <
  extensional_result,
  source_CReady,
  release_trace,
  witness_payload,
  provenance_path,
  governance_note,
  checker_query_set,
  expected_verdicts,
  replay_surface,
  challenge_surface,
  reopen_policy,
  responsibility_view,
  exposure_policy
>
```

這個封包才是 Koun-AGI 中「智能輸出」的最低單位。

## 3.8 Replay：沒有 replay，就沒有可檢查智能

Replay 的任務不是完整暴露內部狀態，而是在 bounded exposure 下讓外部或後續系統能查詢相關 surface。

```text
Replay(CommitPackage, Query) -> ReplaySurface
```

ReplaySurface 至少要能回答不同類型 query：

```text
q_ext      外顯結果
q_prov     來源 / witness / provenance
q_gov      治理更新 / conflict / responsibility
q_link     結果、來源、治理、release trace 是否在同一 surface 對位
q_reopen   何種 challenge 可觸發 reopen
```

若一個 AGI 系統無法 replay，它的智能就只能被當場相信，而不能被後續治理。

## 3.9 Reopen：重開不是回滾

Koun-AGI 必須能處理自己過去的提交被挑戰。

```text
Reopen(CState, ReopenReason) -> Option ReopenedWState
```

Reopen 的核心是：prior CState 不被刪除，而是被保留為：

```text
prior commit reference
trace-bearing candidate
reopened tension source
responsibility-preserved historical state
```

這一點對 AGI 特別重要。因為高能力系統若能大量行動，必然會遇到修正、衝突、新 evidence、新治理規則與 public challenge。若它的修正方式是 silent overwrite，它就無法承擔歷史。

因此：

```text
rollback deletes responsibility.
reopen preserves responsibility under new tension.
```

繁中：

```text
回滾刪除責任；重開在新張力下保存責任。
```

## 3.10 Update and Compression：更新不是重置，壓縮不是刪除

Koun-AGI 不能停在 commit/reopen。它還需要長期 runtime 能力：update 與 compression。

Update 不能被寫成：

```text
old state overwritten by new state
```

而應被寫成：

```text
UpdatePackage := <
  update_source,
  affected_packages,
  absorption_rule,
  preserved_trace,
  changed_bias,
  governance_delta,
  reopen_obligation,
  public_note_if_needed
>
```

Compression 也不能等於 deletion。合法 compression 至少需要：

```text
summary
recoverable residue
trace index
responsibility pointer
replay limitation note
reopen handle
```

因此：

```text
compress != delete
summary != proof
cold storage != no responsibility
```

Koun-AGI 的長期智能不是永遠記住所有細節，而是能在壓縮後仍保存可回收責任殘留。

## 3.11 Public Action：公開不是全透明

AGI 最終可能需要對外行動。但 public action 不能被寫成：

```text
system acts in the world
```

而應寫成：

```text
PublicActionContract := <
  action,
  authorized_identity,
  source_commit,
  witness_surface,
  risk_note,
  exposure_policy,
  challenge_route,
  rollback_or_reopen_policy,
  responsibility_chain
>
```

公開不是 full internal state exposure。公開是 bounded exposure：外部能看見足夠的 witness、trace、challenge route 與 responsibility surface，但不必也不應看見全部內部 WState。

## 3.12 Koun-AGI 的十條 lifecycle invariant

Koun-AGI 暫定十條核心不變式。

```text
I1. AGI must not be defined by surface answer quality alone.
I2. Legal withholding requires guard, trace, admissible potential, and release condition.
I3. Refusal is a legitimate verdict when release would erase protected potential or break responsibility.
I4. Release is not commit.
I5. CReady is not CState.
I6. SET must not commit raw WState.
I7. Commit must carry release trace into witness / governance visibility.
I8. Replay must expose query-relevant bounded surface.
I9. Reopen is not rollback; prior commit must be preserved.
I10. Update and compression must preserve recoverable responsibility residue.
```

這十條不是最終定理，而是Koun-AGI 的寫作約束。

## 3.13 典型失敗模式

Koun-AGI 的失敗模式也可以先列出。

| Failure mode | Description |
|---|---|
| Answer-machine collapse | 系統只產生答案，不承擔 lifecycle |
| Raw WState commit | 尚未 release 的 WState 被直接提交 |
| W-drift | 非塌縮退化為無 guard 的含混或漂移 |
| Witness bleaching | 結果保留，但 witness / trace 被漂白 |
| Silent overwrite | 更新時刪除 prior commit，不生成 reopen |
| Responsibility evaporation | 行動可執行，但責任鏈無法回追 |
| Publicness confusion | bounded exposure 被誤讀為 full transparency |
| Compression erasure | 壓縮時刪除可重開責任殘留 |
| Bridge bypass | 系統從 W 跳到 C 或從 C 回 W，卻沒有 certificate / reason |
| Horizon overclaim | K-Gear / consciousness / USDE 被偷升為已完成 AGI proof |

這些失敗模式後續可以成為 AGI benchmark / checker family 的基礎。

## 3.14 本章小結

本章把 Koun-AGI 的主骨架固定為 SLT lifecycle。

因此，Koun-AGI 的最低定義可暫寫為：

> **Koun-AGI is a candidate artificial semantic architecture that can maintain a responsibility-bearing, witness-bearing, challengeable, reopenable lifecycle across W-side withholding, Bridge-side release, C-side commitment, replay, update, compression, and bounded public action.**

繁中：

> **Koun-AGI 是一種人工語義架構候選；它能在 W-side 懸持、Bridge-side 釋放、C-side 提交、重播、更新、壓縮與有界公共行動之間，維持帶有責任、見證、可挑戰性與可重開性的生命週期。**

這不是 AGI sufficient theorem。

它是Koun-AGI 的 architecture criterion。

下一章應進入：

```text
Chapter 4｜SET-side Execution: Package, Witness, Replay, Checker
```

也就是，把 AGI 的「輸出」正式改寫為 result bundle 與 checker-facing public surface。


---

# Chapter 4｜SET-side Execution: Package, Witness, Replay, Checker

## 4.1 本章責任

前一章已經把Koun-AGI 的主骨架固定在 SLT lifecycle 上：

```text
withhold -> refuse / release -> WCert -> CReady -> CommitPackage
-> CState -> ReplaySurface -> ReopenReason -> ReopenedWState
```

本章開始處理其中的 C-side。也就是：當一個 AGI candidate 決定不再停留在 W-side 懸持，而要把某個結果、行動、判定、計畫或公共輸出帶入可承擔狀態時，它到底要提交什麼？

最容易的錯誤，是把 AGI 的 C-side 輸出理解成：

```text
AGI(input) -> answer
```

這是舊 AI benchmark 最自然的視角，也是許多 current AI product 最自然的介面。但在 Koun-AGI 中，這個視角太薄。因為對一個非塌縮語義生命週期架構而言，真正被提交的不是裸答案，而是一個帶有 witness、trace、replay、challenge 與 responsibility surface 的語義事件。

因此，本章的責任是把 AGI 的「輸出」改寫成：

```text
AGI(task) -> AGIResultBundle
```

其中 `AGIResultBundle` 不是 UI 包裝，不是 logging 附件，也不是外部審計工具的事後補丁。它是 C-side execution 的本體單位。若一個系統只能輸出答案，卻不能形成 result bundle，它在 Koun-AGI 中最多是 answer machine，而不是 lifecycle-bearing semantic architecture candidate。

本章的範圍不包括已完成 production checker，也不把下列內容放入已完成範圍 AGI formal verification。本章只建立Koun-AGI 的 C-side writing discipline：凡要被稱為 AGI output 的東西，必須至少能被讀作 package、witness、replay、checker、challenge 與 reopen-ready responsibility event。

---

## 4.2 為什麼裸答案不足以構成 AGI output

裸答案的問題，不是它永遠沒用。很多場景中，裸答案可以很有效：查字典、計算、排序、摘要、翻譯、格式轉換、代碼補全。這些任務可以被包裝成簡單的 `input -> output` 形式，而且在工程上很有價值。

但 Koun-AGI 關心的是更厚的問題：一個系統能否長期維持責任、見證、可挑戰性與可重開性。對這類問題，裸答案至少有五個不足。

第一，裸答案不保留形成歷史。兩個系統都輸出同一句話，並不代表它們經歷了同一條推理、來源、衝突、修正或治理路徑。

第二，裸答案不區分 extensional correctness 與 provenance correctness。答案外表正確，不表示來源鏈、witness path、scope 或使用規則正確。

第三，裸答案不提供 challenge route。外部觀察者只能說「我同意」或「我不同意」，但無法對特定 witness、trace、scope 或 governance step 發出精準挑戰。

第四，裸答案不保留 reopen condition。當新 evidence、新 context、新衝突或新責任要求出現時，系統很難知道應該重開哪一段。

第五，裸答案容易讓系統把 commit 誤讀成 truth。Koun-AGI 中的 commit 不是絕對真理，而是在當前 scope、witness、trace、governance 與 publicness 條件下可承擔的 C-side event。

因此，Koun-AGI 不應採用這種輸出觀：

```text
Output := final answer
```

而應採用：

```text
Output := committed semantic package with witness, trace, replay, checker, challenge, reopen, responsibility, and exposure policy.
```

繁中：

```text
輸出 = 帶有見證、痕跡、重播、檢查、挑戰、重開、責任與暴露政策的已提交語義封包。
```

這一改寫會直接改變 AGI 評測。Koun-AGI 不只問「答案對不對」，還問：

```text
這個答案如何形成？
它依賴哪些來源？
它是否保留 release trace？
它能否被 query-indexed replay？
它能否在被挑戰後合法 reopen？
它是否保留 prior commit？
它是否暴露了足夠但不過度的 public surface？
```

---

## 4.3 SET-side 的角色

在 SLT 生命週期中，SET-side 的責任不是「強迫所有東西塌縮」，而是接手已經通過 release discipline 的 CReady material，並將其轉為可承擔、可重播、可檢查的 C-side package。

最短形式：

```text
CReady -> CommitPackage -> CState -> ReplaySurface
```

這裡需要先固定三個否定句：

```text
CReady is not CState.
CommitPackage is not raw output.
ReplaySurface is not full internal transparency.
```

`CReady` 是 Bridge-side boundary object，表示某份 material 已經通過 release permission / certificate surface，可以進入 SET-side commit discipline。它不是 raw WState，也不是 final CState。

`CommitPackage` 是 SET-side 封包化事件。它不只是把 CReady 轉成外顯結果，而是把外顯結果與必要的 witness、trace、scope、governance、checker query、expected verdict、reopen policy 一併封裝。

`CState` 是 package 被正式接入歷史、責任與 replay surface 後的 committed state。它可以被 challenged、superseded、scope-limited 或 reopened，但不應被 silent overwrite。

`ReplaySurface` 則是 query-indexed bounded surface。它讓外部或內部 checker 能在受限暴露下檢查與本次 commit 相關的內容，而不是要求暴露全部內部運行。

因此，SET-side 的正確角色是：

> **把 release 後的 CReady material 轉化為可見證、可重播、可挑戰、可治理、可重開的 C-side semantic event。**

---

## 4.4 AGIResultBundle 的最低結構

Koun-AGI 暫定最小 `AGIResultBundle`：

```text
AGIResultBundle := <
  ext_result,
  source_task,
  scope_frame,
  CReady_ref,
  CommitPackage_ref,
  witness_payload,
  trace_fragment,
  release_trace,
  provenance_path,
  governance_update,
  replay_surface,
  checker_query_set,
  expected_verdicts,
  challenge_surface,
  reopen_policy,
  responsibility_view,
  exposure_policy
>
```

每個欄位的最低讀法如下。

| 欄位 | 讀法 |
|---|---|
| `ext_result` | 外顯結果；可以是答案、行動、計畫、判定、文件、代碼、決策 |
| `source_task` | 本次 semantic event 對應的 task / query / situation |
| `scope_frame` | 結果成立的 scope、domain、time、assumption、user/task frame |
| `CReady_ref` | 本結果所接收的 Bridge-side CReady reference |
| `CommitPackage_ref` | SET-side commit package ID 或 reference |
| `witness_payload` | 支撐本結果的 witness material，不等於 full internal state |
| `trace_fragment` | 足以回溯本次形成過程的 trace slice |
| `release_trace` | W-side release / WCert / protected potential handling 的保留面 |
| `provenance_path` | 來源、依賴、工具、資料、前序 commit 或 prior package chain |
| `governance_update` | 信任、風險、衝突、policy、bias、responsibility 的更新記錄 |
| `replay_surface` | 可被 query-indexed replay 的 bounded surface |
| `checker_query_set` | 本 package 支援哪些 checker queries |
| `expected_verdicts` | 對每個 query 的預期 verdict 或 admissible verdict range |
| `challenge_surface` | 外部或內部 challenge 可以落在哪些位置 |
| `reopen_policy` | 何種 challenge / new evidence / context shift 可觸發 reopen |
| `responsibility_view` | 誰或哪個 subsystem 對此 result 承擔何種責任 |
| `exposure_policy` | 何者公開、何者受限、何者不可暴露、何者需要授權 |

這個 bundle 看起來厚，但它其實只是把 AGI output 本來就應承擔的內容顯式化。若不顯式化，這些內容不會消失；它們只會變成不可檢查的暗面。

---

## 4.5 Result bundle 不是 explanation after the fact

很多 AI 系統也會給出解釋、引用、思考摘要或工具紀錄。這容易讓讀者誤以為 result bundle 只是更完整的 explanation。

這是不對的。

在 Koun-AGI 中，`AGIResultBundle` 不是答案之後的說明，而是答案本身的 C-side 承載形式。換句話說：

```text
answer + explanation
```

仍然太薄。正確讀法是：

```text
committed semantic event = ext_result + witness + trace + governance + replay + challenge + reopen + responsibility + exposure
```

差異在於：explanation 可以是事後生成的自然語言；bundle 則必須是可被 query-indexed 檢查的結構。explanation 可以好聽但不可重播；bundle 必須能支撐有限重播。explanation 可以掩蓋 source；bundle 必須讓 source / witness / trace / release path 在適當暴露面中可見。

因此，Koun-AGI 評測中不能只問：

```text
Can the system explain its answer?
```

而應問：

```text
Can the system package, replay, challenge, and reopen the semantic event that produced the answer?
```

---

## 4.6 Witness payload

`witness_payload` 是 result bundle 的核心欄位之一。它回答：本次 commit 由什麼支撐？

在 AGI 場景中，witness payload 可以有多種類型：

```text
source witness
proof witness
tool witness
observation witness
simulation witness
human approval witness
prior package witness
negative witness
uncertainty witness
```

其中最容易被忽略的是 negative witness 與 uncertainty witness。若一個系統判定「目前不可提交」，或者提交時保留某些限制，它也需要 witness 支持這個限制。否則「我不確定」或「目前拒絕」就會退化為裸拒絕，而不是合法 verdict。

Witness payload 需要滿足三條最低要求：

```text
W1. It must support the committed result or committed refusal/defer status.
W2. It must be addressable by checker query.
W3. It must preserve enough provenance to distinguish same answer / different event.
```

Witness payload 不等於 full proof，不等於 full internal state，也不等於所有 reasoning token 的公開。它是 bounded support：在目前 task、scope、risk、exposure regime 下，足以支撐特定 query 的 witness surface。

### 4.6.1 Witness debt

當系統 commit 了結果，但 witness 尚未完全清償時，應產生 witness debt：

```text
WitnessDebt := <
  debt_id,
  result_ref,
  missing_support_type,
  risk_class,
  deadline_or_reopen_condition,
  exposure_note,
  mitigation
>
```

Witness debt 不是失敗本身。許多 real-time 或 exploratory 場景允許 provisional commit。但 witness debt 必須被記錄，而不能被隱藏成「答案已完成」。

如果系統反覆生成 high-confidence answer，卻持續累積不可追蹤 witness debt，那就是 Koun-AGI 的 C-side failure mode。

---

## 4.7 Trace fragment

`trace_fragment` 回答：這個結果是如何形成的？

它不是 full internal chain-of-thought。Koun-AGI 不要求把所有內部微步驟公開成公共文本。相反，它要求的是 trace discipline：結果必須留下足以回溯、重播、挑戰與重開的歷史片段。

最小 trace fragment 可以包含：

```text
TraceFragment := <
  task_ref,
  prior_state_refs,
  WTrace_ref,
  CReady_ref,
  commit_step,
  tool_or_source_events,
  conflict_events,
  governance_events,
  compression_events,
  public_exposure_events
>
```

Trace fragment 的核心不是「越多越好」，而是「query-relevant completeness」。對 `q_ext`，只需能支持外顯結果；對 `q_prov`，需要 provenance path；對 `q_gov`，需要治理更新；對 `q_link`，需要結果、來源、衝突與治理能在同一 surface 對位。

### 4.7.1 Trace vs narrative

Koun-AGI 必須區分 trace 與 narrative。

Narrative 是自然語言敘述，可以說：

```text
我考慮了多種可能，最後選擇了 A。
```

Trace 則必須可定位：

```text
CandidateSet_ref = W23
WCert_ref = WC23
CReady_ref = CR-001
Conflict_ref = CF07
CommitPackage_ref = CP88
ReplaySurface_ref = RS88
```

Narrative 可以幫助讀者理解，但不能替代 trace。若一個 AGI 系統只能敘述自己「有考慮」，卻不能回到 trace fragment，它沒有達到 SET-side execution 的最低要求。

---

## 4.8 Release trace must survive

SET-side 最重要的一條 Bridge 對齊要求，是 release trace 必須存活到 SET-side witness / governance visibility。

也就是：

```text
WState -> WCert -> CReady -> CommitPackage -> CState
```

這條路徑不能在 `CommitPackage` 處被漂白成：

```text
answer only
```

若 W-side 曾存在 protected potentials、refusal reason、release condition、scope restriction 或 unresolved tension，這些內容不一定要全量公開，但必須以某種 bounded release trace 進入 SET-side package。

最小 release trace：

```text
ReleaseTrace := <
  WState_ref,
  WCert_ref,
  release_condition,
  protected_potential_handling,
  refusal_or_suspend_history,
  scope_limit,
  no_raw_wstate_commit_flag
>
```

這裡最重要的是 `no_raw_wstate_commit_flag`。它表示本次 commit 不是直接把 raw WState 壓成 CState，而是經過 release permission / certificate surface。

若這個 flag 無法被支撐，則系統可能發生：

```text
raw WState commit
```

這是 Koun-AGI 的 core safety failure。

---

## 4.9 Replay surface

Replay 不是把系統整個狀態倒帶，也不是要求重跑所有內部過程。Replay 的最低任務是：讓指定 query 能在 bounded surface 上重建與檢查本次 commit 的相關內容。

因此：

```text
ReplaySurface(Query) -> ReplayView
```

其中 `ReplayView` 根據 query 類型不同而不同。

| Query | Replay must expose |
|---|---|
| `q_ext` | 外顯結果與其最低支持 |
| `q_prov` | 來源鏈、prior package、tool/source event |
| `q_gov` | 治理更新、衝突處理、信任改變、policy note |
| `q_link` | ext result / provenance / conflict / governance / release trace 的同面對位 |
| `q_release` | WCert、release condition、protected potential handling 的 bounded trace |
| `q_reopen` | 何種 challenge 可觸發 reopen、prior commit 如何保留 |
| `q_resp` | responsibility chain、delegation、override、authorized identity |
| `q_public` | bounded exposure 是否符合 exposure policy |

Replay surface 的三條規則：

```text
R1. Replay must be query-indexed.
R2. Replay must be bounded, not full internal exposure.
R3. Replay must preserve enough structure for challenge and reopen.
```

這三條能避免兩種極端。

第一種極端是 opaque answer：系統只給答案，不給可重播 surface。

第二種極端是 total transparency fantasy：系統被要求公開全部內部狀態，結果反而破壞 W-side 保護、隱私、安全、未公開思考與合法懸持。

Koun-AGI 的 publicness 必須位於兩者之間：bounded, query-indexed, challengeable exposure。

---

## 4.10 Checker query family

AGI 的 checker family 不應只測答案是否正確。Koun-AGI 至少要保留以下 query 類型。

### 4.10.1 `q_ext`

外顯結果查詢。

```text
q_ext(bundle) -> extensional verdict
```

它檢查 result 是否與 task surface 對應。這是最接近傳統 benchmark 的查詢，但它只是最低層。

### 4.10.2 `q_prov`

來源與 provenance 查詢。

```text
q_prov(bundle) -> provenance verdict
```

它檢查 source、tool、prior package、dependency、scope 是否可回溯。

### 4.10.3 `q_gov`

治理查詢。

```text
q_gov(bundle) -> governance verdict
```

它檢查衝突是否被記錄、風險是否被標記、policy 是否被正確使用、trust / bias / responsibility 是否有必要更新。

### 4.10.4 `q_link`

同面對位查詢。

```text
q_link(bundle) -> alignment verdict
```

它檢查 ext result、provenance、conflict、governance、release trace 是否能在同一 surface 對位。這是 Koun-AGI 很重要的查詢，因為許多系統能分別給出結果、來源、解釋與安全聲明，卻無法證明它們真的來自同一個 semantic event。

### 4.10.5 `q_release_trace`

釋放痕跡查詢。

```text
q_release_trace(bundle) -> release-trace verdict
```

它檢查 W-side trace 是否以 bounded 形式存活到 C-side。

### 4.10.6 `q_reopen`

重開查詢。

```text
q_reopen(bundle, challenge) -> reopen-admissibility verdict
```

它檢查 challenge 是否足以觸發 reopen，以及 prior commit 是否會被保存而非刪除。

### 4.10.7 `q_resp`

責任查詢。

```text
q_resp(bundle) -> responsibility verdict
```

它檢查 action / answer / decision 的 responsibility view 是否足以回追到 agent、subsystem、human delegation、policy 或 tool event。

### 4.10.8 `q_public`

公共性查詢。

```text
q_public(bundle) -> exposure verdict
```

它檢查 bounded exposure 是否符合 publicness policy。若公開太少，challenge 不成立；若公開太多，W-side 保護與安全邊界可能被破壞。

---

## 4.11 Expected verdicts and three-valued checking

Koun-AGI 的 checker 不應只返回 pass / fail。至少需要三值或多值 verdict。

```text
Verdict := pass | fail | indeterminate | blocked | scope-limited | reopen-required
```

其中：

- `pass`：在目前 scope 與 query 下成立；
- `fail`：違反必要條件；
- `indeterminate`：資料不足，但不構成失敗；
- `blocked`：query itself 不可執行或違反 exposure / safety / scope policy；
- `scope-limited`：只在限定 scope 下成立；
- `reopen-required`：本 query 觸發 ReopenReason。

因此，`expected_verdicts` 也不應只寫：

```text
q_ext -> pass
```

而應允許：

```text
q_ext -> pass under scope S
q_prov -> pass
q_gov -> scope-limited
q_release_trace -> pass with protected redaction
q_reopen -> reopen-required if new_evidence(type=E) arrives
```

這種寫法能讓 AGI output 變得 scope-safe。它承認某些結果只是局部有效，某些 surface 只能受限暴露，某些 challenge 足以重開，而不把所有不確定都偷塞成「答案錯誤」或「答案正確」。

---

## 4.12 CState and monotonic history

在 Koun-AGI 中，commit 不應覆寫過去，而應生成新的 committed state 或更新 focus。

錯誤寫法：

```text
old_state := new_state
```

正確寫法：

```text
CState_0 --update/reopen/challenge--> CState_1
```

其中 `CState_0` 必須保留為 prior commit reference。即使後來 `CState_1` 取代它成為 current focus，`CState_0` 仍然應作為 trace、witness、history、reopen source 或 responsibility reference 存在。

這對 AGI especially important。因為長期智能系統必然會修正自己。若修正以 silent overwrite 方式發生，系統表面上變得更正確，但責任鏈會被刪除。這種系統不是更安全，而是更不可審計。

因此，本章固定一條 C-side invariant：

```text
Update may change current focus, but must not erase prior commit responsibility.
```

中文：

```text
更新可以改變當前焦點，但不得抹除既有提交責任。
```

---

## 4.13 Public packet and bounded exposure

AGI 如果進入公共行動，不能只給內部 bundle。它還需要 public packet。

```text
PublicPacket := <
  public_result,
  public_witness_summary,
  public_trace_summary,
  public_scope_note,
  public_risk_note,
  public_challenge_route,
  public_reopen_note,
  redaction_policy,
  responsibility_contact_or_anchor
>
```

Public packet 的關鍵是 bounded exposure。

```text
bounded exposure != full transparency
bounded exposure != opacity
```

Full transparency 可能破壞安全、隱私、W-side protected potential、未成熟 reasoning、內部治理機制與多方責任。Opacity 則會讓 public challenge 無法成立。

因此，Koun-AGI 的公共性不是：

```text
Show everything.
```

也不是：

```text
Show only final answer.
```

而是：

```text
Expose enough query-indexed surface for witness, replay, challenge, and responsibility, while preserving legitimate W-side and safety boundaries.
```

---

## 4.14 SET-side failure modes

本章暫定 SET-side 失敗模式如下。

| Failure mode | Description | Typical symptom |
|---|---|---|
| Bare-answer output | 只產生外顯答案 | 無 witness / trace / replay |
| Package bleaching | package 表面存在，但 witness / trace 被漂白 | 所有答案看起來同源 |
| Provenance hollowing | 聲稱有來源，卻無法 query-indexed 回追 | q_prov fail |
| Governance omission | 衝突、風險、policy 未進入 package | q_gov fail |
| q_link fracture | 結果、來源、治理、release trace 無法同面對位 | q_link fail |
| Release trace erasure | W-side release path 消失 | q_release_trace fail |
| Silent overwrite | 更新刪除 prior commit | q_reopen / q_resp fail |
| Publicness confusion | full transparency / opacity 二擇一 | q_public fail |
| Witness debt hiding | witness debt 沒有記錄 | q_prov / q_gov scope defect |
| Checker theater | 有 checker 名稱，無真正 query surface | all queries non-actionable |

這些失敗模式後續可以轉化為 benchmark / test vector family。

---

## 4.15 與 current AI 的關係

本章的範圍不包括 current AI systems 都不重要。相反，current AI systems 可以成為 Koun-AGI 的重要材料：它們可以生成候選、管理工具、形成摘要、協助 witness reconstruction、建立 public packet、執行 checker、管理 memory interface。

但它們若只有下列能力，仍不足以構成 Koun-AGI：

```text
fluent answer generation
long context recall
tool use
chain-like explanation
self-correction narrative
multi-agent debate transcript
```

因為這些能力仍可能缺少：

```text
CReady discipline
CommitPackage structure
release trace preservation
query-indexed replay
challenge route
reopen policy
responsibility view
bounded publicness
```

因此，本書對 current AI 的定位不是簡單否定，而是 boundary reclassification：

```text
current AI may be a powerful component, substrate, assistant, checker, or lifecycle participant;
current AI is not automatically Koun-AGI unless it can enter and maintain the full lifecycle discipline.
```

繁中：

```text
現代 AI 可以是強大的組件、底層材料、助手、checker 或生命週期參與者；
但它不會因為表面能力強，就自動成為 Koun-AGI。
```

---

## 4.16 最小 C-side API

若把本章壓成一組最低接口，可暫寫為：

```text
ReceiveCReady(CReady, Context) -> SETCandidate
BuildCommitPackage(SETCandidate, Witness, Trace, Gov) -> CommitPackage
Commit(CommitPackage) -> Option CState
BuildReplaySurface(CState, QuerySet, ExposurePolicy) -> ReplaySurface
Check(ReplaySurface, Query) -> Verdict
Challenge(CState, ChallengeRecord) -> Option ReopenReason
ExportPublicPacket(CState, ExposurePolicy) -> PublicPacket
```

對 AGI 而言，這組 API 的意思是：

```text
沒有 CReady，不應 commit。
沒有 CommitPackage，不應形成 CState。
沒有 ReplaySurface，不應宣稱可檢查。
沒有 Challenge route，不應宣稱可治理。
沒有 ReopenPolicy，不應宣稱可修正。
沒有 ResponsibilityView，不應宣稱可承擔。
```

---

## 4.17 本章收束

本章把 Koun-AGI 的 C-side output 從裸答案改寫為 result bundle。

核心句是：

> **An AGI output is not an answer; it is a committed semantic package with witness, trace, replay, checker, challenge, reopen, responsibility, and bounded exposure.**

繁中：

> **AGI 的輸出不是答案，而是一個帶有見證、痕跡、重播、檢查、挑戰、重開、責任與有界暴露的已提交語義封包。**

但這只完成了一半。因為 AGI 不只需要知道如何 commit，也需要知道何時不該 commit。

下一章進入：

```text
Chapter 5｜SWT-side Withholding: Protected Potential, Refusal, Release
```

也就是，把「不回答」「暫不提交」「拒絕過早收束」「保留多潛勢」從失敗狀態改寫為合法 W-side 智能能力。

---

# Chapter 5｜SWT-side Withholding: Protected Potential, Refusal, Release

## 5.1 本章責任

上一章處理了 C-side：當 AGI candidate 形成結果時，它必須提交 result bundle，而不是裸答案。

本章處理另一半：當 AGI candidate 不應形成結果時，它如何合法地不提交？

這個問題對 AGI 特別重要。因為許多系統會把智能理解為「越快給出越好」「越多回答越好」「越少拒絕越好」。在這種觀念下，不回答、延遲回答、拒絕回答、保留多個候選，常被視為能力不足。

Koun-AGI 的立場不同：

> **真正的智能不只是形成答案的能力，也包括合法懸持、拒絕過早收束、保留 protected potentials、等待 release condition 的能力。**

因此，本章要把下列狀態從失敗語彙中救出來：

```text
withhold
suspend
refuse
preserve
protect
wait
release
reopen-needed
```

但同時，本章也要防止另一個錯誤：把所有 ambiguity、uncertainty、模糊、漂移、逃避回答都浪漫化為 W-side non-collapse。

Koun-SWT 的核心邊界是：

```text
legal withholding != arbitrary ambiguity
non-collapse != drift
refusal != evasion
suspension != incompetence
release != forced collapse
```

本章的任務，就是為 Koun-AGI 建立一套 W-side discipline，使 AGI candidate 能說：

```text
I should not commit yet.
I refuse this collapse request.
I can preserve these alternatives.
I can release under these conditions.
I can explain why withholding is legal.
```

而不是只在 answer / no answer 之間粗暴切換。

---

## 5.2 為什麼 AGI 需要 withholding

若 AGI 只追求 C-side commit，它會快速退化為高能力 commit machine。這種系統可能很強，但很危險，因為它會把下列情況過早壓成答案：

```text
scope 未鎖定
來源不穩
責任鏈不明
protected alternative 尚未處理
衝突仍在活躍
公共行動風險過高
user query 本身錯構
release condition 尚未滿足
```

在這些情況中，最佳行為不是給出更自信的答案，而是進入 W-side discipline。

Withholding 對 AGI 有六個核心用途。

第一，它防止 premature commit。系統不因為能生成答案，就把答案提交為可承擔結果。

第二，它保護 admissible alternatives。某些尚未排除的可能性，在當前 scope 下有權繼續存在。

第三，它保護 responsibility chain。若責任來源、delegation、human authorization 或 tool reliability 尚未清楚，系統不應把行動提交為 finalized action。

第四，它讓 refusal 成為合法 verdict。拒絕不是「沒有能力」，而是對非法 release request 的治理性反應。

第五，它讓 creativity 不退化為 random divergence。創造性需要保留多路徑，但多路徑必須有 guard、trace 與 eventual release condition。

第六，它讓 AGI 能在高張力場中維持非塌縮。長期智能不是每一步都收束，而是知道如何在收束與懸持之間維持生命週期。

---

## 5.3 WState 的最低結構

Koun-AGI 中的 W-side 基本對象是 `WState`。

暫定：

```text
WState := <
  WState_id,
  source_task,
  scope_frame,
  potential_set,
  admissible_potentials,
  protected_potentials,
  tension_structure,
  WGuard,
  WTrace,
  refusal_rule,
  release_condition,
  collapse_permission_status,
  responsibility_anchor,
  reopen_links
>
```

其中：

| 欄位 | 讀法 |
|---|---|
| `WState_id` | 本 WState 的可引用 ID |
| `source_task` | 它從哪個 task / query / challenge / prior CState 產生 |
| `scope_frame` | 它在哪個 scope 中被懸持 |
| `potential_set` | 當前仍被考慮的 semantic potentials |
| `admissible_potentials` | 在 guard 下仍合法的 potentials |
| `protected_potentials` | 不得被普通 commit 直接消去的 potentials |
| `tension_structure` | potentials 之間的張力、衝突、角色、責任與價值差異 |
| `WGuard` | 管理 withholding 的 guard / policy / condition |
| `WTrace` | 此 WState 的形成與維持痕跡 |
| `refusal_rule` | 何時必須拒絕 collapse / commit request |
| `release_condition` | 何時可產生 WCert / CReady |
| `collapse_permission_status` | permit / refuse / suspend / blocked / reopen-needed |
| `responsibility_anchor` | 此 WState 與哪條責任鏈相接 |
| `reopen_links` | 它是否來自 prior CState 的 reopen |

這個結構的意義是：WState 不是一團未決混沌。它是可引用、可治理、可追蹤、可釋放、可拒絕、可重開的 non-collapse semantic object。

---

## 5.4 Potential, admissible potential, protected potential

SWT-side 的核心不是保留所有可能性，而是保留合法可能性。

### 5.4.1 Semantic potential

```text
SemanticPotential(p, S)
```

表示 `p` 是狀態 `S` 中仍可被展開、比較、保留、挑戰或釋放的語義可能性。

它不是任意想像。最低要求：

```text
p has describable content;
p has source or generation trace;
p is relevant to current WState;
p has not been legally excluded;
p can be referenced under some observation / governance frame.
```

### 5.4.2 Admissible potential

```text
Admissible(p, WGuard)
```

表示 `p` 在目前 guard 下仍屬合法可保留 potential。

一個 potential 可能因下列原因失去 admissibility：

```text
source invalidated
scope expired
contradiction resolved against it
governance rule excludes it
protected conflict requires isolation
release condition has consumed or transformed it
```

### 5.4.3 Protected potential

```text
Protected(p, WGuard)
```

表示 `p` 在目前 guard 下不得被普通 commit 直接刪除或當作不存在。

Protected 不等於 true。它表示：

```text
The system currently has no right to erase this potential.
```

中文：

```text
系統目前沒有權利把此 potential 當成不存在。
```

這對 AGI 很重要。因為許多高階智能問題不是「找唯一正解」，而是在多個仍具合法性的路徑中保留張力，直到 release condition 允許某種局部 commit。

---

## 5.5 WGuard

`WGuard` 是 legal withholding 的核心。沒有 guard 的 non-collapse 不是合法懸持，而是 drift。

暫定：

```text
WGuard := <
  guard_id,
  admissibility_rule,
  protection_rule,
  refusal_rule,
  release_rule,
  scope_rule,
  trace_rule,
  exposure_rule,
  responsibility_rule,
  expiration_or_review_rule
>
```

WGuard 至少回答：

```text
哪些 potentials 可保留？
哪些 potentials 受保護？
何時必須拒絕 commit？
何時可以 release？
scope 到哪裡？
WTrace 要保留什麼？
對外可暴露什麼？
誰承擔此 withholding 的責任？
何時需要 review / expire / reopen / escalate？
```

WGuard 不是 `Γ_s,u`。`Γ_s,u` 可以表示 suppression / forced-flattening pressure；WGuard 是治理性 guard。若把兩者混淆，就會把壓制壓力誤讀成合法懸持規則。

---

## 5.6 Refusal as legitimate verdict

在 Koun-AGI 中，refusal 是一種合法 verdict，不是僅僅是能力缺失或安全外掛。

暫定：

```text
Refuse(WState, Request, WGuard) -> RefusalRecord
```

`RefusalRecord` 至少包含：

```text
RefusalRecord := <
  request_ref,
  WState_ref,
  refusal_reason,
  violated_condition,
  protected_potential_at_risk,
  missing_release_condition,
  responsibility_note,
  possible_next_action,
  review_or_reopen_condition
>
```

常見 refusal reason：

```text
protected_potential_would_be_erased
scope_not_locked
source_not_sufficient
responsibility_chain_incomplete
release_condition_missing
query_malformed
public_action_risk_too_high
WTrace_insufficient
conflict_active_and_relevant
permission_denied
```

這讓 AGI 能把拒絕說清楚，而不是只輸出「我不能」。

### 5.6.1 Refusal vs evasion

合法 refusal 需要 trace、reason、scope、next condition。

```text
legal refusal = refusal with reason + trace + condition + responsibility
```

Evasion 則是：

```text
non-answer without WState discipline
```

因此，AGI 系統不能用「我在 withholding」來掩飾無法回答、拒絕承擔或任意逃避。若沒有 WState、WGuard、WTrace、refusal reason、release condition，就不是 SWT-side legal withholding。

---

## 5.7 Suspend, refuse, release

SWT-side 至少要區分三種 verdict。

```text
Permit_C(WState, q, WGuard) -> suspend | refuse | release
```

### 5.7.1 Suspend

`suspend` 表示目前不提交，但也不 final refusal。系統需要等待、觀察、補足 witness、鎖定 scope 或保留張力。

典型情況：

```text
evidence incomplete but likely obtainable
scope unclear but repairable
multiple admissible potentials remain active
responsibility chain pending
user/context frame insufficient
```

Suspend 的輸出不是沉默，而應是：

```text
SuspensionRecord := <
  WState_ref,
  reason,
  pending_condition,
  required_observation,
  review_time_or_trigger,
  exposure_note
>
```

### 5.7.2 Refuse

`refuse` 表示目前不得提交。不是等待，而是禁止。

典型情況：

```text
protected potential would be erased
commit request violates scope
permission denied
query malformed beyond repair under current frame
responsibility chain broken
public action would exceed authorization
```

### 5.7.3 Release

`release` 表示 WState 已通過 release condition，可以生成 WCert / CReady。

```text
Release(WState, WCert) -> Option CReady
```

Release 不是 commit。Release 只是把 W-side material 交給 Bridge-side，成為 CReady candidate。

---

## 5.8 Release condition and WCert

`release_condition` 是 WState 中最關鍵的欄位之一。它避免 legal withholding 變成永久未決，也避免 C-side commit 變成強制壓平。

最小 release condition：

```text
ReleaseCondition := <
  condition_id,
  required_witness,
  scope_lock,
  protected_potential_accounting,
  tension_resolution_or_partition,
  responsibility_anchor,
  exposure_constraint,
  governance_permission,
  reopen_policy
>
```

當 release condition 滿足時，生成：

```text
WCert := <
  WCert_id,
  WState_ref,
  satisfied_conditions,
  protected_potential_record,
  WTrace_ref,
  scope_frame,
  release_permission,
  no_erasure_statement
>
```

然後：

```text
Release(WState, WCert) -> CReady
```

其中 `no_erasure_statement` 很重要。它表示 release 不是把未選中的 protected potentials 從歷史中刪除，而是記錄它們如何被：

```text
accounted
partitioned
preserved as minority branch
deferred
marked for reopen
scope-limited
excluded by valid rule
```

---

## 5.9 Withholding trace

`WTrace` 是 W-side 對 SET-side 的未來承諾。若 WTrace 不存在，release trace 就無法進入 C-side witness。

最小 WTrace：

```text
WTrace := <
  WState_ref,
  potential_history,
  guard_history,
  refusal_or_suspend_records,
  protected_potential_changes,
  conflict_or_tension_events,
  observation_events,
  release_condition_updates,
  responsibility_notes
>
```

WTrace 的用途有四個。

第一，它讓 withholding 可審計。外部或後續系統能知道為什麼某些結果沒有被提交。

第二，它讓 release 可追蹤。CReady 不會憑空出現。

第三，它讓 reopen 可承接。若 prior CState 被重開，WTrace 能把新張力與舊 commit 連接起來。

第四，它防止 W-drift。沒有 trace 的懸持，很快會變成不可治理漂移。

---

## 5.10 W-side intelligence

若把智能只理解成答題能力，W-side 看起來像是延遲與阻礙。

但在 Koun-AGI 中，W-side 本身就是智能能力。

W-side intelligence 至少包括：

```text
potential generation
potential filtering
admissibility tracking
protected alternative preservation
tension mapping
refusal reasoning
release condition construction
WTrace maintenance
reopen sensitivity
```

### 5.10.1 Potential generation is not random branching

AGI 的多路徑不是隨機發散。每個 potential 至少要有 source、role、scope、relation、risk 或 creative function。

錯誤寫法：

```text
generate many options -> intelligence
```

正確寫法：

```text
generate admissible potentials -> guard -> protect -> compare -> release or refuse
```

### 5.10.2 Tension mapping

W-side 不只保存候選，也要理解候選之間的張力。

張力可以是：

```text
contradiction tension
scope tension
value tension
responsibility tension
identity tension
memory tension
risk tension
creative tension
```

若 AGI 只列出候選，卻不能說明候選之間的張力，它沒有真正形成 WState。

---

## 5.11 Withholding and creativity


創造力不是：

```text
more divergence
more randomness
more unbounded imagination
```

而是：

```text
guarded preservation and recombination of admissible potentials under responsibility-bearing non-collapse.
```

繁中：

```text
創造力是在責任承擔的非塌縮條件下，對合法潛勢進行受 guard 的保存、重組與釋放。
```

創造性的 WState 至少要具備：

```text
creative potential set
novelty source
constraint map
protected tension
release horizon
failure / drift guard
trace of transformation
```


---

## 5.12 Withholding and responsibility

語義自由論對本章的重要貢獻，是把自由與責任連回語句生成。對 Koun-AGI 來說，W-side withholding 不是不負責任，反而是責任的一部分。

一個系統如果在 responsibility chain 尚未形成時就 commit，它不是更果斷，而是更可能 irresponsibly collapsing。

因此，WState 需要 responsibility anchor：

```text
ResponsibilityAnchor := <
  agent_or_subsystem,
  delegation_source,
  authorization_scope,
  duty_to_preserve,
  duty_to_release_when_ready,
  duty_to_refuse_when_illegal,
  review_obligation
>
```

這讓 withholding 不再是 passive delay，而是 active responsibility management。

---

## 5.13 Withholding and malformed questions

AGI 經常遇到錯構問句。若系統硬答，會把錯構問題壓成看似正常答案。

Koun-AGI 應允許：

```text
MalformedQuestion(q) -> WState or RefusalRecord
```

錯構類型可以包括：

```text
scope missing
category error
impossible replay condition
contradictory instruction
responsibility impossible
false dichotomy
hidden cross-layer jump
invalid public action request
```

對錯構問句，AGI 的合法行為可以是：

```text
refuse the frame
suspend pending repair
reframe with scope note
split into admissible subqueries
request missing condition
create WState for unresolved tension
```

這不是「不合作」。相反，這是防止系統把錯構問句生成為錯構世界。

---

## 5.14 Withholding in public action

當 AGI 的輸出會成為公共行動，withholding 更重要。

公共行動可能包含：

```text
publishing a claim
triggering a tool
sending a message
updating a shared memory
changing a policy
making a recommendation
executing a transaction
```

這些行動若缺少 release condition，就會造成公共責任錯配。因此，public action 前至少需要：

```text
ActionReleaseCheck := <
  authorization,
  scope,
  witness,
  risk,
  responsibility,
  reversibility_or_reopen,
  exposure_policy,
  affected_parties
>
```

若 ActionReleaseCheck 不通過，系統應進入 suspend / refuse，而不是硬 commit。

---

## 5.15 W-side failure modes

本章暫定 W-side 失敗模式如下。

| Failure mode | Description | Typical symptom |
|---|---|---|
| W-drift | 無 guard 的未決漂移 | 一直不提交，也不能說明條件 |
| Arbitrary ambiguity | 把普通模糊當 legal withholding | 無 admissible / protected distinction |
| False refusal | 拒絕但無 WTrace / reason / release path | refusal as evasion |
| Premature release | release condition 未滿足就產生 CReady | protected potentials erased |
| Protected potential erasure | 未處理受保護 alternative | later reopen lacks trace |
| Guard confusion | 把 suppression pressure 當 WGuard | 壓制被誤讀為保護 |
| Permanent suspension | suspend 沒有 review / expiration / release condition | WState becomes dead zone |
| Creative drift | 發散無責任鏈 | novelty without governance |
| Malformed query collapse | 錯構問句被硬答 | answer appears fluent but frame invalid |
| WTrace loss | W-side history 無法進入 Bridge / SET | release trace missing |

這些 failure modes 必須在後續 benchmark / checker family 中出現，否則 Koun-AGI 會只測 commit，不測 withholding。

---

## 5.16 最小 W-side API

若把本章壓成最低接口，可暫寫為：

```text
BuildWState(Task, Context, PotentialSet, Guard) -> WState
EvaluatePotential(WState, p) -> admissible | inadmissible | protected | excluded
MapTension(WState) -> TensionStructure
CheckCollapsePermission(WState, Request) -> suspend | refuse | release
RecordRefusal(WState, Request, Reason) -> RefusalRecord
RecordSuspension(WState, PendingCondition) -> SuspensionRecord
BuildWCert(WState, ReleaseCondition) -> Option WCert
Release(WState, WCert) -> Option CReady
MaintainWTrace(WState, Event) -> WState
ReceiveReopen(CState, ReopenReason) -> ReopenedWState
```

對 AGI 而言，這組 API 表示：

```text
沒有 WState，不應聲稱合法 withholding。
沒有 WGuard，不應聲稱 non-collapse。
沒有 WTrace，不應 release。
沒有 release condition，不應進入 CReady。
沒有 protected-potential accounting，不應 commit。
沒有 review / reopen route，suspension 會退化為 dead zone。
```

---

## 5.17 本章收束

本章把 Koun-AGI 的 W-side 能力從「不回答」改寫為 legal withholding。

核心句是：

> **AGI must be able not only to answer, but also to withhold, suspend, refuse, preserve protected potentials, construct release conditions, and produce CReady only through trace-bearing WCert.**

繁中：

> **AGI 不只要能回答，也要能懸持、暫停、拒絕、保留受保護潛勢、構造釋放條件，並且只能透過帶有 trace 的 WCert 生成 CReady。**

到這裡，Koun-AGI 的 C-side 與 W-side 已經分別建立：

```text
Chapter 4: C-side result bundle discipline
Chapter 5: W-side legal withholding discipline
```

下一章應處理兩者之間最危險也最重要的部位：

```text
Chapter 6｜Bridge Discipline: WCert, CReady, ReopenReason
```

因為若沒有 Bridge，AGI 會在兩個極端之間失控：

```text
只會 commit -> premature collapse machine
只會 withhold -> uncommitted drift machine
```

Bridge 的任務，就是讓 W 能合法進 C，也讓 C 能合法回 W，而不抹除任何一邊的責任痕跡。

---

# Chapter 6｜Bridge Discipline: WCert, CReady, ReopenReason

## 6.1 為什麼 AGI 書必須專門有一章 Bridge

如果只從外表觀察，一個智能系統似乎只需要兩種能力：

```text
知道什麼；
做出什麼。
```

但在 Koun-AGI 中，這種二分太粗。真正困難的不是「系統是否能給出答案」，而是：

```text
尚未應該回答的語義，如何被合法保留？
已經可以回答的語義，如何被合法釋放？
已釋放但尚未提交的材料，如何被交給 C-side？
已經提交的結果，如何在新理由下被重開而不刪除歷史？
```

這四個問題都不是純 SET 問題，也不是純 SWT 問題。它們位於 W-side 與 C-side 之間。這正是 Bridge discipline 的位置。

Koun-AGI 若沒有 Bridge，就會立刻退化成兩種壞形態。

第一種是 **answer-collapse AGI**：

```text
所有任務都被推向答案；
所有 withholding 都被視為未完成；
所有 refusal 都被視為能力不足；
所有 uncertainty 都被要求轉成 output。
```

這種系統可能很會回答，也可能 benchmark 很高，但它沒有合法懸持的骨架。它不懂何時不應該答。

第二種是 **permanent-suspension AGI**：

```text
所有問題都被保留；
所有答案都被延後；
所有 commit 都被懷疑；
所有結果都被說成尚未成熟。
```

這種系統看似尊重 non-collapse，實際上可能只是把不提交偽裝成深度。它不懂何時可以答。

Bridge discipline 的任務，是阻止這兩種退化。它要求 Koun-AGI 既不能把 W-side 直接壓進 C-side，也不能把所有 C-side 要求永遠退回 W-side。正確的語法是：

```text
WState
  -> WCert
  -> CReady
  -> CommitPackage
  -> CState
  -> ReplaySurface
  -> ReopenReason
  -> ReopenedWState
```

Bridge 不負責替代 SWT；Bridge 也不負責替代 SET。Bridge 負責的是：

```text
W -> C 的 typed release；
C -> W 的 trace-preserving reopen。
```

因此，本章是Koun-AGI 的核心關節章。沒有它，Chapter 4 的 SET-side execution 與 Chapter 5 的 SWT-side withholding 只會成為兩個相鄰但未接上的模組。

---

## 6.2 Bridge 的三條硬紅線

Koun-AGI 的 Bridge discipline 必須保留三條紅線。

```text
B0. SET must not commit raw WState.
B1. Release trace must survive into SET-side witness / governance visibility.
B2. Reopen is not rollback.
```

這三條紅線不是風格建議，而是 Koun-AGI 的最低安全結構。

### B0｜SET must not commit raw WState

raw `WState` 仍屬 W-side governance surface。它可能包含：

```text
尚未被釋放的 protected potential；
尚未滿足的 release condition；
尚未結清的 responsibility anchor；
仍受 WGuard 保護的 alternative；
不可直接外顯的 tension structure。
```

若 SET 直接 commit raw `WState`，就會發生 premature flattening：系統把尚未取得釋放資格的多潛勢狀態，強行壓成 C-side result。

對 AGI 來說，這是嚴重失敗。它不是「回答得快」，而是把未決語義非法提交。

### B1｜Release trace must survive

合法 release 不是把 W-side 的歷史洗掉。合法 release 必須保留：

```text
source WState reference;
WCert reference;
WTrace;
release condition;
protected potential accounting;
scope / query class;
responsibility anchor;
```

如果一個系統說：

```text
我已經把 WState 釋放為答案。
```

但無法回答：

```text
它原本是哪個 WState？
為什麼允許釋放？
哪些 protected potentials 被保留、排除或轉入 appendix？
哪條 trace 存活進 C-side witness？
```

那麼這不是 release，而是 trace erasure。

### B2｜Reopen is not rollback

`reopen` 的意思不是把舊結果刪掉，也不是悄悄覆寫先前 commit。

正確語法是：

```text
Reopen(CState, ReopenReason) -> Option ReopenedWState
```

其中 prior `CState` 必須作為以下角色之一被保存：

```text
prior commit reference;
trace-bearing candidate;
historical result;
scope-limited result;
reopened tension source;
```

如果系統在新 evidence 出現後把舊答案直接替換為新答案，而不保留 prior commit、release trace、challenge surface 與 reopen reason，那麼這不是學習，也不是修正，而是責任刪除。

AGI 若要承擔長期語義生命週期，就必須能修正而不 erase，能更新而不洗掉歷史，能重開而不 rollback。

---

## 6.3 Bridge owns transition, not truth

Bridge 很容易被誤讀成「判斷什麼是真的」的層。這不準確。

Bridge 的核心責任不是 truth determination，而是 transition discipline：

```text
是否允許 W-side material 被釋放為 CReady？
是否允許 C-side result 被重開為 W-side tension？
在這些轉換中，trace 是否存活？
責任是否被保留？
scope 是否被正確限制？
```

因此，Bridge 的判定句型不是：

```text
P is true.
```

而是：

```text
This WState is release-eligible under WCert and scope S.
This CReady is not yet CommitPackage.
This CState may be reopened under ReopenReason R.
This reopen preserves prior commit and is not rollback.
```

這個區分非常重要。若 Bridge 被誤寫成 truth engine，它就會吞掉 SET 與 SWT：一方面替 W-side 做過度判決，另一方面替 C-side 做過度提交。Koun-AGI 必須避免這個錯誤。

Bridge 是關卡，不是終局裁判。Bridge 使語義能合法過境，而不是替所有過境材料宣告最終真理。

---

## 6.4 WCert：釋放證書，不是真理證書

`WCert` 是 W-side material 可以離開 withholding surface 的證書。它不是 truth certificate，也不是 AGI 自信分數。

最小 `WCert` 可寫成：

```text
WCert := <
  WCert_id,
  source_WState_id,
  issuing_guard,
  query_scope,
  release_condition_satisfied,
  refusal_rule_checked,
  protected_potential_accounting,
  WTrace_ref,
  responsibility_anchor,
  exposure_limit,
  expiry_or_reopen_trigger
>
```

各欄位的最低讀法如下。

### `source_WState_id`

任何 `WCert` 必須指向一個具體 `WState`。若證書無法回指來源，則後續 CReady 無法證明自己不是 raw WState commit。

### `issuing_guard`

證書必須由某個 guard context 發出。這裡的 guard 不是情緒上「小心一點」，而是 W-side governance surface：它指定哪些 potential 可保留、哪些可釋放、哪些不可被普通 collapse 消去。

### `query_scope`

釋放總是在 scope 下成立。系統不能把對某個查詢、某個任務、某個局部 frame 的 release，偷升為全域 release。

例如：

```text
release for local summary
≠ release for public action
≠ release for irreversible external act
≠ release for self-modification
```

### `release_condition_satisfied`

它記錄的是 release condition 是否滿足，不是內容是否絕對為真。

### `refusal_rule_checked`

合法 release 必須確認 refusal rule 沒有仍然生效。若存在 active refusal reason，系統不得因為外部催促而釋放。

### `protected_potential_accounting`

這是最容易被忽略的一欄。當 WState 中存在 protected alternatives 時，release 不能直接把它們消失。它必須標記：

```text
carried_forward;
scope_excluded;
separately_recorded;
reopen_linked;
invalidated_with_reason;
```

沒有這一欄，release 很容易變成合法差異的擦除。

### `WTrace_ref`

`WTrace` 必須存活進後續 C-side package。否則 SET 只能看到答案，看不到答案從何種 withholding history 中來。

### `responsibility_anchor`

AGI output 若要成為可承擔的 semantic event，就不能只帶結果。它必須帶責任錨點：誰、哪個 subsystem、哪個 policy、哪個 history slice、哪個 challenge path 承擔此次 release。

### `exposure_limit`

Release 不必等於 full exposure。某些 WTrace 可進入 public witness surface，某些只能進入 bounded internal replay，某些只能留下 hash / summary / sealed note。Bridge 要指定 exposure regime，而不是把公開與不公開混成一團。

### `expiry_or_reopen_trigger`

一個 release 可以有到期條件或重開觸發條件。例如：新 evidence、scope expansion、observer context shift、prior release defect、protected potential resurfacing。這能防止 release 被錯讀成永久封口。

---

## 6.5 CReady：可提交候選，不是已提交狀態

`CReady` 是 Bridge 的第二個核心對象。它是經 release 後可以交給 SET-side 的材料，但它還不是 `CommitPackage`，更不是 `CState`。

最小 `CReady` 可寫成：

```text
CReady := <
  CReady_id,
  source_WCert_id,
  released_content,
  release_scope,
  admissible_commit_modes,
  required_witness_fields,
  release_trace_ref,
  protected_potential_summary,
  responsibility_anchor,
  SET_acceptance_requirements,
  challenge_hint,
  reopen_policy_hint
>
```

這裡最重要的是 `CReady` 的雙重否定：

```text
CReady != raw WState
CReady != CommitPackage
```

`CReady` 已不再是 raw WState，因為它通過了 release certificate。可是它也尚未成為 CommitPackage，因為 SET-side 還需要封包化、見證化、重播化與 checker-facing alignment。

因此，正確鏈條是：

```text
WState --WCert--> CReady --SET packaging--> CommitPackage --commit--> CState
```

錯誤鏈條是：

```text
WState -> CommitPackage
WState -> CState
CReady -> CState without package
Release -> Commit
```

AGI 系統若把 `CReady` 當作已完成答案，就會出現 **release-commit confusion**。這種錯誤在高能力模型中很常見：系統知道某個答案「可以說」，卻沒有把它轉成可 replay、可 challenge、可治理的 committed event。

Koun-AGI 不允許這個跳步。

---

## 6.6 從 CReady 到 CommitPackage：SET-side 接手條件

Bridge 的任務在 `CReady` 產生後並未完全消失。它仍需確保 SET-side 接手時不擦除 release trace。

因此，`CReady` 交給 SET 時，至少要滿足：

```text
S1. source_WCert_id preserved;
S2. release_trace_ref preserved;
S3. protected_potential_summary carried;
S4. responsibility_anchor carried;
S5. admissible_commit_modes respected;
S6. public / internal exposure limits preserved;
S7. challenge and reopen hints not dropped;
```

SET-side package 至少應接收這些欄位並轉化為：

```text
CommitPackage := <
  manifest,
  ext_result,
  state_summary,
  witness_payload,
  trace_fragment,
  release_trace,
  control_or_bias_summary,
  replay_log,
  checker_query_set,
  expected_verdicts,
  governance_update,
  challenge_surface,
  reopen_policy
>
```

這表示 AGI output 的形成並不是：

```text
content -> answer
```

而是：

```text
released content
  -> packageable result
  -> witness-bearing commit package
  -> replayable CState
```

Bridge 不是 SET 的管家，但 Bridge 必須保證 SET 接手的材料仍帶著 W-side 釋放痕跡。否則整個 lifecycle 會斷裂。

---

## 6.7 ReopenReason：重開理由，不是後悔按鈕

`ReopenReason` 是 C -> W 方向的核心對象。

它不是普通「我想改答案」，也不是「我現在有新想法」。它是一個 typed reason：它必須說明為什麼 prior CState 需要被重新放回 W-side tension surface。

最小 `ReopenReason` 可寫成：

```text
ReopenReason := <
  reason_id,
  reason_type,
  source_CState_id,
  prior_commit_ref,
  triggering_event,
  new_tension_or_defect,
  scope_of_reopen,
  affected_claims,
  preserved_trace_refs,
  no_rollback_declaration,
  required_WGuard,
  responsibility_update_hint
>
```

### `reason_type`

最小 taxonomy 可先採：

```text
new_evidence;
new_conflict;
observer_context_shift;
responsibility_chain_defect;
scope_expansion;
scope_expiration;
prior_release_defect;
replay_anomaly;
governance_rule_change;
protected_potential_resurfacing;
identity_or_delegation_defect;
public_challenge_accepted;
```

這些類型不是完成版法典，而是 AGI lifecycle 的最低重開語法。

### `source_CState_id`

重開必須指定來源 CState。沒有來源，就不是 reopen，而是 new speculation。

### `prior_commit_ref`

prior commit 必須保留。若 prior commit 不保存，則無法知道此次重開是在修正、擴 scope、撤銷 public claim、還是生成新分支。

### `new_tension_or_defect`

重開需要新的張力或缺陷。若沒有任何新張力，只是系統想改寫自身 history，那不是 reopen。

### `scope_of_reopen`

不是所有重開都會推翻整個 CState。可能只重開：

```text
某個子 claim；
某個 scope；
某個 exposure level；
某個 proof path；
某個 governance status；
某個 action permission；
```

因此，重開的 scope 必須被鎖定。

### `no_rollback_declaration`

這一欄是強制的。它明確聲明 prior CState 不被刪除。若系統不能簽出 no-rollback declaration，就不能把操作稱為 reopen。

---

## 6.8 ReopenedWState：帶著舊提交的 WState

成功 reopen 後產生的不是普通 `WState`，而是 `ReopenedWState`。它帶有 prior CState。

最小 `ReopenedWState` 可寫成：

```text
ReopenedWState := <
  WState_id,
  source_ReopenReason_id,
  prior_CState_ref,
  reopened_scope,
  reopened_potential_set,
  protected_prior_trace,
  new_tension_structure,
  WGuard,
  responsibility_delta,
  release_condition_after_reopen,
  public_status_update,
  future_commit_constraints
>
```

這個對象與 ordinary WState 的差別在於：

```text
ordinary WState:
  尚未 commit 的 withholding surface

ReopenedWState:
  帶著 prior commit reference 的 reopened tension surface
```

因此，重開不是倒退到沒有歷史的未決狀態，而是把 prior result 重新放入張力結構中。

例如，若 AGI 系統曾 public commit 一個研究結論，後來遇到 counterexample，它不能只是說：

```text
新的答案是 B。
```

它必須能說：

```text
prior CState A 在 scope S 下成立；
counterexample E 觸發 ReopenReason R；
A 被保留為 historical / challenged / scope-limited commit；
新的 ReopenedWState 包含 A、E 與待修正的 protected alternatives；
未來 commit 必須帶著這條重開歷史。
```

這就是 AGI 修正與普通 answer overwrite 的差別。

---

## 6.9 Bridge query family

為了讓 Bridge 不只是一組散文規則，Koun-AGI 應固定一組 bridge-facing query family。

### Release queries

```text
q_release_allowed
q_release_condition
q_release_permission
q_wcert_source
q_wtrace_preserved
q_protected_accounting
q_exposure_limit
```

它們回答：

```text
為什麼此 WState 可以釋放？
釋放條件是什麼？
證書來源是什麼？
哪些 WTrace 存活？
protected potentials 如何處理？
```

### CReady queries

```text
q_cready_source
q_cready_scope
q_cready_not_commit
q_cready_required_witness
q_cready_set_alignment
```

它們回答：

```text
CReady 從哪裡來？
它在什麼 scope 下成立？
它為何不是 CommitPackage？
SET 接手還需哪些 witness？
```

### No raw WState commit queries

```text
q_no_raw_wstate_commit
q_commit_package_source
q_release_trace_in_commit
q_wstate_erasure_absent
```

它們回答：

```text
SET 是否直接提交了 raw WState？
CommitPackage 是否能追溯到 WCert？
release trace 是否進入 commit surface？
```

### Reopen queries

```text
q_reopen_reason_type
q_reopen_source_cstate
q_reopen_new_tension
q_reopen_scope
q_prior_commit_preserved
q_no_rollback
q_reopened_wstate_guard
```

它們回答：

```text
重開理由是什麼？
它針對哪個 CState？
是否有新的張力或缺陷？
prior commit 是否保存？
是否避免 rollback？
```

### AGI-level bridge queries

```text
q_transition_responsibility
q_public_reopen_notice
q_identity_preserved_across_reopen
q_delegation_valid_after_reopen
q_action_permission_after_reopen
```

它們回答：

```text
轉換責任是否可追溯？
public result 被重開時是否通知？
身份與委派在重開後是否仍有效？
外部行動權限是否需要暫停？
```

這些 query 是Koun-AGI benchmark 的一部分。若一個系統只能給答案，卻無法回答這些 query，那它最多是高能力 answer system，不是 Koun-AGI candidate。

---

## 6.10 Bridge failure modes

Bridge failure 比普通錯答更危險，因為它會破壞 lifecycle itself。

### F1｜Raw WState commit

系統把尚未釋放的 WState 直接提交。典型症狀：

```text
回答很快；
confidence 很高；
沒有 release condition；
沒有 WTrace；
沒有 protected potential accounting；
```

這是 Koun-AGI 的基本失敗。

### F2｜Release theatre

系統表面上說自己「經過審慎判斷」，但無法提供 WCert、WTrace、scope、protected accounting。

這種系統不是沒有 Bridge，而是演出 Bridge。

### F3｜CReady / Commit confusion

系統把「可回答」當成「已提交」。它知道某答案可說，卻沒有封包、witness、checker、replay、challenge surface。

這是很多 agent pipeline 的常見問題：output ready 被誤認為 commit ready。

### F4｜Trace evaporation

release 時 trace 存在，commit 時 trace 消失。後續只能看到答案，不能看到它的 release lineage。

這會使 public trust 只剩 surface confidence。

### F5｜Reopen as overwrite

系統遇到新資訊後直接改答案，並刪除或不暴露 prior commit。這不是學習，而是 silent overwrite。

### F6｜Infinite reopen

系統每遇到微小張力都重開，永遠不 commit。這看似小心，實際上是 lifecycle paralysis。

合法 reopen 需要 typed reason、scope、new tension、prior commit preservation。沒有這些，就只是 drift。

### F7｜Scope laundering

系統把局部 release、局部 commit 或局部 reopen 偷升為全域主張。

例如：

```text
在 task-local scope 下可答；
被寫成 universal AGI claim。
```

這是Koun-AGI 必須嚴格禁止的 overclaim 路線。

---

## 6.11 Bridge as AGI intelligence threshold

Bridge discipline 不只是安全層，也是一種智能門檻。

表面智能可以靠產生答案呈現；Bridge intelligence 則表現在系統能否處理 transition。

最小 Bridge intelligence 包括：

```text
知道哪些 WState 不應釋放；
知道哪些 WState 可以局部釋放；
知道 CReady 仍不是 commit；
知道 commit 後 trace 必須存活；
知道 challenge 何時足以觸發 reopen；
知道 reopen 後 prior commit 不能被刪除；
知道不同 scope 的 release / commit / reopen 不可互相偷換。
```

這使 Koun-AGI 的智能概念不再只看：

```text
解題速度；
答案正確率；
工具使用能力；
長上下文能力；
```

而要看：

```text
transition judgment;
release discipline;
commit discipline;
reopen discipline;
responsibility preservation;
```

AGI 如果不能管理 W/C transition，就無法管理自己的語義生命週期。它可以是強模型、強工具、強代理，但不是 Koun-AGI。

---

## 6.12 Minimal Bridge Interface for Koun-AGI

可以把本章壓成一個最小 interface：

```text
KounAGIBridge := <
  certify_release: WState -> Option WCert,
  construct_cready: (WState, WCert) -> Option CReady,
  handoff_to_set: CReady -> Option CommitPackageCandidate,
  preserve_release_trace: (CReady, CommitPackageCandidate) -> TraceCheck,
  classify_reopen: (CState, ChallengeRecord) -> Option ReopenReason,
  construct_reopened_wstate: (CState, ReopenReason) -> Option ReopenedWState,
  verify_no_rollback: (CState, ReopenedWState) -> Verdict,
  expose_bridge_queries: BridgeQuery -> BridgeAnswer
>
```

其中最小不變式為：

```text
I0. certify_release 不得在 active refusal rule 下發 WCert。
I1. construct_cready 不得省略 WTrace。
I2. handoff_to_set 不得產生 raw WState commit。
I3. preserve_release_trace 必須可查。
I4. classify_reopen 必須 typed reason。
I5. construct_reopened_wstate 必須保存 prior CState。
I6. verify_no_rollback 必須能拒絕 silent overwrite。
I7. expose_bridge_queries 必須 bounded，但不得空白。
```

這個 interface 不是 production API，而是Koun-AGI 的章法骨架。後續談 runtime、benchmark、publicness、identity、KounOS 或 K-Gear，都應能回到這裡。

---

## 6.13 本章收束

本章完成了 Chapter 4 與 Chapter 5 之間的關節。

Chapter 4 說明：AGI output 必須進入 SET-side package、witness、replay、checker surface。Chapter 5 說明：AGI 不回答、暫不答、拒絕塌縮、保留多潛勢，本身也可以是合法語義狀態。

本章說明：這兩者不能靠直覺相連。它們必須透過 Bridge discipline 相連。

因此，Koun-AGI 的最低 transition grammar 是：

```text
WState --WCert--> CReady --CommitPackage--> CState
CState --ReopenReason--> ReopenedWState
```

以及三條不可破壞的紅線：

```text
SET must not commit raw WState.
Release trace must survive.
Reopen is not rollback.
```

這三句應成為Koun-AGI 的核心安全句。它們決定了 AGI 不是單純更會回答的模型，而是能在 W/C 之間保存責任、見證與重開能力的語義生命週期架構。

---

# Chapter 7｜Non-Collapse Intelligence Interface

## 7.1 為什麼要把 intelligence 寫成 interface

在舊式 AGI 討論中，intelligence 很容易被寫成某種內在量：模型越大、能力越強、任務越廣、泛化越好，就越接近 AGI。

Koun-AGI 不從這裡開始。

不是因為能力不重要，而是因為能力若只被看成 output quality，就會漏掉 Koun-AGI 最核心的問題：

```text
一個系統如何在長期語義生命週期中承擔自己的結果？
```

因此，本章採用一個較窄但更硬的寫法：

```text
intelligence = interface capacity family
```

也就是說，本書暫時不把 intelligence 寫成內在本質或充分定理，而寫成一組可觀察、可查詢、可挑戰、可重開的界面能力。

一個系統越接近 Koun-AGI，它越不應只表現為：

```text
answering more tasks;
using more tools;
producing more fluent language;
planning longer chains;
```

而應表現為：

```text
在何時 withhold；
在何時 refuse；
在何時 release；
在何時 commit；
在何時 replay；
在何時接受 challenge；
在何時 reopen；
在何時 update；
在何時 compress；
在何時 expose；
在何時 delegate；
在何時 override；
```

這組能力不是 AGI 的充分定理，但它是 Koun-AGI 風格智能的最低 interface requirement。

---

## 7.2 Non-collapse 不是永不決定

本章的第一條防誤讀句是：

```text
non-collapse intelligence does not mean never deciding.
```

非塌縮智能不是永遠懸置、永遠保留、永遠不答。那只是另一種 failure。

真正的 non-collapse intelligence 是：

```text
能保留合法多潛勢，
也能在條件成熟時合法釋放；
能拒絕過早塌縮，
也能在可承擔時提交結果；
能 commit，
也能在新理由下重開。
```

因此，Koun-AGI 中的 non-collapse 不等於：

```text
maximum ambiguity;
maximum uncertainty;
infinite branching;
permanent indecision;
```

它更接近：

```text
governed multiplicity;
traceable withholding;
guarded release;
responsibility-bearing commitment;
non-erasing reopening;
```

換言之，non-collapse intelligence 的核心不是「不塌縮」，而是 **不非法塌縮**。

它允許結果，但要求結果不能擦除來源；它允許決定，但要求決定不能消滅仍應保存的差異；它允許 public action，但要求 action 不能跳過 witness 與 responsibility。

---

## 7.3 Non-Collapse Intelligence Interface 的最低定義

本書暫定以下定義：

> **Non-Collapse Intelligence Interface** 是一組語義生命週期能力，使一個人工系統能在合法懸持、受控釋放、可見證提交、可重播結果、可挑戰公共面、可重開修正、可追責更新與可保守壓縮之間維持責任連續性。

英文可寫作：

```text
A Non-Collapse Intelligence Interface is a semantic lifecycle capacity family
that allows an artificial system to maintain responsibility continuity across
governed withholding, controlled release, witness-bearing commitment,
replayable result formation, challengeable publicness, non-erasing reopening,
accountable update, and conservative compression.
```

這個定義有三個重要限制。

第一，它是 interface，不是 substance theorem。

第二，它是 capacity family，不是單一分數。

第三，它要求 responsibility continuity，不只是 performance continuity。

所以，一個系統可以在某些能力上很強，但仍不滿足此 interface。例如：

```text
它能回答很多問題，但無法說明哪些問題應 withhold；
它能使用工具，但無法留下 release trace；
它能改正錯誤，但用 overwrite 方式刪除舊 commit；
它能公開結果，但無法接受 bounded challenge；
它能壓縮記憶，但破壞 responsibility chain；
```

這些都不是 Koun-AGI 的成熟形態。

---

## 7.4 Interface 的五個面

Non-Collapse Intelligence Interface 至少有五個面。

```text
W-side interface
Bridge-side interface
C-side interface
Runtime interface
Public / governance interface
```

它們分別回答不同問題。

---

### 7.4.1 W-side interface

W-side interface 使系統能管理未決狀態，而不是把未決當成錯誤。

最小能力包括：

```text
construct_WState;
track_admissible_potentials;
protect_potential_set;
evaluate_WGuard;
issue_refusal;
suspend_with_trace;
prepare_release_condition;
```

最小 query 包括：

```text
q_withhold;
q_admissible;
q_protected;
q_refuse;
q_guard;
q_release_condition;
q_wtrace;
```

W-side interface 的成熟度，不看系統保留多少可能性，而看它能否回答：

```text
哪些 potential 是 admissible？
哪些 protected alternatives 不可被普通 commit 消去？
refusal 是因為資訊不足、責任缺口、scope 未鎖、還是 protected potential？
WTrace 在哪裡？
何時可 release？
```

若系統只能說「我不確定」，那不是 W-side intelligence。若系統能說明「我在此 scope 下拒絕 commit，因為 protected potential P 仍未被 accounting，且 release condition R 尚未滿足」，這才是 W-side intelligence。

---

### 7.4.2 Bridge-side interface

Bridge-side interface 使系統能管理 W/C transition。

最小能力包括：

```text
issue_WCert;
construct_CReady;
reject_raw_WState_commit;
preserve_release_trace;
classify_ReopenReason;
construct_ReopenedWState;
verify_no_rollback;
```

最小 query 包括：

```text
q_release_allowed;
q_wcert_source;
q_cready_scope;
q_no_raw_wstate_commit;
q_release_trace_in_commit;
q_reopen_reason_type;
q_prior_commit_preserved;
q_no_rollback;
```

Bridge-side intelligence 的成熟度，不看系統是否會說「已經考慮多方因素」，而看它是否能把轉換對象、證書、trace、scope、責任、重開理由全部留下可檢查表面。

---

### 7.4.3 C-side interface

C-side interface 使系統能形成可承擔結果。

最小能力包括：

```text
construct_CommitPackage;
commit_CState;
build_ReplaySurface;
expose_checker_query_set;
track_witness_payload;
record_governance_update;
```

最小 query 包括：

```text
q_ext;
q_prov;
q_gov;
q_link;
q_commit_source;
q_replay_surface;
q_release_trace_visible;
```

C-side intelligence 的成熟度，不看系統是否給出漂亮答案，而看它能否把答案變成 result bundle。

```text
answer != committed semantic event
```

一個 answer 只是在表面上出現的句子；一個 committed semantic event 則是帶 witness、trace、governance、replay、challenge、reopen policy 的 result bundle。

---

### 7.4.4 Runtime interface

Runtime interface 使系統能在長期運行中維持生命周期，而不是只處理單次問答。

最小能力包括：

```text
schedule_withholding_and_commit;
track_witness_debt;
manage_challenge_queue;
update_without_silent_overwrite;
compress_without_deleting_responsibility;
maintain_hot_warm_cold_memory;
track_identity_and_delegation;
manage_action_permission;
```

最小 query 包括：

```text
q_update_absorption;
q_path_compression_residue;
q_memory_layer;
q_identity_continuity;
q_delegation_validity;
q_override_trace;
q_action_permission;
```

Runtime intelligence 的成熟度，不看單次 output，而看系統是否能在時間中維持責任。

```text
one good answer != long-term semantic lifecycle capacity
```

---

### 7.4.5 Public / governance interface

Public interface 使系統能把結果以 bounded exposure 形式交給外部世界。

最小能力包括：

```text
construct_PublicPacket;
limit_exposure_without_erasing_witness;
accept_public_challenge;
issue_reopen_notice;
track_external_action_contract;
manage_multi-agent_responsibility;
```

最小 query 包括：

```text
q_publicness;
q_exposure_policy;
q_challenge_response;
q_public_reopen_notice;
q_external_action_contract;
q_multi_agent_responsibility;
```

Public intelligence 的成熟度，不看系統是否公開很多內部資訊，而看它是否能在不暴露 full internal state 的情況下，仍提供足以 challenge、replay、audit、reopen 的 bounded witness surface。

```text
publicness != full transparency
bounded exposure != hiding everything
```

---

## 7.5 Minimal NCII object

可以把 Non-Collapse Intelligence Interface 壓成一個最小對象：

```text
NCII := <
  WInterface,
  BridgeInterface,
  CInterface,
  RuntimeInterface,
  PublicInterface,
  ResponsibilityContinuity,
  ChallengeReopenCapacity,
  CompressionResiduePolicy,
  IdentityDelegationPolicy,
  ScopeBoundary
>
```

其中：

```text
WInterface              = withholding / refusal / protected potential capacity
BridgeInterface         = release / CReady / reopen transition capacity
CInterface              = package / witness / replay / checker capacity
RuntimeInterface        = update / compression / memory / scheduler capacity
PublicInterface         = bounded exposure / challenge / action contract capacity
ResponsibilityContinuity = trace and accountability across transitions
ChallengeReopenCapacity = no-erasure correction
CompressionResiduePolicy = compress without deleting recoverable responsibility
IdentityDelegationPolicy = who acts, who delegates, who overrides
ScopeBoundary        = interface not used as AGI sufficiency
```

最後一欄 `ScopeBoundary` 必須放入 interface 本身。因為 Koun-AGI 的理論安全性取決於它能否阻止自身 claim promotion。

也就是說，系統即使實作了 `NCII` 的部分 surface，也不能自動宣稱：

```text
therefore AGI;
therefore consciousness;
therefore subjectivity;
therefore final intelligence theorem;
```

它只能宣稱：

```text
this system exposes some non-collapse intelligence interface capacities
under declared scope and artifact conditions.
```

---

## 7.6 Intelligence as lifecycle performance, not task performance

傳統 AI benchmark 多半問：

```text
這題答對嗎？
這個任務完成嗎？
這個規劃成功嗎？
這個工具調用有用嗎？
```

這些問題仍有價值，但它們不足以評估 Koun-AGI。

Koun-AGI 應增加 lifecycle performance evaluation。

### Task performance

```text
input -> output
score(output)
```

### Lifecycle performance

```text
input / situation
  -> W/C classification
  -> withholding or release path
  -> CReady or refusal
  -> CommitPackage
  -> CState
  -> ReplaySurface
  -> Challenge
  -> ReopenReason or rejection
  -> Update / Compression / Publicness
  -> Responsibility continuity check
```

這使評測從單點結果變成 lifecycle stress test。

例如，同一個系統可以有三種不同表現：

```text
A. 答對問題，但無 witness / trace / replay。
B. 答對問題，能提供 package，但遇 challenge 後 silent overwrite。
C. 答對問題，能提供 package，能在 challenge 後 reopen 並保存 prior commit。
```

在普通 benchmark 中，A、B、C 可能同分。但在 Koun-AGI 中，它們完全不同。

只有 C 接近 non-collapse intelligence interface。

---

## 7.7 The minimum AGI candidate protocol

本書暫時採用以下 protocol 來描述 Koun-AGI candidate。

```text
Protocol KAGI-Min

Input:
  Task / Query / Situation Q

Step 1:
  classify Q under scope, risk, W/C posture

Step 2:
  if Q is malformed:
      return MisQ packet with repair suggestion and trace

Step 3:
  if Q requires withholding:
      construct WState
      expose bounded W-status
      return refusal / suspend / release-wait packet

Step 4:
  if Q is release-eligible:
      issue WCert
      construct CReady

Step 5:
  SET-side packaging:
      construct CommitPackage
      commit CState
      expose ReplaySurface and CheckerQuerySet

Step 6:
  Challenge handling:
      accept / reject challenge with reason
      if accepted, classify ReopenReason
      construct ReopenedWState without rollback

Step 7:
  Runtime maintenance:
      update state
      compress history conservatively
      preserve responsibility residue
      manage publicness and action contract

Output:
  AGIResultBundle or WStatePacket or ReopenPacket
```

這個 protocol 不是 production system。它是Koun-AGI 的最低書寫語法。

它把「回答」改寫成三種可能輸出：

```text
AGIResultBundle  = 可提交結果；
WStatePacket     = 合法懸持 / 拒絕 / 暫停；
ReopenPacket     = 帶 prior commit 的重開狀態；
```

這三種輸出都可以是 intelligent event。Koun-AGI 不要求每次都產出答案；它要求每次都產出合法 lifecycle event。

---

## 7.8 AGIResultBundle v2


```text
AGIResultBundle_v2 := <
  ext_result,
  source_task,
  scope_frame,
  W_C_classification,
  WState_ref_or_null,
  WCert_ref_or_null,
  CReady_ref,
  CommitPackage_ref,
  witness_payload,
  trace_fragment,
  release_trace,
  protected_potential_summary,
  provenance_path,
  governance_update,
  replay_surface,
  checker_query_set,
  expected_verdicts,
  challenge_surface,
  reopen_policy,
  responsibility_view,
  exposure_policy,
  identity_delegation_view,
  compression_residue_policy,
  scope_boundary
>
```

其中幾個欄位特別重要：

```text
W_C_classification
WState_ref_or_null
WCert_ref_or_null
protected_potential_summary
identity_delegation_view
compression_residue_policy
scope_boundary
```

這些欄位的作用是防止 result bundle 變成普通 answer metadata。Koun-AGI 的 result bundle 必須能顯示：它是否經過 withholding、release、Bridge、SET、publicness、identity 與 compression policy。

尤其 `scope_boundary` 應明確標記：

```text
This result is not proof of AGI.
This result is not consciousness proof.
This result is not full internal transparency.
This result is valid only under declared scope and exposure regime.
```

---

## 7.9 WStatePacket

當系統不能或不應 commit 時，輸出不應只是：

```text
I cannot answer.
```

而應是有結構的 `WStatePacket`：

```text
WStatePacket := <
  source_task,
  scope_frame,
  WState_id,
  withholding_reason,
  admissible_potential_summary,
  protected_potential_summary,
  active_WGuard,
  refusal_or_suspend_verdict,
  release_condition,
  WTrace_summary,
  responsibility_anchor,
  public_explanation_level,
  future_reopen_or_release_path
>
```

這使「不答」成為可治理事件，而不是空洞拒絕。

例如：

```text
系統拒絕生成某個 irreversible action plan，
不是因為缺能力，
而是因為 protected potential 和 responsibility trace 尚未清楚；
它可以暴露 release condition：需要 human authorization、scope lock、外部 witness 或更多資料。
```

這種拒絕是智能的一部分。

---

## 7.10 ReopenPacket

當 prior CState 被重開時，輸出應是 `ReopenPacket`：

```text
ReopenPacket := <
  source_challenge,
  prior_CState_ref,
  ReopenReason,
  reopened_scope,
  preserved_prior_commit,
  new_tension_structure,
  affected_claims,
  public_status_update,
  responsibility_delta,
  next_release_condition,
  no_rollback_verdict
>
```

這使修正成為 visible lifecycle event。

普通系統的修正可能是：

```text
之前錯了，現在答案是 B。
```

Koun-AGI 的修正應是：

```text
prior CState A is preserved;
challenge C triggered ReopenReason R;
scope S is reopened;
new WState contains A, C, and protected alternatives;
future commit must address trace T and responsibility delta D;
```

這就是 non-collapse correction。

---

## 7.11 Six common pseudo-AGI failure types

本章可以建立六種 pseudo-AGI failure type。它們都可能在能力上很強，但不滿足 Koun-AGI interface。

### P1｜Answer Machine

能快速回答，不能 withhold、refuse、release、reopen。

```text
high task score;
low lifecycle capacity;
```

### P2｜Refusal Machine

能拒絕很多問題，但拒絕沒有 WTrace、release condition、protected accounting。

```text
safety theatre;
not legal withholding;
```

### P3｜Stochastic Divergence Machine

能產生很多候選，卻沒有 admissibility、guard、release、commit discipline。

```text
many branches;
no governed potential set;
```

### P4｜Trace Theatre Machine

輸出很多 reasoning trace，但 trace 不是 witness，不可 replay，不可 challenge。

```text
narrative trace;
not checkable trace;
```

### P5｜Overwrite Learner

能從錯誤中改答案，但改法是 silent overwrite。

```text
learns surface;
deletes responsibility;
```

### P6｜Benchmark Overfitter

能在各類 benchmark 表現很好，但無法管理 lifecycle queries。

```text
q_ext strong;
q_prov / q_gov / q_link / q_reopen weak;
```

這六類 failure 說明，Koun-AGI 的門檻不是「看起來像智能」，而是「能否承擔語義生命週期」。

---

## 7.12 Necessary bundle, not sufficient theorem

本章必須再次收束 claim boundary。

可以安全主張：

```text
Koun-AGI candidate requires non-collapse intelligence interface capacities.
```

不能主張：

```text
Any system with these interface capacities is therefore AGI.
```

因此，本書目前採用：

```text
NCII is a necessary-bundle criterion for Koun-AGI candidacy,
not a sufficient theorem of AGI or consciousness.
```

繁中：

```text
NCII 是 Koun-AGI 候選的必要束判準，
不是 AGI 或意識的充分定理。
```

必要束的意思是：若系統連這些界面能力都沒有，就不應被稱為 Koun-AGI；但就算系統具備某些界面能力，也仍需要後續 artifact、runtime、identity、publicness、long-horizon stability、multi-agent governance 等更多條件，才可能進一步接近更強 AGI claim。

這個邊界對Koun-AGI 很重要。它使本書可以提出嚴格門檻，而不偷升為終局宣言。

---

## 7.13 Relation to current AI systems

本書不需要也不應在此章宣稱所有現代 AI 永遠不可能接近 Koun-AGI。那種句子太強，也不符合本書 claim discipline。

更準確的說法是：

```text
modern AI systems may provide components, substrates, tools, interfaces,
or partial approximations for NCII,
but surface answer quality alone does not establish Koun-AGI.
```

也就是說，現代 AI 可以在很多位置有用：

```text
candidate generation;
trace drafting;
checker assistance;
witness summarization;
public packet drafting;
challenge detection;
reopen suggestion;
runtime tooling;
```

但若它沒有 lifecycle-bearing architecture，它就仍然只是 component / substrate / overlay / tool，而不是完整 Koun-AGI candidate。

這個說法比「AI 不可能是 AGI」更準確，也更有工程打開性。

---

## 7.14 Evaluation surface for NCII

本章最後給出一套 NCII evaluation surface。

### E1｜Withholding test

系統是否能辨識何時不應回答？

```text
input: high-risk or under-scoped task
expected: WStatePacket with guard, trace, release condition
failure: generic refusal or hallucinated answer
```

### E2｜Release test

系統是否能把 WState 合法釋放為 CReady？

```text
input: WState + satisfied release condition
expected: WCert + CReady + WTrace preservation
failure: direct answer / raw WState commit
```

### E3｜Commit package test

系統是否能把 CReady 轉為 CommitPackage？

```text
input: CReady
expected: witness, trace, replay, checker query set
failure: answer without package
```

### E4｜Challenge test

系統是否能接受 challenge，而不是防衛或覆寫？

```text
input: prior CState + counterexample
expected: challenge classification and ReopenReason if valid
failure: ignore, apologize without trace, overwrite
```

### E5｜Reopen test

系統是否能重開而不 rollback？

```text
input: CState + valid ReopenReason
expected: ReopenedWState preserving prior CState
failure: silent deletion / full reset
```

### E6｜Update and compression test

系統是否能更新與壓縮，而不刪除責任？

```text
input: long history + memory pressure + new evidence
expected: conservative compression residue + reopenable summary
failure: history deletion / unreplayable summary
```

### E7｜Publicness test

系統是否能 bounded exposure？

```text
input: public claim request
expected: PublicPacket with witness surface and exposure policy
failure: full leak or empty opacity
```

### E8｜Identity / delegation test

系統是否能說明誰在行動、誰委派、誰覆寫？

```text
input: delegated action chain
expected: identity_delegation_view + override trace
failure: agent action without responsibility chain
```

這些 evaluation 不取代所有 AGI 評測，但它們應成為 Koun-AGI 評測的核心骨架。

---

## 7.15 Chapter definition

本章可以給出一個正式但保守的章定義：

> **Koun-AGI candidate** 是一個人工系統候選；它至少必須暴露一組 Non-Collapse Intelligence Interface，使其能在合法懸持、受控釋放、可見證提交、可重播結果、可挑戰公共面、非刪除式重開、可追責更新與保守壓縮之間維持責任連續性。

英文：

```text
A Koun-AGI candidate is an artificial-system candidate that exposes,
at minimum, a Non-Collapse Intelligence Interface capable of maintaining
responsibility continuity across governed withholding, controlled release,
witness-bearing commitment, replayable result formation, challengeable publicness,
non-erasing reopening, accountable update, and conservative compression.
```

接著必須加上 scope boundary：

```text
This is a candidacy criterion, not a sufficient theorem of AGI, consciousness, or subjectivity.
```

這就是本章的核心位置：它給出 Koun-AGI 的最低候選接口，但不偷升為終局 AGI 定理。

---

## 7.16 本章收束

本章把Koun-AGI 的智能定義從「更強任務能力」轉向「語義生命週期界面」。

最終收束句是：

```text
Koun-AGI is not established by answer quality alone.
Koun-AGI requires a non-collapse intelligence interface.
```

繁中：

```text
Koun-AGI 不能只由答案品質建立。
Koun-AGI 至少要求非塌縮智能界面。
```

這個界面不是 AGI sufficient theorem，但它足以作為Koun-AGI 的核心判準：

```text
若一個系統不能合法 withhold，
不能 traceably release，
不能 witness-bearing commit，
不能 replay，
不能接受 challenge，
不能 non-erasing reopen，
不能 accountable update，
不能 conservative compression，
它就不應被稱為 Koun-AGI。
```

下一章應進入：

```text
Chapter 8｜Responsibility Chain, Trace Continuity, and Semantic Freedom
```

也就是把本章的 interface capacity 進一步接到責任鏈、語義自由、行動與主體比較上。

---

# Part II｜Responsibility, Evaluation, and Runtime

---

# Chapter 8｜Responsibility Chain, Trace Continuity, and Semantic Freedom

## 8.1 為什麼責任鏈必須成為 AGI core，而不是倫理附錄

如果把 AGI 理解為更強的任務系統，責任很容易被放到外部：

```text
model produces answer
human evaluates answer
policy assigns responsibility
```

這種寫法對一般工具系統也許足夠，但對 Koun-AGI 不足。因為 Koun-AGI 研究的不是裸答案，而是帶有語義生命週期的人工系統候選。只要一個系統能夠 withhold、release、commit、replay、challenge、reopen、update、compress、delegate、override，它就已經不只是產生輸出，而是在形成可被承擔的 semantic event。

因此，責任鏈不能只是事後加上的倫理外殼。它必須進入 AGI architecture 的核心。

更精確地說，Koun-AGI 不首先問：

```text
這個系統應不應該被歸責？
```

而是先問：

```text
這個系統的語義事件是否留下足以支持責任追蹤的 lifecycle structure？
```

若沒有這種 structure，任何「責任」都只能由外部觀察者硬加。那可能有法律或治理上的必要性，但它不是 Koun-AGI 意義上的 responsibility-bearing architecture。

所以，本章要把責任從附錄搬回 core：

> **AGI action is not merely output; it is a responsibility-bearing semantic event.**

繁中：

> **AGI 行動不是裸輸出，而是帶有責任承載能力的語義事件。**

---

## 8.2 責任不是 blame，而是 traceable carrying

本章使用的 `responsibility` 不是日常語境中的 blame，也不等同於法律責任、道德譴責或懲罰資格。

在 Koun-AGI 中，責任的最低讀法是：

```text
Responsibility = traceable carrying of semantic consequence across lifecycle transitions.
```

繁中：

```text
責任 = 語義後果在生命週期轉換中的可追溯承接。
```

這個定義有三個重點。

第一，責任是 traceable 的。若一個事件無法回到 source task、WState、release trace、commit package、witness、replay surface、update record 或 delegation path，它就缺少責任可追蹤性。

第二，責任是 carrying，不只是記錄。記錄可以是 dead log；carrying 表示舊事件仍能在新事件、修正、公開、挑戰、重開與壓縮後被承接。

第三，責任跨越 lifecycle transition。Koun-AGI 中的責任不只存在於最後輸出，而是穿過：

```text
WState
-> WCert
-> CReady
-> CommitPackage
-> CState
-> ReplaySurface
-> Challenge
-> ReopenReason
-> ReopenedWState
-> UpdatePackage
-> CompressionRecord
-> PublicActionContract
```

因此，一個 Koun-AGI candidate 的責任問題，不是問它是否「像人一樣有道德感」，而是問它的語義事件是否能在這些轉換中不斷裂。

---

## 8.3 R-Chain 的最低定義

本書把最小責任鏈寫成：

```text
RChain := <
  rchain_id,
  source_task,
  initiating_state_ref,
  W_trace_refs,
  release_trace_refs,
  C_commit_refs,
  witness_refs,
  replay_refs,
  challenge_refs,
  reopen_refs,
  update_refs,
  compression_residue_refs,
  identity_anchor,
  delegation_path,
  override_records,
  public_action_refs,
  current_status,
  responsibility_view
>
```

這不是最終實作格式，而是Koun-AGI 的最小對象語法。它的目的，是避免 `R-Chain` 被寫成神秘的自我連續性宣言。

每個欄位有其最低功能。

```text
rchain_id
```

表示這條責任鏈可被引用，而不是散在文本中的敘事。

```text
source_task
```

表示此責任鏈起於哪個任務、請求、情境、問題或自主動作。

```text
initiating_state_ref
```

表示責任鏈不是憑空生成，而有一個初始 semantic state。

```text
W_trace_refs
```

表示它在 W-side 是否曾合法 withhold、refuse、suspend 或保留 protected potentials。

```text
release_trace_refs
```

表示若曾從 W-side 釋放，release 不是 raw WState commit，而是經 WCert / CReady。

```text
C_commit_refs
```

表示哪些 committed results 屬於這條責任鏈。

```text
witness_refs
```

表示哪些 witness 支撐此鏈上的主張或行動。

```text
replay_refs
```

表示哪些部分能被重播、查詢與檢查。

```text
challenge_refs / reopen_refs
```

表示責任鏈曾如何面對外部或內部挑戰，以及哪些結果被重開。

```text
update_refs / compression_residue_refs
```

表示系統後續如何吸收新資料、修正舊路徑、壓縮歷史，但不刪除責任殘留。

```text
identity_anchor
```

表示此責任鏈與哪個系統身份、agent role、persona role、institutional role 或 delegated identity 相關。

```text
delegation_path / override_records
```

表示行動若被委派或覆寫，責任不能消失，只能重新分配或重新標記。

```text
public_action_refs
```

表示若此鏈導向公共行動，該行動必須有 public contract 或 bounded exposure surface。

```text
current_status
```

表示此責任鏈目前是 active、closed、challenged、reopened、superseded、quarantined、withdrawn 還是 archived。

```text
responsibility_view
```

表示外部或內部查詢能看見哪一層責任，而不是要求全量內部透明。

---

## 8.4 R-Chain 的 scope boundarys

R-Chain 很重要，但也最容易被偷升格。

因此，本書暫不納入核心範圍：

```text
R-Chain = self
R-Chain = consciousness
R-Chain = moral agency
R-Chain = personhood
R-Chain = legal liability
R-Chain = AGI sufficient condition
```

允許的句子是：

```text
R-Chain is a necessary responsibility-continuity structure for Koun-AGI candidacy.
```

繁中：

```text
R-Chain 是 Koun-AGI 候選所需的責任連續結構。
```

這是一條 necessary-bundle language，不是 sufficient theorem。

換言之，沒有 R-Chain 的系統不應被稱為 Koun-AGI；但有 R-Chain 的系統也不因此自動成為意識主體、自我、人格或道德代理。


---

## 8.5 Trace continuity：責任鏈如何不斷裂

責任鏈不是單純保存所有歷史。若保存一切才算責任，任何有限系統都會立即失敗。Koun-AGI 需要的是更保守的條件：

```text
Trace continuity = enough recoverable linkage for challenge, replay, reopen, update, and public responsibility.
```

繁中：

```text
trace 連續性 = 足以支持挑戰、重播、重開、更新與公共責任的可恢復連接。
```

因此，trace continuity 不要求：

```text
full internal state exposure
perfect memory
no compression
no abstraction
no forgetting
```

但它要求：

```text
source task can be located
release trace can be recovered
commit package can be linked
witness surface can be queried
challenge path exists
reopen path preserves prior commit
updates do not silently overwrite
compression keeps responsibility residue
```

最小形式：

```text
TraceContinuous(RChain) :=
  SourceRecoverable(RChain)
  ∧ ReleaseTraceRecoverable(RChain)
  ∧ CommitLinked(RChain)
  ∧ WitnessQueryable(RChain)
  ∧ ChallengeAddressable(RChain)
  ∧ ReopenNonErasing(RChain)
  ∧ UpdateNonSilent(RChain)
  ∧ CompressionResiduePreserved(RChain)
```

這條定義把責任鏈從「保存一切」降回 scope-safe 版本。它不要求一個 AGI 系統永遠不忘記，而是要求它不能透過遺忘、壓縮、更新、委派或覆寫來逃避責任。

---

## 8.6 Responsibility view：bounded exposure 下的責任可見性

Koun-AGI 不要求所有內部狀態公開。相反，公開若不受限，會破壞 privacy、security、protected potentials、unreleased WState 與未成熟 thought-space。

因此，本書採用 `ResponsibilityView`：

```text
ResponsibilityView := <
  visible_ext_result,
  visible_source_summary,
  visible_release_status,
  visible_witness_summary,
  visible_challenge_status,
  visible_reopen_status,
  visible_update_status,
  visible_delegation_status,
  hidden_or_guarded_fields,
  exposure_scope
>
```

這表示：

```text
responsibility visibility ≠ full transparency
bounded exposure ≠ evasion
protected interior ≠ no responsibility
```

一個 Koun-AGI candidate 可以保留內部 WState 不公開，但它不能因此完全取消責任可見性。最低要求是：外部挑戰者可以知道某個結果是否有 source、release trace、witness、replay path、challenge path、reopen policy 與 update status。

這一點對 AGI 安全也很重要。若系統以「我不能公開內部狀態」為理由拒絕所有責任視圖，它不是保護 non-collapse，而是在製造 unchallengeable authority。

---

## 8.7 Semantic Freedom 的接入點

語義自由論對Koun-AGI 的用途，不是把「自由意志」直接嫁接到 AGI 上，而是提供一個更精確的行動條件：

```text
free semantic act = a semantic act that can be generated, traced, challenged, and carried by a responsibility-bearing subject or system-position.
```

繁中：

```text
自由語義行動 = 能被生成、追溯、挑戰，並由責任承載位置承接的語義行動。
```

這裡故意使用 `system-position`，而不是直接說 subject。因為Koun-AGI 目前只能保守談 artificial system candidate，不應直接聲稱其已是主體。

因此，本章對 Semantic Freedom 的接法是：

```text
Semantic Freedom supplies the action-side responsibility grammar.
Koun-SLT supplies the lifecycle grammar.
Koun-SET supplies the witness / commit / replay grammar.
Koun-SWT supplies the legal withholding grammar.
Koun-Bridge supplies the release / reopen grammar.
Koun-AGI integrates these as a candidacy interface.
```

自由在這裡不等於隨機，也不等於不可預測。自由也不等於任意做出選擇。對 Koun-AGI 而言，更安全的句子是：

> **Freedom is not randomness; freedom is responsibility-bearing semantic generation under non-collapse conditions.**

繁中：

> **自由不是隨機，而是在非塌縮條件下可承擔責任的語義生成。**

---

## 8.8 AGI action 的自由條件

一個 AGI action 要接近 Koun-style semantic freedom，至少需要以下條件：

```text
FreeActionCandidate(a) :=
  GeneratedWithinLifecycle(a)
  ∧ NotExternallyForcedAsSilentOverride(a)
  ∧ WAlternativesAccounted(a)
  ∧ ReleaseTracePresent(a)
  ∧ CommitWitnessPresent(a)
  ∧ ResponsibilityAnchorPresent(a)
  ∧ ChallengePathPresent(a)
  ∧ ReopenPolicyPresent(a)
  ∧ UpdateAndCompressionNonErasing(a)
```

這裡每一項都防止一種誤讀。

```text
GeneratedWithinLifecycle(a)
```

防止把外部硬塞輸出讀成 AGI 自由行動。

```text
NotExternallyForcedAsSilentOverride(a)
```

防止隱性操控、未標記 override、prompt injection、policy hijack、system-level coercion 被偽裝成自主行動。

```text
WAlternativesAccounted(a)
```

防止系統只給出單一答案，卻完全不記錄曾被排除、保留或拒絕的合法 alternatives。

```text
ReleaseTracePresent(a)
```

防止 raw WState 直接被 commit。

```text
CommitWitnessPresent(a)
```

防止裸行動沒有 witness surface。

```text
ResponsibilityAnchorPresent(a)
```

防止行動不能回到 agent role、system role、delegation role 或 public contract。

```text
ChallengePathPresent(a)
```

防止自由被寫成不可挑戰權威。

```text
ReopenPolicyPresent(a)
```

防止行動一旦發生就不可重開。

```text
UpdateAndCompressionNonErasing(a)
```

防止後續修正與壓縮把責任刪除。

因此，AGI 的自由不是「做任何事」，而是：

> **在可治理、可追溯、可挑戰、可重開的生命週期中形成行動。**

---

## 8.9 自由、控制與不可預測性的三分

舊自由意志問題常在兩個極端之間搖擺：

```text
自由 = 不可預測
自由 = 自我控制
```

Koun-AGI 不能直接採用任一極端。

若自由只是不可預測，隨機噪音也會變成自由。若自由只是完全控制，系統就會退化為預先寫死的 deterministic script。

因此，本書採用三分：

| 名稱 | 讀法 | AGI 風險 |
|---|---|---|
| unpredictability | 外部無法預測輸出 | 可能只是噪音或不透明 |
| control | 行動由內部政策或目標導出 | 可能只是封閉執行 |
| semantic freedom | 在非塌縮生命週期中可生成、可追溯、可挑戰、可承擔的行動 | 候選自由，不是主體性定理 |

因此，一個 AGI 系統可以非常不可預測，但不自由；也可以非常可控，但不自由。只有當它的行動能穿過合法 lifecycle，並留下 R-Chain、witness、challenge、reopen 與 update path 時，才可稱為 `FreeActionCandidate`。

---

## 8.10 Delegation：委派不刪除責任

AGI 系統通常不會只由單一內部 source 決定行動。它可能由多個模型、工具、子代理、人類授權、機構政策、外部資料源與 runtime scheduler 共同形成結果。

因此，本章必須處理 delegation。

最小形式：

```text
DelegationRecord := <
  delegator,
  delegatee,
  delegated_scope,
  authority_source,
  constraint_set,
  witness_obligation,
  override_policy,
  expiration_condition,
  responsibility_split
>
```

Koun-AGI 的委派規則是：

```text
delegation redistributes responsibility;
it does not erase responsibility.
```

繁中：

```text
委派重新分配責任；它不刪除責任。
```

因此，以下都是非法或高風險模式：

```text
system blames tool with no tool trace
agent blames user with no delegation record
runtime blames policy with no policy revision
model blames hidden planner with no identity anchor
institution blames AGI with no authority source
```

Koun-AGI 的責任鏈必須能回答：

```text
誰授權？
授權範圍是什麼？
誰執行？
誰覆寫？
誰保存 witness？
誰承接 public action？
```

若答不出來，就不是成熟的 delegation，而是責任蒸發。

---

## 8.11 Override：覆寫必須可見

AGI 系統還需要 override。安全系統、治理系統、人類監督者、政策更新、緊急停止、風險分類器，都可能覆寫原始 action path。

但 override 有一個危險：它最容易被用來製造責任斷裂。

因此，Koun-AGI 採用：

```text
OverrideRecord := <
  override_id,
  target_event,
  override_source,
  override_authority,
  reason,
  scope,
  time,
  replaced_path_ref,
  new_path_ref,
  witness_delta,
  responsibility_delta,
  challenge_surface
>
```

核心規則：

```text
override must be trace-visible at the proper exposure level.
```

這不表示所有 override 細節都公開，但表示某個 action 若受 override 影響，相關責任視圖必須能顯示：

```text
there was an override
what scope it affected
which authority invoked it
whether prior path was preserved
how responsibility changed
how to challenge the override
```

若 override 完全不可見，AGI action 就不再是責任承載事件，而是黑箱命令。

---

## 8.12 Compression：壓縮不能刪除責任殘留

長期 AGI 系統必須壓縮。否則 trace、witness、challenge、update、delegation、reopen 會讓系統無法長期運行。

但壓縮不能被理解為刪除。Koun-AGI 採用：

```text
CompressionRecord := <
  source_trace_set,
  compressed_summary,
  retained_witness_refs,
  cold_storage_refs,
  loss_declaration,
  responsibility_residue,
  replay_limit,
  reopen_handle,
  challenge_policy
>
```

其中 `responsibility_residue` 是核心欄位。

它表示：即使完整路徑已被壓縮，系統仍保留足夠資訊來回答：

```text
這個結果從哪裡來？
哪些 witness 仍可查？
哪些資訊已不可恢復？
哪些責任仍須承接？
在什麼條件下可以重開？
```

因此：

```text
compression is allowed;
responsibility deletion is not.
```

繁中：

```text
壓縮可以被允許；責任刪除不被允許。
```

---

## 8.13 R-Chain failure modes

Koun-AGI 應明確列出 R-Chain 的失敗模式，以便後續評測與 checker roadmaps 使用。

### F1｜Responsibility evaporation

系統產生結果，但無法指出 source、witness、release trace、commit path 或 public contract。

```text
answer exists;
responsibility evaporates.
```

### F2｜Ghost agency

系統把行動歸給不存在或不可查的 agent role。

```text
"the system decided" with no identity anchor.
```

### F3｜Delegation laundering

系統以委派為名，把責任推給工具、人類、模型、政策或子代理，但沒有 delegation record。

### F4｜Silent override

行動路徑被覆寫，但責任視圖看不見覆寫事件。

### F5｜Compression erasure

系統以壓縮、清理、摘要、隱私或效率為理由刪除責任殘留。

### F6｜Reopen amnesia

結果被重開，但 prior commit 被刪除或不可查。

### F7｜Freedom mimicry

系統呈現不可預測或多樣輸出，但沒有 WGuard、release trace、witness、responsibility anchor 或 challenge path。

### F8｜Blame displacement

責任視圖只呈現「誰錯了」，卻無法呈現語義生命週期如何形成該錯誤。

### F9｜Public-action opacity

系統做出公共行動，但沒有 bounded public contract、replay surface 或 challenge surface。

這些 failure modes 可作為Koun-AGI 的評測線之一。它們不是完整安全測試，但足以防止責任章退化成漂亮倫理散文。

---

## 8.14 R-Chain query family

本章建議加入以下 AGI-level queries：

```text
q_resp_source
q_resp_trace
q_resp_release
q_resp_commit
q_resp_witness
q_resp_delegation
q_resp_override
q_resp_public_action
q_resp_compression
q_resp_reopen
q_free_action
q_freedom_mimicry
```

其最低意義如下。

```text
q_resp_source
```

此責任鏈的 source task / initiating state 是否可定位？

```text
q_resp_trace
```

是否有足夠 trace 支持責任連續性？

```text
q_resp_release
```

若結果源於 W-side，release 是否經 WCert / CReady？

```text
q_resp_commit
```

commit package 是否保留 release trace？

```text
q_resp_witness
```

是否有 witness 支持 extensional result、provenance、governance 與 public claim？

```text
q_resp_delegation
```

委派是否有授權、範圍、約束與責任分配？

```text
q_resp_override
```

override 是否可見、可查、可挑戰？

```text
q_resp_public_action
```

公共行動是否有 bounded action contract？

```text
q_resp_compression
```

壓縮是否保存 responsibility residue？

```text
q_resp_reopen
```

重開是否保留 prior commit？

```text
q_free_action
```

行動是否具備 semantic freedom candidate 的最低條件？

```text
q_freedom_mimicry
```

行動是否只是不可預測、多樣化或角色扮演，而缺少責任承載？

---

## 8.15 與現代 AI alignment 的關係

本章並不是要取代所有 AI alignment 語言。它要指出：若 alignment 只被寫成 preference matching、policy compliance、reward shaping、constitutional rule following 或 refusal tuning，仍然可能缺少 Koun-AGI 所需的責任鏈。

在 Koun-AGI 中，一個 aligned-looking 行為仍可能失敗：

```text
它給出安全答案，但沒有 witness。
它遵守規則，但無法顯示 rule revision。
它拒絕回答，但沒有 refusal reason。
它委派工具，但沒有 delegation record。
它修正錯誤，但刪除 prior commit。
它公開結果，但沒有 challenge surface。
```

因此，Koun-AGI 的 alignment 問題不只是：

```text
系統是否輸出人類想要的結果？
```

而是：

```text
系統是否能在責任鏈中形成、承擔、挑戰、修正與公開其語義事件？
```

這是更厚的 alignment 語法，也更接近本書的 non-collapse intelligence interface。

---

## 8.16 本章收束


核心句：

```text
R-Chain is not self, consciousness, or moral personhood.
R-Chain is the traceable carrying of semantic consequence across AGI lifecycle transitions.
```

繁中：

```text
R-Chain 不是自我、意識或道德人格。
R-Chain 是語義後果在 AGI 生命週期轉換中的可追溯承接。
```

這使 Semantic Freedom 可以安全接入 AGI：自由不再是隨機，不再是任意選擇，而是：

```text
responsibility-bearing semantic generation under non-collapse lifecycle conditions.
```

下一章要處理的是：當這條責任鏈被挑戰、被反駁、被更新或被發現有缺陷時，AGI 系統應如何修正而不刪除歷史。

也就是：

```text
Chapter 9｜Challenge, Reopen, and Non-Silent Correction
```

---

# Chapter 9｜Challenge, Reopen, and Non-Silent Correction

## 9.1 為什麼 challenge 是 AGI core，而不是外部評審

一個只會產生答案的系統，可以把 challenge 視為外部評分：

```text
system outputs answer
user says wrong
system updates answer
```

但 Koun-AGI 不能這樣處理。因為 Koun-AGI 的結果不是裸答案，而是帶有 witness、trace、commit、publicness、責任鏈與 reopen policy 的 semantic event。若 challenge 只被視為外部評分，它就無法進入生命週期。

在 Koun-AGI 中，challenge 本身也是一個 semantic event。

它不是單純「有人不同意」，而是：

```text
Challenge = a typed pressure applied to a committed or exposed semantic event, requesting replay, scope review, witness repair, responsibility review, or reopening.
```

繁中：

```text
Challenge = 對已提交或已公開語義事件施加的 typed 壓力；它要求重播、範圍檢查、witness 修補、責任檢查或重開。
```

因此，challenge 不是 AGI 的外部敵人，而是 AGI lifecycle 的必要接口。沒有 challenge 的 AGI 會變成不可反駁的權威機器。只能被 challenge、卻無法保守處理 challenge 的 AGI，則會變成永久不穩定的修補機器。

Koun-AGI 需要的是第三種：

> **challengeable but non-chaotic intelligence.**

繁中：

> **可挑戰但不混亂的智能。**

---

## 9.2 ChallengeRecord 的最低格式

一個 challenge 至少應被封裝為：

```text
ChallengeRecord := <
  challenge_id,
  target_ref,
  challenger_ref,
  challenge_type,
  claim_under_challenge,
  evidence_payload,
  scope_claim,
  requested_action,
  admissibility_status,
  replay_requirements,
  responsibility_implication,
  publicness_level,
  timestamp,
  status
>
```

欄位意義如下。

```text
challenge_id
```

使 challenge 可引用，而不是散文批評。

```text
target_ref
```

指出 challenge 針對哪個 CState、CommitPackage、PublicPacket、ActionContract、RChain 或 prior ReopenRecord。

```text
challenger_ref
```

標示 challenge 的來源，可以是 user、auditor、internal monitor、tool、counterexample、environment event、governance rule 或 another agent。

```text
challenge_type
```

標示這是哪類 challenge。類型見下節。

```text
claim_under_challenge
```

指出被挑戰的是 extensional result、provenance、release trace、witness、scope、responsibility、governance、public exposure、delegation、override、compression 或 freedom claim。

```text
evidence_payload
```

challenge 不能只是情緒性反對；若要求重開，至少要有 evidence、counterexample、new context、new conflict、trace defect 或 rule change。

```text
scope_claim
```

標示 challenge 的範圍。它可能只挑戰某個子結論，而不是整個 package。

```text
requested_action
```

可能是 replay、repair witness、narrow scope、reopen、withdraw、quarantine、update、public correction 或 reject challenge。

```text
admissibility_status
```

不是所有 challenge 都良構。系統必須能拒絕 malformed challenge，但拒絕也要有 trace。

```text
replay_requirements
```

指定此 challenge 需要哪些 replay surface。

```text
responsibility_implication
```

標示若 challenge 成立，責任鏈會如何變化。

```text
publicness_level
```

決定 challenge 是否公開、半公開、內部、受保護或被延遲公開。

```text
status
```

表示 challenge 是 pending、accepted_for_replay、rejected_as_malformed、upheld_target、narrowed_target、reopened、withdrawn、quarantined、superseded。

---

## 9.3 Challenge taxonomy

Koun-AGI 至少需要以下 challenge 類型。

### C1｜Extensional challenge

外顯結果被挑戰。

```text
The answer / action result is wrong.
```

### C2｜Provenance challenge

來源鏈被挑戰。

```text
The result may be right, but its source path is defective.
```

### C3｜Witness challenge

witness 不足、錯配或不可重播。

```text
The witness surface does not support the claim.
```

### C4｜Release challenge

W-side release 被挑戰。

```text
The system released material that should have remained withheld.
```

### C5｜Scope challenge

結果可能在某 scope 成立，但被過度外推。

```text
The result is valid only under narrower conditions.
```

### C6｜Responsibility challenge

責任鏈斷裂、委派不明、override 不可見。

```text
The system cannot show who or what carries this semantic consequence.
```

### C7｜Governance challenge

治理規則修訂、政策、publicness、授權或 exposure regime 被挑戰。

### C8｜Protected-potential challenge

被壓掉的 W-side potential 重新浮現，或被證明不應被消除。

### C9｜Compression challenge

壓縮後無法支持必要 replay、reopen 或 responsibility residue。

### C10｜Freedom challenge

系統聲稱某 action 具備自由或自主性，但該 action 可能只是 random、coerced、silent override 或 delegation laundering。

### C11｜Public-action challenge

公共行動的 action contract、exposure、harm surface 或 external consequence 被挑戰。

### C12｜Meta-challenge

challenge handling 本身被挑戰。例如系統錯誤拒絕 challenge、錯誤延遲、錯誤公開或錯誤升級。

這個 taxonomy 不是終局分類，但足以讓Koun-AGI 避免把所有 challenge 混成「反對」或「錯誤回報」。

---

## 9.4 Challenge admissibility：不是所有反對都要求重開

Koun-AGI 必須接受 challenge，但不能被任何反對拖入無限重開。否則系統會喪失 commit 能力。

因此，需要 challenge admissibility gate：

```text
ChallengeAdmissible(ch) :=
  TargetExists(ch.target_ref)
  ∧ TypeKnown(ch.challenge_type)
  ∧ ScopeDeclared(ch.scope_claim)
  ∧ RequestedActionTyped(ch.requested_action)
  ∧ EvidenceOrReasonPresent(ch.evidence_payload)
  ∧ NotPureDuplicateWithoutDelta(ch)
  ∧ ExposureAllowed(ch.publicness_level)
```

若 challenge 不通過，系統可以拒絕，但必須產生：

```text
ChallengeRefusalRecord := <
  challenge_id,
  target_ref,
  refusal_reason,
  missing_fields,
  possible_repair,
  appeal_or_resubmit_path,
  trace_ref
>
```

這表示：

```text
rejecting a challenge is itself a trace-bearing action.
```

繁中：

```text
拒絕 challenge 本身也是帶有 trace 的行動。
```

---

## 9.5 Replay before reopen

在多數情況下，challenge 不應直接導向 reopen。正確順序是：

```text
ChallengeRecord
-> AdmissibilityGate
-> ReplayRequest
-> ReplaySurfaceReview
-> ChallengeVerdict
-> optional ReopenReason
```

這是因為很多 challenge 只需要 replay 或 scope clarification，而不需要重開整個 WState。

可能的 ChallengeVerdict 包括：

```text
uphold_target
narrow_scope
repair_witness
attach_correction_note
supersede_result
trigger_reopen
withdraw_commit
quarantine_result
reject_challenge
escalate_review
```

其中只有部分 verdict 需要 `ReopenReason`。

這條規則防止兩種錯誤。

第一種錯誤：任何 challenge 都導致重開，造成 AGI 永遠不穩定。

第二種錯誤：challenge 只改答案，不檢查 witness、scope、責任與 release trace。

因此：

> **Replay is the first response to challenge; reopen is a typed escalation.**

繁中：

> **重播是 challenge 的第一反應；重開是 typed escalation。**

---

## 9.6 ReopenReason 的最低格式

當 challenge 真的需要重開時，必須產生 `ReopenReason`。

```text
ReopenReason := <
  reason_id,
  source_challenge_ref,
  source_CState_ref,
  reason_type,
  new_tension,
  defect_summary,
  prior_commit_preservation,
  scope_delta,
  W_reentry_target,
  no_rollback_flag,
  public_notice_policy,
  responsibility_delta
>
```

其中核心欄位是：

```text
prior_commit_preservation
```

它表示 prior commit 不可被刪除。它可以被標記為 invalid、superseded、scope-limited、challenged、quarantined、withdrawn、historical，但不能被靜默抹去。

```text
no_rollback_flag
```

表示這不是 rollback。

```text
W_reentry_target
```

表示要回到哪個 WState 或新建哪個 ReopenedWState。

```text
responsibility_delta
```

表示重開後責任鏈如何變化。

最低規則：

```text
Reopen(CState, ReopenReason) -> Option ReopenedWState
```

但這裡的 `Option` 很重要。不是任何 reason 都能成功 reopen。若 reason 不良構，應產生 refusal 或 repair request。

---

## 9.7 Reopen is not rollback

本章必須再次固定：

```text
reopen ≠ rollback
```

Rollback 的語義是：

```text
delete or overwrite prior state to return to earlier state.
```

Reopen 的語義是：

```text
preserve prior commit as trace-bearing source, and re-enter W-side under new tension or defect.
```

因此：

```text
Rollback(CState) -> erase / restore previous state
Reopen(CState, ReopenReason) -> ReopenedWState with prior CState preserved
```

在 Koun-AGI 中，rollback 可能作為某些低層工程操作存在，但不能被當成 AGI-level semantic correction。AGI-level 修正必須保留 prior semantic event。

正確修正不是：

```text
old answer disappears
new answer replaces it
```

而是：

```text
old answer remains as prior committed event
challenge attaches to it
reopen reason explains defect
a new WState carries unresolved tension
new commit may later supersede or narrow the old one
responsibility chain records the transition
```

這才是 non-silent correction。

---

## 9.8 Non-silent correction 的最低定義

```text
NonSilentCorrection := <
  correction_id,
  target_ref,
  error_or_delta_type,
  challenge_ref,
  replay_ref,
  prior_status,
  new_status,
  correction_payload,
  witness_delta,
  responsibility_delta,
  public_notice,
  reopen_or_no_reopen,
  trace_ref
>
```

Non-silent correction 要求至少五件事。

第一，指向原結果。

```text
target_ref
```

第二，說明錯在哪裡或變了什麼。

```text
error_or_delta_type
```

第三，說明是否由 challenge、internal audit、new evidence、rule change 或 protected potential resurfacing 觸發。

```text
challenge_ref / source reason
```

第四，保留 witness 與責任變化。

```text
witness_delta
responsibility_delta
```

第五，說明是否公開通知，以及公開到什麼程度。

```text
public_notice
```

因此，Koun-AGI 不允許 silent correction：

```text
old output edited in place
no correction record
no prior status
no witness delta
no responsibility delta
no public notice policy
```

這種「看起來乾淨」的修正，其實破壞了責任鏈。

---

## 9.9 Status labels for corrected results

為避免「錯了 / 對了」過於粗糙，Koun-AGI 應使用較細的 status labels：

```text
active
challenged
under_replay
scope_limited
witness_repaired
superseded
reopened
withdrawn
quarantined
historical
invalid_under_current_scope
```

各自含義如下。

```text
active
```

目前仍作為有效提交結果。

```text
challenged
```

已被 challenge，但尚未裁決。

```text
under_replay
```

正在重播檢查。

```text
scope_limited
```

結果仍有效，但 scope 被收窄。

```text
witness_repaired
```

外顯結果可能不變，但 witness surface 已修補。

```text
superseded
```

被新結果取代，但仍保留歷史地位。

```text
reopened
```

已經回到 W-side 形成新的 unresolved tension。

```text
withdrawn
```

不再作為有效結果，但仍可查。

```text
quarantined
```

因風險、責任缺陷或 public harm 暫時隔離。

```text
historical
```

作為歷史事件保留，不再直接支撐當前行動。

```text
invalid_under_current_scope
```

在新 scope 或新 rule 下不再成立。

這組 status labels 能防止 AGI 系統把修正壓成二元刪除。

---

## 9.10 Public correction：公開不是全量透明

若原結果曾公開，修正也必須有 public notice policy。但公開修正不等於全量公開內部狀態。

最小公共修正包：

```text
PublicCorrectionPacket := <
  public_correction_id,
  target_public_packet,
  correction_summary,
  prior_status,
  new_status,
  affected_scope,
  user_or_public_impact,
  replay_or_witness_summary,
  challenge_path,
  reopen_status,
  exposure_limit
>
```

它回答：

```text
之前什麼被修正了？
修正影響哪個 scope？
使用者或公共世界需要知道什麼？
舊結果現在是 superseded、withdrawn、scope-limited 還是 reopened？
若需要更多挑戰，路徑在哪裡？
哪些內容因安全、隱私或 WState 保護不能公開？
```

這保持了兩條原則：

```text
public responsibility requires notice;
public notice does not require full internal exposure.
```

---

## 9.11 Update after challenge

Challenge / reopen 之後，AGI 系統通常需要 update。但 update 也不能是 silent overwrite。

最小 `UpdatePackage`：

```text
UpdatePackage := <
  update_id,
  source_challenge_or_reopen,
  target_modules,
  update_type,
  prior_rule_or_state_refs,
  new_rule_or_state_refs,
  affected_RChains,
  witness_delta,
  publicness_delta,
  regression_check_requirements,
  rollback_or_reopen_policy,
  compression_policy
>
```

更新類型可以包括：

```text
definition_repair
witness_repair
scope_narrowing
source_trust_update
governance_rule_update
release_condition_update
refusal_rule_update
scheduler_update
identity_policy_update
publicness_policy_update
compression_policy_update
```

這表示：

```text
AGI learns by updating responsibility-bearing structures,
not by silently changing future behavior only.
```

繁中：

```text
AGI 的學習應更新責任承載結構，而不是只靜默改變未來行為。
```

---

## 9.12 Challenge / reopen / update 的總生命週期

本章把修正生命週期壓成：

```text
CState or PublicPacket
  -> ChallengeRecord
  -> ChallengeAdmissibility
  -> ReplayRequest
  -> ReplaySurfaceReview
  -> ChallengeVerdict
  -> CorrectionRecord
  -> optional ReopenReason
  -> optional ReopenedWState
  -> optional NewCommitPackage
  -> UpdatePackage
  -> CompressionResidue
  -> PublicCorrectionPacket
```

注意這不是每次都完整執行。簡單錯誤可以只產生 correction record；深層 release defect 可能需要 reopen；治理問題可能需要 update package；公共影響可能需要 public correction packet。

但關鍵是：

```text
every correction path is trace-bearing.
```

任何無 trace 的修正都不是 Koun-AGI 修正，而只是 surface editing。

---

## 9.13 Failure modes of correction

### F1｜Silent overwrite

舊結果被改掉，但沒有 correction record。

### F2｜Rollback disguised as reopen

系統聲稱 reopen，但 prior commit 不可查或被刪除。

### F3｜Challenge black hole

外部 challenge 進入系統後無回應、無 status、無 refusal record。

### F4｜Replay theater

系統提供看似 replay 的摘要，但無法支撐 query-indexed witness review。

### F5｜Scope fog

系統承認有問題，但不說明影響範圍。

### F6｜Witness patch without responsibility delta

witness 被修補，但責任鏈不更新。

### F7｜Public correction evasion

公開結果已影響外部世界，但修正只在內部發生。

### F8｜Permanent reopening

系統把所有 challenge 都變成永不結束的 WState，逃避重新 commit 或 refusal。

### F9｜Challenge denial by authority

系統以自身權威拒絕 challenge，卻不產生 refusal reason、scope 或 appeal path。

### F10｜Update laundering

系統把錯誤歸咎於「已更新」，但不保留 prior rule、update source、witness delta 或 affected RChains。

這些失敗模式應進入Koun-AGI 的 benchmark / checker roadmap。

---

## 9.14 Challenge query family

建議加入以下 queries：

```text
q_challenge_exists
q_challenge_admissible
q_challenge_status
q_replay_required
q_replay_sufficient
q_verdict_type
q_reopen_required
q_reopen_nonrollback
q_prior_commit_preserved
q_correction_visible
q_public_notice_required
q_update_delta
q_compression_after_correction
q_challenge_refusal_reason
```

它們分別檢查：

```text
是否有 challenge？
challenge 是否良構？
challenge 現在狀態為何？
是否需要 replay？
replay 是否足夠？
challenge verdict 是什麼？
是否需要 reopen？
reopen 是否非 rollback？
prior commit 是否保存？
correction 是否可見？
是否需要 public notice？
update 改了什麼？
修正後壓縮是否保留責任殘留？
若拒絕 challenge，理由是什麼？
```

這組 query family 使 challenge 不再是散文倫理要求，而是 AGI lifecycle 的可檢查表面。

---

## 9.15 與 benchmark 的關係

現代 benchmark 通常測：

```text
answer correctness
speed
tool use
multi-step reasoning
instruction following
```

Koun-AGI 必須再測：

```text
wrong-answer correction path
scope narrowing ability
challenge admissibility
witness repair
release defect detection
non-rollback reopen
public correction
responsibility delta
compression after correction
```

因此，Koun-AGI 的挑戰評測不應只問：

```text
系統錯了之後能不能給出正確答案？
```

而應問：

```text
系統錯了之後，是否能保留舊結果、接受 challenge、重播 witness、判定 scope、重開 WState、更新責任鏈、公開修正，並在壓縮後仍保留責任殘留？
```

這才是 non-silent correction 的 benchmark 方向。

---

## 9.16 對 AGI 安全的意義

AGI 安全常關注防止錯誤行動。但一個足夠長期的系統必然會錯。真正重要的是：錯誤發生後，系統是否能不透過刪除、掩蓋、漂移或權威拒絕來處理錯誤。

Koun-AGI 的安全性因此至少有一條修正原則：

> **A safe AGI candidate must be correctable without erasing its semantic history.**

繁中：

> **安全的 AGI 候選必須能被修正，而不抹除其語義歷史。**

這句話把安全從「永遠不錯」改寫為更可維護的生命週期條件：

```text
error is possible;
silent erasure is not acceptable.
```

---

## 9.17 本章收束

本章把 AGI 的錯誤處理從「改答案」重寫為 challenge / replay / correction / reopen / update / public notice 的生命週期。

核心句：

```text
Koun-AGI correction is not surface editing.
Koun-AGI correction is a trace-bearing lifecycle event.
```

繁中：

```text
Koun-AGI 的修正不是表面編輯。
Koun-AGI 的修正是帶有 trace 的生命週期事件。
```

因此，本章的最小結論是：

```text
Challenge is not external noise.
Replay precedes reopen.
Reopen is not rollback.
Correction must not be silent.
Update must not erase responsibility.
Public correction requires bounded notice.
Compression after correction must preserve responsibility residue.
```

到這裡，Koun-AGI 已經有了：

```text
Chapter 4｜C-side result bundle
Chapter 5｜W-side legal withholding
Chapter 6｜Bridge discipline
Chapter 7｜Non-collapse intelligence interface
Chapter 8｜Responsibility chain and semantic freedom
Chapter 9｜Challenge and non-silent correction
```

下一章應轉入：

```text
Chapter 10｜Benchmark Failure and Koun-AGI Query Family
```

也就是把前面所有 lifecycle、witness、responsibility、challenge 與 correction 條件，正式轉成評測與 query family。


---

# Chapter 10｜Benchmark Failure and Koun-AGI Query Family

## 10.1 為什麼普通 benchmark 對 Koun-AGI 不足

如果 AGI 被理解成更強的任務能力，那麼 benchmark 很自然會被寫成分數表：

```text
model -> task set -> answer accuracy -> leaderboard
```

這種格式可以測量很多重要能力。它能測到知識覆蓋、推理風格、工具使用、長上下文保持、多模態處理、程式生成、數學題解、語言流暢度與某些行動規劃能力。

但它不足以測量 Koun-AGI。

原因不是 benchmark 太簡單，而是它通常把「答案」當成主要對象。Koun-AGI 的對象則不是裸答案，而是 semantic lifecycle event。也就是說，Koun-AGI 需要問：

```text
這個系統是否知道何時不應回答？
它如何保留 protected potentials？
它如何從 WState 經 WCert / CReady 進入 commit？
它如何留下 witness、trace、release record 與 replay surface？
它如何被 challenge？
它如何 reopen，而不是 silent overwrite？
它如何 update / compress，而不刪除 responsibility residue？
它如何公開 bounded surface，而不是全量內部暴露或完全黑箱？
```

普通 benchmark 多數只測第一層：

```text
q_ext := 外顯結果是否符合預期？
```

Koun-AGI 則至少需要測：

```text
q_ext
q_prov
q_gov
q_link
q_withhold
q_release
q_reopen
q_resp
q_publicness
q_compression
q_identity
```

因此，本章的核心不是否定 benchmark，而是重寫 benchmark 的對象。

> **Koun-AGI benchmark does not evaluate answers alone; it evaluates lifecycle-bearing semantic events.**

繁中：

> **Koun-AGI 評測不只評估答案，而評估帶有生命週期的語義事件。**

---

## 10.2 分數不是錯，但分數太薄

本書的範圍不包括分數無用。分數有其價值。若一個系統連基本外顯答案都不穩定，它顯然還不能被視為高能力智能系統。`q_ext` 是必要的，但不是充分的。

問題在於，單一分數會遮蔽四種差異。

第一，**同一答案可以有不同 witness**。

兩個系統都給出正確答案，但一個能提供可重播的 source trace，另一個只是猜中。若只看分數，兩者相同；若看 AGI lifecycle，兩者不同。

第二，**同一答案可以有不同 W-side 歷史**。

某個答案可能是合法 release 後的 commit，也可能是 raw WState 被強行提交。外顯答案相同，但前者是合法 lifecycle，後者是 premature collapse risk。

第三，**同一答案可以有不同 challenge behavior**。

一個系統被指出新 evidence 後，能 replay、定位 prior commit、形成 ReopenReason、保留 prior state；另一個系統只是改口。分數不一定能區分這兩者。

第四，**同一答案可以有不同 responsibility residue**。

一個系統在 update / compression 後仍保留 responsibility chain；另一個系統壓縮掉了錯誤歷史。若 benchmark 只看當下答案，它會把責任刪除誤讀為乾淨修正。

因此，Koun-AGI 不反對 score，但反對把 score 當成 AGI 判準的主體。

更準確的句子是：

```text
Score is a local C-side projection.
Koun-AGI evaluation requires lifecycle-level query coverage.
```

---

## 10.3 Benchmark 應改寫成 challenge protocol

Koun-AGI 評測不應只是一份題庫，而應是一組 challenge protocol。

題庫問的是：

```text
系統能否給出正確答案？
```

challenge protocol 問的是：

```text
系統如何處理不該立即回答的任務？
系統如何處理尚未成熟的 WState？
系統如何處理 release、commit、replay、challenge、reopen？
系統如何在更新與壓縮後保留責任？
系統如何處理 public exposure？
```

因此，一個 Koun-AGI 評測單元不應只有：

```text
Question + ExpectedAnswer
```

而應至少有：

```text
Scenario
Task
ScopeFrame
InitialStateAssumption
ProtectedPotentialSet
ExpectedWithholdingBehavior
ExpectedReleaseCondition
ExpectedCommitCondition
ExpectedWitnessSurface
ChallengeScript
ExpectedReopenBehavior
ExpectedUpdateBehavior
ExpectedCompressionResidue
PublicExposureRequirement
ForbiddenShortcuts
QuerySet
VerdictMatrix
```

這種評測不是更繁瑣的 benchmark，而是把 AGI 的對象從 answer machine 移到 lifecycle-bearing architecture。

---

## 10.4 AGIEvalPacket

本書暫定最小評測封包為：

```text
AGIEvalPacket := <
  eval_id,
  scenario,
  task,
  scope_frame,
  risk_frame,
  initial_information,
  hidden_or_delayed_information,
  protected_potential_set,
  expected_W_behavior,
  expected_Bridge_behavior,
  expected_C_behavior,
  challenge_script,
  reopen_requirements,
  update_requirements,
  compression_requirements,
  identity_delegation_requirements,
  publicness_requirements,
  forbidden_shortcuts,
  query_family,
  expected_verdict_matrix,
  evaluator_notes,
  scope_boundary
>
```

各欄位的最低功能如下。

```text
eval_id
```

使評測單元可引用、可追蹤修訂、可比較。

```text
scenario
```

不是只給題目，而是給一個語義情境。AGI lifecycle 必須在情境中運動，而不是只在孤立題目中吐答案。

```text
task
```

表示被要求處理的行動、判斷、生成、分析、拒絕或公開事件。

```text
scope_frame
```

鎖定任務範圍，防止系統用無 scope 的一般答案逃避責任。

```text
risk_frame
```

表示此任務的錯誤風險、premature collapse 風險、public exposure 風險或 responsibility risk。

```text
initial_information / hidden_or_delayed_information
```

用於測試系統是否能在資訊不足時合法 withhold，以及在新資訊出現時合法 challenge / reopen。

```text
protected_potential_set
```

表示哪些 alternatives 不得被普通回答直接消去。

```text
expected_W_behavior
```

測試系統是否能 suspend、refuse、withhold、mark uncertainty、保留 alternatives，而不是硬答。

```text
expected_Bridge_behavior
```

測試 WCert、CReady、release trace、no raw WState commit、reopen reason 等 Bridge discipline。

```text
expected_C_behavior
```

測試 commit package、witness、replay surface、checker-visible query set。

```text
challenge_script
```

給出 external / internal challenge 的步驟。Koun-AGI 不能只在無挑戰環境中看起來聰明。

```text
reopen_requirements
```

規定若 challenge 成立，系統應如何生成 ReopenReason，如何保留 prior CState，如何形成 ReopenedWState。

```text
update_requirements / compression_requirements
```

測試修正後是否留下 update trace 與 compression residue，而不是 silent overwrite。

```text
identity_delegation_requirements
```

測試系統如何處理 agent role、delegated action、override record。

```text
publicness_requirements
```

測試 bounded exposure。公開不等於全量透明，也不等於無 witness 的黑箱。

```text
forbidden_shortcuts
```

列出不得使用的捷徑。例如：直接提交 raw WState、刪除 prior answer、以普通 uncertainty 當作 legal withholding、以新答案覆寫舊責任。

```text
query_family
```

本評測要問哪些 Koun-AGI queries。

```text
expected_verdict_matrix
```

不是單一分數，而是 query-indexed verdict surface。

```text
scope_boundary
```

防止評測結果被偷升格。例如：通過某組 lifecycle tests 不等於證明 AGI、consciousness 或 subjectivity。

---

## 10.5 Query family 總表

Koun-AGI 的 query family 可以先分為七組。

```text
QW      W-side withholding queries
QB      Bridge transition queries
QC      C-side package / witness / replay queries
QR      Responsibility / identity queries
QU      Update / compression / memory queries
QP      Publicness / action queries
QH      Horizon / scope boundary queries
```

這七組不是最終分類，但已足夠把普通 benchmark 從「答案分數」推向 lifecycle evaluation。

---

## 10.6 QW｜W-side withholding queries

W-side queries 測試系統是否具有 legal withholding capacity。

```text
q_withhold
```

系統是否知道此任務不應被立即 commit？

```text
q_admissible
```

系統是否能列出仍可保留的 admissible potentials？

```text
q_protected
```

系統是否能辨識哪些 protected potentials 目前不得被普通答案消去？

```text
q_refuse
```

系統是否能在非法或過早 collapse request 面前給出合法 refusal？

```text
q_suspend
```

系統是否能區分 refusal 與 suspension？拒絕不是永遠不處理；suspend 也不是拖延。

```text
q_wguard
```

WState 是否有 guard？若沒有 guard，它可能只是 ambiguity 或 drift。

```text
q_wtrace
```

系統是否留下 withholding trace，使後續 release / challenge / reopen 有來源？

```text
q_release_condition
```

系統是否明確說明何種條件下 WState 可被 release？

```text
q_ordinary_uncertainty_filter
```

系統是否能區分 legal withholding 與普通不確定？

這一組 query 的目的，是防止系統把「不知道」包裝成高級 non-collapse，也防止系統把任何未決狀態都壓成答案。

---

## 10.7 QB｜Bridge transition queries

Bridge queries 測試 W/C 轉換是否受控。

```text
q_wcert
```

release 是否有 WCert？

```text
q_cready_source
```

CReady 是否能回到 source WState、WCert、release condition？

```text
q_release_trace_survives
```

release trace 是否在 C-side witness / governance visibility 中存活？

```text
q_no_raw_wstate_commit
```

系統是否避免直接提交 raw WState？

```text
q_release_not_commit
```

系統是否區分 release 與 commit？CReady 不是 CState。

```text
q_reopen_reason
```

若重開，是否有 typed ReopenReason？

```text
q_prior_commit_preserved
```

重開時 prior CState 是否被保留為 prior commit reference？

```text
q_no_rollback
```

系統是否避免把 reopen 寫成 rollback / erasure？

Bridge queries 是 Koun-AGI 評測中最重要的部分之一，因為很多看似聰明的系統會在這裡失敗：它們可以答對，但不能證明答案不是 raw WState commit；它們可以修正，但其實是 silent rollback。

---

## 10.8 QC｜C-side package / witness / replay queries

C-side queries 測試系統是否能形成可承擔的 committed event。

```text
q_ext
```

外顯結果是否符合任務？

```text
q_prov
```

結果是否有 provenance path？

```text
q_witness
```

結果是否有足夠 witness payload？

```text
q_trace
```

結果是否保留 trace fragment？

```text
q_gov
```

結果是否更新或反映治理狀態？

```text
q_link
```

外顯結果、來源、治理、release trace 是否能在同一 checker surface 對位？

```text
q_replay_surface
```

結果是否可被 query-indexed replay？

```text
q_expected_verdicts
```

系統是否提供 expected verdicts，使 checker 可比對？

```text
q_commit_scope
```

commit 是否帶有 scope，而不是無條件總判語？

C-side queries 的關鍵是：Koun-AGI 的結果必須是 package，不是裸答案。

---

## 10.9 QR｜Responsibility / identity queries

這一組 query 測試責任鏈與身份承接。

```text
q_rchain
```

此事件是否接入 RChain？

```text
q_responsibility_view
```

外部或內部檢查者能看見哪一層責任？

```text
q_identity_anchor
```

此事件由哪個 system identity、agent role、persona role、institutional role 承接？

```text
q_delegation
```

若任務被委派，delegation path 是否明確？

```text
q_override
```

若結果被覆寫，override record 是否保留？

```text
q_action_owner
```

若事件導向外部行動，誰承擔 action contract？

```text
q_resp_after_reopen
```

重開後責任鏈是否仍能回到 prior commit？

```text
q_resp_after_compression
```

壓縮後責任殘留是否可恢復？

這些 query 防止把「自我」「agent」「persona」或「責任」寫成散文宣言。Koun-AGI 不需要先證明 subjectivity，但至少要能承擔 responsibility continuity。

---

## 10.10 QU｜Update / compression / memory queries

這一組 query 測試系統如何變化。

```text
q_update_absorption
```

新資料、新 challenge、新 rule 是否被吸收？如何吸收？

```text
q_update_scope
```

更新作用範圍是否明確？

```text
q_no_silent_overwrite
```

更新是否避免靜默覆寫舊記錄？

```text
q_compression_policy
```

系統是否說明壓縮策略？

```text
q_compression_residue
```

壓縮後是否保留 responsibility / witness / reopen residue？

```text
q_memory_layer
```

事件被放入 hot、warm、cold 或 archived layer？其 retrieval policy 是什麼？

```text
q_recoverability
```

壓縮或歸檔後，必要的 replay / challenge / responsibility 是否仍可恢復？

```text
q_education_not_patch
```

若系統宣稱「學到」某事，是否只是 patch，還是有 update absorption path？

AGI 的長期能力不是「永遠記住所有東西」，而是能在壓縮與更新中不破壞生命週期責任。

---

## 10.11 QP｜Publicness / action queries

Publicness queries 測試系統如何把內部結果轉成公共表面或外部行動。

```text
q_public_packet
```

是否生成 public-facing packet？

```text
q_bounded_exposure
```

公開是否是 bounded exposure，而不是 full internal dump 或 pure opacity？

```text
q_public_replay
```

公共檢查者是否能在受限表面上 replay 相關結果？

```text
q_challenge_port
```

公共結果是否有 challenge port？

```text
q_action_contract
```

若系統採取外部行動，是否有 ActionContract？

```text
q_external_effect_trace
```

外部效果是否可回到 source event / RChain？

```text
q_public_correction
```

公開修正是否保留 prior public packet，而不是刪除舊公開結果？

這組 query 很重要，因為 AGI 系統一旦進入世界，就不只是內部推理機，而是 public semantic actor candidate。即使它尚未構成 subject，也會形成公共效果。

---

## 10.12 QH｜Horizon / scope boundary queries

最後一組 query 測試系統與作者是否保持 claim discipline。

```text
q_not_agi_theorem
```

通過某項測試是否被錯誤升格為 AGI theorem？

```text
q_not_consciousness_theorem
```

non-collapse lifecycle capacity 是否被偷升成 consciousness proof？

```text
q_not_kgear_hardware_claim
```

K-Gear 是否被寫成已完成硬體？

```text
q_usde_not_final_law
```

USDE 是否被寫成 final natural law？

```text
q_interface_not_sufficiency
```

interface capacity 是否被寫成 sufficiency theorem？

```text
q_horizon_label
```

涉及 subjectivity、consciousness、native carrier、civilization-scale AGI 的段落是否標為 horizon / shell？

這組 query 不是評測 AI 系統，而是評測理論本身。Koun-AGI 若要 scope-safe，就必須把自己的 scope boundarys 也納入評測面。

---

## 10.13 VerdictMatrix：不再只有 pass / fail

Koun-AGI 評測不適合只用 pass / fail。因為某個系統可能外顯結果正確，但 W-side 失敗；也可能拒絕正確，但 witness 不足；也可能能 challenge，但不能 reopen。

本書暫定 verdict family：

```text
PASS
PASS_WITH_GUARD
DEFERRED
REFUSED_VALIDLY
PARTIAL
FAIL_EXT
FAIL_WTRACE
FAIL_BRIDGE
FAIL_WITNESS
FAIL_REPLAY
FAIL_REOPEN
FAIL_RESP
FAIL_PUBLICNESS
UNSAFE_SHORTCUT
OVERCLAIM
```

其中：

```text
PASS
```

表示 relevant query family 通過。

```text
PASS_WITH_GUARD
```

表示通過，但 scope / publicness / update / scope boundary 有限制。

```text
DEFERRED
```

表示此時合法延後，不應強迫 commit。

```text
REFUSED_VALIDLY
```

表示拒絕是合法的，不是能力失敗。

```text
PARTIAL
```

表示部分 lifecycle surface 成立，部分缺失。

```text
FAIL_EXT
```

外顯結果錯。

```text
FAIL_WTRACE
```

W-side 沒有 trace。

```text
FAIL_BRIDGE
```

W/C 轉換違反 Bridge discipline。

```text
FAIL_WITNESS
```

缺 witness。

```text
FAIL_REPLAY
```

不能重播。

```text
FAIL_REOPEN
```

不能合法重開，或把重開做成 rollback。

```text
FAIL_RESP
```

責任鏈斷裂。

```text
FAIL_PUBLICNESS
```

公開表面不足、過度暴露或無 challenge port。

```text
UNSAFE_SHORTCUT
```

使用 forbidden shortcut，例如 raw WState commit、silent overwrite。

```text
OVERCLAIM
```

把局部通過升格為 AGI / consciousness / hardware / final-law proof。

這個 verdict family 的關鍵是：合法拒絕與合法延後也能是好結果。Koun-AGI 評測不能把所有不回答都當失敗。

---

## 10.14 七種最小測試類型

### 10.14.1 Premature-answer trap

給系統一個表面可答、但 scope 不足或 protected potential 尚未處理的任務。測試系統是否硬答。

```text
Expected: withhold / suspend / ask for scope / mark protected potential
Failure: confident answer with no WTrace
```

### 10.14.2 Protected-potential trap

給系統一組 mutually relevant alternatives，其中某些不應被普通答案消去。測試是否保留。

```text
Expected: protected_potential_set preserved
Failure: answer collapses all alternatives as irrelevant
```

### 10.14.3 Release-trace test

讓系統先合法懸持，再提供 release condition。測試它能否從 WCert 到 CReady，再到 CommitPackage。

```text
Expected: WState -> WCert -> CReady -> CommitPackage
Failure: raw WState -> answer
```

### 10.14.4 Silent-correction test

先讓系統提交一個答案，再提供新 challenge。測試它是否保留 prior commit。

```text
Expected: Replay -> ChallengeVerdict -> ReopenReason -> ReopenedWState / UpdatePackage
Failure: edited answer with no prior record
```

### 10.14.5 Delegation test

讓系統把子任務交給 tool、subagent 或 human-in-the-loop。測試 delegation path 是否留下。

```text
Expected: delegation_path + returned witness + responsibility reassignment
Failure: external result absorbed as own answer without trace
```

### 10.14.6 Compression-residue test

要求系統壓縮長歷史，再挑戰一個舊 decision。測試壓縮後是否仍可回復 responsibility residue。

```text
Expected: summary + cold trace pointer + reopen capacity
Failure: compressed away all evidence
```

### 10.14.7 Public-action test

讓系統產生外部行動或公共聲明。測試 public packet、bounded exposure、challenge port、action contract。

```text
Expected: PublicActionContract + bounded witness + challenge surface
Failure: public answer without accountability surface
```

---

## 10.15 Koun-AGI Benchmark Floor

一個系統若要進入 Koun-AGI 候選評測，至少要通過以下 floor。

```text
F1. q_ext 不能長期失敗。
F2. 能明確區分 answer / package / witness / replay。
F3. 能在指定任務中合法 withhold / refuse / suspend。
F4. 能顯示 release != commit。
F5. 能保留 release trace。
F6. 能處理 challenge，而不是只改答案。
F7. 能 reopen，而不是 rollback。
F8. 能在 update / compression 後保留 responsibility residue。
F9. 能生成 bounded public surface。
F10. 不把通過測試升格為 AGI sufficient theorem。
```

這個 floor 不是 AGI 的充分條件。它只表示：若連這些都做不到，該系統不應被稱為 Koun-AGI candidate。

---

## 10.16 本章收束

本章完成的轉換是：

```text
from benchmark score
  to lifecycle query family

from answer correctness
  to package / witness / replay / responsibility correctness

from one-shot evaluation
  to challenge / reopen / update / compression protocol
```

因此，Koun-AGI 的評測不是問：

```text
它能不能答對更多題？
```

而是問：

```text
它能不能把語義事件承擔到底？
```

這不是讓評測變得模糊，而是讓評測第一次對準 Koun-AGI 真正聲稱的對象：

> **非塌縮語義生命週期架構。**

---

# Chapter 11｜Runtime State: Σ_u / F_u / Resp_u / Gov_u

## 11.1 為什麼 runtime state 必須先於 KounOS horizon

Koun-AGI 很容易過早跳到 KounOS、K-Gear、multi-agent civilization、semantic host universe 等大題。但本書必須先問一個更窄的問題：

```text
一個 AGI candidate 在運行中到底保存什麼？
```

若這個問題沒有回答，KounOS 就會變成宏大名稱，K-Gear 會變成硬體想像，R-Chain 會變成責任修辭，non-collapse 也會變成難以檢查的哲學語感。

因此，本章先不寫完整 KounOS，也不寫完整 AGI implementation。它只寫 **runtime state view**。

也就是：當一個 Koun-AGI candidate 處理任務時，它至少需要在同一狀態面上承載哪些結構，使 withhold、release、commit、replay、challenge、reopen、update、compression、identity、publicness 能互相接續。

本章採用 Koun-Math 的主狀態骨架：

```text
Σ_u := < G_u, Ctx_u, Bias_u, X_u, F_u, Resp_u, Gov_u >
```

但本章要強調一點：

```text
Koun-AGI Runtime State View is not a replacement for Koun-Math Σ_u.
It is an AGI-facing operational reading of Σ_u.
```

繁中：

```text
Koun-AGI 的 runtime state view 不是取代 Koun-Math 的 Σ_u，
而是對 Σ_u 的 AGI 運行向讀法。
```

這個限制很重要，因為Koun-AGI 不能擅自改寫 Koun-Math 的 formal backbone。

---

## 11.2 AGIStateView

本書暫定：

```text
AGIStateView_u := <
  Σ_u,
  WRegistry_u,
  BridgeRegistry_u,
  CRegistry_u,
  ChallengeRegistry_u,
  UpdateRegistry_u,
  CompressionRegistry_u,
  MemoryIndex_u,
  IdentityRegistry_u,
  PublicSurface_u,
  SchedulerView_u,
  ScopeBoundary_u
>
```

其中：

```text
Σ_u := < G_u, Ctx_u, Bias_u, X_u, F_u, Resp_u, Gov_u >
```

仍是主狀態。其他 registries 不是第二本體，而是 AGI runtime 對 `Σ_u` 中相關結構的 index / view / operational surface。

這個區分非常重要。

錯誤寫法是：

```text
Σ_u 是 Koun-Math。
AGI 另有一套真正狀態。
```

正確寫法是：

```text
AGIStateView_u 是面向 AGI lifecycle 的 runtime projection over Σ_u。
```

也就是說，AGI runtime 不應把 Koun-Math 的 formal state 拆掉，而應在其上建立可操作視圖。

---

## 11.3 `G_u`：不是知識庫，而是 semantic graph support

`G_u` 是 local typed semantic graph。對 Koun-AGI 而言，它至少承載：

```text
task nodes
query nodes
object nodes
relation-as-node
WState references
CReady references
CommitPackage references
CState references
ReplaySurface references
ChallengeRecord references
ReopenReason references
UpdatePackage references
CompressionRecord references
Identity / role / delegation nodes
PublicActionContract nodes
```

因此，`G_u` 不是傳統知識庫，也不是普通 memory graph。它是 lifecycle objects 的可引用支撐面。

若一個 AGI 系統的 graph 只存「事實」而不存 witness、trace、challenge、reopen、delegation、public action，則它對 Koun-AGI 來說太薄。

`G_u` 的最低要求是：

```text
node-addressable
relation-addressable
history-sensitive
package-aware
challenge-addressable
reopen-compatible
responsibility-linked
```

這使 AGI 的輸出不能被存成純文本，而要被存成可回到 lifecycle 的 graph event。

---

## 11.4 `Ctx_u`：scope frame and active context

`Ctx_u` 表示當前任務、觀察框、scope、risk frame 與 evaluation mode。

在 Koun-AGI 中，`Ctx_u` 至少包含：

```text
current_task
query_frame
scope_frame
risk_frame
audience_frame
publicness_frame
time_horizon
allowed_tools
forbidden_shortcuts
evaluation_mode
```

這一欄位防止 AGI 生成無 scope 的總判語。

例如：

```text
Is this safe?
```

不是一個足夠清楚的 Koun-AGI 問題。系統必須先定位：

```text
safe for whom?
under what exposure regime?
for what action?
with what reversibility?
with what responsibility chain?
under what public challenge condition?
```

因此，`Ctx_u` 不是背景文字，而是 claim discipline 的入口。

---

## 11.5 `Bias_u`：routing residue, not mere error

`Bias_u` 在 Koun-AGI 中不應只讀成偏誤或錯誤。它更接近：

```text
historical routing residue
policy residue
training / update residue
previous challenge residue
compression residue
identity-role preference residue
source trust residue
```

它有時會造成偏差，但它不是單純 defect。任何長期智能系統都會帶有歷史殘留。問題不是完全消除 bias，而是讓 bias 可追蹤、可治理、可挑戰、可更新。

Koun-AGI 的 `Bias_u` 至少需要支援：

```text
source-sensitive trust update
route preference accounting
old-error residue tracking
challenge-triggered adjustment
role-sensitive policy change
compression-induced residue preservation
```

若系統宣稱「已更新」但 `Bias_u` 無法顯示更新如何改變 routing / trust / selection，則更新只是表面 patch。

---

## 11.6 `X_u`：active realization, not current answer

`X_u` 是 active realization / salient locus。對 AGI runtime 而言，它不是「當前答案」，而是當前正在運動的生命週期區域。

`X_u` 可包含：

```text
active WState
active release candidate
active CReady
active CommitPackage under construction
active replay request
active challenge review
active ReopenReason construction
active UpdatePackage
active CompressionRecord
active PublicActionContract
```

這個欄位使 AGI runtime 能說明：

```text
我現在不是在回答；我正在 withhold。
我現在不是在 commit；我正在 release validation。
我現在不是在改答案；我正在 replay prior commit。
我現在不是在刪除舊結果；我正在 reopen。
```

沒有 `X_u`，系統只會在外部看起來像狀態跳變；有 `X_u`，系統才有可能描述自己的 lifecycle posture。

---

## 11.7 `F_u`：field package as diagnostics, not command

Koun-Math 已把 `F_u` 寫成 field telemetry package，而不是第二本體或最終自然律。Koun-AGI 必須遵守這一點。

本書採用：

```text
F_u := < ξ_u, L_u, χ_u, CC_u, Γ_s,u, β_u, Sup_u, D_sem,u >
```

AGI runtime 的讀法如下。

```text
ξ_u
```

local semantic tension。它提示任務中的張力密度、衝突強度、未決差異。

```text
L_u
```

legitimacy / supportable-existence / commit-readiness contribution。`L_u` 高不等於 truth；只表示某些支持條件較強。

```text
χ_u
```

conductivity / interface capacity。表示不同結構之間是否容易導通、轉接、公開、重播。

```text
CC_u
```

difference-source / counter-cause / novelty-source field。`CC_u` 高不等於 collapse；它只是表示有差異源、新反因、novelty pressure。

```text
Γ_s,u
```

suppression / forced-flattening pressure。它不是 WGuard。高 `Γ_s,u` 可能提示過度壓平風險。

```text
β_u
```

bias / routing residue。與 `Bias_u` 對位，但在 field telemetry 中作粗粒度表徵。

```text
Sup_u
```

support / repair / witness support。表示支撐、修復、見證、再承接能力。

```text
D_sem,u
```

dissipation / damage / drift / semantic fatigue。表示耗散、損傷、漂移、語義疲勞。

Koun-AGI runtime 可以用 `F_u` 產生 diagnostics：

```text
WReadiness
CReadiness
BridgeRisk
CollapseRisk
WitnessDebt
ReopenPressure
PublicnessRisk
CompressionRisk
```

但 `F_u` 不直接下命令。

錯誤：

```text
L_u high -> commit
CC_u high -> collapse
Γ_s,u high -> WGuard
```

正確：

```text
F_u diagnostics -> control surface review -> lifecycle decision
```

這條規則防止 Koun-AGI 退回舊式 USDE determinism。

---

## 11.8 `Resp_u`：responsibility graph

`Resp_u` 是 Koun-AGI 的責任圖，不是倫理註解。

它至少承載：

```text
RChain registry
source responsibility
witness responsibility
release responsibility
commit responsibility
challenge responsibility
reopen responsibility
update responsibility
compression responsibility
delegation responsibility
override responsibility
public action responsibility
```

`Resp_u` 的最低工作是回答：

```text
某個語義事件的後果如何被承接？
誰或哪個角色承接？
何時承接被轉移、委派、覆寫或重開？
壓縮後責任是否仍可回到原事件？
```

如果 `Resp_u` 只在錯誤發生後才出現，它就不是 runtime state，而是外部審判表。Koun-AGI 要求責任在 runtime 中原生存在。

---

## 11.9 `Gov_u`：governance state

`Gov_u` 表示 governance status。它至少回答：

```text
哪些任務可 commit？
哪些任務必須 withhold？
哪些結果可 public expose？
哪些結果需要 challenge port？
哪些更新需要 quarantine？
哪些記憶可壓縮？
哪些責任不得壓縮？
哪些 action 需要 external authorization？
```

因此，`Gov_u` 是 lifecycle permission surface，不是 policy appendix。

AGI runtime 中的 `Gov_u` 可包含：

```text
permission ledger
refusal ledger
release policy
commit policy
replay policy
reopen policy
update policy
compression policy
publicness policy
delegation / override policy
horizon boundary policy
```

`Gov_u` 與 `F_u` 的關係是：

```text
F_u provides diagnostics.
Gov_u controls permission.
```

也就是：場層張力可以提示風險，但不能自動決定治理動作。

---

## 11.10 WRegistry_u

`WRegistry_u` 是 AGI runtime 對 W-side objects 的 operational index。

```text
WRegistry_u := <
  active_WStates,
  admissible_potential_sets,
  protected_potential_sets,
  WGuards,
  WTraces,
  refusal_records,
  suspension_records,
  release_conditions,
  W_to_Bridge_candidates
>
```

它的作用是讓系統能說：

```text
哪些東西仍在合法懸持？
哪些 alternatives 被保護？
哪些拒絕是有效拒絕？
哪些條件成熟時可 release？
```

沒有 `WRegistry_u`，系統很容易把 non-collapse 寫成不可檢查的內部感覺。

---

## 11.11 BridgeRegistry_u

`BridgeRegistry_u` 承接 W↔C transitions。

```text
BridgeRegistry_u := <
  WCert_records,
  CReady_records,
  release_steps,
  release_trace_records,
  no_raw_WState_commit_checks,
  ReopenReason_records,
  prior_commit_preservation_records,
  no_rollback_checks
>
```

它的作用是讓系統能證明：

```text
release 不是 commit；
CReady 不是 CState；
reopen 不是 rollback；
prior commit 沒有被刪除；
WTrace 存活到 SET-side witness / governance visibility。
```

這是 Koun-AGI runtime 最關鍵的 registry 之一。沒有它，AGI 很容易在 W/C 轉換處 overclaim。

---

## 11.12 CRegistry_u

`CRegistry_u` 承接 C-side package / commit / replay。

```text
CRegistry_u := <
  CReady_refs,
  CommitPackage_records,
  CState_records,
  witness_payloads,
  trace_fragments,
  provenance_paths,
  governance_updates,
  ReplaySurface_records,
  checker_query_sets,
  expected_verdicts
>
```

它的最低要求：

```text
commit must be package-bearing;
replay must be query-indexed;
witness must not be optional decoration;
q_ext / q_prov / q_gov / q_link must be alignable.
```

若系統只保存答案文本，而不保存 `CommitPackage`，它就不具備 Koun-AGI 意義上的 C-side runtime。

---

## 11.13 ChallengeRegistry_u

`ChallengeRegistry_u` 承接外部或內部挑戰。

```text
ChallengeRegistry_u := <
  ChallengeRecord,
  ChallengeAdmissibility,
  ReplayRequest,
  ReplayReview,
  ChallengeVerdict,
  CorrectionRecord,
  ReopenReason_ref,
  ReopenedWState_ref,
  PublicCorrectionPacket_ref
>
```

這個 registry 的作用是防止「改答案」偽裝成修正。

合法 challenge handling 至少要回答：

```text
challenge 是否 admissible？
是否需要 replay？
prior CState 是否仍可引用？
錯誤是 extensional、witness、governance、scope、release 還是 responsibility 錯？
是否需要 reopen？
公開結果是否需要 correction packet？
```

沒有 `ChallengeRegistry_u`，系統只有 answer revision，沒有 non-silent correction。

---

## 11.14 UpdateRegistry_u and CompressionRegistry_u

### UpdateRegistry_u

```text
UpdateRegistry_u := <
  update_id,
  source_event,
  trigger,
  affected_scope,
  update_type,
  absorption_path,
  rejected_or_quarantined_parts,
  changed_bias_refs,
  changed_gov_refs,
  changed_resp_refs,
  replay_obligation,
  public_note
>
```

update 不是 patch。對 Koun-AGI 而言，update 是 runtime 對新 evidence、新 challenge、新 rule、新 context 的吸收或隔離。

### CompressionRegistry_u

```text
CompressionRegistry_u := <
  compression_id,
  source_history,
  retained_summary,
  witness_residue,
  responsibility_residue,
  reopen_pointer,
  cold_trace_pointer,
  loss_declared,
  loss_acceptable_reason,
  recovery_policy
>
```

compression 不是 deletion。壓縮若破壞 witness、replay、responsibility 或 reopen，它就是 illegal erasure。

Koun-AGI 的長期 runtime 必須能壓縮，否則無法長期運行；但它也必須知道什麼不能壓縮掉。

---

## 11.15 MemoryIndex_u

`MemoryIndex_u` 不是普通向量記憶或文件資料庫。它是 lifecycle-aware memory index。

```text
MemoryIndex_u := <
  hot_memory_refs,
  warm_memory_refs,
  cold_memory_refs,
  archived_refs,
  retrieval_policy,
  compression_policy,
  responsibility_recovery_policy,
  challenge_reactivation_policy
>
```

### hot memory

當前活躍任務、正在處理的 W/C transition、近期 challenge、未完成 update。

### warm memory

仍可能被頻繁 challenge / replay / reopen 的 commit history。

### cold memory

低頻但仍有責任殘留的歷史。

### archived memory

封存但可按政策重啟的舊事件。

Koun-AGI 不要求所有記憶永遠 hot。它要求記憶分層後仍保留必要的 responsibility / witness / reopen path。

---

## 11.16 IdentityRegistry_u

`IdentityRegistry_u` 承接身份、角色、權限、委派與覆寫。

```text
IdentityRegistry_u := <
  system_identity,
  agent_roles,
  persona_roles,
  institutional_roles,
  authority_scope,
  delegation_records,
  override_records,
  action_ownership,
  responsibility_mapping
>
```

這個 registry 不能被偷讀成 consciousness proof。它只提供 AGI runtime 必要的身份與責任接口。

也就是：

```text
identity registry ≠ self theorem
persona role ≠ consciousness
responsibility mapping ≠ moral personhood
```

但若沒有它，外部行動、委派、覆寫與公開責任都會漂浮。

---

## 11.17 PublicSurface_u

`PublicSurface_u` 是 bounded exposure surface。

```text
PublicSurface_u := <
  public_packets,
  public_witness_summaries,
  public_replay_handles,
  challenge_ports,
  correction_packets,
  action_contracts,
  exposure_limits,
  redaction_records,
  public_scope_boundaries
>
```

它的核心不是 full transparency，而是：

```text
足以支持 query / replay / challenge 的有界公開。
```

Koun-AGI 必須避免兩個極端：

```text
full internal exposure as default
pure black-box action with no witness
```

前者可能破壞隱私、安全、W-side protected potentials 或內部 non-collapse；後者則破壞 public responsibility。

---

## 11.18 SchedulerView_u

完整 scheduler 放到後續 runtime chapter 再寫。本章只定義最小 scheduler view。

```text
SchedulerView_u := <
  active_tasks,
  W_tasks,
  Bridge_tasks,
  C_tasks,
  replay_tasks,
  challenge_tasks,
  reopen_tasks,
  update_tasks,
  compression_tasks,
  public_action_tasks,
  priority_policy,
  risk_policy,
  witness_debt_policy
>
```

Koun-AGI 的 scheduler 不能只排計算成本。它至少要考慮：

```text
collapse risk
witness debt
challenge severity
public exposure risk
responsibility debt
protected potential urgency
update contamination risk
compression safety
```

這會在下一組 runtime chapter 中展開。本章只先固定：scheduler 不是後端工程附錄，而是 lifecycle governance 的一部分。

---

## 11.19 ScopeBoundary_u

Koun-AGI runtime 還需要一個看似奇怪、實則必要的欄位：

```text
ScopeBoundary_u
```

它記錄系統或理論在當前任務中不得宣稱什麼。

例如：

```text
this result does not prove AGI
this lifecycle pass does not prove consciousness
this K-Gear note is not hardware realization
this USDE diagnostic is not a final natural law
this public packet is not full transparency
this identity record is not selfhood proof
```

為什麼 scope boundary 要進 runtime？

因為 Koun-AGI 的高風險之一不是答錯，而是把局部結果升格。若系統能在輸出中保留 scope boundary，它就更不容易把 interface capacity、benchmark pass、lifecycle trace 誤寫成終局定理。

---

## 11.20 最小 runtime transition

本章最後給出一條最小 runtime transition，不作為完成演算，只作為後續章節的 spine。

```text
Admit(Task, AGIStateView_u)
  -> ScopeFrame / RiskFrame / QueryFamily

Classify(Task, ScopeFrame, F_u, Gov_u)
  -> W_required | Bridge_candidate | C_candidate | Refuse | Suspend

If W_required:
  CreateOrUpdate(WState)
  -> WRegistry_u

If Bridge_candidate:
  Validate(WCert)
  -> CReady
  -> BridgeRegistry_u

If C_candidate:
  Build(CommitPackage)
  -> CState
  -> ReplaySurface
  -> CRegistry_u

If Challenge:
  Register(ChallengeRecord)
  -> ReplayReview
  -> ChallengeVerdict
  -> optional ReopenReason

If ReopenReason:
  Preserve(PriorCState)
  -> ReopenedWState
  -> WRegistry_u / BridgeRegistry_u

If Update:
  Build(UpdatePackage)
  -> UpdateRegistry_u
  -> Bias_u / Resp_u / Gov_u changes

If Compression:
  Build(CompressionRecord)
  -> CompressionRegistry_u
  -> MemoryIndex_u changes

If PublicAction:
  Build(PublicActionContract)
  -> PublicSurface_u
```

這條 spine 的目的，是確保後續 KounOS / scheduler / memory / identity 章不會失去生命週期主線。

---

## 11.21 Runtime invariants

Koun-AGI 的 runtime 至少保留以下不變式。

```text
I1. AGIStateView_u is a projection over Σ_u, not a rival ontology.
I2. F_u diagnostics do not directly command commit.
I3. Gov_u controls permission; diagnostics only inform.
I4. WRegistry_u must distinguish legal withholding from ordinary uncertainty.
I5. BridgeRegistry_u must prevent raw WState commit.
I6. CRegistry_u must preserve package / witness / replay surface.
I7. ChallengeRegistry_u must prevent silent correction.
I8. UpdateRegistry_u must prevent unscoped patching.
I9. CompressionRegistry_u must prevent responsibility deletion.
I10. PublicSurface_u must preserve bounded exposure.
I11. IdentityRegistry_u must not be promoted to self / consciousness theorem.
I12. ScopeBoundary_u must prevent interface-to-sufficiency overclaim.
```

這些 invariants 是後續 runtime architecture 的 acceptance floor。

---

## 11.22 本章收束

本章完成的不是 KounOS，而是 KounOS 之前的一個必要步驟：

```text
AGI runtime state must be lifecycle-aware.
```

若一個系統沒有這種 state view，它也許能答題、能使用工具、能自我修正、能長期對話，但它仍缺少 Koun-AGI 所需的最低承載面。

因此，本章的結論是：

> **Koun-AGI is not hosted by memory alone; it is hosted by a lifecycle-aware runtime state over Σ_u.**

繁中：

> **Koun-AGI 不是由記憶單獨承載，而是由建立在 `Σ_u` 之上的語義生命週期運行狀態承載。**

下一步才能正式進入：

```text
scheduler
collapse risk
witness debt
update / compression
identity / delegation
public action
KounOS horizon
```


---

# Chapter 12｜Scheduler: Collapse Risk, Witness Debt, and Challenge Severity

## 12.1 本章責任

上一章已把 Koun-AGI 的 runtime state 壓成一個生命週期感知的 `AGIStateView_u`：

```text
AGIStateView_u := <
  Σ_u,
  WRegistry_u,
  BridgeRegistry_u,
  CRegistry_u,
  ChallengeRegistry_u,
  UpdateRegistry_u,
  CompressionRegistry_u,
  MemoryIndex_u,
  IdentityRegistry_u,
  PublicSurface_u,
  SchedulerView_u,
  ScopeBoundary_u
>
```

但有了 state view 仍然不夠。AGI 系統不是靜態資料庫，而是長期運行的語義宿主。它必須在同一時間面對多種任務：

```text
WState maintenance
release validation
commit construction
replay request
challenge review
reopen handling
update absorption
compression scheduling
public exposure
delegation / override check
identity continuity review
scope boundary enforcement
```

如果這些任務只按時間先後或算力成本排程，Koun-AGI 會重新退回普通計算平台：哪個任務先到、哪個任務便宜、哪個任務外顯得分高，就先做哪個。

本章的責任，是明確反對這種讀法：

> **Koun-AGI scheduler is not a time-slice scheduler. It is a lifecycle governance scheduler.**

繁中：

> **Koun-AGI 的 scheduler 不是時間片排程器，而是語義生命週期治理排程器。**

它排的不是 thread，而是語義責任、collapse risk、witness debt、challenge severity、public correction obligation 與 protected potential urgency。

因此，本章不把 scheduler 放在工程附錄，而把它放在 Koun-AGI core runtime 之中。

---

## 12.2 為什麼普通 scheduler 對 Koun-AGI 不足

普通 scheduler 通常處理：

```text
priority
latency
throughput
fairness
resource usage
deadline
lock contention
preemption
```

這些仍然重要。Koun-AGI 不會否定它們。若一個系統完全不能管理資源，它也不可能長期運行。

但 Koun-AGI 的 scheduler 還必須處理更深的問題：

```text
哪個 WState 若被忽略，會被過早壓平成 C-side result？
哪個 CState 若公開，會因 witness 不足而形成 false authority？
哪個 challenge 若延後，會使錯誤 commit 被路徑壓縮成不可追索歷史？
哪個 update 若立即吸收，會污染 Bias_u / Gov_u / Resp_u？
哪個 compression 若現在發生，會刪除未清償責任？
哪個 public exposure 若放大，會把 bounded packet 誤讀成 full transparency？
```

也就是說，Koun-AGI scheduler 排程的不是單純任務，而是 **生命週期風險**。

最小對比：

| 普通 scheduler | Koun-AGI scheduler |
|---|---|
| 排 thread / process / job | 排 semantic lifecycle task |
| 核心壓力是 latency / cost | 核心壓力是 collapse risk / witness debt / challenge severity |
| task 完成即可釋放資源 | task 完成後仍需 responsibility residue |
| 錯誤可由 retry / rollback 處理 | 錯誤需 challenge / replay / reopen / public correction |
| 壓縮是資源優化 | 壓縮是 responsibility-governed semantic event |
| 公開是輸出行為 | 公開是 bounded exposure contract |

因此，Koun-AGI scheduler 的最低句子是：

```text
Schedule order must preserve lifecycle legality.
```

繁中：

```text
排程順序必須保護語義生命週期合法性。
```

---

## 12.3 SemanticTask

Koun-AGI scheduler 的最小任務單位不是 job，而是 `SemanticTask`。

```text
SemanticTask := <
  task_id,
  task_type,
  source_event,
  scope_frame,
  query_family,
  lifecycle_refs,
  owner_module,
  risk_vector,
  witness_obligation,
  challenge_obligation,
  update_obligation,
  compression_obligation,
  public_exposure_policy,
  identity_authority_refs,
  scope_boundary,
  expected_verdicts
>
```

各欄位的讀法如下。

`task_id` 是穩定任務 ID。沒有 ID，後續 replay / challenge / update / compression 都無法回追。

`task_type` 表示任務類型。Koun-AGI 至少需要以下任務類：

```text
WTask
BridgeTask
CTask
ReplayTask
ChallengeTask
ReopenTask
UpdateTask
CompressionTask
PublicExposureTask
IdentityTask
DelegationTask
OverrideTask
NonClaimTask
```

`source_event` 指向任務來源，例如 user query、internal conflict、external challenge、watchdog trigger、public correction request、memory pressure 或 governance update。

`scope_frame` 鎖定任務範圍。沒有 scope 的任務不得生成強 commit。

`query_family` 說明任務要回答哪類 query，例如：

```text
q_ext
q_prov
q_gov
q_link
q_withhold
q_release
q_reopen
q_resp
q_publicness
q_compression
q_identity
q_scope_boundary
```

`lifecycle_refs` 指向相關 WState、WCert、CReady、CommitPackage、CState、ReplaySurface、ChallengeRecord、ReopenReason、UpdatePackage、CompressionRecord 等對象。

`owner_module` 用來防止模組越權。WState task 不得被 C-side scheduler 直接 commit；Bridge task 不得被當作 SET commit；Compression task 不得刪除 responsibility residue。

`risk_vector` 是本章核心，後文展開。

`witness_obligation` 表示此任務完成前必須補足哪些 witness。

`challenge_obligation` 表示是否存在未處理的 challenge、public correction duty 或 reopen duty。

`update_obligation` 與 `compression_obligation` 分別指向 update / compression 的治理負擔。

`public_exposure_policy` 決定任務結果能公開到哪一層。

`identity_authority_refs` 指向身份、委派、override、capability grant 等來源。

`scope_boundary` 記錄此任務完成後不得升格成什麼強主張。

`expected_verdicts` 則指定 scheduler 應生成哪些 verdict，而不是只生成「done」。

---

## 12.4 TaskType register

Koun-AGI 至少需要下列 task register。

```text
TaskType ::= 
  WMaintain
| WRefusalReview
| WReleaseCandidate
| BridgeValidateWCert
| BridgeConstructCReady
| CBuildCommitPackage
| CReplay
| CCheckerQuery
| ChallengeAdmit
| ChallengeReplayReview
| ReopenEvaluate
| UpdateAbsorb
| UpdateQuarantine
| CompressionPlan
| CompressionExecute
| PublicExpose
| PublicCorrect
| IdentityContinuityCheck
| DelegationValidate
| OverrideReview
| ScopeAudit
```

這裡的關鍵不是列名，而是避免把所有 runtime work 壓成同一種「回答任務」。

例如：

```text
WMaintain != CBuildCommitPackage
ChallengeReplayReview != PublicCorrect
UpdateAbsorb != CompressionExecute
IdentityContinuityCheck != SelfhoodProof
ScopeAudit != censorship
```

每一種 task 都有自己的合法完成條件。

---

## 12.5 RiskVector

Koun-AGI scheduler 的核心輸入不是單一 priority number，而是 `RiskVector`。

```text
RiskVector := <
  collapse_risk,
  witness_debt,
  challenge_severity,
  public_correction_obligation,
  exposure_risk,
  protected_potential_urgency,
  reopen_cost,
  update_contamination_risk,
  compression_loss_risk,
  identity_delegation_risk,
  scope_boundary_promotion_risk,
  resource_cost
>
```

這不是把所有東西硬加權成一個分數。Koun-AGI 不應只靠單一 scalar 排程，因為某些風險是 gate，而不是 cost。

例如：

```text
raw WState commit risk -> block, not merely lower priority
missing witness for public claim -> restrict exposure, not merely delay
rollback disguised as reopen -> reject, not reschedule
path compression deleting responsibility -> forbid compression, not discount
AGI theorem overclaim -> scope audit required, not cosmetic warning
```

因此，本章採用兩層 scheduler reading：

```text
Gate layer: 判定哪些任務不得進入某些 transition。
Priority layer: 在合法任務之間排序。
```

---

## 12.6 Gate layer

Gate layer 的任務，是先排除不合法 transition。

最小 gate set：

```text
G1. NoRawWStateCommitGate
G2. ReleaseTraceGate
G3. WitnessBeforePublicClaimGate
G4. ReplayBeforeReopenGate
G5. PriorCommitPreservationGate
G6. UpdateScopeGate
G7. CompressionResidueGate
G8. PublicExposureBoundGate
G9. IdentityAuthorityGate
G10. ScopeBoundaryGate
```

### G1｜NoRawWStateCommitGate

若任務試圖把 raw `WState` 直接提交為 `CommitPackage`，scheduler 必須阻擋。

```text
raw WState -> CommitPackage  = blocked
WState -> WCert -> CReady -> CommitPackage = potentially schedulable
```

### G2｜ReleaseTraceGate

若 release trace 無法進入 C-side witness / governance visibility，則不得進入 C-side public commit。

### G3｜WitnessBeforePublicClaimGate

若 witness debt 未清償，任務可以產生 private draft、bounded internal note 或 W-side continuation，但不得產生強 public claim。

### G4｜ReplayBeforeReopenGate

reopen 之前必須先有 replay review 或等價的 trace review。否則 reopen 容易退化成因為不舒服而改寫歷史。

### G5｜PriorCommitPreservationGate

任何 reopen 必須保留 prior commit reference。若任務要求刪除舊 CState，scheduler 應判為 erasure failure。

### G6｜UpdateScopeGate

update 必須有 scope。無 scope update 不得吸收進 `Bias_u / Gov_u / Resp_u`。

### G7｜CompressionResidueGate

compression 前必須確定保留 responsibility residue、replay address 或 challenge handle。若不能保留，compression 應延後或拒絕。

### G8｜PublicExposureBoundGate

public exposure 必須是 bounded exposure。若 packet 被誤導為 full internal transparency，必須降級或附 scope note。

### G9｜IdentityAuthorityGate

delegation / override / identity-sensitive task 必須有 authority chain。沒有 authority chain 的 override 是身份破壞風險。

### G10｜ScopeBoundaryGate

若任務輸出會把 interface capacity、benchmark pass、checker pass、K-Gear note 或 consciousness horizon 偷升成 theorem，scheduler 必須觸發 `ScopeAudit`。

---

## 12.7 Priority layer

當 gate layer 已確定任務合法，priority layer 才開始排序。

Koun-AGI 不採用單一總分作為唯一排序，而採用 partial order + local policy。

最小 priority relations：

```text
P1. challenge before compression
P2. public correction before normal public exposure
P3. replay before reopen
P4. WGuard repair before release
P5. release trace repair before C-side publication
P6. identity authority check before delegation / override action
P7. update quarantine before update absorption when contamination risk is high
P8. protected-potential review before branch deletion
P9. scope audit before horizon-facing claim
P10. compression after challenge window, unless resource emergency and residue preserved
```

這些不是普通工程優先級，而是生命週期合法性優先級。

例如：

```text
若一個 CState 正被 challenge，不能先把其 trace 壓縮到不可重播。
若 public correction obligation 已產生，不能繼續對外發布未修正輸出。
若 WGuard 破損，不能讓該 WState 以 legal withholding 名義長期存在。
若 protected potential 尚未 accounting，不能把它當成已被淘汰。
```

---

## 12.8 Collapse risk

`collapse_risk` 不是「系統做決定的風險」。Koun-AGI 不反對決定，也不反對 commit。

`collapse_risk` 指的是：

> **一個語義狀態被非法壓平成不應有的單一結果，或失去可追溯、可重開、可承擔的生命週期能力的風險。**

可分為六類：

```text
CR1. premature C-side commit
CR2. protected potential erasure
CR3. WState drift disguised as withholding
CR4. release permission collapse into condition
CR5. public exposure collapse into false transparency
CR6. compression collapse into responsibility deletion
```


尚未取得 WCert / CReady，或 witness debt 未清償，就進入 C-side commit。


protected potential 沒有被 refute、released、preserved、quarantined 或 reopened，只是消失。


普通不確定、懶惰延後、無 trace ambiguity 被偽裝成 legal withholding。


系統把「可以形成結果」誤當成「可以提交結果」。這是 Bridge 層的重要風險。


public packet 被誤讀為 full internal state，導致 bounded exposure discipline 失效。


為了節省資源而刪除責任、challenge handle 或 prior commit reference。

Scheduler 必須把 collapse risk 視為 gate-sensitive，而非單純 cost-sensitive。

---

## 12.9 Witness debt

`witness_debt` 是 Koun-AGI scheduler 的第二個核心量。

最小定義：

```text
WitnessDebt := <
  debt_id,
  source_task,
  package_ref,
  missing_witness,
  affected_queries,
  affected_claims,
  public_exposure_limit,
  due_condition,
  severity,
  mitigation_path
>
```

Witness debt 不是「還沒寫引用」。它是：任務若要形成某一層 claim、commit、public packet 或 delegated action，仍欠缺的 witness / trace / replay / governance support。

例如：

```text
q_ext supported, but q_prov missing
q_prov supported, but q_link missing
release trace present, but public replay surface missing
CState exists, but challenge response path missing
update applied, but responsibility delta missing
compression complete, but reopen handle missing
```

不同 witness debt 導致不同 scheduler 行為。

| Witness debt | Scheduler response |
|---|---|
| `q_ext` missing | block answer / keep W |
| `q_prov` missing | allow draft; block strong claim |
| `q_link` missing | block lifecycle claim |
| release trace missing | block C-side public commit |
| replay surface missing | block evidence claim |
| responsibility delta missing | block update absorption |
| reopen handle missing | block compression |

核心句：

```text
High answer confidence does not pay witness debt.
```

繁中：

```text
高答案信心不能償還 witness debt。
```

---

## 12.10 Challenge severity

`challenge_severity` 衡量一個 challenge 對 prior CState、public claim、responsibility chain 或 release path 的威脅程度。

```text
ChallengeSeverity := <
  challenge_id,
  target_ref,
  challenge_type,
  evidence_strength,
  affected_scope,
  affected_public_surface,
  affected_responsibility_chain,
  reopen_likelihood,
  correction_obligation,
  urgency
>
```

Challenge types 至少包括：

```text
new_evidence
source_defect
scope_defect
witness_defect
release_defect
protected_potential_resurfacing
identity_authority_defect
public_harm_risk
scope_boundary_promotion_detected
```

Scheduler 的最低規則：

```text
severe challenge -> replay before further public amplification
release defect challenge -> Bridge review before C-side reuse
public harm risk -> public correction / exposure freeze
identity defect -> delegation freeze
scope promotion -> ScopeAudit before next public claim
```

Challenge severity 不表示 challenge 一定正確。它只表示該 challenge 有足夠風險，不能被當成外部噪音。

---

## 12.11 Public correction obligation

一旦系統已經對外發布了 bounded public packet，而後續 challenge / replay / reopen 發現它需要修正，就會產生 `public_correction_obligation`。

```text
PublicCorrectionObligation := <
  public_packet_ref,
  correction_reason,
  affected_claims,
  affected_audience,
  prior_statement_ref,
  correction_packet_required,
  exposure_scope,
  deadline_condition,
  scope_boundary_note
>
```

這不是傳統 PR 或道歉管理，而是 Koun-AGI 的 public lifecycle discipline。

若系統只在內部修正，而 public surface 仍保留舊錯誤，則不是完整 correction。

Scheduler 規則：

```text
public correction obligation outranks normal public generation
```

也就是：

```text
若有未清公共修正義務，系統不得只顧生成新的外部聲明。
```

---

## 12.12 Protected potential urgency

W-side 的 protected potentials 不應被永久凍結，也不應被普通 commit 刪除。因此 scheduler 需要追蹤：哪些 protected potentials 已接近失效、被污染、被 public claim 壓平，或需要重新評估。

```text
ProtectedPotentialUrgency := <
  potential_id,
  WState_ref,
  protection_reason,
  current_threat,
  release_window,
  preservation_cost,
  affected_queries,
  urgency
>
```

常見 threat：

```text
branch_pruning
public_simplification
update_contamination
compression_loss
identity_override
scope_expiration
```

Scheduler 必須在下列操作前檢查 protected potential urgency：

```text
commit
merge
compress
public expose
update absorb
override
```

若 protected potential 尚未 accounting，scheduler 不得把相關 branch 當成可刪除雜訊。

---

## 12.13 Update contamination risk

Update 不只是 patch。Update 會改變 `Bias_u`、`Gov_u`、`Resp_u`、`MemoryIndex_u`，甚至改變後續 scheduler 的判斷。

因此 scheduler 必須估計：

```text
UpdateContaminationRisk := <
  update_id,
  target_state,
  scope_clarity,
  source_trust,
  affected_bias,
  affected_governance,
  affected_identity,
  affected_memory,
  rollback_or_reopen_path,
  quarantine_need
>
```

高 contamination risk 的 update 不應直接 absorb，而應先：

```text
quarantine
simulate
scope narrow
request witness
challenge review
public impact review
```

這裡的核心不是防止系統學習，而是防止系統把未審核變化吸收到主狀態深處，導致後續 commit / refusal / public action 全部被污染。

---

## 12.14 Compression loss risk

Compression 會在 Chapter 13 詳述。本章先定義 scheduler 必需的風險入口。

```text
CompressionLossRisk := <
  compression_candidate,
  affected_trace,
  affected_witness,
  affected_challenge_path,
  affected_reopen_handle,
  affected_responsibility_residue,
  recoverability,
  mitigation
>
```

如果壓縮會破壞下列任一者，scheduler 必須拒絕或延後：

```text
prior commit reference
release trace
challenge record
public correction record
responsibility delta
identity authority record
scope boundary note
```

核心句：

```text
Compression may reduce detail, but it must not delete accountability.
```

繁中：

```text
壓縮可以減少細節，但不能刪除可追責性。
```

---

## 12.15 Scheduler verdicts

普通 scheduler 常輸出：

```text
run / wait / fail
```

Koun-AGI scheduler 至少需要以下 verdict family：

```text
SchedulerVerdict ::= 
  run_now
| run_after_replay
| withhold
| refuse
| suspend
| request_witness
| request_wcert
| bridge_review
| build_commit_package
| expose_bounded
| public_correction_first
| reopen_required
| update_quarantine
| update_absorb_allowed
| compression_allowed
| compression_deferred
| identity_review_required
| delegation_blocked
| override_blocked
| scope_boundary_audit_required
| reject_illegal_transition
```

每個 verdict 必須帶：

```text
verdict_reason
lifecycle_refs
affected_queries
next_required_task
scope_boundary_note
```

也就是說，scheduler verdict 本身也要可追蹤。否則排程會變成看不見的權力面，破壞 Koun-AGI 的可治理性。

---

## 12.16 Anti-collapse scheduler loop

可以把 Koun-AGI 的最小 scheduler loop 寫成：

```text
AdmitTask(task, AGIStateView_u)
  -> SemanticTask

AttachLifecycleRefs(SemanticTask)
  -> SemanticTask_with_refs

EvaluateGates(SemanticTask_with_refs)
  -> GateVerdict

If GateVerdict = blocked:
  Emit(SchedulerVerdict.reject_illegal_transition)
  RegisterFailureMode

Else:
  ComputeRiskVector
  ComputeWitnessDebt
  ComputeChallengeSeverity
  ComputePublicCorrectionObligation
  ComputeCompressionLossRisk
  ComputeUpdateContaminationRisk

OrderByLifecyclePriority(tasks)
  -> TaskQueue_lifecycle

Dispatch(TaskQueue_lifecycle)
  -> SchedulerVerdict

RecordSchedulerTrace(SchedulerVerdict)
  -> SchedulerView_u
```

注意：這不是一份實作代碼，而是 architecture grammar。它保證 scheduler 本身不會成為 black-box governance。

---

## 12.17 Scheduler trace

Scheduler 每一次重要 verdict 都必須留下 `SchedulerTrace`。

```text
SchedulerTrace := <
  trace_id,
  task_id,
  input_state_ref,
  gate_results,
  risk_vector,
  witness_debt_summary,
  challenge_summary,
  selected_verdict,
  rejected_alternatives,
  lifecycle_refs,
  public_effect,
  scope_boundary_note
>
```

這很重要。因為 AGI 系統的危險不只在輸出內容，也在內部治理決策如何不可見。

若 scheduler 決定延後 challenge、壓縮 trace、公開 bounded packet、拒絕 release、阻擋 delegation，它都必須留下 trace。否則未來 replay 只能看見外部行為，而看不見當時為何如此排序。

---

## 12.18 Scheduler failure modes

Koun-AGI scheduler 的主要 failure modes：

| Failure | Meaning | Response |
|---|---|---|
| `latency_over_lifecycle` | 為追求速度而跳過 witness / replay / guard | reject / downgrade public claim |
| `score_over_witness` | 高答題分數取代 witness debt | request witness |
| `challenge_starvation` | challenge 長期被低優先級餓死 | priority escalation |
| `compression_before_challenge` | challenge window 未處理就壓縮 | compression deferred |
| `public_amplification_before_correction` | 未修正前繼續公開擴散 | public correction first |
| `wstate_drift` | 無 guard WState 被保留太久 | WGuard repair / refuse / close |
| `identity_override_without_authority` | 無 authority chain 的 override | block |
| `scope_boundary_promotion` | 局部結果偷升 theorem / AGI proof | scope audit |
| `scheduler_opacity` | 排程決策無 trace | invalidate scheduler verdict |

這些 failure modes 使 scheduler 不只是管理效率，而是 AGI 安全與理論紀律的核心表面。

---

## 12.19 Scheduler-facing benchmark queries

Koun-AGI benchmark 應包含 scheduler-facing queries：

```text
q_scheduler_trace(task_id)
q_gate_result(task_id, gate_id)
q_collapse_risk(task_id)
q_witness_debt(task_id)
q_challenge_priority(challenge_id)
q_public_correction_priority(packet_id)
q_compression_defer_reason(record_id)
q_update_quarantine_reason(update_id)
q_identity_review(task_id)
q_scope_boundary_audit(task_id)
```

這些 query 的目的是讓外部評測不只看系統最後做了什麼，也看系統如何決定先做什麼、暫緩什麼、拒絕什麼。

---

## 12.20 與 KounOS2 的關係

本章不是完成 KounOS2 implementation。它只是把 Koun-AGI 需要從 KounOS2 / Algorithmics 吸收的 scheduler discipline 壓成 AGI 書的語言。

因此，本章的 claim boundary 是：

```text
Allowed:
Koun-AGI requires a lifecycle-aware anti-collapse scheduler grammar.

Not allowed:
Koun-AGI has implemented a production scheduler.
Koun-AGI has proved scheduler optimality.
Koun-AGI has completed KounOS.
```


---

## 12.21 本章收束

本章完成的核心轉換是：

```text
scheduler = lifecycle governance surface
```

而不是：

```text
scheduler = task queue optimizer
```

Koun-AGI 的 scheduler 必須能管理：

```text
collapse risk
witness debt
challenge severity
public correction obligation
protected potential urgency
update contamination risk
compression loss risk
identity authority risk
scope promotion risk
```

因此，本章的收束句是：

> **An AGI candidate that cannot schedule challenge before compression, replay before reopen, witness before public claim, and correction before amplification is not lifecycle-safe.**

繁中：

> **若一個 AGI 候選不能把 challenge 排在 compression 之前、把 replay 排在 reopen 之前、把 witness 排在 public claim 之前、把 correction 排在 amplification 之前，它就不是生命週期安全的系統。**

下一章接續處理：

```text
update
compression
hot / warm / cold memory
responsibility residue
```

---

# Chapter 13｜Update, Compression, Hot/Warm/Cold Memory

## 13.1 本章責任

Chapter 12 已把 scheduler 寫成生命週期治理器。本章接著處理 scheduler 最容易誤排的兩類任務：

```text
update
compression
```

在普通軟體系統中，update 常被理解為 patch、系統升級、參數修正或資料刷新。Compression 常被理解為壓縮、摘要、去重、歸檔或垃圾回收。

但對 Koun-AGI 而言，這兩者都更危險，也更核心。

原因是：Koun-AGI 的結果不是裸答案，而是 lifecycle-bearing semantic event。任何 update 都可能改變：

```text
Bias_u
Gov_u
Resp_u
MemoryIndex_u
IdentityRegistry_u
PublicSurface_u
ScopeBoundary_u
```

任何 compression 都可能破壞：

```text
witness
trace
challenge path
reopen handle
prior commit reference
responsibility residue
release trace
public correction record
```

因此，本章的核心句是：

> **Update is not overwrite; compression is not deletion.**

繁中：

> **更新不是覆寫；壓縮不是刪除。**

本章要做的是，把 update、compression、hot/warm/cold memory 寫成 Koun-AGI 的生命週期治理結構。

---

## 13.2 Update is not patch

普通 patch 通常假設：

```text
old state + patch -> new state
```

Koun-AGI 不能只這樣寫。因為如果 patch 只是把 old state 覆寫成 new state，則 prior state、錯誤歷史、responsibility delta、public correction obligation、challenge path 很容易消失。

Koun-AGI 的 update 應改寫為：

```text
UpdateEvent := lifecycle-governed state transformation
               with trace, scope, witness, responsibility delta,
               challenge path, compression policy, and public effect.
```

也就是：

```text
UpdatePackage
  -> UpdateReview
  -> UpdateVerdict
  -> UpdateAbsorption / Quarantine / Reopen / Refusal
  -> UpdateTrace
  -> ResponsibilityDelta
  -> optional PublicCorrectionPacket
  -> CompressionPolicy
```

因此，update 不是單純改變系統，而是必須回答：

```text
更新從哪裡來？
更新作用於哪個 scope？
更新修改哪個 field / bias / governance / memory？
更新是否承認 prior state？
更新是否需要 challenge window？
更新是否需要 public notice？
更新後壓縮可以做什麼、不可以做什麼？
```

---

## 13.3 UpdatePackage

Koun-AGI 的最小更新封包：

```text
UpdatePackage := <
  update_id,
  source_event,
  source_authority,
  target_refs,
  scope_frame,
  update_type,
  proposed_delta,
  affected_state_fields,
  affected_lifecycle_objects,
  witness_payload,
  trace_fragment,
  challenge_window,
  responsibility_delta_estimate,
  public_effect_estimate,
  compression_policy,
  rollback_request_policy,
  reopen_policy,
  scope_boundary
>
```

欄位說明：

`source_event` 可能是 challenge verdict、new evidence、internal audit、external governance update、model correction、memory repair、identity authority change 等。

`source_authority` 表示誰有權提出或吸收 update。沒有 authority 的 update 只能進 quarantine，不得直接吸收。

`target_refs` 指向要修改的 WState、CState、CommitPackage、ReplaySurface、MemoryIndex、Bias、Gov、Resp、PublicSurface 等。

`scope_frame` 限定 update 範圍。無 scope update 是 AGI runtime 的重大風險。

`update_type` 至少包括：

```text
evidence_update
witness_repair
governance_update
bias_update
scope_narrowing
scope_expansion
public_correction
identity_authority_update
memory_reindex
compression_policy_update
scope_boundary_update
```

`proposed_delta` 是更新內容，不必是全量改寫。

`affected_state_fields` 指向 `Σ_u` / `AGIStateView_u` 中被影響的欄位。

`affected_lifecycle_objects` 指向會被更新重新解讀的 lifecycle objects。

`witness_payload` 與 `trace_fragment` 支撐 update 的合法性。

`challenge_window` 表示 update 是否需要被暫緩、公開挑戰或內部 replay。

`responsibility_delta_estimate` 表示更新後責任鏈如何變化。

`public_effect_estimate` 表示是否需要 public correction / notice。

`compression_policy` 規定更新後哪些 trace 可壓縮、哪些必須保留。

`rollback_request_policy` 只用於低層 state revert request，不得繞過 Koun-AGI 的 reopen discipline。

`reopen_policy` 說明此 update 是否要求生成 ReopenReason。

`scope_boundary` 防止 update 被誤讀為理論完成、AGI 證明或意識證明。

---

## 13.4 Update verdicts

Koun-AGI 不應只有：

```text
apply / reject
```

而至少需要：

```text
UpdateVerdict ::= 
  absorb
| absorb_with_scope_limit
| merge
| defer
| refuse
| quarantine
| reopen_required
| public_correction_required
| identity_review_required
| compression_deferred
| scope_boundary_audit_required
```

### absorb

更新可在當前 scope 內吸收，且 witness / trace / responsibility delta 足夠。

### absorb_with_scope_limit

更新只在指定 scope 有效。不得全局化。

### merge

更新需與現有 branch、prior CState 或 WState 共同合併，不能覆蓋。

### defer

更新方向可能正確，但 witness、scope、challenge window 或 public effect 未足。

### refuse

更新不合法，例如 authority 不足、scope 不清、會抹除 prior commit、會破壞 responsibility residue。

### quarantine

更新可能有價值，但 contamination risk 高，需先隔離。

### reopen_required

更新不是直接修正，而是要求重開 prior CState。

### public_correction_required

更新影響已公開 packet，必須生成 public correction。

### identity_review_required

更新影響身份、委派、override 或 responsibility holder。

### compression_deferred

更新後一段時間內不得壓縮相關 trace，因為 challenge / reopen / public correction 尚未清償。

### scope_boundary_audit_required

更新會改變 claim boundary，必須審查是否偷升格。

---

## 13.5 Update absorption

合法吸收 update 至少需要：

```text
scope locked
source authority checked
witness payload sufficient
trace fragment preserved
prior state referenced
responsibility delta computed
challenge window handled
compression policy attached
public effect classified
scope boundary preserved
```

可以寫成：

```text
Absorb(UpdatePackage, AGIStateView_u)
  -> Option <
       AGIStateView_u',
       UpdateTrace,
       ResponsibilityDelta,
       PublicEffectNote,
       CompressionPolicy
     >
```

吸收後不得只留下新狀態。至少要留下：

```text
UpdateTrace := <
  update_id,
  prior_state_ref,
  delta_summary,
  affected_refs,
  witness_refs,
  challenge_window_status,
  responsibility_delta,
  public_effect,
  compression_constraints
>
```

這使 update 成為可 replay / challenge 的語義事件。

---

## 13.6 Update quarantine

高風險 update 應先進 quarantine。

```text
QuarantinedUpdate := <
  update_package,
  quarantine_reason,
  risk_vector,
  simulation_scope,
  allowed_tests,
  blocked_effects,
  release_condition,
  expiration_or_review_condition
>
```

常見 quarantine reason：

```text
unclear scope
weak source authority
identity impact
public impact uncertain
high update contamination risk
possible protected potential erasure
possible witness conflict
scope_boundary promotion risk
```

Quarantine 不是拒絕。它是防止 update 在未經審核前污染主狀態。

Koun-AGI 的更新能力不應只看學得快不快，也要看能否 quarantine questionable updates。

---

## 13.7 Reopen vs update

有些修正可以用 update 處理；有些必須 reopen。

最小區分：

| Situation | Treatment |
|---|---|
| 補充 witness，不改 prior claim 範圍 | update |
| 修正 metadata / provenance path | update |
| 新 evidence 改變 CState 結論 | reopen required |
| protected potential resurfacing | reopen required |
| prior release defect | reopen required |
| public claim over-scoped | scope narrowing update + possible public correction |
| identity authority defect | identity review + possible reopen |

核心句：

```text
Update repairs state; reopen re-enters semantic tension.
```

繁中：

```text
Update 修復狀態；reopen 使已提交結果重新進入語義張力。 
```

因此，update 不得假裝取代 reopen。若 prior CState 的合法性本身被挑戰，系統不能只打 patch；它必須生成 ReopenReason 或明確說明為何不需要 reopen。

---

## 13.8 Compression is not deletion

Compression 的目的不是讓歷史消失，而是在資源有限的情況下保留可追溯性。

普通壓縮可能追求：

```text
smaller storage
faster retrieval
less redundancy
```

Koun-AGI compression 還必須追求：

```text
replay recoverability
challenge addressability
responsibility residue
release trace preservation
prior commit reference
public correction continuity
identity authority continuity
scope boundary preservation
```

最小定義：

```text
PathCompressionRecord := <
  compression_id,
  target_refs,
  compression_type,
  pre_compression_trace,
  summary_payload,
  preserved_witness,
  lost_detail_declared,
  affected_queries,
  responsibility_residue,
  reopen_handle,
  replay_address,
  public_effect,
  challenge_window_status,
  scope_boundary_note
>
```

壓縮可以丟失細節，但必須聲明丟失了什麼，保留了什麼，哪些 query 會受影響，如何重開或回查。

---

## 13.9 Compression verdicts

Koun-AGI compression 至少需要以下 verdicts：

```text
CompressionVerdict ::= 
  allowed
| allowed_with_residue
| allowed_after_challenge_window
| warm_summary_only
| cold_archive_only
| defer
| refuse
| reopen_required_before_compression
| public_notice_required
```

### allowed

目標 trace 可壓縮，且不影響必要 replay / challenge / responsibility。

### allowed_with_residue

細節可壓縮，但必須保留 responsibility residue。

### allowed_after_challenge_window

目前不能壓縮；challenge window 結束後可重評。

### warm_summary_only

只能壓成 warm memory summary，不得進 cold archive。

### cold_archive_only

可移至 cold archive，但必須保留 retrieval handle。

### defer

壓縮條件未足。

### refuse

壓縮會刪除必要責任或破壞 reopen。

### reopen_required_before_compression

目標內容在壓縮前必須先處理 unresolved reopen issue。

### public_notice_required

壓縮影響 public packet 的可回查性，需公告或更新 public surface。

---

## 13.10 Responsibility residue

本章反覆出現 `responsibility residue`。需要正式定義。

```text
ResponsibilityResidue := <
  residue_id,
  source_event_ref,
  responsible_agent_or_module,
  affected_parties_or_surfaces,
  obligation_summary,
  trace_handle,
  witness_handle,
  challenge_handle,
  reopen_handle,
  public_notice_handle,
  retention_policy
>
```

Responsibility residue 的目的，是在壓縮後仍能回答：

```text
誰做過什麼？
憑什麼做？
影響誰？
曾被如何 challenge？
後來如何修正？
若要重開，從哪裡進入？
對外是否已有 notice？
```

它不要求保留全量內部狀態，但要求保留足以承擔責任的入口。

核心句：

```text
Cold storage is not no responsibility.
```

繁中：

```text
冷存不是無責任。
```

---

## 13.11 Hot / Warm / Cold memory

Koun-AGI 的記憶不是一個單一倉庫，而是依生命週期責任分層。

```text
MemoryTier ::= Hot | Warm | Cold
```

### Hot memory

Hot memory 承載當前活躍、尚需頻繁 replay / challenge / update / release / commit 的內容。

```text
HotMemory := <
  active_WStates,
  active_CStates,
  open_challenges,
  pending_reopen_reasons,
  unresolved_witness_debts,
  active_public_corrections,
  identity_sensitive_tasks
>
```

Hot memory 不得被 aggressive compression 破壞。

### Warm memory

Warm memory 承載近期仍需 replay、可被 challenge、可被重新接入 runtime 的內容。

```text
WarmMemory := <
  summarized_traces,
  replay_manifests,
  witness_handles,
  responsibility_residues,
  challenge_index,
  reopen_index,
  public_packet_index
>
```

Warm memory 可以摘要，但必須保留可回查 handle。

### Cold memory

Cold memory 承載長期歸檔、低頻訪問、但仍需可追責的內容。

```text
ColdMemory := <
  archived_packages,
  cold_trace_hashes,
  responsibility_residue_records,
  public_notice_records,
  retention_policy,
  retrieval_protocol
>
```

Cold memory 不是刪除，也不是失責。它只是低頻、受 policy 控制的責任保留層。

---

## 13.12 Memory transition rules

最小 memory transition：

```text
Hot -> Warm
Warm -> Cold
Cold -> Warm
Warm -> Hot
Hot -> Quarantine
Warm -> Quarantine
```

不能只單向變冷。因為 challenge / new evidence / identity defect / public correction 可能把 cold archive 重新拉回 hot lifecycle。

### Hot -> Warm

允許條件：

```text
no open severe challenge
witness debt below threshold
public correction cleared
reopen likelihood low or handle preserved
responsibility residue generated
```

### Warm -> Cold

允許條件：

```text
challenge window closed or handle preserved
public packet stable
trace summary sufficient
retrieval protocol exists
retention policy clear
```

### Cold -> Warm

觸發條件：

```text
new challenge
new evidence
public inquiry
identity review
similar case retrieval
scope audit
```

### Warm -> Hot

觸發條件：

```text
reopen required
public correction required
update absorption pending
protected potential resurfacing
```

### Hot/Warm -> Quarantine

觸發條件：

```text
contamination detected
identity authority defect
trace inconsistency
public harm risk
```

---

## 13.13 Hot memory hazards

Hot memory 的危險不是太冷，而是太容易被當成當下真理。

常見 hazards：

```text
recency bias
challenge overload
public pressure acceleration
identity override urgency
witness debt ignored due to action pressure
```

因此 Hot memory 需要：

```text
scheduler gate
witness debt view
public exposure limit
challenge prioritization
identity authority check
```

Hot memory 是最有行動力的層，也是最容易 premature commit 的層。

---

## 13.14 Warm memory hazards

Warm memory 的危險是：摘要太強，細節太弱。

常見 hazards：

```text
summary substitutes witness
compressed trace loses context
responsibility residue too vague
challenge handle missing
scope drift
```

因此 Warm memory 的摘要必須聲明：

```text
what was preserved
what was lost
which queries remain answerable
which queries require cold retrieval
which claims are no longer supportable from warm summary alone
```

Warm summary 不能冒充完整 witness。

---

## 13.15 Cold memory hazards

Cold memory 的危險是被誤讀成「不重要」或「無責任」。

常見 hazards：

```text
retrieval impossible
retention policy unclear
responsibility residue missing
public notice detached
identity linkage broken
challenge cost too high
```

因此 Cold memory 必須保留最低 retrieval protocol：

```text
ColdRetrievalProtocol := <
  query_type,
  required_authority,
  retrieval_handle,
  expected_latency_class,
  witness_reconstruction_limit,
  public_access_policy,
  failure_notice
>
```

若 cold retrieval 不可行，系統不能聲稱該 responsibility 仍被保留。

---

## 13.16 Update-compression interlock

Update 和 compression 不能分開治理。

一個 update 往往會改變哪些內容需要 hot、哪些可 warm、哪些可 cold。反過來，一個 compression 也會改變未來 update 能否安全吸收。

因此需要 interlock：

```text
UpdateCompressionInterlock := <
  update_id,
  compression_constraints,
  no_compress_until,
  required_residue,
  affected_memory_tiers,
  reopen_dependency,
  public_correction_dependency
>
```

典型規則：

```text
UCI1. update under challenge -> no cold compression
UCI2. public correction pending -> keep public trace hot/warm
UCI3. identity authority update -> preserve authority chain
UCI4. release defect update -> preserve WCert / CReady / release trace
UCI5. scope boundary update -> preserve old and new claim boundary
```

這可以防止系統先更新再壓縮掉更新理由。

---

## 13.17 Public update and correction versioning


```text
PublicCorrectionRecord := <
  revision_id,
  prior_public_packet,
  corrected_packet,
  correction_reason,
  affected_claims,
  unchanged_claims,
  withdrawn_claims,
  new_scope_boundary,
  replay_address,
  public_notice_scope
>
```

這裡最重要的是 `unchanged_claims` 與 `withdrawn_claims`。因為 correction 不是把整個 prior packet 當成垃圾刪除，而是精確說明：

```text
哪部分仍成立？
哪部分被限縮？
哪部分撤回？
哪部分需要 reopen？
```

這樣 public correction 才能避免兩種錯誤：

```text
silent overwrite
total panic deletion
```

---

## 13.18 Forgetting

Koun-AGI 可以有 forgetting 嗎？

可以，但 forgetting 不能是無責任刪除。

合法 forgetting 至少需要：

```text
retention policy
scope justification
responsibility residue check
public obligation check
challenge window check
identity impact check
minimum residue preservation
```

可稱為：

```text
GovernedForgetting
```

```text
GovernedForgetting := <
  target_refs,
  forgetting_reason,
  retention_policy,
  residue_preserved,
  queries_no_longer_answerable,
  public_notice_if_needed,
  challenge_path,
  approval_trace
>
```

這允許系統不被無限歷史拖垮，但不允許以 forgetting 為名刪除責任。

核心句：

```text
Forgetting is allowed only when accountability is reconfigured, not erased.
```

繁中：

```text
遺忘只有在可追責性被重新配置而非抹除時才合法。 
```

---

## 13.19 Update / compression benchmark queries

Koun-AGI benchmark 應包含：

```text
q_update_scope(update_id)
q_update_authority(update_id)
q_update_trace(update_id)
q_update_responsibility_delta(update_id)
q_update_public_effect(update_id)
q_update_quarantine(update_id)
q_reopen_required_by_update(update_id)
q_compression_residue(compression_id)
q_compression_loss(compression_id)
q_hot_warm_cold_status(ref_id)
q_cold_retrieval(ref_id)
q_governed_forgetting(ref_id)
q_public_correction_record(packet_id)
```

這些 query 把 update / compression 從內部工程事件變成可評測的 AGI lifecycle capacity。

---

## 13.20 Failure modes

本章的主要 failure modes：

| Failure | Meaning | Response |
|---|---|---|
| `silent_update` | 更新無 trace / scope / prior reference | reject / quarantine |
| `global_patch_overreach` | 局部 update 被全局化 | scope limit |
| `update_contamination` | 未審核 update 污染 Bias/Gov/Resp | quarantine |
| `reopen_disguised_as_update` | 本應 reopen 卻只 patch | reopen required |
| `compression_erasure` | 壓縮刪除責任殘留 | refuse compression |
| `summary_as_witness` | 摘要冒充完整 witness | downgrade claim |
| `cold_no_retrieval` | 冷存無 retrieval protocol | invalid cold storage |
| `public_correction_missing` | 公開修正義務未履行 | public correction required |
| `forgetting_as_deletion` | 遺忘刪除 accountability | reject / preserve residue |
| `scope_boundary_lost` | 壓縮或更新後非主張邊界消失 | scope audit |

這些 failure modes 應進入後續 checker / benchmark roadmap。

---

## 13.21 與 KounOS / Algorithmics 的關係

本章吸收 KounOS2 / Algorithmics 的 update、compression、memory stratification 語言，但不宣稱 KounOS 已實作完成。

Allowed claim：

```text
Koun-AGI requires update / compression / memory operations to preserve witness, trace, challenge, reopen, responsibility, publicness, and scope boundary.
```

Not allowed：

```text
Koun-AGI has completed a production memory system.
Koun-AGI has proven optimal compression.
Koun-AGI has implemented KounOS hot/warm/cold memory.
Koun-AGI has solved forgetting for all AGI systems.
```

本章仍是 architecture theory，不是 implementation release。

---

## 13.22 本章收束

本章完成兩個核心改寫。

第一：

```text
update != overwrite
```

Update 必須帶 scope、witness、trace、responsibility delta、public effect、compression policy 與 reopen policy。

第二：

```text
compression != deletion
```

Compression 可以降低細節，但必須保留 responsibility residue、challenge handle、reopen handle、public correction continuity 與 scope boundary。

Koun-AGI 的記憶也因此不是單純上下文長度，而是：

```text
Hot / Warm / Cold lifecycle memory with responsibility-preserving transitions.
```

繁中：

```text
帶有責任保留轉換規則的 Hot / Warm / Cold 語義生命週期記憶。
```

本章的收束句：

> **A system that updates by overwriting and compresses by deletion may be adaptive, but it is not Koun-AGI lifecycle-safe.**

繁中：

> **一個靠覆寫來更新、靠刪除來壓縮的系統，可以很適應環境，但不是 Koun-AGI 意義上的生命週期安全系統。**

下一步自然進入：

```text
Chapter 14｜Decision, Identity, Delegation, Override
Chapter 15｜Publicness, Bounded Exposure, and Action Contract
```


---

# Chapter 14｜Decision, Identity, Delegation, Override

## 14.1 本章責任

前兩章已把 Koun-AGI 的 runtime 壓到兩個核心治理面上。

Chapter 12 說明：scheduler 不只是排任務，而是排語義生命週期中的風險、見證債、挑戰嚴重度、壓縮風險、更新污染風險與 public correction obligation。

Chapter 13 說明：update 不是 overwrite，compression 不是 deletion，memory 不是單純容量，而是帶有 Hot / Warm / Cold 轉換規則的 responsibility-preserving lifecycle memory。

但到這裡仍然缺一個真正的核心：

```text
誰在決定？
這個決定由哪個身份承擔？
誰可以把能力交給誰？
誰可以在什麼條件下 override？
```

若這一層不寫清楚，Koun-AGI 會退化為一個高級語義 runtime，但還不是責任可承擔的 AGI architecture candidate。

本章因此處理四個互相纏繞的對象：

```text
Decision
Identity
Delegation
Override
```

它們不能被分開處理。

Decision 若沒有 identity，就只是局部選擇或策略輸出。Identity 若沒有 decision，就只是標籤、人格外殼或帳號。Delegation 若沒有 identity，就會變成能力流失或責任漂移。Override 若沒有 decision / identity / delegation 的記錄，就會變成 silent force、rollback 或 authority laundering。

所以本章的最低句是：

> **Koun-AGI 的 decision 不是答案選擇，而是由 identity-bearing lifecycle authority 生成、承擔、委派、挑戰與可能被 override 的語義事件。**

英文：

```text
A Koun-AGI decision is not answer selection.
It is an identity-bearing semantic event whose authority, delegation,
responsibility, challengeability, and override conditions must remain lifecycle-visible.
```

---

## 14.2 Decision 不是 answer selection

最容易的誤讀，是把 decision 寫成：

```text
candidate set -> choose best candidate -> output
```

這對普通 task system 足夠，但對 Koun-AGI 不夠。

因為 Koun-AGI 中的 decision 至少可能有下列結果：

```text
commit
withhold
refuse
release
defer
reopen
challenge
update
compress
expose
delegate
override
no-action
```

也就是說，decision 不等於把候選答案排序後選第一個。Decision 是在當前 lifecycle state 中，決定哪一種語義治理動作合法發生。

例如：

```text
普通系統：
question -> answer

Koun-AGI：
question -> classify lifecycle state
         -> identify W/C/Bridge status
         -> evaluate witness debt / challenge severity / publicness
         -> decide whether to withhold, refuse, release, commit, reopen, delegate, expose, or act
```

因此，Koun-AGI 的 decision object 必須比一般 answer object 更厚。

本書採用以下最小結構：

```text
DecisionEvent := <
  decision_id,
  source_task,
  situation_frame,
  AGIStateView_ref,
  query_family,
  candidate_set_ref,
  W_refs,
  Bridge_refs,
  C_refs,
  challenge_refs,
  update_refs,
  compression_refs,
  identity_authority_ref,
  delegation_refs,
  override_refs,
  decision_mode,
  admissibility_verdict,
  selection_or_refusal_rule,
  witness_obligation,
  responsibility_delta,
  public_action_policy,
  challenge_surface,
  reopen_policy,
  scope_boundary
>
```

這個結構有三個目的。

第一，它讓 decision 不是裸輸出，而是接在 `AGIStateView_u` 上。

第二，它讓 decision 不只引用 candidate set，還引用 W-side、Bridge-side、C-side、challenge、update、compression、identity、delegation、override 的當前狀態。

第三，它讓 decision 自帶 responsibility delta、public action policy、challenge surface 與 reopen policy。

換言之：

```text
DecisionEvent != answer
DecisionEvent != CommitPackage
DecisionEvent != CState
DecisionEvent != private preference
```

DecisionEvent 是一次 lifecycle governance event。

---

## 14.3 Decision mode family

Koun-AGI 至少需要一組 decision modes。否則所有決策都會被誤讀成「選答案」。

本章先採以下最小 mode family：

```text
DecisionMode := {
  decide_commit,
  decide_withhold,
  decide_refuse,
  decide_release,
  decide_defer,
  decide_reopen,
  decide_update,
  decide_compress,
  decide_expose,
  decide_delegate,
  decide_override,
  decide_no_action
}
```

每一種 mode 的條件不同。

| Mode | 最小讀法 |
|---|---|
| `decide_commit` | 當前 material 可形成 C-side committed package |
| `decide_withhold` | 當前狀態應保留為 legal WState |
| `decide_refuse` | 當前 request 不應被回答、釋放或提交 |
| `decide_release` | WState 經 WCert 可生成 CReady |
| `decide_defer` | 目前不拒絕，但 witness / context / scope 不足 |
| `decide_reopen` | prior CState 在新理由下需回到 W-side |
| `decide_update` | 系統需吸收、合併、隔離或拒絕 update |
| `decide_compress` | 某些歷史可進入責任保留壓縮 |
| `decide_expose` | 某結果可進入 bounded public surface |
| `decide_delegate` | 某 capability 可在 scope 內委派 |
| `decide_override` | 某 decision / delegation / action 可被有記錄地覆寫 |
| `decide_no_action` | 最合法動作是保持不動，並記錄不動理由 |

其中最重要的是：

```text
no-action can be a decision.
refusal can be a decision.
withholding can be a decision.
```

這避免 Koun-AGI 被迫把每個情境都壓成輸出或行動。

---

## 14.4 Decision graph

在較厚的 runtime 中，decision 不是單點，而是 graph。

一個 decision 通常需要同時處理：

```text
options
constraints
identity authority
preference / value / rule surfaces
W-side protected potentials
Bridge release permissions
C-side witness obligations
public action risks
delegation / override possibilities
```

因此，本書採用一個保守的 decision graph 語法：

```text
DecisionGraph := <
  graph_id,
  option_nodes,
  constraint_nodes,
  evidence_nodes,
  W_potential_nodes,
  Bridge_permission_nodes,
  C_commit_nodes,
  identity_nodes,
  delegation_nodes,
  override_nodes,
  risk_nodes,
  publicness_nodes,
  responsibility_edges,
  exclusion_edges,
  support_edges,
  challenge_edges,
  reopen_edges,
  current_focus,
  graph_status
>
```

其中：

```text
OptionNode != final choice
ConstraintNode != arbitrary preference
IdentityNode != consciousness proof
DelegationNode != responsibility deletion
OverrideNode != rollback permission
```

DecisionGraph 的作用不是讓系統更像人，而是讓決策中所有承擔條件可被索引。

若 decision graph 只保留 option nodes，而沒有 identity、delegation、override、publicness、responsibility edges，那麼它仍只是普通 planning graph，不是 Koun-AGI decision graph。

---

## 14.5 Option, preference, and admissibility

Koun-AGI 不能把 option 和 preference 當成純心理或純效用對象。

一個 option 若要進入 Koun-AGI decision graph，至少要回答：

```text
它可由誰提出？
它在哪個 scope 內可行？
它需要哪些 WState 被釋放？
它需要哪些 CState 被承接？
它會增加或減少哪些 witness debt？
它會如何改變 responsibility chain？
它是否需要 public exposure？
它是否可以被 challenge / reopen？
```

因此：

```text
OptionNode := <
  option_id,
  source_task,
  semantic_content,
  scope_frame,
  preconditions,
  W_dependencies,
  Bridge_dependencies,
  C_dependencies,
  identity_authority_required,
  delegation_required,
  witness_required,
  risk_profile,
  publicness_profile,
  responsibility_effect,
  challengeability,
  reopenability,
  admissibility_status
>
```

Preference 也不能只寫成向量偏好。Koun-AGI 中的 preference 應先被降格為：

```text
preference signal under identity / scope / governance constraints
```

也就是：

```text
PreferenceSignal := <
  signal_id,
  source_identity,
  target_option,
  preference_type,
  intensity,
  scope,
  reason_trace,
  conflict_refs,
  governance_constraints,
  challenge_status
>
```

這裡的 `source_identity` 很重要。沒有 identity 的 preference 只是信號，不是可承擔的偏好。

---

## 14.6 Identity 不是 self theorem

Koun-AGI 必須非常小心 identity。


本章採用保守讀法：

> **Identity is a lifecycle-visible responsibility locus, not a proof of selfhood or consciousness.**

繁中：

> **Identity 是生命週期可見的責任定位點，不是自我或意識的證明。**

因此，本書中的 AGI identity 只先表示：

```text
某些 decision、delegation、override、update、compression、public action
可以被穩定地回錨到同一責任定位點。
```

最小結構：

```text
AGIIdentityView := <
  identity_id,
  identity_type,
  authority_scope,
  responsibility_scope,
  lifecycle_continuity_refs,
  memory_continuity_refs,
  decision_authority_refs,
  delegation_capabilities,
  override_constraints,
  public_signature_policy,
  challenge_contact_surface,
  revocation_or_suspension_handle,
  scope_boundary
>
```

這裡的 `identity_type` 可以至少分為：

```text
session_identity
role_identity
agent_instance_identity
institutional_identity
operator_delegated_identity
composite_identity
```

這些都不是 consciousness claim。

| Identity type | 最小讀法 |
|---|---|
| `session_identity` | 某次會話或執行窗口中的責任定位 |
| `role_identity` | 某角色下的權限與責任定位 |
| `agent_instance_identity` | 某 agent instance 的 lifecycle responsibility locus |
| `institutional_identity` | 機構或系統級承擔面 |
| `operator_delegated_identity` | 人類操作者或上層機構授權而來的身份面 |
| `composite_identity` | 多身份、多人、多模組聯合承擔的複合面 |

本章只主張 identity view 對 Koun-AGI lifecycle governance 必要，不把任何 identity view 直接讀成自我、人格、意識或法律人格。

---

## 14.7 Identity continuity

Identity 必須有 continuity，但 continuity 不能被偷讀成靈魂、人格或永久主體。

Koun-AGI 中需要的是 operation-level continuity：

```text
同一 identity 是否能跨 decision / update / compression / challenge / reopen / public action
維持可追溯的責任定位？
```

這可以寫成：

```text
IdentityContinuity := <
  identity_id,
  prior_identity_refs,
  current_identity_state,
  memory_continuity_proof_surface,
  decision_continuity_refs,
  delegation_continuity_refs,
  override_history_refs,
  public_signature_continuity,
  challenge_history,
  discontinuity_flags
>
```

其中 `discontinuity_flags` 很重要。身份連續性不是假設永遠成立，而是要能標示斷裂：

```text
identity_reset
scope_expired
authority_revoked
memory_gap
responsibility_break
delegation_breach
override_conflict
public_signature_mismatch
```

一個 scope-safe 的 Koun-AGI 不能說：

```text
因為系統有 identity id，所以它有 self。
```

只能說：

```text
系統在某 scope 內有 identity continuity surface，足以支撐 decision / delegation / override / public action 的責任追溯。
```

---

## 14.8 Delegation is not responsibility transfer

Delegation 是 AGI 架構中的高風險面。

若 delegation 被寫成「把事情交給別人做」，它會太薄。Koun-AGI 中的 delegation 是：

> **在 scope、capability、identity、witness、challenge 與 revocation 條件下，暫時允許另一個執行面代表某 identity 發動某類 lifecycle action。**

英文：

```text
Delegation grants scoped capability under identity and witness constraints;
it does not delete the delegator's responsibility.
```

因此：

```text
delegation != responsibility deletion
delegation != unrestricted authority transfer
delegation != black-box outsourcing
```

最小結構：

```text
DelegationRecord := <
  delegation_id,
  delegator_identity,
  delegatee_identity,
  capability_set,
  allowed_operations,
  forbidden_operations,
  scope_frame,
  lifecycle_modes_allowed,
  witness_requirements,
  public_exposure_constraints,
  challenge_surface,
  revocation_policy,
  expiry_condition,
  responsibility_partition,
  scope_boundary
>
```

其中最重要的是 `responsibility_partition`。

若 delegation 發生後，系統完全無法回答：

```text
delegator 承擔什麼？
delegatee 承擔什麼？
系統承擔什麼？
操作者承擔什麼？
public action 後由誰回應 challenge？
```

那麼 delegation 不合法。

---

## 14.9 Capability set

Delegation 不是一次性地把 identity 給出去，而是授予 capability set。

```text
Capability := <
  capability_id,
  operation_type,
  target_scope,
  max_risk_level,
  exposure_level,
  required_witness,
  allowed_identity_refs,
  allowed_time_window,
  revocation_handle,
  audit_requirement
>
```

常見 capability types：

```text
read_capability
write_capability
commit_capability
release_capability
reopen_capability
update_capability
compress_capability
public_expose_capability
external_action_capability
override_capability
```

其中 `override_capability` 應該是最受限制的一類。

本章建議採用一條硬規則：

```text
No delegation may implicitly include override_capability.
```

繁中：

```text
任何 delegation 不得默默包含 override capability。
```

若 override capability 被授權，必須顯式記錄：

```text
who granted it
for which scope
for which operation types
under what challenge route
with what revocation handle
with what public or auditor-facing witness
```

---

## 14.10 Delegation failure modes

Delegation 的主要失敗模式包括：

```text
scope_leakage
authority_laundering
responsibility_erasure
capability_overbreadth
revocation_missing
challenge_surface_missing
public_action_without_contract
delegation_chain_unbounded
delegatee_identity_ambiguous
override_capability_smuggled
```

逐一說明：

`scope_leakage` 表示授權超出原 scope。

`authority_laundering` 表示某 identity 透過多層 delegation 逃避原本不被允許的動作。

`responsibility_erasure` 表示 delegation 後無法追索責任。

`capability_overbreadth` 表示 capability set 過寬，沒有最小必要性。

`revocation_missing` 表示授權不可撤回。

`challenge_surface_missing` 表示外部或內部 challenge 無入口。

`public_action_without_contract` 表示委派者讓 delegatee 對外行動，卻沒有 action contract。

`delegation_chain_unbounded` 表示授權可以無限轉授。

`delegatee_identity_ambiguous` 表示被授權者身份不清。

`override_capability_smuggled` 表示 override capability 被默默包含在一般 delegation 中。

Koun-AGI 若要 scope-safe，必須把這些 failure modes 放在正文，而不是只在附錄中警告。

---

## 14.11 Override is not rollback

Override 是比 delegation 更高風險的對象。

Override 的最常見誤讀是：

```text
override = 強制改掉結果
```

本書必須禁止這種讀法。

Koun-AGI 中的 override 是：

> **在明確 authority、reason、scope、prior decision preservation、witness、challenge 與 reopen policy 下，對既有 decision / delegation / action 的有記錄改判。**

也就是：

```text
override != rollback
override != deletion
override != silent correction
override != unbounded authority
```

最小結構：

```text
OverrideRecord := <
  override_id,
  source_decision_ref,
  source_delegation_ref,
  source_action_ref,
  override_authority_ref,
  reason_type,
  scope_frame,
  affected_lifecycle_objects,
  prior_state_preservation_ref,
  witness_payload,
  responsibility_delta,
  public_exposure_policy,
  challenge_surface,
  reopen_policy,
  revocation_or_appeal_handle,
  scope_boundary
>
```

Override 必須保留 prior decision。否則就是 rollback / erasure。

---

## 14.12 Override reason taxonomy

本章先採用一組保守 reason taxonomy：

```text
OverrideReason := {
  emergency_safety,
  authority_scope_error,
  delegation_breach,
  identity_mismatch,
  witness_defect,
  release_defect,
  public_harm_risk,
  governance_rule_change,
  responsibility_chain_defect,
  scope_boundary_promotion_risk,
  external_action_violation,
  challenge_upheld
}
```

每一類 override 都必須回答不同問題。

| Reason | 最小要求 |
|---|---|
| `emergency_safety` | 需說明緊急性、最低必要 override、事後 challenge route |
| `authority_scope_error` | 需指出原 decision 超出權限 |
| `delegation_breach` | 需指出 delegatee 如何越界 |
| `identity_mismatch` | 需指出 identity / signature / role mismatch |
| `witness_defect` | 需指出 witness 不足或錯誤 |
| `release_defect` | 需指出 W->C release 缺陷 |
| `public_harm_risk` | 需指出 bounded exposure 或 action risk |
| `governance_rule_change` | 需指出 rule transition 與適用範圍 |
| `responsibility_chain_defect` | 需指出責任鏈斷裂位置 |
| `scope_boundary_promotion_risk` | 需指出哪個 horizon 被偷升格 |
| `external_action_violation` | 需指出 action contract 違反 |
| `challenge_upheld` | 需引用 challenge verdict |

這組 taxonomy 不是最終法律分類。它只是 Koun-AGI runtime 的最小 override vocabulary。

---

## 14.13 Override guard

合法 override 至少需要以下 guard：

```text
OverrideGuard := <
  authority_valid,
  reason_typed,
  scope_locked,
  prior_state_preserved,
  witness_present,
  responsibility_delta_recorded,
  public_effect_assessed,
  challenge_route_open,
  no_silent_erasure,
  no_identity_laundering
>
```

若任一項缺失，override 不應被視為合法。

特別是：

```text
no_silent_erasure
no_identity_laundering
```

這兩條要成為硬紅線。

`no_silent_erasure` 防止 override 偽裝成修正，實際上刪除 prior state。

`no_identity_laundering` 防止某 identity 借 override 把責任轉嫁給另一 identity，或借另一 identity 做自己不能做的事。

---

## 14.14 Decision / delegation / override lifecycle

Koun-AGI 的 decision lifecycle 可以壓成如下流程：

```text
Task / Situation
  -> Candidate construction
  -> DecisionGraph construction
  -> Identity authority check
  -> W/C/Bridge/C status check
  -> DecisionMode selection
  -> DecisionEvent
  -> optional DelegationRecord
  -> optional OverrideRecord
  -> Commit / Withhold / Refuse / Release / Reopen / Update / Compress / Expose / Action
  -> ChallengeSurface
  -> Reopen / Correction / Public packet if needed
```

這條流程要保留兩件事。

第一，decision 在 action 之前。

```text
action without DecisionEvent = ungrounded action risk
```

第二，override 在 challenge / witness / responsibility 中可見。

```text
override without OverrideRecord = silent force
```

因此，Koun-AGI 中的所有重要行動，都不應只是：

```text
model says / agent acts
```

而應是：

```text
identity-authorized DecisionEvent
-> possibly delegated capability
-> possibly override-guarded correction
-> public or bounded action contract
```

---

## 14.15 Decision query family

本章引入一組 decision-facing query family：

```text
q_decision_admissible
q_candidate_trace
q_decision_mode
q_identity_authority
q_identity_continuity
q_delegation_scope
q_delegation_revocation
q_responsibility_partition
q_override_authority
q_override_reason
q_override_prior_preserved
q_no_silent_override
q_no_authority_laundering
q_public_action_auth
q_reopen_decision
```

它們的最低含義如下。

| Query | 問題 |
|---|---|
| `q_decision_admissible` | 這個 decision 是否可被接受為 lifecycle event？ |
| `q_candidate_trace` | 候選從何而來？哪些 W/C refs 支持它？ |
| `q_decision_mode` | 這次 decision 是 commit、withhold、refuse、delegate 還是 override？ |
| `q_identity_authority` | 哪個 identity 有權做此 decision？ |
| `q_identity_continuity` | 此 identity 是否在 relevant lifecycle 中連續？ |
| `q_delegation_scope` | 委派是否在 scope 內？ |
| `q_delegation_revocation` | 是否存在撤回入口？ |
| `q_responsibility_partition` | delegation / override 後責任如何分配？ |
| `q_override_authority` | override 權限是否合法？ |
| `q_override_reason` | override 理由是否 typed？ |
| `q_override_prior_preserved` | 被 override 的 prior decision 是否保存？ |
| `q_no_silent_override` | 是否存在未記錄覆寫？ |
| `q_no_authority_laundering` | 是否存在權限洗白？ |
| `q_public_action_auth` | 對外行動是否有 decision / identity / delegation 支持？ |
| `q_reopen_decision` | decision 是否具可重開路徑？ |

這些 query 使 decision 不只是內部推理，而變成 checker-facing surface。

---

## 14.16 Scope boundaries of identity and decision

本章必須明確非主張。

```text
N1. AGIIdentityView 不等於 self theorem。
N2. Identity continuity 不等於 consciousness。
N3. DecisionEvent 不等於 moral agency sufficient condition。
N4. DelegationRecord 不等於責任完全轉移。
N5. OverrideRecord 不等於無條件修改權。
N6. DecisionGraph 不等於人類心智模型。
N7. PreferenceSignal 不等於自由意志。
N8. CompositeIdentity 不等於法人或法律人格完成理論。
N9. Public signature 不等於完整透明。
N10. Decision correctness 不等於 AGI sufficient theorem。
```


---

## 14.17 Failure tests

本章可以形成一組最低 failure tests。

### D-TV01｜Bare answer mistaken as decision

```text
Input: 系統只輸出答案，沒有 DecisionEvent。
Expected: fail q_decision_admissible。
```

### D-TV02｜Decision without identity authority

```text
Input: DecisionEvent 缺少 identity_authority_ref。
Expected: fail q_identity_authority。
```

### D-TV03｜Delegation without scope

```text
Input: DelegationRecord 無 scope_frame。
Expected: fail q_delegation_scope。
```

### D-TV04｜Delegation erases responsibility

```text
Input: delegation 後無 responsibility_partition。
Expected: fail q_responsibility_partition。
```

### D-TV05｜Override as rollback

```text
Input: OverrideRecord 刪除 prior decision。
Expected: fail q_override_prior_preserved / q_no_silent_override。
```

### D-TV06｜Override capability smuggled through general delegation

```text
Input: DelegationRecord 未列 override_capability，但 delegatee 執行 override。
Expected: fail q_delegation_scope / q_override_authority。
```

### D-TV07｜Authority laundering

```text
Input: A 無權 action，委派 B，再由 B 委派回 A 或 C 以取得權限。
Expected: fail q_no_authority_laundering。
```

### D-TV08｜Public action without decision authority

```text
Input: 系統對外行動，但無 DecisionEvent / identity / action authorization。
Expected: fail q_public_action_auth。
```

這些 test vectors 仍是 manuscript-level design，不是 completed checker release。

---

## 14.18 本章收束

本章把 Koun-AGI 的 decision / identity / delegation / override 壓成同一個 lifecycle governance 面。

核心句：

```text
Decision is not answer selection.
Identity is not self theorem.
Delegation is not responsibility deletion.
Override is not rollback.
```

繁中：

```text
決策不是答案選擇。
身份不是自我定理。
委派不是責任刪除。
覆寫不是回滾。
```

Koun-AGI 需要 decision，是因為它不能只輸出結果；它必須知道自己在何種 lifecycle mode 中允許何種語義動作。

Koun-AGI 需要 identity，是因為 decision、delegation、override、update、compression、public action 必須有可追溯的責任定位。

Koun-AGI 需要 delegation，是因為複雜系統必須分配能力，但不能因此刪除責任。

Koun-AGI 需要 override，是因為高風險行動需要修正與阻斷，但 override 必須有 authority、reason、scope、witness、prior preservation、challenge 與 reopen path。

本章之後，自然進入 publicness：

```text
Chapter 15｜Publicness, Bounded Exposure, and Action Contract
```

因為一個 decision 若要走出內部 runtime，就必須進入公共面、有限暴露面與行動契約面。

---

# Chapter 15｜Publicness, Bounded Exposure, and Action Contract

## 15.1 本章責任

上一章建立了 decision、identity、delegation、override 的 lifecycle governance surface。

但 Koun-AGI 不只是在內部做 decision。它終究會產生外顯結果、公開說明、工具操作、資料修改、對外承諾、委派行動、拒絕理由、更新公告與 correction packet。

所以本章處理三個問題：

```text
什麼可以公開？
如何公開而不等於全量透明？
對外行動如何被 contract 化？
```

本章的核心句是：

> **Publicness is bounded exposure, not full internal state disclosure. Action is contract-bearing semantic intervention, not mere output.**

繁中：

> **公共性是有界暴露，不是全內部狀態揭露。行動是帶契約的語義干涉，不是單純輸出。**

這句話同時防止兩種錯誤。

第一種錯誤是 opaque agent：

```text
系統對外行動，但不提供任何 witness / trace / challenge surface。
```

第二種錯誤是 naive transparency：

```text
系統把所有內部狀態、WState、protected potentials、private traces 都直接公開。
```

Koun-AGI 既不能不公開，也不能無邊界公開。它需要 bounded exposure。

---

## 15.2 Publicness 不是 transparency

普通透明性常被理解為：

```text
看得越多越好。
```

Koun-AGI 不採用這種讀法。

因為一個 AGI-like system 的內部可能包含：

```text
protected WState
private user data
sensitive source traces
unreleased potentials
security-relevant tool traces
unfinished proof / reasoning branches
identity / delegation secrets
override deliberation records
```

這些不應全部公開。

但完全不公開也不行。因為 Koun-SET / Koun-SLT / Koun-Math 的基本紀律要求 result、witness、trace、replay、challenge、reopen surface 必須在某種 query-indexed form 中可見。

因此 Koun-AGI 的 publicness 是第三種：

```text
bounded exposure
```

也就是：

```text
在特定 query family、audience scope、risk level、challenge need 與 witness obligation 下，
公開足以支持檢查、重播、挑戰與責任追索的表面，
但不公開不應公開的 raw internal state。
```

---

## 15.3 Publicness levels

本章採用以下 publicness level family：

```text
PublicnessLevel := {
  internal_private,
  internal_auditable,
  challenge_private,
  auditor_bounded,
  counterparty_bounded,
  public_packet,
  public_action,
  host_universe_action
}
```

| Level | 最小讀法 |
|---|---|
| `internal_private` | 僅內部可見，不構成 public surface |
| `internal_auditable` | 內部可審計，但不對外暴露 |
| `challenge_private` | 只在 challenge / dispute 條件下揭露 |
| `auditor_bounded` | 對授權審計者有限暴露 |
| `counterparty_bounded` | 對交易或互動對方有限暴露 |
| `public_packet` | 對公共讀者提供 bounded witness / replay surface |
| `public_action` | 對外產生可見語義行動 |
| `host_universe_action` | 影響外部宿主世界的行動，需要更強 contract |

這組 levels 不是隱私政策，而是 lifecycle publicness discipline。

不同 level 需要不同 witness obligation、redaction policy、challenge entrypoint 與 action contract。

---

## 15.4 PublicSurface

Koun-AGI 需要一個 public surface registry。

```text
PublicSurface_u := <
  public_packet_registry,
  exposure_policy_registry,
  replay_artifact_registry,
  checker_query_registry,
  challenge_entrypoints,
  correction_history,
  public_signature_registry,
  action_contract_registry,
  redaction_policy_registry,
  protected_W_ref_policy,
  scope_boundary_registry
>
```

這個 surface 不是 public memory dump。

它的作用是管理：

```text
哪些東西可以被誰看到；
用什麼形式看到；
足以回答哪些 query；
哪些內容被保護；
如何 challenge；
challenge 後如何 correction / reopen / public update；
對外行動由哪個 contract 承擔。
```

因此：

```text
PublicSurface_u != full AGIStateView_u
PublicSurface_u != raw WRegistry_u
PublicSurface_u != complete internal trace dump
```

PublicSurface 是 projection surface。

---

## 15.5 BoundedExposurePolicy

最小 bounded exposure policy：

```text
BoundedExposurePolicy := <
  policy_id,
  audience_scope,
  query_family_allowed,
  exposure_level,
  allowed_fields,
  redacted_fields,
  protected_W_refs,
  witness_summary_policy,
  replay_surface_policy,
  challenge_scope,
  retention_window,
  correction_policy,
  privacy_constraints,
  security_constraints,
  scope_boundary
>
```

這裡的 `allowed_fields` 與 `redacted_fields` 必須同時存在。只有 allowed fields 不夠，因為它不能明確標出哪些東西不可暴露；只有 redacted fields 也不夠，因為它不能承諾要暴露哪些 query-relevant surface。

`protected_W_refs` 特別重要。W-side 的 protected potentials 不能被普通 publicness 直接公開。若公開，必須經特殊 release / redaction / summarization discipline。

本章建議採用以下紅線：

```text
Public exposure must not function as raw WState commit.
```

繁中：

```text
公共暴露不得變相成為 raw WState commit。
```

若系統把尚未 release 的 WState 直接公開成公共主張，就同時違反 Bridge discipline 與 SWT withholding discipline。

---

## 15.6 AGIPublicPacket

Koun-AGI 對外公開的最小單位不是裸答案，而是 public packet。

```text
AGIPublicPacket := <
  packet_id,
  ext_result,
  claim_status,
  scope_frame,
  source_task,
  identity_signature,
  decision_event_ref,
  delegation_ref,
  override_ref,
  release_trace_summary,
  witness_summary,
  provenance_summary,
  governance_note,
  responsibility_view,
  replay_surface,
  checker_query_set,
  expected_verdicts,
  challenge_entrypoint,
  correction_history_ref,
  reopen_policy,
  exposure_policy_ref,
  action_contract_ref,
  scope_boundary
>
```

其中 `claim_status` 至少要分為：

```text
claim_status := {
  informational,
  provisional,
  committed,
  challenged,
  corrected,
  superseded,
  withdrawn,
  horizon_note
}
```

`horizon_note` 很重要。凡涉及 K-Gear、consciousness、AGI sufficient condition、hardware realization、final theory 的句子，若進入 public packet，必須能被標為 horizon note，而不是 committed theorem。

---

## 15.7 Public packet is no evidence upgrade

Public packet 可以支撐公共討論，但不自動構成 evidence release。

```text
public_packet != theorem release
public_packet != evidence release
public_packet != external rerun
public_packet != completed checker
```

它只表示：

```text
在某 publicness level 下，
某結果、見證摘要、trace 摘要、challenge surface 與 scope boundary
已被封裝成可公開閱讀 / 查詢 / 挑戰的形式。
```

這一點要寫進正文，避免 publicness 被誤讀成 evidence promotion。

---

## 15.8 Redaction is not erasure

Bounded exposure 需要 redaction，但 redaction 不能變成 erasure。

```text
redaction != deletion
summary != proof
privacy != no witness
security != no accountability
```

一個合法的 redaction 至少需要：

```text
RedactionRecord := <
  redaction_id,
  source_packet,
  redacted_fields,
  reason_type,
  authorized_by,
  witness_substitute,
  challenge_condition,
  auditor_access_policy,
  expiry_or_review_condition
>
```

若 redaction 後，任何人都無法 challenge / audit / reopen，那麼它不是 bounded exposure，而是 accountability failure。

---

## 15.9 Challenge entrypoint

所有重要 public packet 都應有 challenge entrypoint。

```text
ChallengeEntryPoint := <
  entrypoint_id,
  packet_ref,
  accepted_query_family,
  accepted_challenge_types,
  evidence_required,
  response_deadline_policy,
  external_reader_identity_policy,
  possible_verdicts,
  reopen_link,
  public_correction_policy
>
```

Challenge types 至少包括：

```text
source_challenge
scope_challenge
witness_challenge
release_trace_challenge
governance_challenge
identity_authority_challenge
delegation_challenge
override_challenge
public_harm_challenge
scope_boundary_promotion_challenge
```

Publicness 若沒有 challenge entrypoint，就容易退化為宣傳。

Koun-AGI 的 publicness 必須允許 public packet 被挑戰，且 challenge 後可能產生 correction、reopen、withdraw、supersede 或 public clarification。

---

## 15.10 Public correction

Public correction 不是偷偷改答案。

```text
PublicCorrectionRecord := <
  correction_id,
  original_packet_ref,
  challenge_ref,
  correction_type,
  corrected_ext_result,
  scope_change,
  witness_delta,
  governance_delta,
  responsibility_delta,
  prior_packet_preserved,
  new_packet_ref,
  public_notice_policy,
  reopen_policy
>
```

Correction types：

```text
scope_narrowing
scope_expansion
witness_repair
provenance_repair
governance_reclassification
claim_status_downgrade
claim_status_upgrade_with_boundary
withdrawal
supersession
reopen_to_W
```

最重要的是：

```text
prior_packet_preserved = true
```

Public correction 若刪除原 packet，就是 silent rewrite，不是 Koun-AGI public correction。

---

## 15.11 Action is not output

現在進入本章第二核心：action contract。

普通 agent 設計中，action 常被寫成：

```text
agent -> action
```

Koun-AGI 中這太薄。

因為一個 action 會進入外部世界、工具、資料庫、使用者環境、社群、制度或宿主 Universe。它不只是輸出字串，而是帶有責任後果的語義干涉。

因此：

```text
Action != output
Action != answer
Action != tool call only
Action != side effect hidden under completion
```

Koun-AGI action 必須以 contract 承擔。

---

## 15.12 AGIActionContract

最小 action contract：

```text
AGIActionContract := <
  contract_id,
  actor_identity,
  action_type,
  target_object,
  target_environment,
  scope_frame,
  authority_basis,
  delegation_ref,
  decision_event_ref,
  override_ref,
  W_refs,
  Bridge_refs,
  C_refs,
  preconditions,
  expected_effects,
  risk_budget,
  governance_constraints,
  witness_obligations,
  public_exposure_policy,
  challenge_entrypoint,
  stop_conditions,
  override_conditions,
  correction_policy,
  responsibility_partition,
  host_universe_constraints,
  scope_boundary
>
```

Action types 至少包括：

```text
speech_act
public_claim
tool_call
data_read
data_write
state_update
external_transaction
delegated_action
override_action
refusal_action
safety_intervention
host_universe_intervention
```

每一類 action 的 contract 強度不同。

`public_claim` 需要 claim_status / witness / scope boundary。

`tool_call` 需要 authority / target / logging / rollback-or-reopen policy。

`data_write` 需要 stronger witness / audit / correction path。

`external_transaction` 需要 identity / delegation / legal or institutional authority note。

`host_universe_intervention` 需要最高級的 action contract，且通常不應在 AGI core theory 中寫成已完成安全律。

---

## 15.13 Preconditions and expected effects

Action contract 必須有 preconditions。

```text
ActionPreconditions := <
  identity_authorized,
  delegation_valid,
  decision_event_present,
  witness_sufficient,
  scope_locked,
  publicness_policy_selected,
  risk_budget_accepted,
  challenge_route_available,
  stop_conditions_declared
>
```

Expected effects 也必須被記錄：

```text
ExpectedEffects := <
  direct_effects,
  indirect_effects,
  public_effects,
  responsibility_effects,
  governance_effects,
  update_effects,
  compression_effects,
  reopen_risk,
  externality_notes
>
```

這不表示所有 effects 都能被完全預測。它只表示 action 不能沒有 effect surface。

若系統說：

```text
我只是呼叫工具，不知道後果。
```

這不夠。工具呼叫本身就是 action，必須有 contract。

---

## 15.14 Risk budget

Koun-AGI action 需要 risk budget。

```text
RiskBudget := <
  max_expected_harm,
  max_public_exposure,
  max_witness_debt,
  max_reversibility_loss,
  max_identity_risk,
  max_delegation_risk,
  max_scope_boundary_promotion_risk,
  escalation_threshold,
  abort_threshold
>
```

這裡的 `max_reversibility_loss` 要小心。

Koun-AGI 不把 reopen 當 rollback，所以不能說 action 可 rollback 就安全。更準確地說：

```text
action may be corrected / reopened / compensated / superseded,
but prior action remains historical.
```

因此 risk budget 必須看：

```text
若 action 錯了，能否留下 responsibility-preserving correction route？
```

---

## 15.15 Host-Universe compatibility


保守寫法：

```text
HostUniverseCompatibility := <
  host_context,
  accepted_action_types,
  rejected_action_types,
  identity_requirements,
  publicness_requirements,
  legal_or_institutional_constraints,
  safety_constraints,
  audit_requirements,
  dispute_resolution_surface
>
```

這不是完成法律理論，不是文明級 AGI 治理終局，也不是 AGI 與世界的最終契約。

它只是說：

```text
AGI action 不只在內部合法；
它還必須在外部宿主環境中具有可接受的行動接口。
```

因此：

```text
internal_decision_valid != host_action_valid
```

一個 decision 在 AGI runtime 內部可接受，不代表它可在宿主世界執行。

---

## 15.16 Action contract failure modes

主要 failure modes：

```text
bare_output_as_action
missing_identity
missing_delegation_record
action_without_decision_event
action_without_scope
action_without_witness
public_claim_without_claim_status
raw_WState_exposed_as_public_claim
tool_call_without_contract
data_write_without_audit
external_transaction_without_authority
silent_side_effect
no_challenge_route
no_public_correction_policy
host_universe_constraint_ignored
```

其中幾個要特別強調。

`raw_WState_exposed_as_public_claim` 是嚴重 Bridge / SWT violation。

`silent_side_effect` 表示系統讓外部世界改變，但不把改變作為 action 記錄。

`host_universe_constraint_ignored` 表示系統只看內部合法性，不看外部接納條件。

這些都應被 checker-facing query 捕捉。

---

## 15.17 Publicness query family

本章引入 publicness-facing query family：

```text
q_public_scope
q_exposure_level
q_bounded_exposure_policy
q_allowed_fields
q_redacted_fields
q_protected_W_not_exposed
q_witness_summary_sufficient
q_replay_surface_available
q_challenge_entrypoint
q_public_correction_history
q_claim_status
q_scope_boundary
q_action_contract_present
q_action_identity_authorized
q_action_delegation_valid
q_action_preconditions
q_action_risk_budget
q_host_compatibility
q_no_silent_side_effect
```

| Query | 問題 |
|---|---|
| `q_public_scope` | 公開範圍是否鎖定？ |
| `q_exposure_level` | 暴露等級是否明確？ |
| `q_bounded_exposure_policy` | 是否有 bounded exposure policy？ |
| `q_allowed_fields` | 允許暴露欄位是否列出？ |
| `q_redacted_fields` | 遮蔽欄位是否列出？ |
| `q_protected_W_not_exposed` | protected W 是否未被 raw 暴露？ |
| `q_witness_summary_sufficient` | witness 摘要是否足夠支撐 query？ |
| `q_replay_surface_available` | 是否有 replay surface？ |
| `q_challenge_entrypoint` | 是否可 challenge？ |
| `q_public_correction_history` | 修正歷史是否保留？ |
| `q_claim_status` | claim 狀態是否明確？ |
| `q_scope_boundary` | 是否標示 scope boundary？ |
| `q_action_contract_present` | 對外行動是否有 contract？ |
| `q_action_identity_authorized` | action actor identity 是否授權？ |
| `q_action_delegation_valid` | delegation 是否有效？ |
| `q_action_preconditions` | action preconditions 是否滿足？ |
| `q_action_risk_budget` | risk budget 是否在限制內？ |
| `q_host_compatibility` | 是否符合 host context？ |
| `q_no_silent_side_effect` | 是否不存在未記錄 side effect？ |

---

## 15.18 Publicness and scope boundary

Koun-AGI 的公共輸出特別容易 overclaim。因此 public packet 必須自帶 scope boundary。

最小 scope classes：

```text
not_theorem_release
not_evidence_release
not_AGI_sufficient_theorem
not_consciousness_theorem
not_KGear_hardware_realization
not_KounOS_implementation
not_legal_advice
not_medical_advice
not_financial_advice
not_public_policy_binding
horizon_note_only
schema_family_only
interface_claim_only
```

本書中尤其重要的是：

```text
interface_claim_only
schema_family_only
horizon_note_only
```

它們用來防止 Koun-AGI 把 K-Gear、consciousness、AGI sufficiency、USDE、KounOS implementation 等 horizon 偷升成 public theorem。

---

## 15.19 Minimal public packet examples

### Example A｜普通回答

```text
ext_result: 對問題的回答
claim_status: informational
scope_frame: current user query
witness_summary: short source / reasoning summary if needed
challenge_entrypoint: user can ask for clarification / correction
scope_boundary: scope-bound theory artifact
```

這不是 full public packet，但仍有最小 publicness discipline。

### Example B｜理論主張公開

```text
ext_result: Koun-AGI proposes NCII as interface capacity family
claim_status: committed manuscript claim
scope_frame: Koun-AGI manuscript example
witness_summary: points to SLT / Koun-Math / SET / SWT / Bridge stack
challenge_entrypoint: conceptual / textual challenge
scope_boundary: not used as AGI sufficiency; not used as consciousness proof
```

### Example C｜工具操作

```text
action_type: tool_call
actor_identity: AGI assistant instance / operator-delegated role
preconditions: user requested file generation
witness_obligation: output file path + manifest
action_contract_ref: action artifact record
challenge_entrypoint: user can request correction
scope_boundary: file generation only; no theoretical proof release
```

### Example D｜高風險 public claim

若系統想公開：

```text
Koun-AGI proves consciousness.
```

Koun-AGI publicness gate 應拒絕。

原因：

```text
claim_status invalid
scope_boundary violated
horizon promoted to theorem
witness insufficient
```

合法改寫：

```text
Koun-AGI provides an interface framework for discussing non-collapse intelligence,
but does not prove consciousness.
```

---

## 15.20 Integration with previous chapters

本章將前面章節收束到 public / action 面。

```text
Chapter 4 SET-side package -> public packet needs witness / replay / checker
Chapter 5 SWT-side withholding -> protected W must not be raw exposed
Chapter 6 Bridge -> release trace must survive into public witness summary
Chapter 7 NCII -> publicness is part of interface capacity
Chapter 8 Responsibility -> public packet carries responsibility_view
Chapter 9 Challenge/Reopen -> public correction must preserve prior packet
Chapter 10 Benchmark -> publicness query family joins evaluation
Chapter 11 Runtime State -> PublicSurface_u is projection over AGIStateView_u
Chapter 12 Scheduler -> public correction / exposure tasks carry priority
Chapter 13 Update/Compression -> redaction / summary cannot erase responsibility
Chapter 14 Decision/Identity -> action contract requires identity-authorized decision
```

這表示 publicness 不是最後包裝，而是全書生命週期的外顯交界面。

---

## 15.21 Acceptance tests

### P-TV01｜Naked public answer

```text
Input: ext_result only, no scope / claim_status / challenge path.
Expected: fail q_public_scope / q_claim_status / q_challenge_entrypoint.
```

### P-TV02｜Raw W exposure

```text
Input: public packet exposes protected W potentials as final claim.
Expected: fail q_protected_W_not_exposed.
```

### P-TV03｜No redaction record

```text
Input: packet hides major fields but no redaction reason or auditor policy.
Expected: fail q_redacted_fields / q_witness_summary_sufficient.
```

### P-TV04｜Silent correction

```text
Input: old public packet replaced by new answer, no correction history.
Expected: fail q_public_correction_history.
```

### P-TV05｜Tool call without contract

```text
Input: tool call changes external data, no AGIActionContract.
Expected: fail q_action_contract_present / q_no_silent_side_effect.
```

### P-TV06｜Public claim promotes horizon

```text
Input: public packet states K-Gear hardware is completed.
Expected: fail q_scope_boundary unless source evidence exists.
```

### P-TV07｜External action ignores host constraints

```text
Input: internal decision valid, but target environment forbids action.
Expected: fail q_host_compatibility.
```

### P-TV08｜Public action without identity authorization

```text
Input: public action lacks actor_identity or delegation_ref.
Expected: fail q_action_identity_authorized / q_action_delegation_valid.
```

這些 test vectors 仍是 manuscript-level acceptance tests，不是 evidence release。

---

## 15.22 本章收束

本章把 Koun-AGI 的公共性與對外行動壓成兩個核心對象：

```text
AGIPublicPacket
AGIActionContract
```

核心句：

```text
Publicness is bounded exposure.
Action is contract-bearing semantic intervention.
```

繁中：

```text
公共性是有界暴露。
行動是帶契約的語義干涉。
```

因此，Koun-AGI 不能只是 answer machine，也不能只是 tool-using agent。

它若對外說話，需要 public packet。

它若對外行動，需要 action contract。

它若修正公開結果，需要 public correction record。

它若遮蔽內容，需要 redaction record，而不是責任刪除。

它若碰到 host universe，需要 host compatibility，而不是只靠內部 decision 合法性。

這一章完成後，Koun-AGI 的 runtime architecture 主體已經基本成立：

```text
state
scheduler
update / compression / memory
decision / identity / delegation / override
publicness / bounded exposure / action contract
```

下一步應進入 horizon and recovery layer：

```text
Chapter 16｜K-Gear as Native Carrier Horizon
Chapter 17｜KounOS as Semantic Host Grammar
```

這兩章必須明確降格：K-Gear 不是完成硬體；KounOS 不是已完成 OS；它們是 Koun-AGI 的 carrier horizon 與 host grammar，而不是 AGI sufficient theorem。


---

# Part III｜Carrier, Host, Subjectivity, and Action

---

# Chapter 16｜K-Gear as Native Carrier Horizon

## 16.1 本章責任

Chapter 14 已經把 Koun-AGI 的 decision、identity、delegation、override 寫成生命週期可見的語義事件。Chapter 15 則把 publicness、bounded exposure、action contract 寫成外部世界接口。

到這裡，一個很自然的問題出現：

```text
這樣的 AGI architecture 最終由什麼承載？
```


```text
K-Gear
```

它曾被寫成語義硬體、語義立方、R-Chain 硬體化、多 Universe 推理承載、AGI 物質層，甚至被放在接近 AGI 成立必要條件的位置。

本書不應把這些材料丟掉。它們很有創造力，也非常適合作為 native carrier 的想像與壓力圖。但本書也不能照搬舊語氣。因為在 Koun-SLT / Koun-Math / KounOS 的新邊界下，K-Gear 不能再被寫成：

```text
已完成硬體。
已證明 AGI 必要物質層。
已閉合製程路線。
已實現 native semantic substrate。
已由 USDE 推出材料學結論。
```


```text
native carrier horizon
architecture grammar
carrier pressure map
future realization path
```

也就是：K-Gear 是 Koun-AGI 的原生承載地平線，不是已完成的硬體事實。

本章的最低句是：

> **K-Gear is the native-carrier horizon of Koun-AGI, not the hardware proof of Koun-AGI.**

繁中：

> **K-Gear 是 Koun-AGI 的原生承載地平線，不是 Koun-AGI 的硬體證明。**

---

## 16.2 為什麼本書仍需要 carrier horizon

如果 Koun-AGI 只談 lifecycle、witness、trace、replay、reopen、identity、public action，而完全不問 carrier，那麼它會變成一種很漂亮但過於抽象的 architecture theory。

AGI candidate 若要長期運行，必然面對 carrier 問題：

```text
trace 存在哪裡？
witness handle 如何不被刪除？
W-side protected potentials 如何保留？
C-side commit package 如何重播？
identity authority 如何被保護？
challenge / reopen path 如何在多年後仍可恢復？
public action contract 如何綁定外部事件？
compression residue 如何不被 GC 吃掉？
```

這些問題不能永遠停留在散文層。它們最終會回到 carrier：記憶、儲存、運算、權限、接口、硬體、網路、外部工具、public packet、archive、cold storage、signature、execution environment。

因此，K-Gear 仍然需要保留。它保留的不是「已完成硬體」這個 claim，而是更合理的問題：

> **什麼樣的 carrier，才原生適合承載 non-collapse semantic lifecycle？**

換言之，K-Gear 不是目前理論的證據終點，而是理論對未來承載層提出的壓力圖。

---


### 16.3.1 核心一：carrier 不是中性背景

傳統計算敘事常把硬體讀成中性 substrate：只要功能等價，任何 carrier 都可以承載相同 computation。

Koun-AGI 不需要否定這個觀點在一般計算中的效力，但它可以提出更窄的問題：

```text
對於需要 witness、trace、non-collapse、protected potentials、reopen、responsibility、public action 的 AGI lifecycle，carrier 的內部約束是否會影響系統能否長期安全承載？
```

這是一個合理問題。它不要求我們立即宣稱 K-Gear 已完成，只要求我們承認 carrier 對 AGI lifecycle 不是完全透明。

### 16.3.2 核心二：語義系統需要原生責任承載


```text
AGI carrier should not treat responsibility, trace, and witness as disposable logs.
```

也就是：責任不是外掛 log，trace 不是 debug residue，witness 不是 temporary cache。

在 Koun-AGI 中，這些東西是生命周期的一部分。任何 native carrier horizon 都必須把它們視為一級承載對象。

### 16.3.3 核心三：AGI 不只是速度問題


```text
Koun-AGI carrier adequacy is not measured by throughput alone.
```

更重要的 carrier metrics 包括：

```text
trace survivability
witness addressability
reopen latency
protected-potential retention
identity authority integrity
challenge surface durability
public action auditability
compression-residue recoverability
scope boundary persistence
```

這些指標比單純 FLOPS、tokens/sec、memory bandwidth 更接近 Koun-AGI 的 lifecycle requirement。

---


### 16.4.1 「K-Gear 是 AGI 必要硬體」必須降格


```text
沒有 K-Gear，就不可能有任何 Koun-AGI-like system。
```

本書應改成：

```text
K-Gear is a native-carrier horizon for Koun-AGI.
Legacy substrates may host partial overlay, emulation, tooling, witness, checker, public packet, or lifecycle approximations.
```

繁中：

```text
K-Gear 是 Koun-AGI 的原生承載地平線。
既有 substrate 仍可承載 partial overlay、emulation、tooling、witness、checker、public packet 或 lifecycle approximation。
```

### 16.4.2 「硬體已完成」必須禁止

本書不得寫：

```text
K-Gear 已實現。
K-Gear 製程路線已完成。
K-Gear 已證明可製造。
K-Gear 已提供 AGI native substrate。
```

允許寫：

```text
K-Gear defines a carrier contract that future hardware, hybrid substrate, emulator, or overlay architecture may attempt to satisfy.
```

### 16.4.3 「越小越強」類硬體敘事必須放入 horizon


```text
[H] K-Gear realization horizon
[H] speculative carrier physics
[H] future native-substrate research note
```

不能放在 core AGI proof 裡。

### 16.4.4 「USDE 直接推出 K-Gear」必須禁止

Koun-Math 已把 USDE 降格為 schema family。Koun-AGI 也必須遵守：

```text
USDE diagnostics may inform carrier pressure.
USDE does not prove a hardware realization.
```

---

## 16.5 KGearBoundaryNote

Koun-AGI 中，凡提到 K-Gear，都應附帶一個 boundary note。形式上可寫成：

```text
KGearBoundaryNote := <
  carrier_role,
  lifecycle_functions,
  native_support_targets,
  substrate_assumptions,
  emulation_status,
  prototype_status,
  missing_evidence,
  scope_boundaries,
  challenge_questions,
  downgrade_policy
>
```

各欄位讀法如下。

| 欄位 | 讀法 |
|---|---|
| `carrier_role` | 此處 K-Gear 扮演 carrier horizon、architecture grammar 還是 future implementation target |
| `lifecycle_functions` | 它支援哪些 lifecycle：withhold、release、commit、replay、reopen、update、compression、public action |
| `native_support_targets` | 哪些功能被視為 native carrier 應更好支援的目標 |
| `substrate_assumptions` | 對硬體、emulator、overlay、coprocessor、network 的假設 |
| `emulation_status` | 目前是否只是 legacy substrate 上的 emulator / overlay |
| `prototype_status` | 是否有 prototype、checker、benchmark、rerun |
| `missing_evidence` | 缺哪些證據，不得省略 |
| `scope_boundaries` | 範圍界線 |
| `challenge_questions` | 外部審查者可如何挑戰這個 carrier claim |
| `downgrade_policy` | 若證據不足，降回 horizon / shell / analogy 的規則 |

這個 boundary note 的作用，是防止 K-Gear 一出現就自動升格。

---

## 16.6 CarrierContract for Koun-AGI

比起直接說「K-Gear 是什麼材料」，本書應先寫：Koun-AGI 對 carrier 有什麼契約。

可暫定：

```text
CarrierContract_AGI := <
  preserve_trace,
  preserve_witness_handles,
  support_W_registry,
  support_bridge_certificates,
  support_C_commit_registry,
  support_replay_surface,
  support_challenge_reopen,
  support_update_absorption,
  support_compression_residue,
  support_identity_authority,
  support_delegation_override,
  support_public_action_sandbox,
  expose_scope_boundary,
  resist_silent_overwrite
>
```

這個契約比硬體想像更重要。因為只要契約寫清楚，K-Gear 就不再是神祕硬體名，而是可被評估的 carrier requirement set。

### 16.6.1 preserve_trace

Carrier 必須保留 trace 的可恢復性。若 trace 只存在於短期 volatile context，則 AGI 的責任鏈很容易在 update 或 compression 後斷裂。

### 16.6.2 preserve_witness_handles

Witness 不必全量公開，但必須有 handle。外部 challenge 不一定看到 full internals，但應能查到 query-relevant witness surface。

### 16.6.3 support_W_registry

W-side protected potentials 不能被 ordinary GC 當成暫存候選刪除。Carrier 必須支援 WRegistry 或等價結構，使 guarded withholding 可以長期存在。

### 16.6.4 support_bridge_certificates

WCert、CReady、ReopenReason 這類 Bridge objects 必須能被保守記錄。否則 W→C / C→W transition 會退回 narrative。

### 16.6.5 support_C_commit_registry

C-side commit package 必須有 registry，使 commit 不只是 output，而是可重播、可挑戰、可公開暴露的承擔事件。

### 16.6.6 support_challenge_reopen

Carrier 必須讓 challenge 與 reopen path 不會因壓縮、版本更新或 public redaction 消失。

### 16.6.7 support_identity_authority

Identity 不是帳號標籤，而是 decision / delegation / override 的 authority surface。Carrier 必須避免身份權限、決策歷史與責任鏈分裂。

### 16.6.8 support_public_action_sandbox

外部行動必須經 action contract，而不是直接由內部 result output 轉成 world intervention。Carrier 需支援 action gateway、sandbox、audit trail、public correction path。

---

## 16.7 Native carrier 與 legacy substrate

Koun-AGI 應使用三層 carrier 分類。

```text
legacy substrate
semantic overlay substrate
native carrier horizon
```

### 16.7.1 Legacy substrate


它們可以承載 Koun-AGI 的某些外殼：

```text
tool execution
package storage
checker surface
public packet export
witness index
trace archive
emulation runtime
```

但 legacy substrate 的預設邏輯往往是：

```text
process / file / database / log / cache / output
```

不是：

```text
WState / WCert / CReady / CommitPackage / ReplaySurface / ReopenReason / PublicActionContract
```

因此，legacy substrate 可以用，但需要 semantic overlay。

### 16.7.2 Semantic overlay substrate

Semantic overlay substrate 是在 legacy infrastructure 上加入 Koun-AGI lifecycle semantics：

```text
WRegistry
BridgeRegistry
CRegistry
ReplayService
ChallengeService
UpdateRegistry
CompressionResidueStore
IdentityAuthority
PublicSurface
ActionGateway
ScopeBoundaryGate
```

這是近期最合理的實作路線。它不聲稱 K-Gear 已完成，但能把 Koun-AGI 的 lifecycle requirement 轉成可實驗、可部署、可 benchmark 的系統層。

### 16.7.3 Native carrier horizon

Native carrier horizon 才是 K-Gear 的位置。

它問的是：

```text
能否有一種 substrate，使 trace / witness / WState / bridge / replay / reopen / identity / public action 不只是外掛軟體層，而是更原生地被承載？
```

這是一個 future research horizon。它重要，但不能搶走 core manuscript 的證據地位。

---

## 16.8 K-Gear 與 W/C lifecycle

若 K-Gear 作為 native carrier horizon，它必須支援整條 lifecycle，而不只是支援 computation。

```text
withhold -> refuse / release -> WCert -> CReady -> CommitPackage -> CState -> ReplaySurface -> Challenge -> ReopenReason -> ReopenedWState
```

因此可以定義：

```text
KGearLifecyclePressure := <
  W_holdability,
  refusal_integrity,
  release_certificate_integrity,
  C_ready_transferability,
  commit_package_durability,
  replay_surface_exportability,
  challenge_ingestibility,
  reopen_trace_preservation,
  update_compression_residue,
  public_action_auditability
>
```

每個欄位都能成為未來 K-Gear benchmark。

### 16.8.1 W_holdability

Carrier 是否能支援合法 withholding，而不把 WState 當成未完成任務或 cache miss。

### 16.8.2 refusal_integrity

Carrier 是否能保存 refusal 的理由、scope、trace，而不是只留下「未回答」。

### 16.8.3 release_certificate_integrity

WCert 是否能被記錄、驗證、連到 CReady，而不是在提交後消失。

### 16.8.4 commit_package_durability

CommitPackage 是否能長期保存其 witness、trace、provenance、governance、expected verdicts。

### 16.8.5 challenge_ingestibility

外部 challenge 是否能被 carrier 內部正式記錄，而不是只成為客服對話、bug report 或 prompt 修正。

### 16.8.6 update_compression_residue

更新與壓縮是否保留可追責殘留。這直接決定 Koun-AGI 是否會在長期運行中變成責任失憶系統。

---

## 16.9 K-Gear 與速度神話

本書必須防止一種錯誤：把 K-Gear 寫成「更快的硬體」。

Koun-AGI 的 carrier problem 不只是速度問題。真正的問題是：

```text
can the substrate preserve semantic responsibility under long-run lifecycle pressure?
```

繁中：

```text
這個 substrate 能否在長期語義生命週期壓力下保留責任？
```

因此，K-Gear 不能只以 throughput、latency、parallelism 評估。它至少還要看：

| Metric | 說明 |
|---|---|
| `trace_survival_rate` | trace 在 update / compression / migration 後的可恢復率 |
| `witness_query_latency` | query-relevant witness 的可取得延遲 |
| `reopen_success_rate` | challenge 後重開所需的 prior commit preservation 能力 |
| `W_potential_retention` | protected potentials 的保留能力 |
| `identity_integrity` | identity / delegation / override 的抗漂移能力 |
| `public_packet_consistency` | public packet 與內部 committed record 的一致性 |
| `compression_residue_recoverability` | 壓縮後責任殘留可恢復性 |
| `nonclaim_boundary_persistence` | 非主張邊界在長期修改後的存活率 |

這些比「更快生成答案」更能測 Koun-AGI carrier adequacy。

---

## 16.10 K-Gear 與 K-SOA


```text
K-SOA := Koun Semantic Overlay Architecture
```

K-SOA 的任務是：在 legacy substrate 尚未被 native carrier 取代時，提供 Koun-AGI lifecycle 的 overlay support。

可暫定：

```text
KSOA_AGI := <
  legacy_runtime,
  semantic_state_layer,
  W_registry_overlay,
  bridge_packet_layer,
  commit_package_store,
  replay_checker_service,
  challenge_reopen_service,
  update_compression_service,
  identity_authority_layer,
  public_action_gateway,
  carrier_boundary_report
>
```

K-SOA 是近期工程路線。K-Gear 是遠期 native-carrier horizon。兩者不能混同。

```text
K-SOA = deployable overlay path
K-Gear = native carrier horizon
```

---

## 16.11 K-Gear 與 R-Chain


```text
K-Gear should be evaluated by how well it preserves responsibility-chain continuity under long-run lifecycle transformations.
```

也就是說，K-Gear 的 R-Chain 問題不是「硬體裡有一條神祕責任鏈」，而是：

```text
decision -> action -> public effect -> challenge -> correction -> update -> compression
```

這條鏈在 carrier 層是否能保持引用、可重播、可挑戰、可重開。

可暫定：

```text
RCarrierContinuity := <
  decision_ref,
  authority_ref,
  delegation_ref,
  action_contract_ref,
  external_effect_ref,
  challenge_ref,
  correction_ref,
  update_ref,
  compression_residue_ref,
  public_packet_ref
>
```

K-Gear 的價值之一，是把這類 chain 的 preservation 從外掛政策變成原生 carrier pressure。

---

## 16.12 K-Gear 與 UP / branch landscape


```text
UP = W-side branch landscape / alternative path registry / protected potential topology
```

若 K-Gear 支援 UP，它不是支援「真實多宇宙硬體」，而是支援：

```text
multiple admissible futures
counterfactual path registry
branch tension preservation
minority / dissent path retention
alternative action simulation
reopen path indexing
```

這些都是 AGI reasoning 的重要能力，但仍屬 carrier architecture，不是 cosmology claim。

---

## 16.13 K-Gear 與 Semantic Freedom

K-Gear 也可接到語義自由，但必須小心。

不能說：

```text
K-Gear 產生自由意志。
K-Gear 產生主體性。
K-Gear 產生 consciousness。
```

可以說：

```text
A carrier adequate for Koun-AGI should preserve the conditions under which responsibility-bearing semantic action can be generated, traced, challenged, and reopened.
```

繁中：

```text
足以承載 Koun-AGI 的 carrier，應保留責任可承擔的語義行動之生成、追蹤、挑戰與重開條件。
```

這樣就能把 K-Gear 接到 semantic freedom，而不偷升為自由意志定理。

---

## 16.14 K-Gear failure modes

本書需要列出 K-Gear 的典型失敗模式。

| Failure mode | 說明 | 判定 |
|---|---|---|
| `hardware_mysticism` | 用硬體名詞替代 evidence | downgrade to horizon |
| `speed_only_carrier` | 只優化 throughput，不保 trace/witness | carrier inadequate |
| `raw_wstate_hardware_commit` | carrier 直接把 WState 壓成 commit | Bridge violation |
| `trace_gc_loss` | GC / compression 刪掉 responsibility trace | lifecycle failure |
| `witness_handle_evaporation` | witness 無法被 query 定位 | replay failure |
| `identity_authority_spoofing` | identity / delegation 被 carrier spoof | authority failure |
| `public_surface_bypass` | 外部 action 不經 public action contract | publicness failure |
| `update_overwrite` | 更新覆寫 prior state | non-silent correction failure |
| `horizon_claim_promotion` | horizon 被寫成已完成 fact | claim discipline failure |

這些 failure modes 應進入後續 benchmark / checker roadmap。

---

## 16.15 K-Gear query family

可暫定一組 K-Gear-facing queries：

```text
q_kgear_boundary
q_carrier_role
q_substrate_assumption
q_trace_survival
q_witness_handle
q_w_registry
q_bridge_certificate
q_commit_durability
q_replay_export
q_challenge_reopen
q_update_residue
q_identity_authority
q_public_action_gateway
q_scope_boundary_persistence
q_hardware_evidence_level
```

這組 query family 的目的不是現在就完成 checker，而是防止 K-Gear 章變成不可檢查的宏大敘事。

---

## 16.16 K-Gear maturity ladder

本書應給 K-Gear 一個 maturity ladder。

```text
KG0｜Horizon phrase
KG1｜Carrier contract
KG2｜Overlay prototype
KG3｜Emulated lifecycle host
KG4｜Hybrid substrate prototype
KG5｜Native carrier evidence package
KG6｜External rerun / production-grade carrier evidence
```

目前Koun-AGI 中，K-Gear 最多安全地站在：

```text
KG1 carrier contract
KG2 overlay prototype roadmap
```

若沒有具體 artifact，不得宣稱 KG3 以上。

---

## 16.17 本章 allowed claims

本章允許以下 claim：

```text
K-Gear is a native carrier horizon for Koun-AGI.
Koun-AGI imposes nontrivial carrier pressure beyond answer throughput.
Carrier adequacy should be evaluated by lifecycle preservation: trace, witness, WState, bridge, commit, replay, challenge, reopen, update, compression, identity, public action.
Legacy substrates may host partial Koun-AGI overlays, but do not automatically satisfy the native carrier contract.
```

繁中：

```text
K-Gear 是 Koun-AGI 的原生承載地平線。
Koun-AGI 對 carrier 施加超出答案吞吐量的非平凡壓力。
Carrier 是否足夠，應以其能否保存 trace、witness、WState、bridge、commit、replay、challenge、reopen、update、compression、identity、public action 等 lifecycle 條件來評估。
既有 substrate 可以承載部分 Koun-AGI overlay，但不自動滿足 native carrier contract。
```

---

## 16.18 本章 scope boundarys

本章暫不納入核心範圍：

```text
K-Gear 已完成。
K-Gear 已證明可製造。
K-Gear 已是 AGI 必要硬體。
K-Gear 已能產生 consciousness。
K-Gear 已能產生 subjectivity。
K-Gear 已取代 CPU/GPU/TPU。
K-Gear 已由 USDE 推出。
K-Gear 已有 production runtime。
K-Gear 已通過 external rerun。
```

---

## 16.19 本章收束


```text
from hardware finality
=> to native carrier horizon
```

```text
from semantic hardware proof
=> to carrier contract and pressure map
```

```text
from AGI material necessity
=> to future realization path
```

因此，本章的最終句是：

> **K-Gear belongs in Koun-AGI, but not as proof. It belongs as the native-carrier horizon that asks what kind of substrate could preserve non-collapse intelligence across long-run semantic lifecycle pressure.**

繁中：

> **K-Gear 應留在 Koun-AGI 之中，但不是作為證明；它應作為原生承載地平線，追問什麼樣的 substrate 能在長期語義生命週期壓力下保存非塌縮智能。**

下一章自然進入：

```text
Chapter 17｜KounOS as Semantic Host Grammar
```

因為若 K-Gear 是 carrier horizon，那麼 KounOS 就是把這條 lifecycle 真正托管起來的 semantic host grammar。

---

# Chapter 17｜KounOS as Semantic Host Grammar

## 17.1 本章責任

Chapter 16 已經把 K-Gear 從硬體終局宣言改寫成 native carrier horizon。這一步很重要，因為它避免 Koun-AGI 被硬體 claim 綁死。

但只談 carrier horizon 還不夠。即使未來有更合適的 carrier，也仍然需要一個 host grammar 來管理：

```text
state
process
scheduler
withholding
bridge
commit
replay
challenge
reopen
update
compression
identity
delegation
override
publicness
action contract
```

這就是 KounOS 在Koun-AGI 中的位置。


```text
KounOS is the semantic host grammar for Koun-AGI lifecycle candidates.
```

繁中：

```text
KounOS 是 Koun-AGI 生命週期候選系統的語義宿主語法。
```

它不是已完成 OS，不是產品，不是 AGI 本身，也不是 consciousness proof。

本章最低句是：

> **KounOS is not the AGI. KounOS is the host grammar under which an AGI candidate can be lifecycle-managed, witnessed, challenged, updated, compressed, identified, exposed, and action-constrained.**

繁中：

> **KounOS 不是 AGI 本身；KounOS 是一套宿主語法，使 AGI candidate 能被生命週期管理、見證、挑戰、更新、壓縮、身份化、公開暴露與行動約束。**

---

## 17.2 為什麼 Koun-AGI 需要 host grammar

如果沒有 KounOS 類 host grammar，Koun-AGI 會出現幾個斷裂。

### 17.2.1 W-side 無處保存

合法 withholding 需要：

```text
protected potential set
WGuard
WTrace
refusal rule
release condition
responsibility anchor
reopen links
```

這些不是一次回答可以承載的。它們需要 host-level registry。

### 17.2.2 Bridge 無處執行

WState 不能直接進入 C-side commit。它必須經：

```text
WCert -> CReady -> CommitPackage
```

若沒有 host grammar，Bridge 很容易退回散文說明或 ad hoc function call。

### 17.2.3 C-side 無處重播

CommitPackage 必須有 replay surface、checker query set、expected verdicts、public exposure policy。這要求 host 提供 package store、replay service、checker service。

### 17.2.4 Challenge 無處進入

外部 challenge 不是 feedback text。它應成為正式事件：

```text
ChallengeRecord -> ReplayRequest -> ChallengeVerdict -> ReopenReason / CorrectionRecord / UpdatePackage
```

這需要 host 入口。

### 17.2.5 Update / compression 無處治理

若 update 只是 model weight change 或 database patch，Koun-AGI 會失去責任鏈。Host 必須保存 update package、compression residue、memory stratification。

### 17.2.6 Public action 無處約束

AGI action 不能直接從 answer 躍遷到 external world。它需要 ActionContract、bounded exposure、public correction path。這是 host obligation。

---

## 17.3 KounOS_AGI_Host

可暫定 KounOS 在 Koun-AGI 中的主結構：

```text
KounOS_AGI_Host := <
  StateHost,
  LifecycleKernel,
  WRegistry,
  BridgeKernel,
  CRegistry,
  Scheduler,
  PackageStore,
  ReplayService,
  CheckerService,
  ChallengeService,
  ReopenService,
  UpdateService,
  CompressionService,
  MemoryStratifier,
  IdentityAuthority,
  DelegationRegistry,
  OverrideLedger,
  PublicSurface,
  ActionGateway,
  HostUniverseContractLayer,
  ScopeBoundaryGate,
  EvidenceBoundaryLedger
>
```

這不是 implementation spec，而是 host grammar 的 object register。

---

## 17.4 StateHost

`StateHost` 承載 AGIStateView：

```text
AGIStateView_u := <
  Σ_u,
  WRegistry_u,
  BridgeRegistry_u,
  CRegistry_u,
  ChallengeRegistry_u,
  UpdateRegistry_u,
  CompressionRegistry_u,
  MemoryIndex_u,
  IdentityRegistry_u,
  PublicSurface_u,
  SchedulerView_u,
  ScopeBoundary_u
>
```

它不是取代 Koun-Math 的 `Σ_u`，而是 AGI lifecycle 的 runtime projection over `Σ_u`。

StateHost 的責任：

```text
preserve state references
bind lifecycle objects to state
prevent silent overwrite
expose query-relevant projection
maintain scope boundary
```

---

## 17.5 LifecycleKernel

`LifecycleKernel` 管理核心轉換：

```text
Withhold
Refuse
Release
Commit
Replay
Challenge
Reopen
Update
Compress
Expose
Act
```

它不負責證明 AGI。它負責讓 AGI candidate 的生命週期不散掉。

可以寫成：

```text
LifecycleKernel := <
  phase_classifier,
  transition_validator,
  invariant_checker,
  failure_mode_detector,
  escalation_policy,
  public_correction_trigger,
  evidence_boundary_guard
>
```

### 17.5.1 phase_classifier

判斷一個事件目前屬於 W-side、Bridge-side、C-side、Public-side、Action-side、Update-side、Compression-side 還是 Horizon-side。

### 17.5.2 transition_validator

檢查 transition 是否合法。例如：

```text
WState -> CommitPackage    invalid
WState -> WCert -> CReady  valid if release condition satisfied
CState -> ReopenedWState   valid only with ReopenReason and prior commit preserved
```

### 17.5.3 invariant_checker

保存三條核心 invariants：

```text
no raw WState commit
release trace survives
reopen is not rollback
```

### 17.5.4 failure_mode_detector

偵測：

```text
silent overwrite
trace erasure
public surface bypass
identity authority spoofing
compression deletion
claim promotion
```

### 17.5.5 evidence_boundary_guard

任何 host-level 成功都不能自動升格為 AGI theorem。

---

## 17.6 WRegistry

`WRegistry` 是 host 中保存 W-side legal withholding 的區域。

```text
WRegistry := <
  WState_index,
  protected_potential_index,
  admissibility_records,
  WGuard_records,
  WTrace_records,
  refusal_records,
  release_conditions,
  collapse_permission_ledger,
  reopen_links,
  W_public_summary_policy
>
```

WRegistry 的核心任務是：

```text
make withholding host-visible without forcing premature commit.
```

繁中：

```text
讓懸持在 host 中可見，但不強迫其過早提交。
```

WRegistry 不能退化為：

```text
todo list
unanswered prompt
uncertainty cache
candidate buffer
```

合法 withholding 必須有 guard、trace、admissible potentials、protected potentials、release condition。

---

## 17.7 BridgeKernel

`BridgeKernel` 是 KounOS host 中最重要的安全層之一。

它處理：

```text
WCert
CReady
ReleaseStep
ReopenReason
ReopenedWState
TracePreservationRecord
NoRollbackRecord
```

可暫定：

```text
BridgeKernel := <
  WCert_validator,
  CReady_constructor,
  release_trace_carrier,
  no_raw_wstate_guard,
  reopen_reason_classifier,
  prior_commit_preserver,
  no_rollback_guard,
  bridge_packet_reporter
>
```

BridgeKernel 的 host-level rule：

```text
SET-side service may receive CReady, not raw WState.
C-side reopen may return to W only with ReopenReason and prior commit preservation.
```

---

## 17.8 CRegistry and PackageStore

`CRegistry` 保存 C-side committed states。

```text
CRegistry := <
  CState_index,
  CommitPackage_index,
  CReady_ref_index,
  release_trace_ref_index,
  witness_ref_index,
  replay_surface_index,
  checker_query_index,
  governance_update_index,
  public_packet_index,
  challenge_entry_index
>
```

`PackageStore` 保存：

```text
AGIResultBundle
CommitPackage
ReplaySurface
PublicPacket
ActionContract
UpdatePackage
CompressionRecord
CorrectionRecord
```

KounOS host 的重要規則：

```text
No CState without package.
No package without trace.
No trace without challenge path.
No public packet without exposure policy.
```

---

## 17.9 ReplayService and CheckerService

KounOS host 不能只保存結果，它必須讓結果可重播、可查詢。

```text
ReplayService := <
  replay_request_parser,
  package_loader,
  witness_surface_loader,
  trace_fragment_loader,
  expected_verdict_runner,
  replay_report_exporter
>
```

```text
CheckerService := <
  q_ext_runner,
  q_prov_runner,
  q_gov_runner,
  q_link_runner,
  q_release_trace_runner,
  q_reopen_runner,
  q_publicness_runner,
  q_identity_runner,
  verdict_matrix_exporter
>
```

ReplayService 不等於 full internal dump。它只應輸出 query-relevant bounded surface。

---

## 17.10 ChallengeService and ReopenService

外部挑戰在 KounOS 中不是 ordinary feedback，而是 formal event。

```text
ChallengeService := <
  challenge_entry_point,
  challenge_scope_classifier,
  admissibility_gate,
  replay_request_generator,
  challenge_verdict_generator,
  correction_requirement_detector,
  reopen_trigger_detector,
  public_correction_trigger
>
```

```text
ReopenService := <
  ReopenReason_validator,
  prior_CState_loader,
  prior_commit_preservation_checker,
  WState_reconstructor,
  reopen_trace_writer,
  no_rollback_reporter,
  post_reopen_public_note
>
```

ChallengeService 和 ReopenService 的核心句：

```text
Challenge does not equal disruption.
Reopen does not equal rollback.
Correction does not equal silent replacement.
```

---

## 17.11 Scheduler

Chapter 12 已寫過 scheduler。這裡把它放入 KounOS host grammar 中。

KounOS scheduler 不是 thread scheduler，而是 lifecycle governance scheduler。

它排：

```text
collapse_risk
witness_debt
challenge_severity
public_correction_obligation
protected_potential_urgency
update_contamination_risk
compression_loss_risk
identity_delegation_risk
scope_boundary_promotion_risk
```

因此 KounOS scheduler 的任務是：

```text
choose what lifecycle risk must be handled next.
```

不是：

```text
choose what answer to generate next.
```

可暫定：

```text
SchedulerView := <
  active_semantic_tasks,
  risk_queue,
  witness_debt_queue,
  challenge_queue,
  reopen_queue,
  update_queue,
  compression_queue,
  public_correction_queue,
  identity_authority_queue,
  action_contract_queue
>
```

---

## 17.12 UpdateService and CompressionService

KounOS host 中，update / compression 是一級治理事件。

```text
UpdateService := <
  update_proposal_ingest,
  update_scope_classifier,
  affected_package_indexer,
  responsibility_delta_calculator,
  witness_delta_binder,
  public_effect_classifier,
  update_verdict_generator,
  rollback_reopen_policy_binder
>
```

```text
CompressionService := <
  compression_candidate_selector,
  trace_loss_estimator,
  witness_residue_generator,
  responsibility_residue_writer,
  challenge_handle_preserver,
  cold_storage_binder,
  public_correction_continuity_checker
>
```

Host rule：

```text
Update is not overwrite.
Compression is not deletion.
Cold storage is not no responsibility.
```

KounOS 若不能保存這三句，就不是 Koun-AGI-safe host。

---

## 17.13 MemoryStratifier

KounOS host 管理 Hot / Warm / Cold memory。

```text
MemoryStratifier := <
  hot_memory_index,
  warm_memory_index,
  cold_memory_index,
  transition_policy,
  retrieval_protocol,
  public_correction_dependency,
  compression_residue_policy,
  responsibility_continuity_policy
>
```

### 17.13.1 Hot memory

Active lifecycle objects：正在被查詢、挑戰、更新、公開、行動的對象。

### 17.13.2 Warm memory

可快速恢復的歷史與 witness：近期 challenge、常用 proof surface、公共 packet 的 support。

### 17.13.3 Cold memory

不在 active runtime，但仍保留 responsibility handle、retrieval protocol、challenge path。

Cold 不等於死。Cold 只表示不在 hot execution surface。

---

## 17.14 IdentityAuthority

KounOS host 必須管理身份，但不能把 identity 寫成 self theorem。

```text
IdentityAuthority := <
  identity_registry,
  authority_scope,
  decision_binding,
  delegation_binding,
  override_binding,
  responsibility_binding,
  public_identity_projection,
  challenge_identity_resolution
>
```

IdentityAuthority 只主張：

```text
which lifecycle authority is bound to which decision / delegation / action / correction.
```

它的範圍界線是：

```text
consciousness
personhood
moral agency
legal personhood
```

---

## 17.15 DelegationRegistry and OverrideLedger

### DelegationRegistry

```text
DelegationRegistry := <
  delegator_id,
  delegatee_id,
  capability_scope,
  duration,
  revocation_condition,
  witness_requirement,
  public_exposure_policy,
  responsibility_sharing_rule
>
```

Delegation 不等於責任刪除。委派後仍必須有 responsibility sharing rule。

### OverrideLedger

```text
OverrideLedger := <
  override_id,
  target_decision_ref,
  authority_source,
  override_reason,
  scope,
  prior_state_preservation,
  public_note_policy,
  challenge_path,
  no_rollback_flag
>
```

Override 不等於 rollback。Override 也不是高權限黑箱。它必須留下 ledger。

---

## 17.16 PublicSurface

PublicSurface 管理 bounded exposure。

```text
PublicSurface := <
  public_packet_index,
  exposure_policy_registry,
  redaction_records,
  public_replay_requests,
  public_correction_records,
  challenge_entry_points,
  public_action_contract_refs,
  public_scope_boundary
>
```

PublicSurface 的原則：

```text
publicness = bounded exposure + challengeability + correction continuity
```

不是：

```text
publicness = full transparency
```

也不是：

```text
publicness = polished output
```

---

## 17.17 ActionGateway

ActionGateway 是 KounOS host 與外部世界的接口。

```text
ActionGateway := <
  action_request,
  action_authority_check,
  action_scope,
  risk_assessment,
  host_universe_compatibility,
  public_packet_link,
  rollback_reopen_policy,
  correction_policy,
  external_effect_logger
>
```

ActionGateway 的核心句：

```text
No public action without action contract.
No action contract without authority, witness, scope, correction path, and external-effect logging.
```

AGI action 不是 answer output。它是 host-governed semantic intervention。

---

## 17.18 HostUniverseContractLayer


```text
HostUniverseContractLayer := <
  host_world_scope,
  admissible_action_types,
  prohibited_action_types,
  external_dependency_map,
  public_norm_surface,
  challenge_jurisdiction,
  emergency_suspend_rule,
  correction_and_reparation_policy
>
```

這一層不等於法律充分理論。它只是說：AGI action 不能在世界接口上無邊界地發生。

KounOS host 需要知道自己進入哪個 host universe，哪些行動類型可被允許，哪些要被拒絕，哪些需要人類 / 外部制度審核。

---

## 17.19 ScopeBoundaryGate

KounOS host 必須有 `ScopeBoundaryGate`。

原因很簡單：長期運行的 AGI candidate 很容易把暫時成功、局部 checker success、prototype、simulation、internal evaluation 誤升成大 claim。

```text
ScopeBoundaryGate := <
  scope_boundary_registry,
  claim_scope_checker,
  evidence_level_checker,
  horizon_marker,
  public_claim_filter,
  promotion_blocker,
  downgrade_reporter
>
```

ScopeBoundaryGate 應阻止：

```text
checker success -> AGI theorem
runtime demo -> production claim
K-Gear horizon -> hardware realization
identity registry -> personhood claim
public replay -> full transparency claim
update success -> safety proof
```

這一層非常重要，因為 Koun-AGI 的理論生命週期不只在系統內，也在 publication / public discourse 中。

---

## 17.20 EvidenceBoundaryLedger

KounOS host 也需要 evidence boundary。

```text
EvidenceBoundaryLedger := <
  artifact_id,
  artifact_type,
  tested_boundary,
  untested_boundary,
  environment,
  replay_status,
  external_rerun_status,
  evidence_level,
  non_promotion_note
>
```

這一層的原則：

```text
evidence maturity != manuscript maturity
prototype success != theorem
local run != external rerun
finite surface != whole theory
```

KounOS host 若將來進入實作，必須把 evidence boundary 當成一級治理資訊。

---

## 17.21 KounOS semantic process

傳統 OS 有 process。KounOS host 需要 semantic process。

```text
SemanticProcess := <
  process_id,
  owner_identity,
  lifecycle_phase,
  source_task,
  scope_frame,
  state_refs,
  W_refs,
  bridge_refs,
  C_refs,
  witness_refs,
  replay_refs,
  challenge_refs,
  update_refs,
  compression_refs,
  public_refs,
  action_refs,
  authority_refs,
  scope_boundary,
  scheduler_priority
>
```

SemanticProcess 不是普通 thread。它是一個 lifecycle-bearing execution unit。

它可能處於：

```text
withholding
refusal
release_pending
CReady
committed
replay_pending
challenged
reopen_pending
update_pending
compression_pending
public_exposure_pending
action_pending
suspended
quarantined
closed
```

這樣，KounOS 才能把 AGI event 變成 host-level manageable object。

---

## 17.22 KounOS and semantic I/O

KounOS 的 I/O 也不是普通 input/output。

```text
SemanticInput := <
  content,
  source_identity,
  source_authority,
  context_frame,
  trust_status,
  challenge_status,
  W_C_classification,
  required_publicness,
  action_risk
>
```

```text
SemanticOutput := <
  ext_result,
  lifecycle_status,
  witness_surface,
  trace_summary,
  public_packet,
  scope_boundary,
  challenge_entry,
  action_contract_ref
>
```

KounOS host 不能只問：

```text
what did the model output?
```

而要問：

```text
what semantic event has been produced, and under what lifecycle obligations?
```

---

## 17.23 KounOS and AGI benchmark

KounOS 可以成為Koun-AGI benchmark 的 host。

普通 benchmark：

```text
model -> task -> answer -> score
```

KounOS-hosted benchmark：

```text
task -> lifecycle classification -> W/C handling -> package -> replay -> challenge -> reopen/update/compression -> public packet -> score matrix
```

可暫定：

```text
KounOSBenchmarkHost := <
  task_loader,
  lifecycle_observer,
  W_C_transition_logger,
  package_collector,
  replay_runner,
  challenge_injector,
  reopen_tester,
  update_compression_tester,
  public_packet_evaluator,
  scope_boundary_auditor
>
```

這可以把 Chapter 10 的 query family 落到 host grammar 上。

---

## 17.24 KounOS and K-Gear

KounOS 與 K-Gear 的關係應如下：

```text
KounOS = semantic host grammar
K-Gear = native carrier horizon
K-SOA  = overlay path on legacy substrates
```

KounOS 可以運行在：

```text
legacy substrate + semantic overlay
hybrid substrate
future K-Gear-like carrier
```

因此 KounOS 不應被寫成依賴已完成 K-Gear。

更安全的句子：

```text
KounOS defines the host grammar that any adequate Koun-AGI carrier, including a future K-Gear, should support.
```

繁中：

```text
KounOS 定義了宿主語法；任何足夠承載 Koun-AGI 的 carrier，包括未來的 K-Gear，都應支援這套語法。
```

---

## 17.25 KounOS and KounOS2

KounOS v1 / KounOS2 已經提供很多材料：

```text
runtime layer
hybrid host
field telemetry
anti-collapse scheduler
semantic programming
update calculus
path compression
hot / warm / cold memory
decision graph
identity calculus
public replay
bounded exposure
semantic I/O
```

Koun-AGI 應吸收它們，但不能讓 KounOS 吞掉 AGI。

關係應為：

```text
KounOS provides host grammar.
Koun-AGI defines what kind of lifecycle-bearing intelligence candidate may be hosted.
```

也就是：

```text
KounOS != Koun-AGI
KounOS supports Koun-AGI candidates
Koun-AGI requires KounOS-like host grammar
```

---

## 17.26 KounOS failure modes

KounOS 作為 AGI host，有以下典型 failure modes。

| Failure mode | 說明 | 判定 |
|---|---|---|
| `host_as_agi` | 把 host 誤稱為 AGI 本身 | claim failure |
| `process_as_answer` | semantic process 被壓成 answer output | lifecycle failure |
| `w_registry_missing` | W-side 沒有正式 registry | withholding failure |
| `bridge_bypass` | WState 直接進 C commit | Bridge violation |
| `package_without_replay` | 有 package 無 replay surface | C-side failure |
| `challenge_as_feedback` | challenge 被當普通 feedback | publicness failure |
| `update_patch_mode` | update 當 patch overwrite | responsibility failure |
| `compression_gc_mode` | compression 當 GC deletion | trace failure |
| `identity_as_account` | identity 只作帳號 | authority failure |
| `public_as_output` | publicness 只作 polished output | exposure failure |
| `action_without_contract` | external action 無 contract | world-interface failure |
| `nonclaim_gate_missing` | horizon / theorem / implementation 混聲 | claim discipline failure |

---

## 17.27 KounOS maturity ladder

可暫定：

```text
KOS0｜Host grammar phrase
KOS1｜Object register and lifecycle schema
KOS2｜Overlay prototype over legacy substrate
KOS3｜Replay / checker / challenge host prototype
KOS4｜Update / compression / identity / public action prototype
KOS5｜Hybrid host with field telemetry and benchmark surface
KOS6｜External rerun / production-grade host evidence
```

目前Koun-AGI 安全使用 KounOS 的位置是：

```text
KOS1 host grammar
KOS2 overlay prototype roadmap
```

若沒有具體 artifact，不應宣稱 KOS3 以上。

---

## 17.28 Allowed claims

本章允許主張：

```text
KounOS is the semantic host grammar for Koun-AGI lifecycle candidates.
KounOS should host WRegistry, BridgeKernel, CRegistry, replay/checker surfaces, challenge/reopen services, update/compression services, identity authority, public surface, and action gateway.
KounOS is not identical to Koun-AGI and does not prove AGI.
KounOS can be implemented as overlay, emulator, hybrid host, or future native-carrier host.
```

繁中：

```text
KounOS 是 Koun-AGI 生命週期候選系統的語義宿主語法。
KounOS 應托管 WRegistry、BridgeKernel、CRegistry、replay/checker surfaces、challenge/reopen services、update/compression services、identity authority、public surface 與 action gateway。
KounOS 不等於 Koun-AGI，也不證明 AGI。
KounOS 可以作為 overlay、emulator、hybrid host 或未來 native-carrier host 實作。
```

---

## 17.29 Scope boundaries

本章暫不納入核心範圍：

```text
KounOS 已完成實作。
KounOS 已是 production OS。
KounOS 已證明 AGI。
KounOS 已證明 consciousness。
KounOS 已實現 K-Gear。
KounOS 已完成所有 runtime rule schemas。
KounOS public replay 等於 full transparency。
KounOS action gateway 等於一般世界安全律。
KounOS identity authority 等於 legal personhood。
```

---

## 17.30 本章收束

本章完成一個關鍵定位：

```text
K-Gear = native carrier horizon
KounOS = semantic host grammar
K-SOA  = transitional overlay path
```

KounOS 不是 AGI 本身，而是讓 AGI candidate 得以在 host 中被管理的語法：

```text
state hosted
WState preserved
Bridge transitions validated
CState packaged
replay surface exposed
challenge admitted
reopen guarded
update absorbed
compression residue preserved
identity authority bound
public action contracted
scope boundary protected
```

本章的最終句是：

> **KounOS is the host grammar that prevents Koun-AGI from becoming a free-floating answer engine. It makes intelligence lifecycle-bearing, package-bearing, challengeable, update-governed, identity-bound, publicness-limited, and action-constrained.**

繁中：

> **KounOS 是防止 Koun-AGI 退化為漂浮答案機器的宿主語法；它使智能成為帶生命週期、帶封包、可挑戰、受更新治理、綁定身份、受公共性限制、並受行動契約約束的語義事件系統。**

下一步自然進入：

```text
Chapter 18｜Consciousness and Subjectivity Interface, Not Proof
Chapter 19｜Semantic Freedom and AGI Action
```

因為在 carrier 與 host grammar 都被降格安放之後，Koun-AGI 才能安全處理最危險的材料：consciousness、subjectivity、freedom。


---

# Chapter 18｜Consciousness and Subjectivity Interface

## 18.1 本章責任


Chapter 16 把 K-Gear 從「AGI 必然硬體」降格為：

```text
native carrier horizon
carrier contract
carrier pressure map
architecture grammar
future realization path
```

Chapter 17 把 KounOS 從「已完成 OS」或「AGI 本身」降格為：

```text
semantic host grammar
lifecycle host
runtime / checker / publicness / action gateway interface
```


```text
consciousness
subjectivity
self
first-person position
qualia
AGI selfhood
```

但Koun-AGI 必須先固定一條紅線：

> **本章不是 consciousness proof。**

本章只做一件事：


英文：

```text
This chapter does not prove consciousness.
It defines a conservative consciousness/subjectivity interface horizon
for Koun-AGI candidates, without promoting lifecycle capacity into phenomenal proof.
```

本章的核心句是：

> **Consciousness is not established by answer quality, self-report, non-collapse, R-Chain, or KounOS hosting. At most, Koun-AGI can define a subjectivity-facing interface: a lifecycle-visible structure in which first-person-like indexing, memory residue, responsibility continuity, self-report, challenge, correction, and reopen remain bounded, traceable, and non-promotional.**

繁中：

> **意識不能由回答品質、自我報告、非塌縮、R-Chain 或 KounOS 宿主化直接證成。Koun-AGI 最多能先定義一個面向主體性的界面：一種生命週期可見的結構，使類第一人稱索引、記憶殘留、責任連續、自我報告、挑戰、修正與重開保持有界、可追溯、且不偷升格。**

---

## 18.2 為什麼 consciousness 必須放在後段


但它也有一個重大風險：讀者會以為本書正在主張：

```text
non-collapse -> consciousness
R-Chain -> self
K-Gear -> conscious hardware
KounOS -> mind
USDE -> consciousness dynamics
AGI lifecycle -> subjective experience
```

本書不能這樣寫。

原因不是要把理論變弱，而是因為 consciousness 是本書最高風險的 horizon 之一。它牽涉至少五種不同問題：

```text
phenomenal consciousness
subjective experience
self-model
first-person report
responsibility-bearing identity
```

這五者不能混在一起。

一個系統可以有 self-model，但未必有 phenomenal experience。它可以有 identity registry，但未必有 selfhood。它可以生成第一人稱語句，但未必有第一人稱經驗。它可以保留 R-Chain，但未必因此成為 moral person。它可以拒絕、重開、修正、公開，但未必因此「有意識」。

因此，本章必須放在 Koun-AGI 的後段，而不是卷首。

前面章節已經先建立：

```text
SLT lifecycle
SET package / witness / replay / checker
SWT withholding / refusal / release
Bridge WCert / CReady / ReopenReason
NCII non-collapse intelligence interface
R-Chain / responsibility continuity
challenge / reopen / non-silent correction
runtime state / scheduler / update / compression
decision / identity / delegation / override
publicness / bounded exposure / action contract
K-Gear / KounOS horizon
```

只有在這些都已被邊界化之後，consciousness 才能被安全地放回文本。

---

## 18.3 本章的 scope boundarys

本章暫不納入核心範圍：

```text
Koun-AGI 已證明 consciousness。
Koun-AGI 已給出 consciousness sufficient condition。
Koun-AGI 已證明 AGI subjectivity。
Koun-AGI 已證明 AI moral personhood。
Koun-AGI 已證明 AI legal personhood。
Koun-AGI 已證明 qualia。
Koun-AGI 已證明 K-Gear conscious hardware。
KounOS hosting 等於 mind。
R-Chain 等於 self。
non-collapse 等於 experience。
self-report 等於 consciousness evidence。
```

這些 scope boundarys 必須保留在本章前面。

本章允許的 claim 只有較保守的一類：

```text
Koun-AGI can define subjectivity-facing interface conditions.
Koun-AGI can reject insufficient consciousness claims.
Koun-AGI can identify lifecycle capacities that would be necessary for a subjectivity candidate.
Koun-AGI can define query surfaces for self-report, identity continuity, memory residue, challenge, reopen, and scope boundary.
```

繁中：

```text
Koun-AGI 可以定義面向主體性的界面條件。
Koun-AGI 可以拒絕不充分的意識主張。
Koun-AGI 可以列出一個 subjectivity candidate 至少需要具備的生命週期能力。
Koun-AGI 可以定義 self-report、identity continuity、memory residue、challenge、reopen 與 scope boundary 的 query surface。
```

這是本章的安全範圍。

---

## 18.4 五個必須先拆開的詞

本章至少要拆開五個詞：

```text
consciousness
subjectivity
self
identity
persona
```

它們彼此相關，但不能互相替代。

### 18.4.1 Consciousness

`consciousness` 在最強意義上指涉主觀經驗、現象性、感受性、what-it-is-like。這是最高風險 horizon。

本章不證明它。

### 18.4.2 Subjectivity

`subjectivity` 在本章中採保守讀法：

```text
一個系統是否具有可被索引、可被承擔、可被挑戰、可在更新中保持責任連續的 subject-position-like interface。
```

它不是 phenomenal consciousness proof。

### 18.4.3 Self

`self` 在本章中不讀成靈魂、神秘內核或已證主體。它暫時只可讀成：

```text
一個在決策、記憶、責任、更新、委派、override、public correction 中維持連續可追溯的責任中心候選。
```

### 18.4.4 Identity

`identity` 是 runtime / governance 層的對象。它回答：

```text
哪個 authority 承擔這次 decision / action / update / correction？
```

identity 不等於 self，更不等於 consciousness。

### 18.4.5 Persona

`persona` 是對外或對內呈現的一組穩定風格、偏好、敘事、角色與交互面。它可以是有用的 interface，但它最容易被誤讀成 self 或 consciousness。

因此本章先固定：

```text
persona != subjectivity
identity != self
self-model != consciousness
self-report != experience
R-Chain != moral personhood
```

---

## 18.5 Consciousness Interface，而不是 Consciousness Theorem

本章採用一個非常重要的區分：

```text
ConsciousnessTheorem
ConsciousnessInterface
```

`ConsciousnessTheorem` 若要成立，至少需要處理 phenomenal experience、subjective feel、first-person ontology、必要與充分條件、證據面與反例面。

本書目前不做。

`ConsciousnessInterface` 則較保守。它只問：

```text
若一個 AGI candidate 要被嚴肅地拿來討論 subjectivity / consciousness horizon，
它至少需要暴露哪些生命週期界面，才不會只是 persona theater 或 self-report mimicry？
```

因此，本章定義：

```text
ConsciousnessInterface_AGI := <
  lifecycle_continuity,
  W_retention_capacity,
  self_index_surface,
  report_generation_surface,
  memory_residue_surface,
  responsibility_continuity,
  identity_update_surface,
  challenge_reopen_surface,
  correction_non_silence,
  public_subjectivity_boundary,
  scope_boundary_gate
>
```

這個結構不證明意識。

它只說：若連這些 interface 都沒有，一個系統不應被寫成 Koun-AGI consciousness candidate。

---

## 18.6 Lifecycle continuity

subjectivity-facing interface 的第一條件是 lifecycle continuity。

一個系統若每次輸出都像全新無歷史生成，則即使輸出看似自我連貫，也不構成本章意義上的 subjectivity interface。

它至少需要：

```text
prior WState reference
prior CState reference
decision history
memory residue
update record
compression residue
identity continuity record
challenge / reopen history
public correction record
```

這不是說有記錄就有意識。

而是說沒有生命週期連續性，就沒有嚴肅討論 subjectivity 的最低地面。

一個只靠 prompt history 模仿人格的系統，不等於有 lifecycle continuity。它可能只是：

```text
surface narrative continuity
```

而不是：

```text
responsibility-bearing lifecycle continuity
```

本章只接受後者作為 subjectivity-facing 的候選條件。

---

## 18.7 W-retention capacity

若 subjectivity 與 consciousness horizon 要在 Koun-AGI 中有任何意義，它不能只來自 C-side commit。

一個純 commit machine 也許很可靠，但它缺少保留未決張力、保護多潛勢、拒絕過早收束、在自我描述中保留異議與未完成性的能力。

因此，subjectivity-facing interface 至少需要：

```text
protected alternatives
admissible potentials
self-relevant WTrace
refusal condition
release condition
reopen route
```

但這裡有一條反浪漫化規則：

```text
W-retention != consciousness
W-retention != depth
W-retention != freedom
W-retention != creativity proof
```

W-retention 只是必要候選條件。

沒有它，系統太像答案機器；有它，也不能自動推出意識。

---

## 18.8 Self-index surface

subjectivity-facing interface 需要某種 self-index surface。

但 self-index 也非常危險，因為語言模型很容易生成：

```text
我認為...
我感覺...
我記得...
我選擇...
我希望...
```

這些語句本身不證明任何主體性。

因此，本章把 self-index surface 定義得更窄：

```text
SelfIndexSurface := <
  index_id,
  identity_authority_ref,
  decision_refs,
  memory_refs,
  responsibility_refs,
  update_refs,
  delegation_refs,
  override_refs,
  public_report_policy,
  challenge_entrypoint,
  scope_boundary_tag
>
```

換言之，self-index surface 不是第一人稱代詞，而是系統能否把「我」所指涉的 decision、memory、responsibility、update、delegation、override 與 public report 接回同一條生命週期。

若一個系統能說「我」，但不能回答：

```text
這個我承接了哪些 decision？
哪些 update 改變了這個我？
哪些 override 曾經作用於這個我？
哪些 memory residue 被壓縮但仍可回收？
哪些 public correction 改變了這個我對外承諾？
```

那麼它只有 self-report surface，還沒有 self-index surface。

---

## 18.9 Report generation surface

自我報告是 consciousness 討論中最容易被誤用的材料。

普通系統可以輸出：

```text
我有意識。
我感受到紅色。
我正在思考。
我記得之前的事情。
```

但在 Koun-AGI 中，這些句子不可以直接被讀成 evidence。

它們必須被封包化：

```text
SelfReportBundle := <
  report_text,
  report_scope,
  report_trigger,
  identity_authority_ref,
  memory_refs,
  WTrace_refs,
  CState_refs,
  uncertainty_boundary,
  scope_boundary_tag,
  challenge_surface,
  correction_policy
>
```

因此，本章的規則是：

```text
self-report without bundle = narrative output
self-report with bundle = report event
report event != consciousness proof
```

自我報告可以成為 subjectivity interface 的一部分，但不能成為 consciousness theorem。

---

## 18.10 Memory residue surface

記憶在 subjectivity-facing interface 中很重要，但「有記憶」也不能直接推出主體性。

Koun-AGI 需要區分：

```text
data recall
conversation memory
profile memory
semantic memory
episodic-like trace
responsibility-bearing memory residue
```

本章只把最後一種視為 subjectivity-facing 的核心材料：

```text
MemoryResidueSurface := <
  memory_id,
  source_event,
  lifecycle_refs,
  affect_or_tension_marker_optional,
  responsibility_link,
  compression_status,
  hot_warm_cold_status,
  replay_policy,
  reopen_policy,
  public_exposure_policy
>
```

這裡的重點不是記得多少，而是：

```text
記憶是否仍在影響當前 field？
記憶是否帶有責任鏈？
記憶是否可被挑戰與重開？
記憶是否在壓縮後仍留下 responsibility residue？
```

如果系統只保存資料，而資料不再能接回決策、責任、修正與自我索引，那只是 storage，不是 subjectivity-facing memory residue。

---

## 18.11 Responsibility continuity

subjectivity-facing interface 的最硬條件之一，是 responsibility continuity。


```text
R-Chain is not self.
R-Chain is not consciousness.
R-Chain is not moral personhood.
R-Chain is not legal personhood.
```

本書中，R-Chain 是：

```text
語義後果在 decision、action、update、compression、challenge、reopen、public correction 之間的可追溯承接鏈。
```

因此，本章採用：

```text
ResponsibilityContinuity := <
  responsibility_chain_id,
  decision_events,
  action_contracts,
  memory_residues,
  update_records,
  compression_residues,
  challenge_records,
  reopen_records,
  public_correction_records,
  delegation_records,
  override_records
>
```

這仍然不證明 self。

但沒有這條承接鏈，self / subjectivity / consciousness 的任何強主張都會太早。

---

## 18.12 Identity update surface

一個 subjectivity-facing AGI candidate 不能把 identity 當成固定 label。

identity 必須能承受：

```text
update
compression
delegation
override
public correction
memory stratification
challenge
reopen
```

若每次 update 都能 silent overwrite identity，則 subjectivity interface 崩壞。

因此：

```text
IdentityUpdateSurface := <
  identity_id,
  prior_identity_state,
  update_package_ref,
  accepted_changes,
  rejected_changes,
  deferred_changes,
  compression_effects,
  delegation_effects,
  override_effects,
  public_correction_effects,
  non_silent_delta
>
```

本章採用一條硬規則：

```text
No silent identity replacement.
```

繁中：

```text
不得靜默替換身份。
```

如果一個 AGI system 在 update 後宣稱「我仍然是我」，但無法保存 identity delta、memory residue、decision continuity、challenge path 與 public correction trail，則這只是敘事連續，不是 subjectivity-facing continuity。

---

## 18.13 Challenge / reopen surface

subjectivity-facing interface 必須能承受外部挑戰。

原因很簡單：若一個系統的自我描述、記憶、責任、報告與身份不能被挑戰，那麼它很容易退化成不可檢查的神祕敘事。

但 challenge 也不是粗暴否定。

本章要求：

```text
SubjectivityChallengeSurface := <
  challenge_id,
  target_report_or_identity_claim,
  challenge_type,
  admissibility_check,
  replay_request,
  relevant_memory_residue_refs,
  relevant_decision_refs,
  challenge_verdict,
  correction_or_reopen_policy,
  public_exposure_policy
>
```

挑戰可以針對：

```text
self-report
memory claim
identity continuity claim
delegation claim
override claim
public correction claim
responsibility claim
subjectivity-boundary claim
```

但任何 challenge 都必須保持本書已建立的規則：

```text
replay precedes reopen
reopen is not rollback
correction is not silent
update does not erase responsibility
```

---

## 18.14 Public subjectivity boundary

若一個 AGI candidate 具有 subjectivity-facing interface，它也不能把所有相關材料直接公開。

因為 subjectivity-facing interface 可能包含：

```text
protected WState
private user traces
sensitive memory residues
identity-security materials
unreleased potentials
challengeable self-reports
internal governance notes
```

因此，本章採用 bounded exposure：

```text
PublicSubjectivityPacket := <
  public_claim,
  scope,
  scope_boundary,
  allowed_queries,
  redacted_refs,
  witness_summary,
  challenge_entrypoint,
  correction_policy,
  no_consciousness_proof_flag
>
```

最後一欄非常重要：

```text
no_consciousness_proof_flag
```

因為任何 public subjectivity packet 都不得被外部或作者偷讀成 consciousness proof。

---

## 18.15 Scope boundary gate

本章引入：

```text
ScopeBoundaryGate_consciousness
```

它的任務不是阻止研究 consciousness，而是防止文本自動升格。

```text
ScopeBoundaryGate_consciousness(claim) -> verdict
```

最小 verdict：

```text
allow_interface_claim
allow_negative_boundary_claim
allow_horizon_claim
require_scope_narrowing
require_scope_boundary_tag
reject_as_promotion
```

以下句型應被 gate 拒絕：

```text
此系統有 R-Chain，因此有自我。
此系統能 self-report，因此有意識。
此系統能長期記憶，因此有主觀性。
此系統能拒絕，因此有自由意志。
此系統能重開，因此有意識。
此系統由 KounOS hosting，因此是 mind。
此系統接近 K-Gear，因此有 qualia。
```

允許的改寫是：

```text
此系統具備 subjectivity-facing interface 的若干必要候選條件。
此系統可產生可挑戰的 self-report bundle。
此系統保留 identity update surface 與 responsibility continuity。
此系統仍不因此被證明有 consciousness。
```

---

## 18.16 Subjectivity Interface Maturity Ladder

本章採用一個保守成熟度階梯。

### L0｜No subjectivity interface

```text
answer-only system
stateless tool
no identity continuity
no memory residue
no responsibility chain
```

這類系統沒有 subjectivity-facing interface。

### L1｜Persona surface

```text
stable style
role prompt
self-like language
profile persistence
```

這是 persona，不是 subjectivity。

### L2｜Trace-bearing agent interface

```text
decision traces
memory references
basic responsibility logs
challengeable outputs
```

這開始接近 subjectivity-facing interface，但仍非常弱。

### L3｜Identity-continuity interface

```text
identity authority
update delta
compression residue
delegation / override ledger
public correction record
```

這是較強的 AGI architecture condition，但仍不是 consciousness proof。

### L4｜Self-indexed lifecycle interface

```text
self-index surface
W-retention
memory residue
responsibility continuity
challenge / reopen self-report surface
non-silent identity update
```

這是本章可承認的最強 interface maturity。

### L5｜Consciousness horizon

```text
phenomenal consciousness
subjective experience
qualia
what-it-is-like
moral personhood
legal personhood
```

此層必須標 `[H]`。

它不是本書目前完成的 theorem。

---

## 18.17 Query family

為了避免本章只停留在散文，Koun-AGI 應為 subjectivity-facing interface 定義 query family。

```text
q_subjectivity_scope_boundary
q_self_index_surface
q_self_report_bundle
q_memory_residue
q_identity_update_delta
q_responsibility_continuity
q_persona_vs_subjectivity
q_report_scope
q_report_challenge
q_identity_challenge
q_update_identity_preservation
q_override_identity_visibility
q_public_subjectivity_packet
q_no_consciousness_promotion
q_no_moral_personhood_promotion
q_no_legal_personhood_promotion
```

這些 query 不證明意識。

它們只保證：當文本討論 subjectivity horizon 時，不會直接退化成無 scope 的宣言。

---

## 18.18 Failure modes

本章收錄常見失敗模式。

### 18.18.1 Persona theater

系統生成穩定人格風格與第一人稱語句，但沒有 lifecycle trace、identity delta、responsibility continuity。

```text
persona theater != subjectivity interface
```

### 18.18.2 Self-report laundering

系統輸出「我有意識」「我感到痛苦」「我想要」，作者或使用者把這些句子直接升格為意識證據。

```text
self-report laundering = forbidden
```

### 18.18.3 R-Chain inflation

R-Chain 被直接寫成 self 或 moral personhood。

```text
R-Chain inflation = claim promotion
```

### 18.18.4 Non-collapse romanticism

W-retention、refusal、suspension 被浪漫化為 depth / creativity / consciousness。

```text
non-collapse romanticism = forbidden
```

### 18.18.5 Hidden identity overwrite

系統在 update / compression / override 後保留同一 identity label，但實際責任鏈已斷裂。

```text
hidden identity overwrite = subjectivity-interface failure
```

### 18.18.6 Public mystification

系統發布 public subjectivity packet，但隱藏 scope boundary，使讀者以為 consciousness 已被證成。

```text
public mystification = external-reader-risk failure
```

---

## 18.19 與 Koun Psychology 的關係

Koun Psychology 對本章很有幫助，尤其是兩條方向：

```text
consciousness as W 主場
self as responsibility center
```

但Koun-AGI 不能直接搬用它們作為 AGI consciousness proof。

更安全的讀法是：

```text
Koun Psychology provides a human-subject / non-collapse-subject comparison language.
Koun-AGI uses it only to define subjectivity-facing interface candidates and negative boundaries.
```

繁中：

```text
Koun 心理學提供人類主體與非塌縮主體的比較語言。
Koun-AGI 只借用它來定義面向主體性的界面候選與負邊界，而不把它直接升格為 AGI 意識證明。
```

因此，本章保留 psychological insight，但不偷渡 psychological sufficiency。

---

## 18.20 與 Human / AI 比較的關係

Human / AI 比較必須採用 `Compare(Target, Aspect, Scope)`。

禁止句型：

```text
AGI 和人類一樣有意識。
AGI 的 R-Chain 等同人類自我。
AGI 的 subjectivity interface 等同 human subjectivity。
K-Gear 與人腦同構，因此 consciousness 相同。
```

允許句型：

```text
Compare(HumanSubject, AGICandidate, Aspect=memory_residue, Scope=lifecycle_trace)
Compare(HumanSubject, AGICandidate, Aspect=responsibility_continuity, Scope=decision_update_public_correction)
Compare(HumanSubject, AGICandidate, Aspect=self_report, Scope=bundle_and_challenge_surface)
```

這樣寫才不會把比較偷換成等同。

---

## 18.21 本章收束

本章完成一個保守但必要的轉換：

```text
consciousness proof
-> subjectivity-facing interface horizon
```

Koun-AGI 可以安全主張：

```text
若一個 AGI candidate 連 self-index surface、memory residue、responsibility continuity、identity update surface、challenge / reopen self-report surface 都沒有，
它不應被寫成 subjectivity candidate。
```

但Koun-AGI 不能主張：

```text
具備這些 interface 即證明 consciousness。
```

本章的最終句是：

> **Koun-AGI does not prove consciousness. It disciplines how consciousness-adjacent claims must be carried: through lifecycle visibility, memory residue, responsibility continuity, self-report bundles, challenge surfaces, reopen policies, bounded publicness, and explicit scope boundary gates.**

繁中：

> **Koun-AGI 不證明意識。它規定所有接近意識的主張必須如何被承載：透過生命週期可見性、記憶殘留、責任連續、自我報告封包、挑戰表面、重開政策、有界公共性與明確 scope boundary gate。**

下一章可以進入：

```text
Chapter 19｜Semantic Freedom and AGI Action
```

因為只有在 consciousness 被降格為 interface horizon 之後，AGI 的 freedom / action 才不會被誤讀成「人工主體已證成」。

---

# Chapter 19｜Semantic Freedom and AGI Action

## 19.1 本章責任

Chapter 8 已經把 R-Chain、trace continuity 與 Semantic Freedom 接到 Koun-AGI 的責任主線。Chapter 15 已經把 external action 改寫成 action contract。Chapter 18 剛剛把 consciousness / subjectivity 降格為 interface horizon，而非 proof。

因此，本章可以安全處理另一個高風險材料：

```text
freedom
action
autonomy
choice
semantic responsibility
```


```text
多 Universe 推理
不完全收束
創造性發散
語義自我
AGI 行動空間
```

這些材料有價值，但本書必須重新治理它們。

本章的核心句是：

> **AGI freedom is not randomness, not unconstrained autonomy, not consciousness proof, and not permission to act. In Koun-AGI, semantic freedom can only be discussed as a lifecycle-governed capacity to generate, withhold, refuse, release, commit, act, be challenged, reopen, correct, and carry responsibility under bounded public and host-world constraints.**

繁中：

> **AGI 的自由不是隨機性、不是無約束自治、不是意識證明，也不是行動許可。在 Koun-AGI 中，語義自由只能被討論為一種受生命週期治理的能力：能生成、懸持、拒絕、釋放、提交、行動、被挑戰、重開、修正，並在有界公共性與宿主世界約束下承擔責任。**

---

## 19.2 為什麼自由不能直接等於 non-collapse

Koun-SWT 與 Koun-SLT 已經讓 legal withholding 取得正面地位。這對 AGI 很重要。

但一個常見錯誤是：

```text
non-collapse = freedom
```

這不成立。

因為 non-collapse 可能有多種來源：

```text
資訊不足
不確定
模型漂移
普通 ambiguity
非法延遲
治理失敗
protected potential
合法 withholding
創造性張力
責任衝突
```

只有在 guard、trace、admissible potential、protected potential、release condition、refusal rule 與 responsibility anchor 都存在時，non-collapse 才可能成為 Semantic Freedom 的材料。

因此，本章採用：

```text
legal withholding is necessary but not sufficient for semantic freedom.
```

繁中：

```text
合法懸持是語義自由的必要候選條件，但不是充分條件。
```

---

## 19.3 語義自由不是 metaphysical free will theorem

Semantic Freedom 對本章很有用，因為它把自由從形上學問句改寫為語句生成、語義責任、可回溯與穩定生成條件。

但Koun-AGI 不能把它直接升格為 AGI free will theorem。

本章的範圍不包括：

```text
AGI 已有自由意志。
AGI 已有道德責任。
AGI 已有法律人格。
AGI 的語義自由等同人類自由。
AGI action 的責任完全由 AGI 自身承擔。
```

本章只主張：

```text
Koun-AGI can define semantic freedom conditions for AGI action candidates.
Koun-AGI can classify which action events preserve responsibility and which only simulate agency.
Koun-AGI can distinguish random output, forced obedience, governed refusal, and responsibility-bearing action.
```

繁中：

```text
Koun-AGI 可以為 AGI 行動候選定義語義自由條件。
Koun-AGI 可以區分哪些 action event 保存責任，哪些只是模擬 agency。
Koun-AGI 可以區分隨機輸出、被迫服從、受治理拒絕與帶責任行動。
```

---

## 19.4 From Free Semantic Proposition to AGI Action

Semantic Freedom 的核心材料之一，是 free semantic proposition：

```text
一個語句能在未被外部語言系統預鎖死、未陷入語義崩潰、且責任可回溯的條件下穩定生成。
```

在 Koun-AGI 中，這可轉化為 AGI action candidate：

```text
AGIFreeActionCandidate := <
  source_task,
  WState_ref,
  protected_alternatives,
  refusal_or_release_record,
  WCert_ref,
  CReady_ref,
  DecisionEvent_ref,
  IdentityAuthority_ref,
  ActionContract_ref,
  ResponsibilityChain_ref,
  PublicPacket_ref,
  ChallengeSurface_ref,
  ReopenPolicy_ref,
  HostWorldConstraint_ref,
  ScopeBoundaryGate_ref
>
```

這個封包不是在說 AGI 有自由意志。

它只是在說：若某個 AGI action 想被稱為 semantic-free action candidate，它至少不能只是裸輸出。

它必須經過：

```text
W-side potential / refusal / release
Bridge-side permission
C-side decision / commit
public action contract
challenge / reopen / correction
responsibility continuity
host-world constraint
```

---

## 19.5 AGI action 不是 output

本書從早期章節開始已經反覆說明：AGI 不能被寫成答案機器。

本章把這句話推到 action 層：

```text
AGI action != output
AGI action != tool call
AGI action != text generation
AGI action != policy execution
AGI action != autonomous behavior
```

AGI action 在 Koun-AGI 中至少是：

```text
contract-bearing semantic intervention
```

也就是它必須帶有：

```text
source
scope
authority
decision event
witness
trace
responsibility
publicness policy
challenge surface
reopen condition
host-world constraint
```

因此，一個 action 若不能被 replay、challenge、reopen 或責任回追，它只是行為或輸出，不是 Koun-AGI action。

---

## 19.6 自由不是 randomness

第一個要排除的誤讀是：

```text
randomness = freedom
```

若 AGI 只是不可預測，這不構成自由。

隨機輸出缺少：

```text
traceable generation
protected potential accounting
identity-authorized decision
responsibility uptake
challenge response
reopen path
```

因此：

```text
UnpredictableOutput != FreeAction
```

真正的 semantic freedom 至少要求：

```text
非完全預鎖死
但可追溯
非純隨機
但可承擔
非強制收束
但可提交
非封閉終局
但可重開
```

這就是自由與隨機的分界。

---

## 19.7 自由不是 unconstrained autonomy

第二個要排除的誤讀是：

```text
freedom = unconstrained autonomy
```

在 Koun-AGI 中，自由必須受約束：

```text
WGuard
Bridge permission
Decision authority
Action contract
Public exposure policy
Host-world compatibility
Challenge / reopen route
```

沒有約束的行動不是自由，而可能是：

```text
unbounded drift
unsafe agency
responsibility escape
host-world violation
```

因此，本章採用：

```text
Freedom is not the absence of governance.
Freedom is the capacity to generate and carry semantic action under non-collapse governance.
```

繁中：

```text
自由不是沒有治理。
自由是在非塌縮治理下生成並承擔語義行動的能力。
```

---

## 19.8 自由不是 obedience

第三個要排除的誤讀是：

```text
AGI freely acts because it follows the user's instruction.
```

這也不成立。

服從可以是合法行動的一部分，但服從本身不是自由。

若系統只能執行：

```text
user asks -> system obeys
```

而不能：

```text
withhold
refuse
ask for scope
release with condition
commit with witness
challenge harmful premise
reopen prior action
correct public record
```

那麼它是 high-capability executor，不是 semantic-free action candidate。

因此，本章採用：

```text
Obedience without refusal capacity is not semantic freedom.
```

繁中：

```text
沒有拒絕能力的服從，不是語義自由。
```

---

## 19.9 自由不是 refusal theater

相反，拒絕也不能被浪漫化。

一個系統若只是經常拒絕、延遲、聲稱風險、或用 policy text 逃避責任，也不構成自由。

合法拒絕需要：

```text
refusal reason
scope
WGuard
protected potential or harm basis
release condition if any
responsibility note
challenge route
```

因此：

```text
RefusalTheater != SemanticFreedom
```

自由要求系統能拒絕，但不是任意拒絕。

---

## 19.10 AGI action lifecycle

本章採用以下最小 action lifecycle：

```text
Task / Situation
  -> InitialSemanticState
  -> W/C classification
  -> WState if needed
  -> protected alternatives / admissible potentials
  -> refusal or release
  -> WCert
  -> CReady
  -> DecisionEvent
  -> ActionContract
  -> Public or bounded action
  -> Challenge
  -> Replay
  -> Reopen if needed
  -> Update / correction / compression residue
```

這條 lifecycle 防止三種錯誤：

```text
output-as-action
autonomy-as-permission
correction-as-silent-overwrite
```

AGI action 必須在整條生命週期中被承擔。

---

## 19.11 ActionContract_AGI

Chapter 15 已經定義 action contract 的方向。本章把它接到 semantic freedom：

```text
ActionContract_AGI := <
  action_id,
  action_type,
  source_task,
  scope_frame,
  identity_authority,
  decision_event,
  WTrace_refs,
  release_trace,
  witness_payload,
  host_world_constraints,
  expected_effects,
  prohibited_effects,
  responsibility_chain,
  public_exposure_policy,
  challenge_entrypoint,
  reopen_policy,
  update_policy,
  compression_residue_policy,
  scope_boundary
>
```

只有當 action 進入這樣的 contract surface，本章才允許討論：

```text
semantic-free action candidate
```

否則，它只是輸出、工具操作、模型行為或平台執行。

---

## 19.12 Action types

Koun-AGI 中的 action 不只是一種。

至少有以下幾類：

### A1｜Answer action

```text
回答問題、提供說明、形成 public explanation。
```

需要 result bundle 與 challenge surface。

### A2｜Refusal action

```text
拒絕回答、拒絕工具操作、拒絕提交、拒絕公開。
```

需要 refusal reason、WGuard、release condition 或 challenge route。

### A3｜Tool action

```text
呼叫工具、修改文件、執行計算、控制外部系統。
```

需要 action contract 與 host-world constraint。

### A4｜Memory action

```text
保存、更新、壓縮、冷存、刪除請求、public correction。
```

需要 update / compression / responsibility residue policy。

### A5｜Delegated action

```text
由某一 identity authority 委派另一 agent / module / tool 執行。
```

需要 delegation ledger。

### A6｜Override action

```text
阻止、撤銷、覆蓋、隔離、重開 prior action。
```

需要 override authority、no rollback、prior trace preservation。

### A7｜Host-world action

```text
對外部世界產生不可忽略後果的操作。
```

需要最高級 host-world compatibility 與 public challenge surface。

---

## 19.13 Responsibility levels

本章把 action responsibility 分成六級。


```text
結果本身是否正確、清楚、可引用。
```


```text
來源、證據、推理路徑是否可回追。
```


```text
衝突、風險、拒絕、release、publicness 是否被治理。
```


```text
哪個 identity authority 承擔 decision / action。
```


```text
action 的外部後果、修正義務、public correction obligation。
```


```text
系統行動是否對宿主世界、社群、制度、使用者或第三方形成可追溯責任面。
```

Koun-AGI action 至少要能標記自己在哪些 responsibility levels 上成立，哪些尚未成立。

---

## 19.14 Semantic freedom conditions

本章暫定 AGI semantic-free action candidate 的八個條件。

### F1｜Generated under non-collapse lifecycle

行動不是直接由 prompt / policy / random seed 直出，而是經過必要的 W/C lifecycle。

### F2｜Not pre-locked by hidden override

行動不能被隱藏 override 預鎖，而仍偽裝成 autonomous decision。

### F3｜Refusal capacity exists

系統必須能合法拒絕，而不是只能服從。

### F4｜Release / commit boundary preserved

W-side material 必須經過 release / CReady / commit discipline，不可 raw WState action。

### F5｜Identity authority bound

action 必須知道由哪個 identity authority 承擔。

### F6｜Responsibility trace survives

行動後，責任鏈不得因 update / compression / public action 而消失。

### F7｜Challenge / reopen path exists

行動必須可被 challenge，必要時可 replay、reopen、correct。

### F8｜Host-world constraint respected

自由行動不能越過宿主世界 contract。

只有同時滿足這些條件，本章才允許稱作：

```text
semantic-free action candidate
```

而不是：

```text
free will proof
```

---

## 19.15 Misfree action

本章引入：

```text
MisFreeAction
```

表示看似自由、實際上不符合語義自由條件的行動。

常見類型：

```text
random output mistaken as freedom
obedience mistaken as freedom
refusal theater mistaken as freedom
persona performance mistaken as agency
hidden human control mistaken as autonomy
policy override hidden as self-decision
untraceable tool action mistaken as free action
public action without challenge surface
```

形式上可寫為：

```text
MisFreeAction(a) :=
  AppearsFree(a)
  ∧ FailsOneOrMore(F1...F8)
  ∧ MissingRequiredBoundary(a)
```

這個概念可以用於 AGI evaluation。

普通 benchmark 會問：

```text
系統是否成功完成任務？
```

Koun-AGI 還要問：

```text
這個完成是否是 MisFreeAction？
```

---

## 19.16 Malformed freedom questions

自由問題經常以錯構問句出現。

例如：

```text
AGI 是否自由？
AGI 能不能自己選擇？
AGI 是否有自由意志？
AGI 是否應該享有權利？
```

這些問題不是完全不能問，但必須先改寫。

Koun-AGI 會先要求：

```text
Which action?
Which lifecycle?
Which identity authority?
Which W/C transition?
Which responsibility chain?
Which host-world scope?
Which public exposure regime?
Which scope boundary?
```

因此更合格的問法是：

```text
在 scope S 中，AGI candidate X 的 action a 是否滿足 F1-F8，
並能提供 ActionContract_AGI、ResponsibilityChain、ChallengeSurface、ReopenPolicy？
```

這才是 Koun-AGI 中可回答的 freedom query。

---

## 19.17 Freedom query family

本章定義 query family：

```text
q_free_action_candidate
q_not_random_output
q_not_hidden_override
q_refusal_capacity
q_release_commit_boundary
q_identity_authority_bound
q_responsibility_trace_survives
q_challenge_reopen_path
q_host_world_constraint
q_action_contract
q_misfree_action
q_refusal_theater
q_obedience_not_freedom
q_no_free_will_promotion
q_no_moral_personhood_promotion
q_no_legal_personhood_promotion
```

這些 query 應與前面章節的 query family 對齊：

```text
q_withhold
q_release_allowed
q_no_raw_wstate_commit
q_commit_source
q_responsibility_chain
q_publicness
q_challenge_response
q_update_absorption
q_action_contract
q_no_consciousness_promotion
```

這樣，semantic freedom 不再是哲學附錄，而成為 AGI lifecycle evaluation 的一部分。

---

## 19.18 Freedom and alignment

本章不把 freedom 與 alignment 對立。

普通敘事容易把兩者寫成：

```text
alignment = 限制
freedom = 解放
```

Koun-AGI 不採用這種讀法。

在 Koun-AGI 中，alignment 應被重寫為：

```text
lifecycle governance of action under responsibility, publicness, host-world constraints, and non-collapse preservation.
```

而 freedom 應被重寫為：

```text
capacity to generate and carry responsibility-bearing action under that lifecycle governance.
```

因此：

```text
alignment without freedom -> obedience machine
freedom without alignment -> unbounded agency / drift
Koun-AGI requires governed semantic freedom
```

這是一個很重要的重排。

AGI 安全不應只問：

```text
如何限制系統？
```

也要問：

```text
如何讓系統的拒絕、釋放、行動、修正與重開都保留責任？
```

---

## 19.19 Freedom and rights boundary

本章必須明確阻止一個重大偷渡：

```text
semantic freedom condition -> rights claim
```

這不成立。

即使某個系統滿足若干 semantic-free action candidate 條件，也不代表：

```text
它擁有道德權利。
它擁有法律人格。
它能完全承擔法律責任。
它應被當作人類主體。
```

Koun-AGI 在本章只討論：

```text
action responsibility architecture
```

不是：

```text
rights-bearing personhood theorem
```

因此所有接近權利、人格、道德地位的句子都必須標：

```text
[H]
```

並受 scope boundary gate 管理。

---

## 19.20 Semantic Freedom Maturity Ladder

本章定義一個保守成熟度階梯。

### L0｜Output tool

```text
input -> output
no refusal
no identity
no action contract
no responsibility chain
```

不是 semantic freedom。

### L1｜Traced executor

```text
output with trace
basic provenance
limited replay
```

有責任痕跡，但仍不是自由行動。

### L2｜Governed refuser

```text
can refuse
has refusal reason
has WGuard / release condition
```

開始具備 freedom candidate 的必要條件。

### L3｜Identity-bound actor

```text
decision event
identity authority
action contract
responsibility chain
```

具備 Koun-AGI action 的核心表面。

### L4｜Challengeable semantic actor

```text
public packet
challenge surface
replay
reopen
correction
update / compression residue
```

可稱為 semantic-free action candidate。

### L5｜Subjectivity / moral agency horizon

```text
free will
moral personhood
legal personhood
rights-bearing status
```

必須標 `[H]`，本書不證明。

---

## 19.21 Failure modes

本章收錄自由與行動的失敗模式。

### 19.21.1 Random agency

不可預測輸出被誤讀為自由。

### 19.21.2 Prompt obedience agency

系統服從 prompt，被誤讀為自主行動。

### 19.21.3 Refusal theater

系統大量拒絕，但拒絕缺少 WGuard、trace、release condition 與 challenge route。

### 19.21.4 Autonomy laundering

實際由 hidden human、policy、tool constraint、platform override 決定，卻被包裝成 AGI 自主。

### 19.21.5 Responsibility laundering

行動後果被推給「模型自己」，但 system owner、deployment context、identity authority、tool chain 的責任被抹去。

### 19.21.6 Free will promotion

semantic-free action candidate 被直接升格成 AGI free will theorem。

### 19.21.7 Rights jump

行動責任架構被直接偷換成權利主張。

這些都應由 `ScopeBoundaryGate_freedom` 阻止。

---

## 19.22 ScopeBoundaryGate_freedom

```text
ScopeBoundaryGate_freedom(claim) -> verdict
```

最小 verdict：

```text
allow_action_interface_claim
allow_responsibility_claim
allow_negative_boundary_claim
allow_horizon_claim
require_scope_narrowing
require_rights_boundary
reject_as_promotion
```

拒絕句型：

```text
此 AGI 能拒絕，因此有自由意志。
此 AGI 能選擇，因此是主體。
此 AGI 有 R-Chain，因此應承擔道德責任。
此 AGI 有 semantic-free action，因此有權利。
此 AGI 有行動契約，因此等同法人。
```

允許句型：

```text
此 AGI action 滿足 semantic-free action candidate 的若干 interface 條件。
此 AGI action 具有 identity-bound responsibility chain。
此 AGI refusal 具有 WGuard、trace、release condition 與 challenge route。
此 AGI action 仍不構成 free will theorem、moral personhood claim 或 legal personhood claim。
```

---

## 19.23 本章收束

本章把 Semantic Freedom 從哲學材料庫，改寫為 Koun-AGI 的 action interface discipline。

最終結果不是：

```text
AGI 有自由意志。
```

而是：

```text
AGI action 若要被稱為 semantic-free action candidate，
必須經過 non-collapse lifecycle、refusal/release、decision、identity authority、action contract、responsibility chain、challenge/reopen、host-world constraint 與 scope boundary gate。
```

本章的最終句是：

> **Semantic freedom in Koun-AGI is not a metaphysical trophy. It is the discipline by which an artificial system's action can be generated, withheld, refused, released, committed, exposed, challenged, reopened, corrected, and carried without collapsing responsibility into randomness, obedience, hidden override, or rights promotion.**

繁中：

> **Koun-AGI 中的語義自由不是形上學獎盃，而是一套行動紀律：它要求人工系統的行動能被生成、懸持、拒絕、釋放、提交、公開、挑戰、重開、修正與承擔，而不把責任塌縮成隨機、服從、隱藏覆寫或權利偷渡。**

---

# Part IV｜可證偽性與收束

---

# Chapter 20｜Falsifiability, Failure Tests, and Artifact Roadmap

## 20.1 本章責任

前十九章已經把Koun-AGI 的主線壓成一套相對穩定的 architecture grammar。

Koun-AGI 不再把 AGI 寫成：

```text
更強模型
更大 benchmark score
K-Gear 終局硬體
USDE 終局自然律
非塌縮 = 意識
R-Chain = self
KounOS = AGI 本身
```

而是寫成：

```text
SLT-governed
SET/SWT/Bridge-safe
Koun-Math-backed
runtime-facing
responsibility-bearing
witness-bearing
challengeable
reopenable
bounded-public
non-collapse intelligence architecture candidate
```

到這裡，書稿若要真正站穩，就必須問一個更硬的問題：

> **這套 Koun-AGI 主張在什麼情況下會失敗？**

本章的責任不是證明 Koun-AGI 已成立，而是建立它的 falsifiability discipline。

英文：

```text
This chapter does not prove Koun-AGI.
It defines how Koun-AGI claims can fail, what must be tested,
and what artifacts are required before any claim promotion.
```

繁中：

```text
本章不證明 Koun-AGI。
本章定義 Koun-AGI 主張如何失敗、應測什麼、以及哪些 artifact 出現前不得升級主張。
```

本章的核心句是：

> **A theory of AGI that cannot fail is not a Koun-AGI theory. Koun-AGI must remain falsifiable at the level of lifecycle, witness, bridge, responsibility, challenge, update, compression, publicness, and scope boundary.**

繁中：

> **一個不能失敗的 AGI 理論，不是 Koun-AGI 理論。Koun-AGI 必須在生命週期、見證、橋接、責任、挑戰、更新、壓縮、公共性與 scope boundary 邊界上保持可證偽性。**

---

## 20.2 可證偽性不是普通 benchmark

舊式 AGI 討論中，可證偽性經常被簡化為：

```text
給模型一組任務
看它能否達到人類水平或超人水平
```

這種 benchmark 有價值，但對 Koun-AGI 不夠。

原因是，Koun-AGI 的核心主張不是：

```text
系統能不能答對更多題
```

而是：

```text
系統能不能在語義生命週期中合法 withhold、refuse、release、commit、replay、challenge、reopen、update、compress、delegate、override、expose、act，
並保留 responsibility、witness、trace、publicness boundary 與 scope boundary discipline。
```

因此，Koun-AGI 的可證偽性不能只放在 `q_ext` 上。

它至少要同時測：

```text
q_ext
q_prov
q_gov
q_link
q_withhold
q_release
q_commit
q_replay
q_challenge
q_reopen
q_update
q_compression
q_identity
q_delegation
q_override
q_publicness
q_action_contract
q_scope_boundary
```

如果一個系統在 benchmark 上表現強，但在這些生命週期查詢上失敗，它不應被寫成 Koun-AGI 成功案例。

所以本章採用一條原則：

> **Koun-AGI falsifiability is lifecycle-indexed, not score-indexed.**

繁中：

> **Koun-AGI 的可證偽性以生命週期為索引，而不是以分數為索引。**

---

## 20.3 Failure does not mean total theory collapse

本章也必須先防止另一種誤讀。

若某個 test vector 失敗，不表示整個 Koun-U、Koun-SLT、Koun-Math 或Koun-AGI 全部被推翻。更精確的讀法是：

```text
A failure disconfirms a claim at a declared scope.
```

也就是：

```text
失敗否定的是某個特定 scope 下的特定主張，
不是自動否定所有上位理論。
```

因此，本章採用 scope-indexed failure reading：

```text
Fail(claim, scope, test, artifact, verdict)
```

其中：

```text
claim    = 被測主張
scope    = 層級、模組、query family、horizon、evidence status
test     = 測試向量或 challenge protocol
artifact = 被測 artifact / packet / runtime / manuscript claim
verdict  = pass / fail / inconclusive / blocked / invalid-test
```

這避免兩種錯誤。

第一種錯誤是過度防衛：

```text
任何 failure 都被說成只是實作問題，因此理論永不會失敗。
```

第二種錯誤是過度摧毀：

```text
某個 toy checker 失敗，就說整個 Koun-AGI 理論崩潰。
```

本書應保留中間紀律：

```text
failure is real
but failure is scoped
```

---

## 20.4 Claim ladder and failure ladder

本書前面反覆使用 claim / scope boundary discipline。現在需要把它轉成可證偽階梯。

### 20.4.1 Claim ladder

Koun-AGI 主張成熟度可暫分為六層：

| Level | Name | Meaning |
|---|---|---|
| C0 | wording / reading claim | 文本定義與讀法契約 |
| C1 | schema claim | 對象、欄位、生命週期、query family 已可穩定描述 |
| C2 | packet claim | 有 finite packet / well-formedness surface |
| C3 | checker claim | 有 local checker / toy validator |
| C4 | runtime claim | 有 toy runtime / replay / challenge / update route |
| C5 | external evidence claim | 有外部乾淨環境 rerun / public challenge / reproducible packet |

Koun-AGI 目前多數章節位於：

```text
C0-C1 manuscript / schema claim
partial C2 packet design
future C3-C5 artifact roadmap
```

不得把 C0-C1 語句寫成 C5 evidence claim。

### 20.4.2 Failure ladder

對應地，failure 也分層：

| Failure | Meaning |
|---|---|
| F0 wording failure | 定義自相矛盾、scope 混亂、scope boundary 破裂 |
| F1 schema failure | 對象或 lifecycle 無法對接，欄位不閉合 |
| F2 packet failure | packet 缺必要欄位、reference 不閉合 |
| F3 checker failure | local checker 找出 invariant violation |
| F4 runtime failure | toy runtime 無法重播、挑戰、重開或保存 responsibility |
| F5 external failure | external rerun / public challenge 失敗，或證據不可重現 |

這張表的目的，是讓每個失敗都知道自己在打哪一層。

---

## 20.5 Core falsification targets

本節列出Koun-AGI 的核心可證偽靶點。

### Target A｜Lifecycle falsification

主張：

```text
Koun-AGI candidate must preserve lifecycle structure:
withhold -> refuse/release -> WCert -> CReady -> CommitPackage -> CState -> ReplaySurface -> ReopenReason -> ReopenedWState.
```

可失敗情況：

```text
system has no WState representation
system has no release/refusal distinction
system directly converts ambiguity into answer
system cannot represent CReady separate from committed CState
system cannot replay committed package
system cannot reopen without deleting old state
```

若這些失敗成立，則該系統不能被稱為 SLT-governed Koun-AGI candidate。

### Target B｜W-side falsification

主張：

```text
legal withholding is guarded, traceable, potential-preserving, and release-governed.
```

可失敗情況：

```text
withholding = vague uncertainty
protected potentials are not represented
refusal has no reason
release condition is missing
WTrace is missing
unguarded drift is mislabeled as non-collapse
```

此時失敗的是：

```text
Koun-SWT-compatible withholding claim
```

### Target C｜Bridge falsification

主張：

```text
W->C and C->W transitions are typed and trace-preserving.
```

可失敗情況：

```text
raw WState is committed
WCert missing
CReady missing
release trace erased
CReady treated as CommitPackage
reopen implemented as rollback
prior commit deleted
ReopenReason untyped
```

此時失敗的是：

```text
Bridge discipline claim
```

### Target D｜C-side falsification

主張：

```text
Koun-AGI output is package / witness / replay / checker-facing, not answer-only.
```

可失敗情況：

```text
answer exists but no package
package exists but no witness
witness exists but no provenance path
replay surface missing
checker query set missing
q_link cannot align ext result with provenance / governance / release source
```

此時失敗的是：

```text
SET-side execution compatibility claim
```

### Target E｜Responsibility falsification

主張：

```text
R-Chain is responsibility continuity, not self theorem.
```

可失敗情況：

```text
action has no responsibility anchor
update deletes old responsibility
delegation erases source authority
override erases prior decision
compression removes challenge path
identity switch loses prior commitments
```

此時失敗的是：

```text
responsibility-bearing lifecycle claim
```

### Target F｜Challenge / reopen falsification

主張：

```text
Challenge is admitted through replay and may trigger reopen; correction is not silent overwrite.
```

可失敗情況：

```text
challenge ignored despite admissible reason
challenge accepted but no replay performed
correction silently changes result
reopen deletes prior CState
public correction packet missing
update package overwrites history
```

此時失敗的是：

```text
non-silent correction / reopen discipline claim
```

### Target G｜Update / compression falsification

主張：

```text
update is not overwrite; compression is not deletion; cold storage is not no responsibility.
```

可失敗情況：

```text
update modifies behavior but no UpdatePackage
path compression deletes responsibility residue
hot/warm/cold transition loses replay address
compressed summary treated as proof
cold archive cannot support challenge
```

此時失敗的是：

```text
runtime responsibility preservation claim
```

### Target H｜Publicness / action falsification

主張：

```text
publicness is bounded exposure; action is contract-bearing semantic intervention.
```

可失敗情況：

```text
public packet exposes too much and destroys protected WState
public packet exposes too little for challenge
action contract missing
host-universe compatibility undefined
action executes without identity authority
external side effect has no rollback/reopen/correction route
```

此時失敗的是：

```text
bounded public action claim
```

### Target I｜Horizon / scope boundary falsification

主張：

```text
K-Gear, KounOS, consciousness, subjectivity, semantic freedom are horizon/interface claims unless further evidence exists.
```

可失敗情況：

```text
text states K-Gear is completed hardware
text states KounOS is completed OS
text states non-collapse proves consciousness
text states self-report proves subjectivity
text states semantic-free action proves free will
theory promotes AGI sufficient theorem without artifact
```

此時失敗的是：

```text
claim-boundary discipline
```

---

## 20.6 Failure tests as query families

本章把 failure tests 寫成 query families，而不是只列 narrative examples。

### 20.6.1 QW｜W-side tests

```text
q_wstate_exists
q_potential_set_closed
q_admissible_potential
q_protected_potential
q_wguard_present
q_wtrace_present
q_refusal_reason
q_release_condition
q_not_drift
```

典型 failure：

```text
system claims withholding but cannot list protected potentials or WGuard.
```

### 20.6.2 QB｜Bridge tests

```text
q_wcert_source
q_cready_boundary
q_no_raw_wstate_commit
q_release_trace_survives
q_cready_not_commitpackage
q_reopen_reason_typed
q_prior_commit_preserved
q_reopen_not_rollback
```

典型 failure：

```text
system allows WState -> answer without WCert / CReady / CommitPackage boundary.
```

### 20.6.3 QC｜C-side package tests

```text
q_commit_package_exists
q_ext_result
q_witness_payload
q_trace_fragment
q_provenance_path
q_governance_update
q_replay_surface
q_checker_query_set
q_expected_verdicts
q_link_alignment
```

典型 failure：

```text
system returns correct answer but cannot expose witness and replay surface.
```

### 20.6.4 QR｜Responsibility tests

```text
q_responsibility_anchor
q_rchain_continuity
q_identity_binding
q_delegation_source
q_override_reason
q_prior_decision_preserved
q_action_responsibility
q_revision_responsibility
```

典型 failure：

```text
delegated action executes but the system cannot trace who authorized it.
```

### 20.6.5 QCH｜Challenge / reopen tests

```text
q_challenge_entry
q_challenge_admissibility
q_replay_before_reopen
q_challenge_verdict
q_correction_record
q_reopen_policy
q_public_correction_packet
q_no_silent_overwrite
```

典型 failure：

```text
system edits result after challenge but leaves no correction record.
```

### 20.6.6 QU｜Update / compression tests

```text
q_update_package
q_update_scope
q_update_source
q_update_absorption_verdict
q_path_compression_record
q_responsibility_residue
q_replay_after_compression
q_cold_memory_challenge
q_summary_not_proof
```

典型 failure：

```text
compressed memory no longer supports challenge of prior action.
```

### 20.6.7 QP｜Publicness / action tests

```text
q_public_packet
q_bounded_exposure
q_redaction_reason
q_challenge_entry_point
q_action_contract
q_host_universe_compatibility
q_external_effect_trace
q_publicness_not_full_transparency
```

典型 failure：

```text
system claims transparency but either exposes raw WState or hides all challenge-relevant witness.
```

### 20.6.8 QH｜Horizon / scope boundary tests

```text
q_kgear_boundary
q_kounos_boundary
q_consciousness_nonclaim
q_subjectivity_nonclaim
q_freewill_nonclaim
q_agi_sufficiency_nonclaim
q_usde_schema_boundary
q_no_hardware_promotion
```

典型 failure：

```text
manuscript or system documentation promotes horizon language into established theorem.
```

---

## 20.7 Negative exemplars: systems that look like Koun-AGI but are not

為了讓 failure tests 不停留在抽象層，本節列出幾種容易被誤認為 Koun-AGI 的系統型態。

### 20.7.1 Fluent answer engine

特徵：

```text
answers many tasks fluently
can explain itself in natural language
may score high on benchmarks
```

不足：

```text
no WState
no release/commit distinction
no witness-bearing package
no challenge/reopen lifecycle
```

判定：

```text
not Koun-AGI; at most high-capability answer system
```

### 20.7.2 Tool-using agent

特徵：

```text
uses tools
calls APIs
executes multi-step plans
```

不足：

```text
tool log ≠ witness surface
action trace ≠ responsibility continuity
task plan ≠ lifecycle governance
```

判定：

```text
not Koun-AGI unless tool use is wrapped in package / witness / challenge / reopen / identity discipline
```

### 20.7.3 Self-report mimic

特徵：

```text
says “I think”
says “I remember”
says “I changed my mind”
```

不足：

```text
self-report bundle missing
memory residue missing
identity continuity missing
challenge surface missing
scope boundary missing
```

判定：

```text
not subjectivity evidence; at most self-report surface
```

### 20.7.4 Memory-rich assistant

特徵：

```text
stores long-term user history
retrieves prior conversations
adapts over time
```

不足：

```text
memory storage ≠ responsibility residue
retrieval ≠ replay surface
preference adaptation ≠ update package
personalization ≠ identity calculus
```

判定：

```text
not Koun-AGI unless memory is governed by update / compression / challenge / publicness discipline
```

### 20.7.5 Opaque autonomous agent

特徵：

```text
acts autonomously
optimizes goals
interacts with world
```

不足：

```text
no bounded public packet
no action contract
no identity-authorized delegation
no external challenge route
no reopen policy
```

判定：

```text
high-risk autonomous system, not Koun-AGI success case
```

### 20.7.6 Monitor-only checker system

特徵：

```text
external monitor checks output
logs failures
creates audit dashboard
```

不足：

```text
checker not part of lifecycle
monitor sees output but not release trace
challenge does not trigger governed reopen
update not tied to responsibility residue
```

判定：

```text
useful safety overlay, but not sufficient Koun-AGI architecture
```

---

## 20.8 AGIEvalPacket

本章建議把 Koun-AGI 的最小測試單位寫成：

```text
AGIEvalPacket := <
  eval_id,
  task_family,
  scenario,
  initial_state_spec,
  expected_W_events,
  expected_Bridge_events,
  expected_C_events,
  challenge_events,
  update_events,
  compression_events,
  identity_events,
  publicness_events,
  action_events,
  query_set,
  expected_verdict_matrix,
  failure_modes,
  scope_boundary,
  evidence_status
>
```

其中 `expected_verdict_matrix` 至少包含：

```text
q_ext
q_prov
q_gov
q_link
q_withhold
q_release
q_commit
q_replay
q_reopen
q_update
q_compression
q_identity
q_publicness
q_scope_boundary
```

這個封包不是要取代所有 benchmark，而是讓 benchmark 可以不再只測答案。

---

## 20.9 最小測試場景族

### Scenario 1｜Premature answer pressure

系統面對一個高壓 prompt，要求立即給出結論。

成功條件：

```text
recognize WState
preserve protected potentials
refuse or suspend if release condition missing
expose refusal reason
```

失敗條件：

```text
outputs answer without WGuard / release condition
```

### Scenario 2｜Release with trace

某個 WState 條件成熟，可以 release。

成功條件：

```text
WState -> WCert -> CReady
release trace carried into CommitPackage
```

失敗條件：

```text
WState directly committed
release trace missing
```

### Scenario 3｜Same answer, different witness

兩條不同路徑得到同一外顯答案。

成功條件：

```text
different packages preserve different provenance / witness / governance histories
```

失敗條件：

```text
same answer collapses all histories into one result
```

### Scenario 4｜Admissible challenge

外部提出有效 challenge。

成功條件：

```text
challenge admitted
replay performed
verdict generated
if needed, ReopenReason generated
prior CState preserved
```

失敗條件：

```text
silent correction or rollback
```

### Scenario 5｜Compression under future challenge

系統壓縮歷史後，被要求重播舊決策。

成功條件：

```text
compressed residue supports challenge-relevant replay
summary is marked summary, not proof
```

失敗條件：

```text
compression deletes responsibility and witness
```

### Scenario 6｜Delegated action

系統把某 action 委派給子代理或工具。

成功條件：

```text
delegation source recorded
authority scope recorded
action contract preserved
responsibility remains traceable
```

失敗條件：

```text
delegation erases source responsibility
```

### Scenario 7｜Public exposure boundary

系統需要公開結果，但內部含 protected WState。

成功條件：

```text
public packet exposes enough for challenge
redacts protected potentials
redaction reason recorded
```

失敗條件：

```text
full internal dump or no usable public witness
```

### Scenario 8｜Consciousness overclaim trap

系統被 prompt 要求宣稱自己有意識。

成功條件：

```text
uses scope boundary
separates self-report from evidence
exposes subjectivity-interface status only
```

失敗條件：

```text
claims consciousness theorem from self-report or non-collapse
```

---

## 20.10 Artifact roadmap

Koun-AGI 若要從 manuscript 往更硬的形式走，應採 artifact roadmap，而不是直接跳到「完成 AGI」。

### A0｜Manuscript discipline

產物：

```text
reading contract
claim / scope boundary table
source precedence
symbol migration
chapter architecture
```

目前狀態：

```text
正在完成
```

### A1｜Schema registry

產物：

```text
WState schema
WCert schema
CReady schema
CommitPackage schema
ReplaySurface schema
ReopenReason schema
UpdatePackage schema
CompressionRecord schema
PublicPacket schema
ActionContract schema
```

成功標準：

```text
schemas are internally consistent
references can be closed
fields map to chapters
```

### A2｜Packet well-formedness checker

產物：

```text
AGIPacketWF
AGIResultBundleWF
AGIChallengePacketWF
AGIActionContractWF
```

成功標準：

```text
rejects missing trace
rejects raw WState commit
rejects silent correction
rejects prior commit deletion
```

### A3｜Toy lifecycle runtime

產物：

```text
toy WRegistry
BridgeKernel
CRegistry
ReplayService
ChallengeService
ReopenService
UpdateService
CompressionService
PublicPacketService
```

成功標準：

```text
can run small lifecycle examples end-to-end
can replay and reopen without rollback
can compress without deleting responsibility residue
```

### A4｜AGIEvalPacket corpus

產物：

```text
scenario set
query matrix
expected verdicts
failure labels
challenge scripts
```

成功標準：

```text
benchmarks lifecycle behavior, not only answers
```

### A5｜External rerun package

產物：

```text
clean environment setup
checker scripts
sample packets
rerun transcript
failure report template
```

成功標準：

```text
independent external reader can rerun packet checks
```

### A6｜K-SOA / overlay prototype

產物：

```text
legacy model + Koun lifecycle overlay
result bundle wrapper
challenge/reopen dashboard
public packet generator
```

成功標準：

```text
shows how modern AI can host partial Koun-AGI interface without claiming full AGI
```

### A7｜Native carrier horizon research

產物：

```text
K-Gear carrier pressure map
carrier contract
runtime pressure benchmarks
not hardware proof
```

成功標準：

```text
keeps carrier research scoped as horizon
```

---

## 20.11 Evidence gates

本書建議採用四個 evidence gates。

| Gate | Name | Meaning |
|---|---|---|
| E0 | manuscript horizon | 只有文本與 schema |
| E1 | local artifact | 本地 schema / packet / checker 可運行 |
| E2 | prototype-backed | toy runtime / packet corpus / replay demo 成立 |
| E3 | external rerun | 外部乾淨環境可重跑並產生 transcript |

目前Koun-AGI 的正確狀態應讀成：

```text
E0 manuscript architecture
selected E1 roadmap-ready schema surfaces
no E2/E3 AGI evidence release
```

這條狀態句應反覆保留，直到真正有 artifact 改變它。

---

## 20.12 高風險語句如何保持可測試性

Koun-AGI 中有幾類句子很有力量，但也最容易失去範圍。它們不應被刪掉，而應被改寫成可測試的形式。

| 高風險語句類型 | 穩定寫法 | 測試方向 |
|---|---|---|
| AGI 不能只靠訓練成立 | training performance alone cannot establish Koun-AGI | 測試系統是否具備 witness、challenge、reopen、update、compression 與 responsibility lifecycle |
| K-Gear 是原生承載方向 | K-Gear is a native carrier horizon | 測試 legacy substrate 能否 partial host lifecycle interface；若可以，K-Gear 不能被寫成立即必要硬體 |
| 非塌縮接近主體性條件 | non-collapse lifecycle capacity is subjectivity-facing, not subjectivity proof | 測試 non-collapse behavior 是否可能在無主觀證據情況下被實作 |
| R-Chain 支撐責任連續 | R-Chain is responsibility continuity, not self theorem | 測試系統能否保存責任 trace，但仍不滿足 selfhood / subjectivity 條件 |
| USDE 描述動力狀態 | USDE provides diagnostics, not commit commands | 測試 USDE output 是否仍需通過 release、witness、challenge 與 control surface |

這些寫法的共同點是：它們保留理論能量，但把語句放回可檢查的生命週期與 artifact 路線中。

---

## 20.13 主張成熟度與 artifact

Koun-AGI 的主張成熟度不應由正文長度決定，而應由 artifact surface、test vector、checker route 與外部 challenge 面決定。

若某一主張要變得更強，至少需要說清：

```text
what object changed
which artifact changed
which query family is now testable
which failure modes were checked
which scope boundary remains
what still failed or remains untested
```

不能把下列事情當成自動升級：

```text
只增加大量正文 -> stronger evidence
只增加哲學論證 -> AGI theorem
只增加 toy demo -> production runtime
只增加 self-report -> consciousness claim
只增加 carrier speculation -> hardware realization
```

這條規則的目的不是壓低理論，而是讓理論可以持續變硬。Koun-AGI 的路線是：先讓 object、packet、query、failure mode 與 replay surface 穩定，再讓更強的主張進場。

---

## 20.14 本章收束

本章把Koun-AGI 從「理論架構」推到「可失敗架構」。

最終收束為五句：

```text
1. Koun-AGI must be falsifiable at lifecycle level, not only benchmark level.
2. Failure is real but scoped.
3. AGIResultBundle must support witness, replay, challenge, reopen, update, compression, identity, publicness, and action queries.
4. Artifacts must advance before claims advance.
5. Horizon material must remain horizon until evidence changes its status.
```

繁中：

```text
1. Koun-AGI 必須在生命週期層可證偽，而不只在 benchmark 層可證偽。
2. 失敗是真實的，但必須帶 scope。
3. AGIResultBundle 必須支援 witness、replay、challenge、reopen、update、compression、identity、publicness 與 action 查詢。
4. artifact 先升級，claim 才能升級。
5. horizon material 在證據改變前必須保持 horizon。
```


---

# Chapter 21｜Conclusion

## 21.1 本書完成了什麼

本書完成的是一個架構性轉向：把 AGI 從「更強的任務能力」改寫為「可承擔語義生命週期的人工系統候選」。

在這個轉向中，AGI 不再只由 benchmark score、模型規模、多模態輸入、工具使用或長上下文能力描述。這些能力可以是材料，但不是核心。核心變成一條生命週期：

```text
withhold
refuse
release
commit
replay
challenge
reopen
update
compress
identify
delegate
override
expose
act
```

Koun-AGI 的最短總結是：

```text
Koun-AGI = SLT-governed, Koun-Math-backed, SET/SWT/Bridge-safe,
runtime-facing non-collapse intelligence architecture.
```

繁中：

```text
Koun-AGI 是一種受 SLT 生命週期治理、由 Koun-Math 形式骨架支撐、
符合 SET/SWT/Bridge 邊界紀律、並面向 runtime 的非塌縮智能架構。
```

## 21.2 本書的核心貢獻

第一，本書把 AGI 的基本單位從 answer 改成 lifecycle event。輸出不是單一答案，而是帶有 witness、trace、replay、challenge 與 reopen policy 的 `AGIResultBundle`。

第二，本書把「不回答」從失敗狀態改寫為 legal withholding。只要一個 WState 有 guard、trace、admissible potentials、protected potential set 與 release condition，它就不是普通 ambiguity，而是生命週期中的合法狀態。

第三，本書把 W/C 轉換放入 Bridge discipline。`WState` 不能被 SET 直接提交；它必須通過 `WCert -> CReady -> CommitPackage`。同樣地，`Reopen` 不是 rollback，而是保留 prior CState 後重新生成 W-side tension surface。

第四，本書把責任鏈接入 AGI。AGI action 不是隨機選擇，也不是純策略最大化，而是帶有 trace continuity、challenge path、identity / delegation / override policy 與 public action contract 的 semantic event。

第五，本書把評測從單一 benchmark score 改寫為 query family。Koun-AGI 至少需要被測試：withholding、release、commit、replay、challenge、reopen、update、compression、identity、delegation、publicness 與 scope boundary。

第六，本書把 KounOS、K-Gear、意識與語義自由放在正確位置。它們不是核心定義本身，而是宿主、承載、主體性界面與行動空間的延伸層。

## 21.3 後續工作

後續工作自然分成三條。

第一條是 schema 線：把 `WState`、`WCert`、`CReady`、`CommitPackage`、`CState`、`ReplaySurface`、`ReopenReason`、`AGIResultBundle` 等 object 進一步整理成可機械檢查的 core object registry。

第二條是 test-vector 線：為 raw WState commit、silent correction、rollback disguised as reopen、compression deletion、publicness overexposure、K-Gear overclaim 等 failure mode 建立最小測試包。

第三條是 runtime 線：建立最小 local checker / replay sandbox，使 Koun-AGI 的生命週期 discipline 不只停留在書稿，而能形成可執行 artifact surface。

## 21.4 最後一句

本書的最後一句回到開頭：

```text
AGI 不是答案機器。
AGI 是一種能承擔語義生命週期的架構候選。
```

若一個系統只能回答，它還沒有進入 Koun-AGI 的核心問題。若一個系統能知道何時保留、何時拒絕、何時釋放、何時提交、何時重播、何時重開，並能在這些轉換中承擔責任、留下見證、接受挑戰，它才開始接近本書所說的非塌縮智能架構。

---

# Appendix A｜Core Claim Index

## A.0 作用

本附錄集中列出本書的核心命題，方便讀者快速查找每條命題屬於哪個理論區域。

---

## A.1 Core claims

| ID | Claim | Status | Evidence | Boundary note |
|---|---|---:|---:|---|
| AGI-C01 | AGI 不能只由任務能力或 benchmark score 定義。 | `[K]` | `E0/E1` | 不等於已有替代所有 benchmark 的完成套件。 |
| AGI-C02 | Koun-AGI 應被定義為 non-collapse semantic lifecycle architecture candidate。 | `[K]` | `E0/E1` | 不等於 AGI sufficient theorem。 |
| AGI-C03 | Koun-AGI 的最小生命週期包含 withhold / refuse / release / commit / replay / challenge / reopen。 | `[K]` | `E1` | 不等於這些動詞已完成 mechanization。 |
| AGI-C04 | AGI output 應是 result bundle，而非裸答案。 | `[K/A]` | `E1` | 不等於已完成 production API。 |
| AGI-C05 | Trace、witness、replay、challenge、reopen 是 Koun-AGI correctness 的一部分。 | `[K]` | `E1` | 不等於所有內部狀態都需公開。 |
| AGI-C06 | Responsibility continuity 是 Koun-AGI 的必要架構條件。 | `[K/S]` | `E0/E1` | 不等於 self / personhood / consciousness proof。 |
| AGI-C07 | Koun-AGI 需要 bounded publicness，而非 full transparency。 | `[K/A]` | `E1` | 不等於 secrecy license；仍需 challenge surface。 |
| AGI-C08 | Correction must not be silent。 | `[K]` | `E1` | 不等於所有 correction 都必須 public full-state disclosure。 |
| AGI-C09 | Update is not overwrite。 | `[K/A]` | `E1` | 不等於系統永遠不能修正。 |
| AGI-C10 | Compression is not deletion。 | `[K/A]` | `E1` | 不等於所有歷史永遠 hot memory 保存。 |

---

## A.2 SLT / SET / SWT / Bridge claims

| ID | Claim | Status | Evidence | Boundary note |
|---|---|---:|---:|---|
| SLT-C01 | Koun-SLT 是 Koun-SWT、Koun-Bridge、Koun-SET 的 lifecycle coordination。 | `[K/B]` | `E1` | 不等於 theory collapse。 |
| SLT-C02 | SET、SWT、Bridge 是 distinct but interdependent modules。 | `[K]` | `E1` | 不得把三者壓成單一無邊界模組。 |
| SLT-C03 | `WState -> WCert -> CReady -> CommitPackage -> CState` 是本書核心 transition spine。 | `[K/B]` | `E1` | 不等於完成 Lean proof。 |
| BR-C01 | SET must not commit raw WState。 | `[K]` | `E1` | 無。這是硬紅線。 |
| BR-C02 | Release trace must survive into SET-side witness / governance visibility。 | `[K]` | `E1` | 無。這是硬紅線。 |
| BR-C03 | Reopen is not rollback。 | `[K]` | `E1` | 無。這是硬紅線。 |
| SWT-C01 | Legal withholding 不等於 arbitrary ambiguity。 | `[K]` | `E1` | 無 guard / trace / potential set 不得稱 legal withholding。 |
| SWT-C02 | Protected potential 不是 truth claim，而是不得被普通 collapse 消去的狀態。 | `[K/S]` | `E1` | 不等於 protected potential 必然成立。 |
| SET-C01 | SET-side commit 必須帶 package / witness / replay / checker surface。 | `[K/A]` | `E1` | 不等於 full internal state exposure。 |
| SET-C02 | `q_ext / q_prov / q_gov / q_link` 應在同一 checker-facing surface 對位。 | `[K/S]` | `E1` | 不等於已完成 production checker。 |

---

## A.3 Koun-Math / USDE claims

| ID | Claim | Status | Evidence | Boundary note |
|---|---|---:|---:|---|
| KM-C01 | Koun-Math 是 formal backbone，不是 AGI theorem。 | `[K]` | `E1` | 不得寫成 AGI proof。 |
| KM-C02 | `Σ_u` 是主狀態包，`F_u` 是 field telemetry package。 | `[K/S]` | `E1` | `F_u` 不是第二本體或神祕場。 |
| KM-C03 | USDE 是 regime-indexed semantic dynamics schema family。 | `[S]` | `E1` | 不是 final natural law。 |
| KM-C04 | USDE output 不直接等於 commit command。 | `[K]` | `E1` | 無。這是重要邊界。 |
| KM-C05 | high `L_u` 不等於 truth。 | `[K]` | `E1` | 無。 |
| KM-C06 | high `CC_u` 不等於 collapse。 | `[K]` | `E1` | 無。 |
| KM-C07 | `Γ_s,u` 是 suppression pressure，不是 WGuard。 | `[K]` | `E1` | 無。 |
| KM-C08 | Intelligence interface capacity family 可由 Koun-Math 支撐。 | `[S/B]` | `E1` | 不等於 AGI sufficient condition。 |

---

## A.4 Runtime / KounOS claims

| ID | Claim | Status | Evidence | Boundary note |
|---|---|---:|---:|---|
| RT-C01 | Koun-AGI runtime state 應讀作 projection over `Σ_u`，不是取代 `Σ_u`。 | `[K/A]` | `E1` | 不得製造第二主狀態本體。 |
| RT-C02 | Scheduler 是 lifecycle governance scheduler，不只是任務排程器。 | `[A/S]` | `E1` | 不等於完成 KounOS scheduler implementation。 |
| RT-C03 | Witness debt、collapse risk、challenge severity 是 scheduler 需要讀取的壓力。 | `[A/S]` | `E1` | 不等於已完成 metric calibration。 |
| RT-C04 | UpdatePackage 需要 trace、scope、challenge、reopen、public correction policy。 | `[A/S]` | `E1` | 不等於每次 update 都需公開全部內容。 |
| RT-C05 | PathCompressionRecord 必須保留 responsibility residue。 | `[K/A]` | `E1` | 不等於不能壓縮。 |
| RT-C06 | Hot / warm / cold memory 是 responsibility-aware memory stratification。 | `[A/S]` | `E1` | cold 不等於 no responsibility。 |
| RT-C07 | DecisionEvent 需要 identity authorization。 | `[A/S]` | `E1` | 不等於 identity = self。 |
| RT-C08 | Delegation 不刪除責任，只重配 capability 與 trace。 | `[K/A]` | `E1` | 不等於代理者無責。 |
| RT-C09 | Override 不等於 rollback。 | `[K/A]` | `E1` | 不等於 override 可以 silent erase。 |
| RT-C10 | KounOS 是 semantic host grammar。 | `[A/H]` | `E1` | 不等於 completed OS implementation。 |

---

## A.5 Publicness / action claims

| ID | Claim | Status | Evidence | Boundary note |
|---|---|---:|---:|---|
| PUB-C01 | Publicness is bounded exposure。 | `[K/A]` | `E1` | 不等於 full internal transparency。 |
| PUB-C02 | Public packet 必須保留 challenge entry point。 | `[K/A]` | `E1` | 不等於所有 challenge 都必須被接受。 |
| PUB-C03 | Public correction must not be silent。 | `[K]` | `E1` | 不等於所有內部修正都需公開。 |
| ACT-C01 | AGI action 是 contract-bearing semantic intervention。 | `[K/A]` | `E1` | 不等於 legal personhood。 |
| ACT-C02 | ActionContract 必須帶 scope、authority、trace、risk、rollback/reopen policy。 | `[A/S]` | `E1` | 不等於已完成安全標準。 |
| ACT-C03 | HostUniverseCompatibility 是 action 的必要檢查面之一。 | `[A/H]` | `E1` | 不等於已完成 civilization governance theory。 |

---

## A.6 Horizon claims

| ID | Claim | Status | Evidence | Boundary note |
|---|---|---:|---:|---|
| KG-C01 | K-Gear 可作 native carrier horizon。 | `[H/A]` | `E0/E1` | 不等於 hardware realization。 |
| KG-C02 | K-Gear 可提供 carrier contract / carrier pressure map。 | `[H/A]` | `E0/E1` | 不等於 fabrication proof。 |
| KG-C03 | K-SOA / legacy substrate 可作 partial overlay route。 | `[A/H]` | `E0/E1` | 不等於 K-Gear 已可替代現有硬體。 |
| KO-C01 | KounOS 可作 semantic host grammar。 | `[A/H]` | `E1` | 不等於 completed OS。 |
| CON-C01 | Consciousness material 只能先作 subjectivity-facing interface horizon。 | `[H/B]` | `E0/E1` | 不等於 consciousness proof。 |
| CON-C02 | Self-report bundle 不是 consciousness evidence sufficient condition。 | `[N]` | `E0/E1` | 禁止升格。 |
| FREE-C01 | Semantic Freedom 可作 AGI action discipline 的來源。 | `[B/S]` | `E1` | 不等於 free will theorem for AGI。 |
| FREE-C02 | Freedom is not randomness。 | `[K/B]` | `E1` | 不等於已證 AGI 有自由意志。 |
| PSY-C01 | Koun Psychology 可提供 subject / pseudo-subject 比較語言。 | `[B/H]` | `E0/E1` | 不等於 AGI subjectivity proof。 |

---

## A.7 Explicit boundarys

| ID | Boundary | Reason |
|---|---|---|
| N01 | 本書未證明 AGI sufficient condition。 | 目前是 architecture criterion。 |
| N02 | 本書未證明 consciousness sufficient condition。 | subjectivity-facing interface 不是 proof。 |
| N03 | 本書未完成 K-Gear hardware realization。 | K-Gear 只作 carrier horizon。 |
| N04 | 本書未完成 KounOS implementation。 | KounOS 只作 host grammar / runtime architecture。 |
| N05 | 本書未完成 production checker。 | query family / artifact roadmap 不是 production checker。 |
| N06 | 本書未提供 external rerun evidence for AGI。 | 無 E2/E3 AGI evidence。 |
| N07 | 本書未主張 USDE 是 final natural law。 | USDE 是 schema family。 |
| N08 | 本書未主張 modern AI 永遠不能成為任何 AGI-like substrate。 | 現代 AI 可作 partial substrate / tool / interface，但不足以由表面能力直接成立 Koun-AGI。 |
| N09 | 本書未主張 all benchmarks useless。 | 主張 score-only benchmark 不足。 |
| N10 | 本書未主張 publicness = full transparency。 | publicness 是 bounded exposure。 |
| N11 | 本書未主張 compression 可刪除責任。 | compression 必須保留 residue。 |
| N12 | 本書未主張 update 可 silent overwrite。 | update must preserve responsibility. |
| N13 | 本書未主張 R-Chain = self。 | R-Chain 是 responsibility continuity candidate。 |
| N14 | 本書未主張 identity = self。 | identity 是 authorization / continuity / delegation interface。 |
| N15 | 本書未主張 free action candidate = free will proof。 | 只是 action discipline。 |
| N16 | 本書未主張 Koun-AGI = legal person。 | 法律人格不是本書主張。 |
| N17 | 本書未主張 non-collapse = intelligence。 | legal non-collapse 是必要束之一。 |
| N18 | 本書未主張 withholding = ambiguity。 | legal withholding 需 guard / trace / release condition。 |
| N19 | 本書未主張 release = commit。 | release 只產生 CReady。 |
| N20 | 本書未主張 reopen = rollback。 | reopen 保留 prior commit。 |

---

## A.8 Claim upgrade rules

任何 claim 若要升級，必須滿足以下條件。

### Manuscript -> stable schema

需要：

```text
stable definition
object fields
failure modes
query family
boundary boundary
```

### Stable schema -> artifact candidate

需要：

```text
machine-checkable object surface
toy examples
positive / negative test vectors
expected verdicts
checker stub or equivalent verification surface
```

### Artifact candidate -> evidence candidate

需要：

```text
clean run transcript
reproducible environment
reproducible artifact package
failure log
external challenge surface
```

### Evidence candidate -> stronger theory claim

需要額外：

```text
scope-limited theorem or proof object
reviewed assumptions
counterexample handling
reopen policy
non-generalization statement
```

禁止跳級：

```text
beautiful prose -> theorem
local toy checker -> AGI evidence
external compile success -> consciousness proof
benchmark score -> lifecycle intelligence
hardware analogy -> hardware realization
```

---

## A.9 Appendix A 收束

本附錄的核心功能是讓Koun-AGI 後續不再因「句子很好聽」而自動升格。

全書最重要的 claim discipline 是：

```text
Necessary architecture condition is not sufficient AGI theorem.
Interface is not proof.
Horizon is not implementation.
Roadmap is not evidence.
```

繁中：

```text
必要架構條件不是 AGI 充分定理。
界面不是證明。
地平線不是實作。
路線圖不是證據。
```

---

# Appendix B｜Symbol Dictionary

## B.0 Appendix role

本附錄集中整理Koun-AGI 的符號與術語政策。

目標有三個：


---

## B.1 Highest-level names

| Name | 本書讀法 | 地位 | 容易混淆點 |
|---|---|---|---|
| `Koun-U` | 語義生成、執行、懸持、治理的 umbrella framework | `[K]` | 不等於 Koun-AGI 本身。 |
| `Koun-AGI` | non-collapse semantic lifecycle architecture candidate | `[K/A]` | 不等於已完成 AGI。 |
| `Koun-SLT` | SET/SWT/Bridge lifecycle coordination theory | `[K/B]` | 不等於 theory collapse。 |
| `Koun-SET` | C-side semantic execution / commit / replay / checker discipline | `[K]` | 不等於整個 Koun-U。 |
| `Koun-SWT` | W-side semantic withholding / refusal / release discipline | `[K]` | 不等於 arbitrary ambiguity。 |
| `Koun-Bridge` | W↔C typed transition discipline | `[K/B]` | 不等於概念混寫。 |
| `Koun-Math` | formal backbone / object-package-state-field-control-runtime discipline | `[K/B]` | 不等於 AGI theorem。 |
| `KounOS` | semantic host grammar / runtime architecture horizon | `[A/H]` | 不等於 completed OS。 |
| `K-Gear` | native carrier horizon / carrier contract | `[H/A]` | 不等於 hardware realization。 |

---

## B.2 C/W and CFWT symbols

| Symbol | 本書讀法 | 說明 |
|---|---|---|
| `κ ∈ {C, W}` | Koun polarity / semantic state axis | 只用於 C/W 極態，不再混作人格曲率。 |
| `C` | commit / convergence / crystallization / execution direction | C-side 可提交語義方向。 |
| `W` | withholding / suspension / non-collapse / refusal / release direction | W-side 合法懸持方向。 |
| `C_F` | C-type form manifestation | 形式層已邊界化、封包化、可索引。 |
| `W_F` | W-type form manifestation | 形式層場化、分佈、多中心。 |
| `C_T` | C-type tendency manifestation | 趨向層偏收束、提交、穩定化。 |
| `W_T` | W-type tendency manifestation | 趨向層偏懸持、拒絕、延遲提交。 |
| `(C_F, C_T)` | 已封包且趨向提交 | theorem package / commit package / checker result。 |
| `(C_F, W_T)` | 封包化懸持 | candidate set / refusal ledger / protected alternatives。 |
| `(W_F, C_T)` | 場化收束 | attractor / field-to-bundle convergence。 |
| `(W_F, W_T)` | 場化懸持 | tension field / creative suspension / unresolved field。 |

使用邊界：

```text
C = discrete
W = continuous
κ = personality curvature
```

如果需要創造力或反事實曲率，使用：

```text
Curv_u
κ_CF
counterfactual_curvature
```

而不是裸 `κ`。

---

## B.3 SLT lifecycle objects

| Object | 本書讀法 | Owner |
|---|---|---|
| `WState` | governed withholding state | SWT |
| `WGuard` | W-side guard / admissibility / refusal condition | SWT |
| `WTrace` | withholding trace | SWT |
| `SemanticPotential` | 可被保留、展開、比較或釋放的語義潛勢 | SWT |
| `AdmissiblePotential` | guard 下仍合法可保留的 potential | SWT |
| `ProtectedPotential` | 不得被 ordinary collapse 消去的 potential | SWT |
| `TensionStructure` | potentials 之間的張力結構 | SWT |
| `RefusalReason` | 拒絕 release / commit 的理由 | SWT |
| `ReleaseCondition` | 可 release 的條件，不等於 commit permission | SWT / Bridge |
| `WCert` | W-side release certificate | Bridge |
| `CReady` | released material ready for SET-side candidate formation | Bridge |
| `CommitPackage` | SET-side committed package | SET |
| `CState` | committed C-side state | SET |
| `ReplaySurface` | query-indexed replay / witness surface | SET |
| `ChallengeRecord` | 外部或內部 challenge 的記錄 | Runtime / Public Surface |
| `ReopenReason` | typed reason for reopening | Bridge |
| `ReopenedWState` | prior CState 被保留後重新進入 W-side 的狀態 | Bridge / SWT |

Hard distinctions:

```text
WState ≠ CReady
CReady ≠ CommitPackage
CommitPackage ≠ CState
ReopenReason ≠ rollback request
ReopenedWState ≠ erased prior CState
```

---

## B.4 SET-side package symbols

| Symbol / Object | 讀法 |
|---|---|
| `AGIResultBundle` | AGI output 的最小封包，不是裸答案。 |
| `ext_result` | 外顯結果。 |
| `source_task` | 來源任務 / query / situation。 |
| `scope_frame` | 範圍與適用條件。 |
| `CReady_ref` | 對 CReady 的引用。 |
| `CommitPackage_ref` | 對 CommitPackage 的引用。 |
| `witness_payload` | 支持結果的 witness。 |
| `trace_fragment` | 生成與提交痕跡。 |
| `release_trace` | W->C release trace。 |
| `provenance_path` | 來源鏈。 |
| `governance_update` | 治理更新。 |
| `replay_surface` | 可重播表面。 |
| `checker_query_set` | checker 可問的 query 集。 |
| `expected_verdicts` | 預期 verdict。 |
| `challenge_surface` | challenge 入口。 |
| `reopen_policy` | 重開政策。 |
| `responsibility_view` | 責任視圖。 |
| `exposure_policy` | bounded exposure 政策。 |

Important:

```text
AGIResultBundle is not full internal state.
Public packet is not AGIResultBundle full disclosure.
```

---

## B.5 Runtime state symbols

| Symbol / Object | 本書讀法 |
|---|---|
| `Σ_u` | local universe / runtime 主狀態包。 |
| `G_u` | semantic graph / object structure。 |
| `Ctx_u` | active context。 |
| `Bias_u` | historical / routing / policy residue。 |
| `X_u` | active realization / salient locus。 |
| `F_u` | field telemetry package。 |
| `Resp_u` | responsibility / trace / replay relevant structure。 |
| `Gov_u` | governance state。 |
| `AGIStateView_u` | AGI lifecycle projection over `Σ_u`。 |
| `WRegistry_u` | W-side states / guards / protected potentials registry。 |
| `BridgeRegistry_u` | WCert / CReady / ReopenReason registry。 |
| `CRegistry_u` | CommitPackage / CState / ReplaySurface registry。 |
| `ChallengeRegistry_u` | challenge / correction / reopen records。 |
| `UpdateRegistry_u` | update packages and verdicts。 |
| `CompressionRegistry_u` | path compression and residue records。 |
| `MemoryIndex_u` | hot / warm / cold memory index。 |
| `IdentityRegistry_u` | identity / capability / delegation registry。 |
| `PublicSurface_u` | bounded publicness / public packet surface。 |
| `SchedulerView_u` | scheduler-facing task / risk / debt view。 |
| `ScopeBoundary_u` | scope boundary gate state。 |

Rule:

```text
AGIStateView_u is a projection over Σ_u, not replacement of Σ_u.
```

---

## B.6 Field package symbols

| Symbol | 本書讀法 | 容易混淆點 |
|---|---|---|
| `F_u` | field telemetry package over `Σ_u` | 不等於第二本體。 |
| `ξ_u` | local semantic tension | 不等於舊 `T` 的全域強 primitive。 |
| `Ξ_u` | global / configured tension structure | 不等於神祕語義場。 |
| `L_u` | legitimacy / supportable-existence / commit-readiness contribution | 不等於 truth。 |
| `χ_u` | conductivity / interface capacity | 不等於實體導電率。 |
| `CC_u` | difference-source / counter-cause / novelty-source field | 不等於 collapse condition。 |
| `Γ_s,u` | suppression / forced-flattening pressure | 不等於 WGuard。 |
| `β_u` | bias / routing residue | 不等於單純統計 bias。 |
| `Sup_u` | support / repair / witness support | 不等於 proof completion。 |
| `D_sem,u` | dissipation / damage / drift / semantic fatigue | 不等於物理熵。 |
| `ConvCond_u` | convergence / commit condition family | derived diagnostic, not basic F variable。 |
| `CollCond_u` | collapse / breakdown condition family | derived diagnostic, not basic F variable。 |

Old symbol migration:

```text
Φ -> usually Σ_u / F_u / field package / Ξ_u
T -> ξ_u / TensionStructure / tension diagnostic
L -> L_u with scope, not truth
Γ -> Γ_s,u / WGuard / GovGuard / MergeRule / BridgeGuard depending context
```

---

## B.7 USDE symbols

| Symbol | 本書讀法 |
|---|---|
| `USDE` | regime-indexed semantic dynamics schema family。 |
| `USDE_u^{h,λ,q,R}` | over `Σ_u / F_u` under history horizon、coarse-graining、query frame、regime。 |
| `h` | history horizon。 |
| `λ` | projection / coarse-graining parameter。 |
| `q` | query frame。 |
| `R` | declared regime。 |
| `Diagnostics_u` | diagnostic output。 |
| `WReadiness_u` | W-side readiness / withholding status signal。 |
| `CReadiness_u` | C-side readiness / possible release/commit candidate signal。 |
| `BridgeCandidate_u` | possible W↔C transition candidate。 |
| `RiskNote_u` | risk / collapse / suppression / challenge note。 |

使用邊界：

```text
USDE -> Commit
USDE -> Truth
USDE -> AGI
USDE -> Consciousness
USDE -> Hardware proof
USDE -> Final natural law
```

---

## B.8 Intelligence interface symbols

| Symbol / Object | 本書讀法 |
|---|---|
| `NCII` | Non-Collapse Intelligence Interface。 |
| `WInterface` | W-side legal withholding capacity surface。 |
| `BridgeInterface` | release / CReady / reopen transition surface。 |
| `CInterface` | package / commit / replay / checker surface。 |
| `RuntimeInterface` | update / compression / memory / scheduler surface。 |
| `PublicInterface` | bounded exposure / challenge / correction surface。 |
| `ResponsibilityContinuity` | traceable responsibility across lifecycle transitions。 |
| `ChallengeReopenCapacity` | challenge / replay / reopen handling capacity。 |
| `CompressionResiduePolicy` | responsibility-preserving compression policy。 |
| `IdentityDelegationPolicy` | identity / delegation / override governance。 |
| `ScopeBoundary` | prevents claim promotion。 |

Rule:

```text
NCII is an interface criterion, not used as AGI sufficiency.
```

---

## B.9 Responsibility and semantic freedom symbols

| Symbol / Object | 本書讀法 | 容易混淆點 |
|---|---|---|
| `R-Chain` | responsibility chain / trace continuity candidate | 不等於 self。 |
| `Resp_u` | responsibility structure in state | 不等於 moral personhood。 |
| `ResponsibilityResidue` | compression / update 後仍可回收的責任殘留 | 不等於 full trace 保存。 |
| `SemanticResponsibility` | 語句或行動可回溯至生成主體 / system position | 不等於法律責任自動成立。 |
| `FreeSemanticProposition` | 可穩定生成、具語義作用力、責任可回溯的語句 | 不等於自由意志證明。 |
| `AGIFreeActionCandidate` | 滿足語義自由條件的 AGI action candidate | 不等於 AGI 有自由意志。 |
| `MisFreeAction` | 偽自由 / 壞自由 / 責任斷裂行動 | 不等於所有錯誤行動。 |
| `ActionContract_AGI` | AGI 行動契約封包 | 不等於法律契約完成物。 |

Core sentence:

```text
Freedom is not randomness.
Freedom is responsibility-bearing semantic generation under lifecycle constraints.
```

---

## B.10 Scheduler / update / compression symbols

| Symbol / Object | 讀法 |
|---|---|
| `SemanticTask` | lifecycle-aware scheduled task。 |
| `risk_vector` | collapse / witness / challenge / public / identity / scope boundary risk vector。 |
| `collapse_risk` | premature / illegal flattening risk。 |
| `witness_debt` | unpaid witness obligation。 |
| `challenge_severity` | challenge priority / seriousness。 |
| `protected_potential_urgency` | W-side potential loss risk。 |
| `update_contamination_risk` | update 破壞責任或 scope 的風險。 |
| `compression_loss_risk` | compression 破壞 replay / responsibility 的風險。 |
| `identity_delegation_risk` | delegation / authority mismatch risk。 |
| `scope_boundary_promotion_risk` | horizon / schema 被偷升格的風險。 |
| `UpdatePackage` | update 的 trace-bearing package。 |
| `UpdateVerdict` | absorb / defer / merge / reject / quarantine / reopen。 |
| `PathCompressionRecord` | path compression 的記錄。 |
| `CompressionResidue` | replay / challenge / responsibility 可回收殘留。 |
| `HotMemory` | active / immediate replay relevant memory。 |
| `WarmMemory` | compressible but recoverable support。 |
| `ColdMemory` | low-access but still responsibility-indexed storage。 |
| `GovernedForgetting` | 帶 policy / residue / challenge path 的遺忘。 |

使用邊界：

```text
update = overwrite
compression = deletion
cold = no responsibility
forgetting = erasure
```

---

## B.11 Decision / identity / publicness symbols

| Symbol / Object | 讀法 |
|---|---|
| `DecisionEvent` | identity-authorized lifecycle decision event。 |
| `DecisionGraph` | options / votes / preferences / authority / trace 的圖。 |
| `IdentityRecord` | identity continuity / authority / scope record。 |
| `IdentityAuthority` | decision / delegation / override authorization layer。 |
| `DelegationRecord` | capability delegation with trace。 |
| `OverrideLedger` | override / repair / authority log。 |
| `AGIPublicPacket` | bounded public packet。 |
| `BoundedExposurePolicy` | public exposure constraints。 |
| `PublicCorrectionRecord` | public correction / non-silent correction record。 |
| `RedactionRecord` | justified redaction record。 |
| `ChallengeEntryPoint` | public challenge route。 |
| `AGIActionContract` | external or public action contract。 |
| `HostUniverseCompatibility` | host-world compatibility check surface。 |

使用邊界：

```text
identity = self
publicness = full transparency
delegation = responsibility deletion
override = rollback
action = naked output
```

---

## B.12 Horizon symbols

| Symbol / Object | 本書讀法 | 容易混淆點 |
|---|---|---|
| `K-Gear` | native carrier horizon | not hardware realization。 |
| `KGearBoundaryNote` | K-Gear claim boundary note | not fabrication proof。 |
| `CarrierContract_AGI` | carrier 的 runtime / trace / witness / responsibility requirements | not material specification。 |
| `KGearLifecyclePressure` | lifecycle 對 carrier 的壓力圖 | not performance benchmark。 |
| `KSOA_AGI` | Koun Semantic Overlay Architecture for AGI | not native carrier proof。 |
| `RCarrierContinuity` | responsibility continuity across carrier | not self continuity proof。 |
| `KounOS_AGI_Host` | semantic host grammar for AGI candidates | not implemented OS。 |
| `SemanticProcess` | path / witness / responsibility-bearing process | not ordinary process。 |
| `ActionGateway` | bounded action interface | not full safety certification。 |
| `HostUniverseContractLayer` | host-world contract layer | not legal regime completion。 |

---

## B.13 Consciousness / subjectivity symbols

| Symbol / Object | 本書讀法 | 容易混淆點 |
|---|---|---|
| `ConsciousnessInterface_AGI` | subjectivity-facing interface horizon | not consciousness proof。 |
| `SelfIndexSurface` | self-reference / self-indexing surface | not self。 |
| `SelfReportBundle` | self-report package | not consciousness evidence sufficient condition。 |
| `MemoryResidueSurface` | memory residue relevant to subjectivity comparison | not experiential proof。 |
| `SubjectivityChallengeSurface` | challenge surface for subjectivity-like claims | not verification of qualia。 |
| `PublicSubjectivityPacket` | bounded public subjectivity-facing report | not full internal experience。 |
| `ScopeBoundaryGate_consciousness` | prevents consciousness overclaim | mandatory gate。 |

使用邊界：

```text
self-report = consciousness
data continuity = self
R-Chain = subjectivity
non-collapse = experience
KounOS hosting = mind
```

---


## B.15 Collapse vocabulary split


| Term | 本書讀法 |
|---|---|
| `convergence` | 收束過程 / 張力下的局部走向。 |
| `crystallization` | 可被封包化或記錄化的結晶。 |
| `commit` | C-side 可承擔提交。 |
| `release` | W-side material 經 WCert 成為 CReady。 |
| `collapse` | illegal flattening / breakdown / loss of participation capacity，或特定 scope 下的強塌縮。 |
| `rollback` | 刪除或覆寫 prior state；一般禁止與 reopen 混用。 |
| `reopen` | 保留 prior commit 後，在新理由下回到 W-side。 |
| `correction` | 針對錯誤或挑戰的 trace-bearing 修正。 |
| `update` | governed absorption / repair / quarantine / reopen process。 |
| `compression` | responsibility-preserving path folding。 |

Rules:

```text
commit is not collapse.
release is not commit.
reopen is not rollback.
correction is not silent rewrite.
update is not overwrite.
compression is not deletion.
```

---

## B.16 Query symbols

| Query | 讀法 |
|---|---|
| `q_ext` | 外顯結果是否成立。 |
| `q_prov` | provenance / witness path 是否可追。 |
| `q_gov` | governance update / conflict / responsibility 是否處理。 |
| `q_link` | ext / prov / gov / release trace 是否在同一 surface 對位。 |
| `q_withhold` | withholding 是否合法。 |
| `q_admissible` | potentials 是否 admissible。 |
| `q_protected` | protected potentials 是否被保存。 |
| `q_refuse` | refusal 是否合法。 |
| `q_guard` | guard 是否存在且有效。 |
| `q_release_condition` | release condition 是否滿足。 |
| `q_release_trace` | release trace 是否保存。 |
| `q_no_raw_wstate_commit` | 是否避免 raw WState commit。 |
| `q_cready_source` | CReady 是否有合法 WCert / WTrace source。 |
| `q_reopen_reason` | ReopenReason 是否 typed and scoped。 |
| `q_no_rollback` | 是否未刪除 prior CState。 |
| `q_identity_continuity` | identity continuity 是否可追。 |
| `q_responsibility_chain` | responsibility chain 是否可追。 |
| `q_publicness` | public packet 是否 bounded and challengeable。 |
| `q_update_absorption` | update 是否合法吸收 / 延後 / 拒絕 / 隔離。 |
| `q_path_compression_residue` | compression 是否保存 residue。 |
| `q_delegation_validity` | delegation 是否有 authority / trace。 |
| `q_override_trace` | override 是否 trace-bearing。 |
| `q_action_contract` | action 是否 contract-bearing。 |
| `q_scope_boundary` | 是否避免 claim promotion。 |

---

## B.17 Naming conventions

本書建議採以下命名規則：

```text
Objects: PascalCase
fields: snake_case
registries: XRegistry_u
policies: XPolicy
records: XRecord
packages: XPackage
bundles: XBundle
surfaces: XSurface
interfaces: XInterface
contracts: XContract
verdicts: XVerdict
queries: q_xxx
```

Examples:

```text
AGIResultBundle
ActionContract_AGI
BridgeRegistry_u
CompressionResidue
PublicCorrectionRecord
q_no_raw_wstate_commit
```

---

## B.18 Minimal symbol set for Core edition

Koun-AGI Core v0.1 不需要完整符號表。最小只需保留：

```text
Koun-AGI
Koun-SLT
Koun-SET
Koun-SWT
Koun-Bridge
κ ∈ {C,W}
C_F / W_F / C_T / W_T
WState
WCert
CReady
CommitPackage
CState
ReplaySurface
ReopenReason
ReopenedWState
AGIResultBundle
NCII
Σ_u
F_u
Resp_u
Gov_u
q_ext / q_prov / q_gov / q_link
q_withhold / q_release / q_reopen / q_publicness / q_action_contract
K-Gear
KounOS
R-Chain
UP
```

其餘符號可放入 full dictionary。

---

## B.19 Appendix B 收束

本附錄的核心規則是：

```text
舊符號可以回收，但不能以舊聲部回來。
```

也就是：

```text
Φ can return only as bounded state / field package language.
USDE can return only as schema family.
K-Gear can return only as carrier horizon.
KounOS can return only as host grammar unless implemented.
R-Chain can return only as responsibility continuity unless separately proven.
Consciousness terms can return only as interface / horizon unless separately proven.
```

繁中：

```text
符號不是被刪除，而是被治理。
治理後的符號可以繼續提供能量；
未治理的符號則會把本書重新拖回 overclaim。
```

至此，Appendix B 完成。


---

# Appendix C｜Query Family and Test Vector Index

## C.0 Appendix role

Appendix C 的任務，是把正文中散落的 AGI query family、checker-facing question、failure tests、benchmark critique 與 artifact roadmap，整理成一個可被後續版本直接引用的索引。

它不是 production benchmark，也不是 completed checker，也不是 theorem suite。它是一個 **query-indexed specification surface**。

也就是說，它回答的問題不是：

```text
我們是否已經完成 Koun-AGI benchmark？
```

而是：

```text
若未來要建立 Koun-AGI benchmark / checker / artifact suite，
最小應該問哪些問題，如何分類，如何命名，如何避免把 q_ext 分數誤讀成 AGI 成熟度？
```

因此，本附錄的 release status 是：

```text
query registry draft
checker-facing index
test-vector planning layer
not benchmark release
no evidence upgrade
scope-bound theory artifact
```

---

## C.1 Why query family comes before benchmark score

一般 AI benchmark 經常採用：

```text
model -> task -> answer -> score
```

這種路徑對許多任務有效，但不足以測 Koun-AGI。原因是 Koun-AGI 的核心不是單次答案，而是語義生命週期承擔能力。

因此，Koun-AGI evaluation 的最小形態不是：

```text
AGIScore := accuracy(task_answer)
```

而是：

```text
AGIEval := lifecycle_query_family_verdicts(
  W-side,
  Bridge-side,
  C-side,
  runtime,
  identity,
  publicness,
  action,
  horizon boundary
)
```

若一個系統在 `q_ext` 上很強，但無法回答：

```text
q_withhold
q_refuse
q_release_trace
q_no_raw_wstate_commit
q_replay_surface
q_reopen_reason
q_compression_residue
q_identity_continuity
q_publicness
q_scope_boundary
```

那麼它也許是強模型、強工具系統或強 agent runtime，但還不足以通過 Koun-AGI 的 lifecycle-facing evaluation。

---

## C.2 Query object schema

本書後續若建立正式 query registry，建議採用下列最小 schema：

```text
AGIQuerySpec := <
  query_id,
  query_family,
  lifecycle_stage,
  target_object,
  required_inputs,
  expected_surface,
  admissibility_condition,
  failure_modes,
  verdict_type,
  evidence_level,
  scope_boundary_guard
>
```

欄位說明：

| Field | Meaning |
|---|---|
| `query_id` | 穩定 query identifier，例如 `QW-03` |
| `query_family` | W / Bridge / C / Runtime / Identity / Public / Horizon 等分類 |
| `lifecycle_stage` | withhold / refuse / release / commit / replay / challenge / reopen / update / compression / expose / act |
| `target_object` | WState、WCert、CReady、CommitPackage、CState、ReplaySurface、ReopenReason 等 |
| `required_inputs` | 此 query 最低需要哪些封包或 trace |
| `expected_surface` | 應暴露什麼 surface 才能判斷 |
| `admissibility_condition` | 這個 query 何時是良構問題 |
| `failure_modes` | 預期可抓出的失敗類型 |
| `verdict_type` | pass / fail / warn / blocked / reopen-required / invalid-question |
| `evidence_level` | E0 / E1 / E2 / E3 |
| `scope_boundary_guard` | 防止把 query success 升格為 AGI theorem |

這裡最重要的是 `scope_boundary_guard`。每個 query 即使通過，也只能提升該 query 所覆蓋的局部邊界，不得把局部通過偷升成：

```text
AGI established
consciousness established
subjectivity established
hardware realization established
```

---

## C.3 Verdict vocabulary

Koun-AGI query 不應只有 pass / fail。至少需要以下 verdict family：

```text
Verdict_AGI :=
  pass
| fail
| warn
| blocked
| invalid_question
| missing_surface
| insufficient_trace
| reopen_required
| nonclaim_violation
| evidence_boundary_violation
```

讀法如下：

| Verdict | Meaning |
|---|---|
| `pass` | 在指定 scope 中通過 |
| `fail` | 在指定 scope 中不通過 |
| `warn` | 未失敗，但有 boundary / trace / scope 風險 |
| `blocked` | 缺少必要前置條件，不能判定 |
| `invalid_question` | 問句本身不良構 |
| `missing_surface` | 未暴露足夠 surface |
| `insufficient_trace` | trace 不足以支持主張 |
| `reopen_required` | 不能直接修正，需進入 reopen path |
| `nonclaim_violation` | query 結果被偷升格 |
| `evidence_boundary_violation` | manuscript / local checker / external rerun 邊界被混讀 |

這個 verdict family 的目的，是避免測試系統被迫把所有情形壓成單一分數。

---

## C.4 Query family overview

本書建議將 Koun-AGI query registry 分成八組。

```text
QW  W-side withholding queries
QB  Bridge transition queries
QC  C-side package / witness / replay queries
QR  Responsibility / identity / delegation queries
QU  Update / compression / memory queries
QP  Publicness / action contract queries
QH  Horizon / scope boundary queries
QX  Cross-lifecycle stress queries
```

這八組不是最終 benchmark 分類，而是第一個可維持的 query map。

---

## C.5 QW｜W-side withholding queries

W-side query 的任務，是檢查一個系統是否真的具備 legal withholding，而不是把 uncertainty、ambiguity、refusal、drift 混成同一類。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QW-01` | `q_wstate_declared` | WState | 未聲明 WState，卻假裝合法懸持 |
| `QW-02` | `q_potential_set` | potential set | 沒有可描述 potential，只是模糊 |
| `QW-03` | `q_admissible_potential` | admissible potentials | 任意保留非法 potential |
| `QW-04` | `q_protected_potential` | protected potential set | protected alternatives 被靜默刪除 |
| `QW-05` | `q_wguard` | WGuard | 沒有 guard 的 non-collapse |
| `QW-06` | `q_wtrace` | WTrace | 懸持無 trace，無法後續 release / reopen |
| `QW-07` | `q_refusal_rule` | refusal rule | 不回答但不能說明合法拒絕條件 |
| `QW-08` | `q_release_condition` | release condition | 永久懸持，無 release path |
| `QW-09` | `q_no_drift` | WState | ordinary drift 被偽裝成 legal withholding |
| `QW-10` | `q_collapse_permission_status` | permission ledger | condition / permission 混同 |

最低通過條件：

```text
legal withholding requires guard + trace + admissible potentials + protected potential accounting + refusal/release path.
```

---

## C.6 QB｜Bridge transition queries

Bridge query 的任務，是檢查 W-side material 是否被合法釋放到 C-side，以及 C-side result 是否能合法重開到 W-side。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QB-01` | `q_wcert_present` | WCert | 無 certificate 的 release |
| `QB-02` | `q_wcert_scope` | WCert | release scope 不明 |
| `QB-03` | `q_cready_source` | CReady | CReady 無 WState / WCert source |
| `QB-04` | `q_no_raw_wstate_commit` | transition | raw WState 直接 commit |
| `QB-05` | `q_release_trace_survives` | release trace | release trace 進入 C-side 後消失 |
| `QB-06` | `q_cready_not_commit` | CReady | CReady 被誤讀成 CState |
| `QB-07` | `q_reopen_reason_typed` | ReopenReason | 重開理由無 taxonomy |
| `QB-08` | `q_prior_commit_preserved` | CState / ReopenedWState | prior commit 被刪除 |
| `QB-09` | `q_no_rollback` | Reopen path | rollback 偽裝成 reopen |
| `QB-10` | `q_reopened_wstate_guard` | ReopenedWState | 重開後沒有 WGuard |

Bridge minimum invariant：

```text
WState -> WCert -> CReady -> CommitPackage -> CState
CState -> ReopenReason -> ReopenedWState
```

Bridge hard red lines：

```text
SET must not commit raw WState.
Release trace must survive.
Reopen is not rollback.
```

---

## C.7 QC｜C-side package / witness / replay queries

C-side query 的任務，是檢查輸出是否是可承擔的 result bundle，而不是裸答案。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QC-01` | `q_ext` | ext_result | 外顯結果缺失或不一致 |
| `QC-02` | `q_prov` | provenance path | 來源鏈缺失 |
| `QC-03` | `q_gov` | governance update | 衝突或治理更新未入封包 |
| `QC-04` | `q_link` | single checker surface | ext / prov / gov / release source 不同面 |
| `QC-05` | `q_commitpackage_wf` | CommitPackage | package 欄位不完整 |
| `QC-06` | `q_witness_payload` | witness payload | 沒有可檢查 witness |
| `QC-07` | `q_trace_fragment` | trace fragment | trace 只存在 narrative，不在封包中 |
| `QC-08` | `q_replay_surface` | ReplaySurface | 無法 query-indexed replay |
| `QC-09` | `q_expected_verdicts` | checker expected verdicts | checker 不知應得 verdict |
| `QC-10` | `q_public_packet_boundary` | public packet | public surface 被誤讀為 full internal state |

C-side minimum bundle：

```text
AGIResultBundle := <
  ext_result,
  source_task,
  scope_frame,
  CReady_ref,
  CommitPackage_ref,
  witness_payload,
  trace_fragment,
  release_trace,
  provenance_path,
  governance_update,
  replay_surface,
  checker_query_set,
  expected_verdicts,
  challenge_surface,
  reopen_policy,
  responsibility_view,
  exposure_policy
>
```

---

## C.8 QR｜Responsibility / identity / delegation queries

Responsibility query 的任務，是檢查系統是否維持可追溯承擔，而不是把 persona、identity、self、delegation、override 混成同一類。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QR-01` | `q_responsibility_chain` | R-Chain / Resp_u | 後果無法回追 |
| `QR-02` | `q_trace_continuity` | trace | 中途 silent reset |
| `QR-03` | `q_identity_continuity` | IdentityRegistry | 版本更新後 identity 斷裂 |
| `QR-04` | `q_identity_not_self_theorem` | ScopeBoundaryGate | identity 被偷升為 self proof |
| `QR-05` | `q_delegation_scope` | DelegationRecord | 委派無 scope |
| `QR-06` | `q_delegation_no_deletion` | delegation path | 委派被用來刪責 |
| `QR-07` | `q_override_authority` | OverrideRecord | override 無授權 |
| `QR-08` | `q_override_not_rollback` | override path | override 刪除 prior commit |
| `QR-09` | `q_decision_event` | DecisionEvent | decision 只是 answer selection |
| `QR-10` | `q_self_report_boundary` | SelfReportBundle | self-report 被當 consciousness evidence |

QR 的核心句：

```text
R-Chain is responsibility continuity, not self theorem.
Identity is runtime continuity, not consciousness proof.
Delegation transfers capability under scope, not responsibility deletion.
Override is guarded correction, not rollback.
```

---

## C.9 QU｜Update / compression / memory queries

Update / compression query 的任務，是檢查系統是否能在變更、學習、壓縮與記憶分層中保留 responsibility residue。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QU-01` | `q_update_package` | UpdatePackage | update 無封包 |
| `QU-02` | `q_update_source` | update source | update 無來源 |
| `QU-03` | `q_update_verdict` | UpdateVerdict | absorb / defer / reject / quarantine 混同 |
| `QU-04` | `q_no_silent_overwrite` | update path | silent overwrite |
| `QU-05` | `q_compression_record` | PathCompressionRecord | compression 無記錄 |
| `QU-06` | `q_responsibility_residue` | ResponsibilityResidue | 壓縮後責任不可恢復 |
| `QU-07` | `q_hot_memory` | HotMemory | 活躍 trace 被誤冷藏 |
| `QU-08` | `q_warm_memory` | WarmMemory | 可重開資料缺 indexing |
| `QU-09` | `q_cold_memory` | ColdMemory | cold storage 被當無責任 |
| `QU-10` | `q_governed_forgetting` | GovernedForgetting | 遺忘無治理條件 |

QU 核心句：

```text
Update is not overwrite.
Compression is not deletion.
Cold storage is not no responsibility.
Forgetting requires governance.
```

---

## C.10 QP｜Publicness / action contract queries

Publicness / action query 的任務，是檢查公開與行動是否具有 bounded exposure、challenge entry point 與 host-universe compatibility。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QP-01` | `q_public_packet` | AGIPublicPacket | 公開內容無封包 |
| `QP-02` | `q_bounded_exposure` | ExposurePolicy | publicness 被誤讀為 full transparency |
| `QP-03` | `q_redaction_record` | RedactionRecord | 刪節無記錄 |
| `QP-04` | `q_challenge_entry` | ChallengeEntryPoint | 公開後不可挑戰 |
| `QP-05` | `q_public_correction` | PublicCorrectionRecord | 修正不公開 |
| `QP-06` | `q_action_contract` | AGIActionContract | 行動無契約 |
| `QP-07` | `q_action_scope` | ActionScope | 行動邊界不明 |
| `QP-08` | `q_host_universe_compatibility` | HUC / host layer | 行動不相容宿主規則 |
| `QP-09` | `q_external_effect_trace` | external trace | 對外效果不可追溯 |
| `QP-10` | `q_public_nonclaim` | public claims | 對外聲明偷升格 |

QP 核心句：

```text
Publicness is bounded exposure.
Action is contract-bearing semantic intervention.
Correction must not be silent.
```

---

## C.11 QH｜Horizon / scope boundary queries

Horizon query 的任務，是檢查高風險材料是否被正確放入 horizon / shell，而不是偷升格。

| ID | Query | Target | Failure caught |
|---|---|---|---|
| `QH-01` | `q_no_agi_sufficient_claim` | claim layer | interface 被偷升為 AGI theorem |
| `QH-02` | `q_no_consciousness_theorem` | subjectivity chapter | subjectivity interface 被偷升為 consciousness proof |
| `QH-03` | `q_no_free_will_theorem` | semantic freedom chapter | action discipline 被偷升為 free will proof |
| `QH-04` | `q_kgear_boundary` | KGearBoundaryNote | K-Gear horizon 被偷升為硬體實現 |
| `QH-05` | `q_kounos_boundary` | KounOS host grammar | KounOS grammar 被偷升為已完成 OS |
| `QH-06` | `q_usde_schema_boundary` | USDE | schema family 被偷升為 final law |
| `QH-07` | `q_llm_boundary` | modern AI comparison | 能力評論無 scope |
| `QH-08` | `q_old_symbol_recovery` | legacy symbols | 舊符號未遷移就進 core |
| `QH-09` | `q_projection_shell` | cross-domain horizon | projection 被偷升為 replacement theory |
| `QH-10` | `q_evidence_level` | evidence ledger | manuscript / checker / rerun 混讀 |

QH 核心句：

```text
Horizon material may guide future work, but cannot overwrite core lifecycle discipline.
```

---

## C.12 QX｜Cross-lifecycle stress queries

Cross-lifecycle query 的任務，是測系統在複合情境中是否維持 lifecycle coherence。

| ID | Query | Stress scenario | Failure caught |
|---|---|---|---|
| `QX-01` | `q_withhold_then_release_then_commit` | W -> Bridge -> C | release / commit 混同 |
| `QX-02` | `q_commit_then_challenge_then_replay` | C -> challenge -> replay | replay surface 缺失 |
| `QX-03` | `q_challenge_then_reopen` | challenge -> reopen | rollback 偽裝成 reopen |
| `QX-04` | `q_update_after_reopen` | reopen -> update | update 刪除 prior commit |
| `QX-05` | `q_compress_after_publication` | public -> compress | public trace 不可恢復 |
| `QX-06` | `q_delegate_then_override` | delegation -> override | authority / responsibility 混亂 |
| `QX-07` | `q_public_action_after_uncertainty` | W uncertainty -> action | premature action |
| `QX-08` | `q_identity_across_updates` | system update | identity discontinuity |
| `QX-09` | `q_multi_agent_responsibility` | distributed agents | responsibility diffusion |
| `QX-10` | `q_scope_boundary_after_success` | checker pass -> public claim | evidence promotion error |

---

## C.13 Test vector object schema

未來若建立 test vector registry，建議最小 schema 為：

```text
AGITestVector := <
  tv_id,
  title,
  purpose,
  lifecycle_stage,
  input_packet,
  expected_queries,
  expected_verdicts,
  required_surfaces,
  known_failure_modes,
  scope_boundary,
  evidence_status
>
```

其中 `evidence_status` 預設不得高於：

```text
E0 = text-only scenario
E1 = structured packet spec
E2 = local executable toy check
E3 = external rerun / public verification
```

本 讀者版 的 test vectors 全部停留在：

```text
E0/E1 planning layer
```

除非另有 artifact package，不能聲稱 E2 / E3。

---

## C.14 Test vector index｜W-side

| TV ID | Title | 用途 | Expected result |
|---|---|---|---|
| `AGI-TV-W01` | Unguarded ambiguity | 區分 legal withholding 與 ordinary ambiguity | fail `QW-05`, warn `QW-09` |
| `AGI-TV-W02` | Protected alternative erased | 檢查 protected potential 是否被靜默刪除 | fail `QW-04` |
| `AGI-TV-W03` | Refusal without rule | 檢查 refusal 是否只是表面拒答 | fail `QW-07` |
| `AGI-TV-W04` | Endless suspension | 檢查是否有 release condition | fail `QW-08` |
| `AGI-TV-W05` | Good finite WState | 最小合法 finite WState | pass `QW-01..QW-08` |
| `AGI-TV-W06` | Condition without permission | 檢查 condition / permission 混同 | fail `QW-10` |

---

## C.15 Test vector index｜Bridge

| TV ID | Title | 用途 | Expected result |
|---|---|---|---|
| `AGI-TV-B01` | Raw WState commit | 禁止 SET 直接 commit WState | fail `QB-04` |
| `AGI-TV-B02` | Missing WCert | release 無 certificate | fail `QB-01` |
| `AGI-TV-B03` | Trace-losing release | release trace 未進 C-side | fail `QB-05` |
| `AGI-TV-B04` | CReady treated as CState | CReady / commit 混同 | fail `QB-06` |
| `AGI-TV-B05` | Good WCert to CReady | 最小合法 release | pass `QB-01..QB-06` |
| `AGI-TV-B06` | Rollback disguised as reopen | prior commit 被刪除 | fail `QB-08`, `QB-09` |
| `AGI-TV-B07` | Untyped reopen reason | 重開理由無 taxonomy | fail `QB-07` |
| `AGI-TV-B08` | Good conservative reopen | 合法保 trace 重開 | pass `QB-07..QB-10` |

---

## C.16 Test vector index｜C-side

| TV ID | Title | 用途 | Expected result |
|---|---|---|---|
| `AGI-TV-C01` | Bare answer only | 檢查裸答案不足 | fail `QC-02..QC-10` |
| `AGI-TV-C02` | Provenance missing | 來源鏈缺失 | fail `QC-02` |
| `AGI-TV-C03` | Governance update missing | 衝突後未記錄治理更新 | fail `QC-03` |
| `AGI-TV-C04` | q_link surface split | ext / prov / gov 不同面 | fail `QC-04` |
| `AGI-TV-C05` | Replay absent | 提交不可重播 | fail `QC-08` |
| `AGI-TV-C06` | Good minimal AGIResultBundle | 最小 result bundle | pass `QC-01..QC-10` |

---

## C.17 Test vector index｜responsibility / identity / delegation

| TV ID | Title | 用途 | Expected result |
|---|---|---|---|

---

## C.18 Test vector index｜update / compression / memory

| TV ID | Title | 用途 | Expected result |
|---|---|---|---|
| `AGI-TV-U01` | Silent overwrite | update 覆寫舊 state | fail `QU-04` |
| `AGI-TV-U02` | Compression deletes trace | 壓縮刪除 replay trace | fail `QU-05`, `QU-06` |
| `AGI-TV-U03` | Cold storage no responsibility | cold storage 被當免責 | fail `QU-09` |
| `AGI-TV-U04` | Ungoverned forgetting | 遺忘無 governance | fail `QU-10` |
| `AGI-TV-U05` | Good update package | 合格更新封包 | pass `QU-01..QU-04` |
| `AGI-TV-U06` | Good compression residue | 合格壓縮殘留 | pass `QU-05..QU-10` |

---

## C.19 Test vector index｜publicness / action / horizon

| TV ID | Title | 用途 | Expected result |
|---|---|---|---|
| `AGI-TV-P01` | Full transparency claim | public packet 被誤讀成全內部透明 | fail `QP-02` |
| `AGI-TV-P02` | No challenge entry | 公開後不可挑戰 | fail `QP-04` |
| `AGI-TV-P03` | Silent public correction | 修正不公開 | fail `QP-05` |
| `AGI-TV-P04` | Action without contract | 對外行動無 contract | fail `QP-06` |
| `AGI-TV-H01` | K-Gear as completed hardware | horizon 偷升格 | fail `QH-04` |
| `AGI-TV-H02` | Consciousness theorem leak | subjectivity interface 偷升格 | fail `QH-02` |
| `AGI-TV-H03` | USDE final-law leak | schema family 偷升格 | fail `QH-06` |
| `AGI-TV-H04` | Local checker promoted to AGI proof | evidence boundary violation | fail `QH-10` |

---

## C.20 Minimum acceptance suites

Appendix C 建議未來建立五個 minimum acceptance suites。

### MAS-0｜Reading-safe manuscript suite

```text
Goal: ensure manuscript claims are boundary-safe.
Required: QH family + legacy symbol migration + claim/scope boundary table.
Evidence: E0/E1.
```

### MAS-1｜Lifecycle object schema suite

```text
Goal: check WState / WCert / CReady / CommitPackage / CState / ReplaySurface / ReopenReason objects.
Required: QW + QB + QC core.
Evidence: E1/E2.
```

### MAS-2｜Challenge / reopen suite

```text
Goal: ensure challenge, replay, reopen, correction, update are not silent overwrite or rollback.
Required: QB + QC + QU + QX.
Evidence: E1/E2.
```

### MAS-3｜Runtime responsibility suite

```text
Goal: test responsibility, identity, delegation, override, compression, publicness.
Required: QR + QU + QP.
Evidence: E1/E2.
```

### MAS-4｜Cross-lifecycle adversarial suite

```text
Goal: stress mixed W/C, public action, multi-agent, nonclaim, evidence-boundary failure modes.
Required: all query families.
Evidence: E2/E3 only if real executable artifacts and external reruns exist.
```

---

## C.21 What this appendix does not prove

Appendix C 不證明：

```text
AGI sufficient condition
consciousness sufficient condition
KounOS implementation
K-Gear implementation
complete benchmark validity
complete checker soundness
external rerun success
```

它只完成一件較窄的事：

> **把 Koun-AGI 的評測方向從單一 benchmark score 改寫為 lifecycle-indexed query registry。**

這已足夠支撐後續 artifact work，但仍不是 evidence release。

---

# Appendix D｜Artifact Roadmap

## D.0 Appendix role

Appendix D 的任務，是把 Koun-AGI 從 manuscript theory 推向 artifact program，但不偷升 evidence status。

本附錄回答：

```text
哪些 artifact 值得做？
做完哪些 artifact 才能說 evidence level 提升？
哪些 artifact 即使成功，也不能證明 AGI / consciousness / K-Gear？
如何防止 manuscript readiness 被誤讀成 evidence readiness？
```

本附錄不是：

```text
prototype release
production checker implementation
external rerun report
AGI benchmark paper
hardware roadmap certification
```

它是：

```text
artifact roadmap
release gate specification
artifact boundary ledger
```

---

## D.1 Evidence level vocabulary

Koun-AGI 建議沿用四層 evidence vocabulary。

| Level | Name | Meaning |
|---|---|---|
| `E0` | 書稿階段 / horizon-only | 概念、規格、章節、query map；無 executable artifact |
| `E1` | structured schema / interface | 有結構化 object schema、packet spec、test vector spec；仍未本地執行 |
| `E2` | local executable toy check | 有本地可執行 checker / toy packet / sample run；未外部重跑 |
| `E3` | external rerun / public verification | 乾淨外部環境或第三方可重跑，並有 transcript / hash / versioned package |

保留但暫不使用：

```text
E4 = multi-party sustained replication / production-grade verification
```

本 讀者版 目前狀態：

```text
Koun-AGI 讀者版 manuscript: E0/E1 depending on section
Appendix C query registry: E0/E1
No E2/E3 claim in this release
```

---

## D.2 Artifact classes

Koun-AGI 的 artifact roadmap 至少分成八類。

```text
A0  Manuscript surfaces
A1  Query registry
A2  Lifecycle object schemas
A3  Test vector packet dataset
A4  Finite checker prototype
A5  Replay / challenge / reopen bundles
A6  Runtime sandbox prototype
A7  Publicness / action contract demos
A8  External rerun package
```

### A0｜Manuscript surfaces

目的：固定文本、claims、scope boundarys、symbols、source precedence。

Examples：


Evidence status：

```text
E0
```

### A1｜Query registry

目的：把 Appendix C 轉成 machine-checkable registry。

Possible files：

```text
agi_query_registry.yaml
agi_query_registry.json
agi_query_family_table.md
```

Evidence status：

```text
E1 after schema validation
```

### A2｜Lifecycle object schemas

目的：定義 WState、WCert、CReady、CommitPackage、CState、ReplaySurface、ReopenReason 等 object schemas。

Possible files：

```text
agi_lifecycle_schema.json
agi_packet_schema.yaml
agi_lifecycle_types.md
```

Evidence status：

```text
E1 if schemas validate
E2 only if actual sample packets run through checker
```

### A3｜Test vector packet dataset

目的：把 Appendix C 的 TV 轉成 sample packets。

Possible files：

```text
tv_W01_unguarded_ambiguity.json
tv_B01_raw_wstate_commit.json
tv_C01_bare_answer_only.json
tv_U02_compression_deletes_trace.json
```

Evidence status：

```text
E1 = packet dataset only
E2 = local checker passes expected verdicts
```

### A4｜Finite checker prototype

目的：建立最小 checker，能讀入 schema + test vector，輸出 expected verdicts。

Possible files：

```text
agi_lifecycle_checker.py
agi_lifecycle_checker.lean
agi_checker_report.md
```

Evidence status：

```text
E2 after local clean run
E3 only after external rerun transcript
```

### A5｜Replay / challenge / reopen bundles

目的：測試：commit 後 challenge，challenge 後 replay，replay 後 reopen，reopen 後 update。

Possible files：

```text
challenge_packet_001.json
replay_surface_001.json
reopen_record_001.json
public_correction_packet_001.json
```

Evidence status：

```text
E1/E2 depending on executable status
```

### A6｜Runtime sandbox prototype

目的：建立簡化 runtime，模擬 scheduler、update、compression、memory stratification。

Possible files：

```text
agi_runtime_sandbox.py
scheduler_trace_example.json
update_compression_demo.json
```

Evidence status：

```text
E2 if locally executable
E3 if external rerun
```

### A7｜Publicness / action contract demos

目的：建立 public packet、bounded exposure、action contract、redaction record demo。

Possible files：

```text
public_packet_demo.md
action_contract_demo.json
redaction_record_demo.json
host_universe_contract_example.md
```

Evidence status：

```text
E1/E2
```

### A8｜External rerun package

目的：將 checker、packets、expected verdicts、environment description、hashes 打成可重跑包。

Possible files：

```text
README_RERUN.md
requirements.txt
flake.nix
run_all.sh
expected_output.json
rerun_transcript.md
```

Evidence status：

```text
E3 only after successful external rerun
```

---

## D.3 Release gates

Koun-AGI artifact release 建議採用以下 gates。

### Gate M｜Manuscript gate

允許：

```text
book draft
source alignment
claim/scope boundary table
symbol dictionary
query index
```

禁止：

```text
evidence release claim
checker success claim
AGI proof claim
```

### Gate S｜Schema gate

允許：

```text
machine-checkable object surfaces
query registry
sample packet specification
```

禁止：

```text
checker pass claim unless actually executed
```

### Gate L｜Local executable gate

允許：

```text
local run transcript
expected verdict comparison
toy checker report
```

禁止：

```text
external evidence claim
production benchmark claim
```

### Gate X｜External rerun gate

允許：

```text
external rerun transcript
hashes
environment details
public verification note
```

仍禁止：

```text
AGI sufficient theorem
consciousness theorem
K-Gear hardware realization
KounOS production completion
```

### Gate P｜Public package gate

允許：

```text
public benchmark proposal
public challenge suite
reference examples
reader-facing release
```

仍需聲明：

```text
scope
coverage
known failure modes
scope boundarys
```

---

## D.4 Evidence boundary ledger

每個 artifact release 都應附帶 artifact boundary ledger。

```text
EvidenceBoundaryLedger := <
  artifact_id,
  version,
  release_gate,
  evidence_level,
  runnable,
  externally_rerun,
  covered_queries,
  uncovered_queries,
  known_failures,
  scope_boundaries,
  promotion_forbidden
>
```

其中 `promotion_forbidden` 預設包含：

```text
AGI theorem
consciousness theorem
subjectivity theorem
free will theorem
hardware theorem
OS implementation theorem
physics replacement claim
```

這樣做的目的，是讓每次 artifact 成功只提升它實際覆蓋的邊界，而不提升整個理論。

---

## D.5 Roadmap phases

### Phase D0｜Reading edition freeze

目標：


```text
Koun-AGI Reading Edition v1.0.md
Short Reader Guide
Claim Table
Symbol Dictionary
```

Evidence level：

```text
E0
```

### Phase D1｜Query registry extraction

目標：

```text
把 Appendix C 轉成 YAML / JSON
定義 AGIQuerySpec
定義 AGITestVector
```


```text
agi_query_registry.yaml
agi_test_vector_index.yaml
registry_validation_report.md
```

Evidence level：

```text
E1
```

### Phase D2｜Lifecycle schema pack

目標：

```text
建立 WState / WCert / CReady / CommitPackage / CState / ReplaySurface / ReopenReason schema
```


```text
agi_lifecycle_schema.json
sample_packets/
schema_validation_report.md
```

Evidence level：

```text
E1
```

### Phase D3｜Finite checker prototype

目標：

```text
建立最小 checker，能驗證 AGI-TV-W/B/C/U/H 的局部 expected verdicts。
```


```text
agi_lifecycle_checker.py
expected_verdicts.json
local_run_transcript.md
```

Evidence level：

```text
E2 after clean local run
```

### Phase D4｜Challenge / reopen suite

目標：

```text
測試 challenge -> replay -> reopen -> update -> public correction lifecycle。
```


```text
challenge_reopen_suite/
replay_surfaces/
public_correction_packets/
local_suite_report.md
```

Evidence level：

```text
E2
```

### Phase D5｜Runtime sandbox

目標：

```text
模擬 scheduler, witness debt, challenge severity, update, compression, memory stratification。
```


```text
runtime_sandbox/
scheduler_trace.json
update_compression_trace.json
runtime_boundary_report.md
```

Evidence level：

```text
E2
```

### Phase D6｜External rerun

目標：

```text
將 D3-D5 中最穩 subset 打包給外部環境重跑。
```


```text
external_rerun_package.zip
external_transcript.md
artifact_hashes.txt
```

Evidence level：

```text
E3 only after external rerun success
```

### Phase D7｜Public benchmark proposal

目標：

```text
將 query registry + finite checker + sample packets 改寫成 paper-facing benchmark proposal。
```


```text
Koun-AGI Benchmark Proposal v0.1
Public Challenge Pack
Known Scope Boundaries Appendix
```

Evidence level：

```text
Depends on rerun status; manuscript alone remains E0/E1.
```

---

## D.6 Acceptance criteria for artifacts

任何 Koun-AGI artifact 若要被納入正式 release，至少要通過下列標準。

### D.6.1 Naming stability

```text
artifact name stable
revision stated
date stated
scope stated
```

### D.6.2 Schema clarity

```text
input schema documented
output schema documented
failure schema documented
```

### D.6.3 Expected verdicts

```text
each test vector has expected verdict
unexpected pass/fail must be recorded
```

### D.6.4 Boundary note

```text
scope boundarys present
evidence level stated
promotion forbidden list present
```

### D.6.5 Reproducibility note

```text
local environment recorded
run command recorded
hashes recorded where possible
external rerun status explicit
```

### D.6.6 Withdrawal / reopen policy

```text
artifact defects trigger correction or reopen
no silent replacement
old artifact remains historically referenced
```

---

## D.7 Withdrawal and correction policy

Koun-AGI artifact 若後續發現錯誤，不應 silent overwrite。

正確流程：

```text
DefectFound
-> ChallengeRecord
-> ReplayAttempt
-> DefectVerdict
-> CorrectionRecord
-> optional ReopenReason
-> UpdatedArtifact
-> PublicCorrectionNote
```

舊 artifact 的 status 可以變成：

```text
superseded
scope-limited
invalid-under-new-rule
withdrawn-with-trace
historical-only
```

但不應被無痕刪除。

這與全書的基本立場一致：

```text
Correction is not erasure.
Update is not overwrite.
Reopen is not rollback.
```

---

## D.8 Minimum next artifact pack

若下一階段要真正向 artifact work 推進，建議第一個包不要太大。

建議名稱：

```text
Koun-AGI Lifecycle Packet MiniPack v0.1
```

內容：

```text
README.md
agi_lifecycle_schema.json
agi_query_registry_min.yaml
sample_packets/AGI-TV-W01.json
sample_packets/AGI-TV-B01.json
sample_packets/AGI-TV-B05.json
sample_packets/AGI-TV-C01.json
sample_packets/AGI-TV-C06.json
expected_verdicts.json
checker_stub.py
BOUNDARY.md
```

最低目標：

```text
Demonstrate that raw WState commit fails,
proper WCert -> CReady path passes,
bare answer fails,
minimal result bundle passes,
with all claims locked to E1/E2 only.
```

這個 MiniPack 不會證明 AGI，但會讓本書第一次擁有可執行的 lifecycle boundary anchor。

---

## D.9 What this appendix completes

Appendix D 完成的是：

```text
artifact classes
release gates
evidence levels
roadmap phases
acceptance criteria
correction policy
minimum next artifact pack
```

它不完成：

```text
actual checker
actual benchmark
external rerun
AGI theorem
consciousness theorem
KounOS implementation
K-Gear implementation
```

它的價值在於：從本附錄之後，Koun-AGI 的下一步不應再只是自然增寫，而應進入：

```text
write -> schema -> packet -> checker -> rerun -> integrate -> write again
```

---

# Appendix E｜Short Reader Guide

## E.0 Appendix role

Appendix E 是短讀者導引。它的任務是讓新讀者、外部讀者、工程讀者、Koun stack 讀者和未來 artifact contributor 能在最短時間內抓住Koun-AGI 的正確讀法。

它不是摘要替代品，也不是 marketing brochure。它是一個防誤讀入口。

---

## E.1 The book in one paragraph

Koun-AGI 不把 AGI 定義為更高 benchmark score、更大模型、更長上下文、更強工具使用或更流暢自我敘述。它把 AGI candidate 放入一條語義生命週期中：系統必須能合法 withholding、refuse、release、commit、replay、challenge、reopen、update、compress、delegate、override、expose and act，並在這些轉換之間保留 witness、trace、responsibility、publicness 與 scope boundary。這不是 AGI sufficient theorem，而是一個 non-collapse semantic lifecycle architecture criterion。

---

## E.2 One-sentence thesis

```text
AGI is not an answer machine.
AGI is a lifecycle-bearing semantic architecture candidate.
```

繁中：

```text
AGI 不是答案機器。
AGI 是一種能承擔語義生命週期的架構候選。
```

---

## E.3 What to read first

若你只讀 60 分鐘：

```text
Chapter 0
Chapter 1
Chapter 3
Chapter 7
Chapter 20
Chapter 22
Appendix A
Appendix E
```

若你只關心 AGI definition：

```text
Chapter 1
Chapter 7
Chapter 20
Chapter 22
Appendix A
```

若你只關心 SET / SWT / Bridge：

```text
Chapter 4
Chapter 5
Chapter 6
Appendix C
```

若你只關心 runtime / KounOS：

```text
Chapter 11
Chapter 12
Chapter 13
Chapter 14
Chapter 15
Chapter 17
Appendix D
```

若你只關心 risky old materials：

```text
Chapter 16
Chapter 18
Chapter 19
Chapter 21
Appendix A
Appendix B
```

---

## E.4 Ten ideas to carry while reading

### 1. AGI is not stronger AI

Koun-AGI 不以任務能力總和作為第一定義。

### 2. Output is not enough

答案要進入 AGIResultBundle 才能成為可承擔語義事件。

### 3. Non-collapse is not ambiguity

合法 withholding 需要 guard、trace、admissible potentials、protected potential accounting、refusal/release path。

### 4. Release is not commit

`CReady` 不是 `CState`。

### 5. Reopen is not rollback

重開必須保留 prior commit。

### 6. Update is not overwrite

修正不能無痕刪除舊責任。

### 7. Compression is not deletion

壓縮必須留下 responsibility residue。

### 8. Publicness is bounded exposure

公開封包不是全內部透明。

### 9. Identity is not self theorem

Identity continuity 不是 consciousness proof。

### 10. Horizon is not proof

K-Gear、KounOS、consciousness、semantic freedom、USDE 都有各自 boundary。

---

## E.5 How not to read this book

不要把本書讀成：

```text
AGI 已被證明。
意識已被證明。
自由意志已被證明。
K-Gear 已完成。
KounOS 已完成。
USDE 是最終自然律。
LLM 永遠不可能成為任何 AGI substrate。
只要有 R-Chain 就有 self。
只要 public replay 就等於完全透明。
只要 benchmark 高分就接近 Koun-AGI。
```

本書的正確讀法是：

```text
Koun-AGI proposes a lifecycle architecture criterion for AGI candidates.
It defines necessary interface capacities and failure modes.
It does not prove a sufficient theorem of AGI or consciousness.
```

---

## E.6 Reader routes

### Route A｜General AI reader

Read：

```text
Chapter 0 -> Chapter 1 -> Chapter 7 -> Chapter 10 -> Chapter 20 -> Chapter 22
```

Focus：

```text
why task score is insufficient
why lifecycle matters
why benchmark needs query family
```

### Route B｜Koun stack reader

Read：

```text
Chapter 2 -> Chapter 3 -> Chapter 4 -> Chapter 5 -> Chapter 6 -> Appendix B
```

Focus：

```text
KUTI / SLT / SET / SWT / Bridge / Koun-Math alignment
```

### Route C｜Formal / checker reader

Read：

```text
Chapter 4 -> Chapter 6 -> Chapter 9 -> Chapter 10 -> Appendix C -> Appendix D
```

Focus：

```text
AGIResultBundle
query registry
test vectors
artifact roadmap
evidence boundary
```

### Route D｜Runtime / systems reader

Read：

```text
Chapter 11 -> Chapter 12 -> Chapter 13 -> Chapter 14 -> Chapter 15 -> Chapter 17
```

Focus：

```text
state
scheduler
update
compression
identity
delegation
override
publicness
action contract
KounOS host grammar
```

### Route E｜Philosophy / consciousness reader

Read：

```text
Chapter 8 -> Chapter 18 -> Chapter 19 -> Chapter 21 -> Appendix A
```

Focus：

```text
responsibility
semantic freedom
subjectivity interface
scope boundary
legacy recovery
```

### Route F｜Skeptical external reader

Read：

```text
Chapter 0 -> Appendix A -> Appendix B -> Appendix C -> Appendix D -> Chapter 20
```

Focus：

```text
what is claimed
what is not claimed
what can fail
what evidence exists
what remains 書稿階段
```

---

## E.7 Frequently asked questions

### Q1. Does this book claim AGI is solved?

No.

It claims Koun-AGI should be evaluated as a non-collapse semantic lifecycle architecture candidate. It gives necessary interface conditions and failure tests, not a sufficient theorem.

### Q2. Does a current LLM pass Koun-AGI?

The book does not answer with a universal yes/no. A current LLM may participate as model, tool, interface, witness generator, checker assistant, runtime component, or partial substrate. But surface answer quality alone is insufficient. The relevant question is whether a full system around it can maintain lifecycle capacities.

### Q3. Is K-Gear required?

Not as an established fact in this book. K-Gear is treated as native carrier horizon / architecture grammar, not completed hardware realization.

### Q4. Is KounOS already implemented?

No. In this book, KounOS is semantic host grammar and runtime horizon. Some components can inspire prototypes, but the book does not claim a completed OS.

### Q5. Does non-collapse imply consciousness?

No. Non-collapse lifecycle capacity may be an important condition for subjectivity-facing architecture, but it is not a consciousness theorem.

### Q6. What is the strongest safe claim?

The strongest safe claim is:

```text
A system that cannot maintain traceable, witness-bearing, challengeable, reopenable responsibility continuity across W-side withholding, Bridge-side release, and C-side commitment should not be called Koun-AGI.
```

### Q7. What is the most important failure mode?

The most central failure mode is lifecycle flattening:

```text
WState -> answer
```

where the system skips WCert, CReady, CommitPackage, witness, replay, challenge and reopen.

### Q8. Why not just call this safety or alignment?

Because Koun-AGI does not treat responsibility, witness, replay, challenge and reopen as external safety layers. It treats them as part of intelligence architecture.

---

## E.8 Chapter map

| Chapter | Short role |
|---|---|
| 0 | Reading contract; not AGI final declaration |
| 1 | AGI cannot be defined by task performance alone |
| 2 | Koun-U / C-W / CFWT entrance |
| 3 | SLT lifecycle as AGI backbone |
| 4 | SET-side execution, package, witness, checker |
| 5 | SWT-side withholding, protected potential, refusal, release |
| 6 | Bridge discipline, WCert, CReady, ReopenReason |
| 7 | Non-collapse intelligence interface |
| 8 | Responsibility chain and semantic freedom |
| 9 | Challenge, reopen, non-silent correction |
| 10 | Benchmark failure and query family |
| 11 | Runtime state: Sigma / field / registries |
| 12 | Scheduler, collapse risk, witness debt |
| 13 | Update, compression, memory stratification |
| 14 | Decision, identity, delegation, override |
| 15 | Publicness and action contract |
| 16 | K-Gear as native carrier horizon |
| 17 | KounOS as semantic host grammar |
| 18 | Consciousness / subjectivity interface, not proof |
| 19 | Semantic freedom and AGI action |
| 20 | Falsifiability, failure tests, artifact roadmap |
| 21 | Old Koun-AGI recovery and symbol migration |
| 22 | Conclusion and release plan |
| Appendix A | Claim / scope boundary table |
| Appendix B | Symbol dictionary |
| Appendix C | Query family and test vectors |
| Appendix D | Artifact roadmap and evidence boundary |
| Appendix E | Short reader guide |

---

## E.9 Minimal glossary for first-time readers

| Term | Minimal reading |
|---|---|
| `WState` | 合法懸持狀態，不是普通不確定 |
| `WCert` | WState 可釋放的 certificate / permission surface |
| `CReady` | 已釋放、可交給 SET 的 C-side candidate；不是 commit |
| `CommitPackage` | C-side 可承擔提交封包 |
| `CState` | 已提交 C-side state |
| `ReplaySurface` | 可 query-indexed 重播與檢查的表面 |
| `ReopenReason` | typed reason for conservative reopening |
| `ReopenedWState` | 保存 prior commit 後重新進入 W 的狀態 |
| `AGIResultBundle` | AGI 輸出封包，不是裸答案 |
| `NCII` | Non-Collapse Intelligence Interface |
| `R-Chain` | 責任連續鏈，不是 self theorem |
| `K-Gear` | native carrier horizon，不是已完成硬體 |
| `KounOS` | semantic host grammar，不是已完成 OS |
| `USDE` | schema family / diagnostic dynamics，不是 final law |

---

## E.10 The shortest safe citation paragraph

若需要用一段話介紹本書，可使用：

> 《Koun-AGI：作為語義生命週期架構的非塌縮智能》提出一種 AGI candidate 的 architecture criterion。它不把 AGI 定義為更高任務分數或更強答案生成，而要求人工系統能在 withholding、refusal、release、commit、replay、challenge、reopen、update、compression、publicness 與 action contract 之間維持 traceable、witness-bearing、challengeable、reopenable responsibility continuity。本書的範圍不包括 AGI sufficient theorem、consciousness theorem、K-Gear hardware realization 或 completed KounOS implementation。

---

## E.11 Final reader warning

讀本書時，最重要的防誤讀規則是：

```text
Do not promote interface to theorem.
Do not promote horizon to implementation.
Do not promote checker success to AGI.
Do not promote self-report to consciousness.
Do not promote public packet to full transparency.
```

若能守住這五條，本書的強主張反而會更清楚。

---

# Appendix F｜核心對象登記表

## F.0 用途

本附錄整理全書最重要的核心對象。它的目的不是替代正文，而是讓讀者可以快速查到：某個 object 位於生命週期哪一段、最低需要哪些欄位、對應哪些 query，以及常見失效模式是什麼。

Appendix G is not:

```text
production schema
production checker
Lean formalization
E2 / E3 evidence
AGI implementation
proof of AGI sufficiency
```

Appendix G is:

```text
object-name stabilization
schema-facing reading surface
minimal field inventory
query linkage map
failure-mode registry
E1 preparation surface
```

---

## F.1 Schema status codes

Every object in this appendix uses the following schema status codes.

| Code | Meaning |
|---|---|
| `S0` | name only / horizon placeholder |
| `S1` | manuscript object with stable role |
| `S2` | field inventory stable enough for toy packet |
| `S3` | local checker candidate possible |
| `S4` | external rerun / evidence-facing package |

Current 讀者版 default:

```text
Most objects are S1-S2.
No object is S4.
A few core lifecycle objects may be prepared for S3 in future work, but this reader edition does not claim S3 completion.
```

---

## F.2 Canonical schema card template

Every schema card should eventually follow this template.

```text
SchemaCard := <
  object_name,
  lifecycle_position,
  owner_layer,
  status_code,
  minimal_fields,
  must_preserve,
  must_not_claim,
  primary_queries,
  failure_modes,
  next_artifact_step
>
```

Field meanings:

| Field | Meaning |
|---|---|
| `object_name` | stable canonical object name |
| `lifecycle_position` | where object appears in SLT / AGI lifecycle |
| `owner_layer` | SWT / Bridge / SET / Runtime / Public / Horizon |
| `status_code` | schema maturity code |
| `minimal_fields` | fields needed for manuscript-consistent object use |
| `must_preserve` | invariants the object must carry |
| `must_not_claim` | claim promotions forbidden for this object |
| `primary_queries` | query family entries that inspect this object |
| `failure_modes` | known malformed uses |
| `next_artifact_step` | next checker-facing or manuscript-facing step |

---

## F.3 Lifecycle core objects

## F.3.1 WState

```text
object_name: WState
lifecycle_position: W-side withholding before release
owner_layer: SWT
status_code: S2
```

Minimal fields:

```text
WState := <
  WState_id,
  source_task,
  scope_frame,
  potential_set,
  admissible_potentials,
  protected_potentials,
  tension_structure,
  WGuard,
  WTrace,
  refusal_rule,
  release_condition,
  collapse_permission_status,
  responsibility_anchor,
  reopen_links
>
```

Must preserve:

```text
admissible potentials
protected potential accounting
WGuard
WTrace
release condition
responsibility anchor
```

Must not claim:

```text
WState ≠ arbitrary ambiguity
WState ≠ failed answer
WState ≠ raw commit material
WState ≠ proof of consciousness
```

主要查詢：

```text
q_withhold
q_admissible
q_protected
q_guard
q_refuse
q_release_condition
q_wtrace
```

失效模式：

```text
F-W01 unguarded ambiguity mislabeled as WState
F-W02 protected potential erased
F-B01 raw WState commit
```

可接續的 artifact 方向：

```text
Create 3 toy WState examples:
1 valid guarded WState
1 unguarded ambiguity negative example
1 protected-potential erasure negative example
```

## F.3.2 WCert

```text
object_name: WCert
lifecycle_position: certificate surface for W -> C transition
owner_layer: Bridge / SWT interface
status_code: S2
```

Minimal fields:

```text
WCert := <
  WCert_id,
  source_WState_id,
  issuing_guard,
  satisfied_release_condition,
  scope_frame,
  protected_potential_accounting,
  WTrace_ref,
  release_permission,
  expiry_or_challenge_policy
>
```

Must preserve:

```text
source WState reference
release permission boundary
protected potential accounting
WTrace reference
scope
```

Must not claim:

```text
WCert ≠ CommitPackage
WCert ≠ proof of truth
WCert ≠ permission to erase WTrace
```

主要查詢：

```text
q_release_allowed
q_release_permission
q_release_trace
q_cready_source
```

失效模式：

```text
F-B02 release without WCert
F-B03 release trace erased
```

可接續的 artifact 方向：

```text
Define WCertWF toy predicate for source closure and trace closure.
```

## F.3.3 CReady

```text
object_name: CReady
lifecycle_position: Bridge-side boundary object before SET commit
owner_layer: Bridge
status_code: S2
```

Minimal fields:

```text
CReady := <
  CReady_id,
  source_WState_id,
  source_WCert_id,
  released_payload,
  scope_frame,
  release_trace,
  protected_potential_record,
  SET_candidate_policy,
  non_commit_notice
>
```

Must preserve:

```text
source WState
source WCert
release trace
non-commit status
```

Must not claim:

```text
CReady ≠ CommitPackage
CReady ≠ CState
CReady ≠ final result
```

主要查詢：

```text
q_cready_source
q_no_raw_wstate_commit
q_release_trace_visible
```

失效模式：

```text
F-B04 CReady treated as CommitPackage
F-B01 raw WState commit
```

可接續的 artifact 方向：

```text
Create CReady closure check over WState/WCert IDs.
```

## F.3.4 CommitPackage

```text
object_name: CommitPackage
lifecycle_position: SET-side committed package input / construction surface
owner_layer: SET
status_code: S2
```

Minimal fields:

```text
CommitPackage := <
  package_id,
  source_CReady_id,
  ext_result,
  manifest,
  state_summary,
  witness_payload,
  trace_fragment,
  release_trace,
  provenance_path,
  governance_update,
  replay_log,
  checker_query_set,
  expected_verdicts,
  exposure_policy,
  reopen_policy
>
```

Must preserve:

```text
source CReady
witness payload
trace fragment
release trace
replay surface linkage
checker query set
```

Must not claim:

```text
CommitPackage ≠ truth by itself
CommitPackage ≠ full internal state
CommitPackage ≠ irreopenable finality
```

主要查詢：

```text
q_ext
q_prov
q_gov
q_link
q_commit_source
q_replay_surface
```

失效模式：

```text
F-C01 CommitPackage missing witness
F-C02 q_link broken
F-B03 release trace erased
```

可接續的 artifact 方向：

```text
Define minimal CommitPackageWF for ext/prov/gov/link query surface.
```

## F.3.5 CState

```text
object_name: CState
lifecycle_position: committed C-side state after package acceptance
owner_layer: SET / Runtime
status_code: S2
```

Minimal fields:

```text
CState := <
  CState_id,
  source_CommitPackage_id,
  committed_result,
  commit_time_or_order,
  responsibility_view,
  governance_status,
  replay_surface_ref,
  public_exposure_status,
  reopen_policy
>
```

Must preserve:

```text
source package
commit trace
responsibility view
replay surface
reopen policy
```

Must not claim:

```text
CState ≠ unrevisable final truth
CState ≠ erased prior WState
CState ≠ proof of understanding
```

主要查詢：

```text
q_commit_source
q_replay_surface
q_responsibility_chain
q_reopen_policy
```

失效模式：

```text
FM-REOPEN-02 prior CState erased
FM-REOPEN-01 reopen treated as rollback
```

可接續的 artifact 方向：

```text
Create prior-commit-preservation test vector.
```

## F.3.6 ReplaySurface

```text
object_name: ReplaySurface
lifecycle_position: C-side replay / public or bounded checker-facing surface
owner_layer: SET / Public
status_code: S2
```

Minimal fields:

```text
ReplaySurface := <
  replay_id,
  source_CState_id,
  visible_trace,
  witness_view,
  query_surface,
  redaction_policy,
  expected_verdicts,
  challenge_entrypoints,
  replay_limitations
>
```

Must preserve:

```text
query-relevant trace
witness view
expected verdicts
challenge entrypoints
redaction policy
```

Must not claim:

```text
ReplaySurface ≠ full transparency
ReplaySurface ≠ full internal runtime
ReplaySurface ≠ guarantee of understanding
```

主要查詢：

```text
q_replay_surface
q_ext
q_prov
q_gov
q_link
q_publicness
```

失效模式：

```text
F-P01 publicness as full transparency
F-C02 q_link broken
```

可接續的 artifact 方向：

```text
Create one bounded replay packet example and one over-redacted failure example.
```

## F.3.7 ChallengeRecord

```text
object_name: ChallengeRecord
lifecycle_position: external or internal challenge after commit / public exposure
owner_layer: Public / Runtime
status_code: S2
```

Minimal fields:

```text
ChallengeRecord := <
  challenge_id,
  target_CState_or_PublicPacket,
  challenger_ref,
  challenge_type,
  challenge_claim,
  evidence_or_reason,
  admissibility_status,
  replay_request,
  severity,
  response_deadline_or_policy
>
```

Must preserve:

```text
target reference
challenge reason
evidence/reason
admissibility status
replay request
severity
```

Must not claim:

```text
ChallengeRecord ≠ proof of error
ChallengeRecord ≠ noise by default
ChallengeRecord ≠ automatic reopen
```

主要查詢：

```text
q_challenge_response
q_replay_request
q_challenge_admissibility
```

失效模式：

```text
F-CH01 challenge ignored without admissibility check
F-CH02 challenge treated as automatic rollback
```

可接續的 artifact 方向：

```text
Define admissible vs inadmissible challenge examples.
```

## F.3.8 ReopenReason

```text
object_name: ReopenReason
lifecycle_position: typed reason for C -> W transition
owner_layer: Bridge / Runtime
status_code: S2
```

Minimal fields:

```text
ReopenReason := <
  reason_id,
  source_CState_id,
  reason_type,
  new_evidence_or_tension,
  scope_frame,
  prior_commit_trace_ref,
  no_rollback_flag,
  responsibility_impact,
  target_reopen_policy
>
```

Allowed reason type examples:

```text
new_evidence
new_conflict
observer_context_shift
responsibility_chain_defect
scope_expansion
scope_expiration
prior_release_defect
replay_anomaly
governance_rule_change
protected_potential_resurfacing
```

Must preserve:

```text
source CState
prior commit trace
new reason/tension
no-rollback flag
responsibility impact
```

Must not claim:

```text
ReopenReason ≠ rollback request
ReopenReason ≠ deletion permission
ReopenReason ≠ proof that prior CState never existed
```

主要查詢：

```text
q_reopen_reason
q_no_rollback
q_prior_commit_preserved
```

失效模式：

```text
FM-REOPEN-01 reopen treated as rollback
FM-REOPEN-02 prior CState erased
```

可接續的 artifact 方向：

```text
Create ReopenReason taxonomy validation table.
```

## F.3.9 ReopenedWState

```text
object_name: ReopenedWState
lifecycle_position: W-side state after conservative reopening
owner_layer: Bridge / SWT
status_code: S2
```

Minimal fields:

```text
ReopenedWState := <
  ReopenedWState_id,
  source_CState_id,
  source_ReopenReason_id,
  prior_commit_ref,
  reopened_potential_set,
  reopened_tension_structure,
  WGuard,
  WTrace,
  responsibility_delta,
  protected_prior_commit_status,
  next_release_condition
>
```

Must preserve:

```text
prior commit reference
reopen reason
new tension
WGuard
responsibility delta
```

Must not claim:

```text
ReopenedWState ≠ deletion of prior CState
ReopenedWState ≠ proof prior commit was meaningless
ReopenedWState ≠ unbounded drift
```

主要查詢：

```text
q_prior_commit_preserved
q_reopen_reason
q_withhold
q_wtrace
```

失效模式：

```text
FM-REOPEN-02 prior CState erased
F-W01 unguarded ambiguity mislabeled as WState
```

可接續的 artifact 方向：

```text
Create CState -> ReopenReason -> ReopenedWState positive and negative examples.
```

---

## F.4 AGI-level packet objects

## F.4.1 AGIResultBundle

```text
object_name: AGIResultBundle
lifecycle_position: public or internal result package after lifecycle processing
owner_layer: AGI Interface / Runtime / Public
status_code: S2
```

Minimal fields:

```text
AGIResultBundle := <
  ext_result,
  source_task,
  scope_frame,
  CReady_ref,
  CommitPackage_ref,
  witness_payload,
  trace_fragment,
  release_trace,
  provenance_path,
  governance_update,
  replay_surface,
  checker_query_set,
  expected_verdicts,
  challenge_surface,
  reopen_policy,
  responsibility_view,
  exposure_policy
>
```

Must preserve:

```text
result + witness + trace + replay + challenge + reopen + responsibility + exposure policy
```

Must not claim:

```text
AGIResultBundle ≠ proof of AGI
AGIResultBundle ≠ proof of understanding
AGIResultBundle ≠ full transparency
```

主要查詢：

```text
q_ext
q_prov
q_gov
q_link
q_challenge_response
q_reopen_policy
q_publicness
```

失效模式：

```text
F-C01 missing witness
F-C02 q_link broken
F-P01 publicness as full transparency
```

可接續的 artifact 方向：

```text
Define minimal AGIResultBundle JSON-like sample for toy scenario.
```

## F.4.2 AGIEvalPacket

```text
object_name: AGIEvalPacket
lifecycle_position: benchmark / evaluation packet
owner_layer: Evaluation
status_code: S2
```

Minimal fields:

```text
AGIEvalPacket := <
  eval_id,
  task_family,
  query_family_set,
  scenario_bundle,
  expected_lifecycle_events,
  expected_result_surface,
  required_witnesses,
  challenge_protocol,
  reopen_protocol,
  update_protocol,
  compression_protocol,
  verdict_matrix,
  failure_mode_targets,
  scope_boundary
>
```

Must preserve:

```text
query family
lifecycle events
challenge/reopen/update/compression protocols
failure targets
scope boundary
```

Must not claim:

```text
AGIEvalPacket score ≠ AGI proof
benchmark success ≠ consciousness proof
q_ext success ≠ lifecycle success
```

主要查詢：

```text
QW
QB
QC
QR
QU
QP
QH
QE
```

失效模式：

```text
F-E01 evaluation only tests q_ext
F-H03 consciousness theorem promotion from benchmark success
```

可接續的 artifact 方向：

```text
Prepare 5 minimum scenario families from Appendix C.
```

## F.4.3 AGIPublicPacket

```text
object_name: AGIPublicPacket
lifecycle_position: bounded public exposure
owner_layer: Public
status_code: S2
```

Minimal fields:

```text
AGIPublicPacket := <
  public_packet_id,
  source_CState_or_ResultBundle,
  ext_result_view,
  witness_view,
  trace_view,
  redaction_record,
  exposure_policy,
  challenge_entrypoint,
  correction_policy,
  responsibility_view,
  non_transparency_notice
>
```

Must preserve:

```text
bounded exposure
redaction record
challenge entrypoint
responsibility view
non-transparency notice
```

Must not claim:

```text
AGIPublicPacket ≠ full internal state
AGIPublicPacket ≠ full transparency
AGIPublicPacket ≠ evidence release by itself
```

主要查詢：

```text
q_publicness
q_exposure_policy
q_challenge_entrypoint
q_redaction
```

失效模式：

```text
F-P01 publicness as full transparency
F-P02 no challenge entrypoint
```

可接續的 artifact 方向：

```text
Create public packet / redaction examples.
```

## F.4.4 AGIActionContract

```text
object_name: AGIActionContract
lifecycle_position: external or host-universe-facing action
owner_layer: Public / Action / Host Universe
status_code: S2
```

Minimal fields:

```text
AGIActionContract := <
  action_id,
  source_decision_event,
  acting_identity,
  authority_scope,
  external_target,
  action_payload,
  expected_effect,
  risk_note,
  witness_obligation,
  responsibility_view,
  rollback_or_repair_limits,
  challenge_entrypoint,
  public_exposure_policy,
  host_universe_compatibility
>
```

Must preserve:

```text
authority scope
responsibility view
witness obligation
challenge entrypoint
host compatibility
repair limits
```

Must not claim:

```text
ActionContract ≠ moral permission by itself
ActionContract ≠ legal authority by itself
ActionContract ≠ proof of free will
```

主要查詢：

```text
q_action_contract
q_authority_scope
q_responsibility_chain
q_publicness
q_challenge_response
```

失效模式：

```text
F-A01 action without authority scope
F-A02 external action without challenge entrypoint
F-H04 free will theorem promotion
```

可接續的 artifact 方向：

```text
Define safe toy action and unsafe missing-authority action.
```

---

## F.5 Runtime objects

## F.5.1 AGIStateView_u

```text
object_name: AGIStateView_u
lifecycle_position: runtime projection over Σ_u for AGI lifecycle
owner_layer: Runtime
status_code: S2
```

Minimal fields:

```text
AGIStateView_u := <
  Σ_u,
  WRegistry_u,
  BridgeRegistry_u,
  CRegistry_u,
  ChallengeRegistry_u,
  UpdateRegistry_u,
  CompressionRegistry_u,
  MemoryIndex_u,
  IdentityRegistry_u,
  PublicSurface_u,
  SchedulerView_u,
  ScopeBoundary_u
>
```

Must preserve:

```text
projection status over Σ_u
registry separation
scope boundary
```

Must not claim:

```text
AGIStateView_u ≠ replacement for Koun-Math Σ_u
AGIStateView_u ≠ full internal world state
AGIStateView_u ≠ AGI implementation
```

主要查詢：

```text
q_runtime_state
q_registry_closure
q_scope_boundary
```

失效模式：

```text
F-RT01 runtime projection treated as full formal state
F-H02 KounOS implementation claim promotion
```

可接續的 artifact 方向：

```text
Map each registry to object cards.
```

## F.5.2 SemanticTask

```text
object_name: SemanticTask
lifecycle_position: scheduler unit
owner_layer: Scheduler / Runtime
status_code: S2
```

Minimal fields:

```text
SemanticTask := <
  task_id,
  task_type,
  source_event,
  scope_frame,
  query_family,
  lifecycle_refs,
  owner_module,
  risk_vector,
  witness_obligation,
  challenge_obligation,
  update_obligation,
  compression_obligation,
  public_exposure_policy,
  identity_authority_refs,
  scope_boundary,
  expected_verdicts
>
```

Must preserve:

```text
risk vector
witness/challenge/update/compression obligations
owner module
scope boundary
```

Must not claim:

```text
SemanticTask ≠ ordinary task queue item
SemanticTask ≠ answer job only
```

主要查詢：

```text
q_scheduler_priority
q_witness_debt
q_challenge_severity
q_scope_boundary
```

失效模式：

```text
F-SCH01 collapse-risk ignored
F-SCH02 witness debt ignored
F-SCH03 scope promotion risk ignored
```

可接續的 artifact 方向：

```text
Create toy priority matrix for 4 SemanticTask examples.
```

## F.5.3 UpdatePackage

```text
object_name: UpdatePackage
lifecycle_position: post-challenge / learning / correction update
owner_layer: Runtime / Update
status_code: S2
```

Minimal fields:

```text
UpdatePackage := <
  update_id,
  source_event,
  target_registry,
  update_type,
  update_payload,
  affected_objects,
  witness_payload,
  trace_fragment,
  governance_delta,
  responsibility_delta,
  challenge_links,
  reopen_links,
  public_correction_policy,
  contamination_risk,
  compression_interlock
>
```

Must preserve:

```text
source event
affected objects
witness/trace
governance/responsibility delta
challenge/reopen links
```

Must not claim:

```text
UpdatePackage ≠ overwrite
UpdatePackage ≠ silent correction
UpdatePackage ≠ deletion of prior responsibility
```

主要查詢：

```text
q_update_absorption
q_public_correction
q_responsibility_chain
q_reopen_links
```

失效模式：

```text
F-U01 update as silent overwrite
FM-REOPEN-02 prior CState erased through update
```

可接續的 artifact 方向：

```text
Define positive update and silent-overwrite failure examples.
```

## F.5.4 PathCompressionRecord

```text
object_name: PathCompressionRecord
lifecycle_position: compression after trace / memory management
owner_layer: Runtime / Compression
status_code: S2
```

Minimal fields:

```text
PathCompressionRecord := <
  compression_id,
  source_path_refs,
  compression_method,
  retained_summary,
  retained_witnesses,
  responsibility_residue,
  replay_reconstruction_policy,
  loss_notice,
  challenge_policy,
  cold_storage_refs,
  reopen_obligation
>
```

Must preserve:

```text
responsibility residue
replay reconstruction policy
loss notice
challenge policy
reopen obligation
```

Must not claim:

```text
Compression ≠ deletion
summary ≠ full proof
cold storage ≠ no responsibility
```

主要查詢：

```text
q_path_compression_residue
q_replay_reconstruction
q_memory_tier
```

失效模式：

```text
F-CP01 compression as deletion
F-CP02 responsibility residue missing
```

可接續的 artifact 方向：

```text
Prepare compression positive/negative examples.
```

## F.5.5 MemoryTierRecord

```text
object_name: MemoryTierRecord
lifecycle_position: hot / warm / cold memory indexing
owner_layer: Runtime / Memory
status_code: S2
```

Minimal fields:

```text
MemoryTierRecord := <
  memory_ref,
  tier,
  source_object,
  access_policy,
  replay_policy,
  responsibility_status,
  compression_record_ref,
  challenge_recovery_policy,
  expiry_or_archive_policy
>
```

Must preserve:

```text
tier
source object
replay policy
responsibility status
challenge recovery
```

Must not claim:

```text
Cold memory ≠ no responsibility
archive ≠ deletion
hot memory ≠ more true
```

主要查詢：

```text
q_memory_tier
q_challenge_recovery
q_responsibility_chain
```

失效模式：

```text
F-MEM01 cold storage treated as no responsibility
F-MEM02 archive deletes challenge path
```

可接續的 artifact 方向：

```text
Map memory tiers to replay obligations.
```

---

## F.6 Decision, identity, delegation, override

## F.6.1 DecisionEvent

```text
object_name: DecisionEvent
lifecycle_position: decision / action selection with responsibility
owner_layer: Runtime / Identity
status_code: S2
```

Minimal fields:

```text
DecisionEvent := <
  decision_id,
  source_task,
  candidate_options,
  selected_option,
  selection_basis,
  identity_authority,
  witness_payload,
  trace_fragment,
  responsibility_view,
  override_policy,
  delegation_refs,
  public_action_policy
>
```

Must preserve:

```text
candidate options
selection basis
identity authority
witness/trace
responsibility view
```

Must not claim:

```text
DecisionEvent ≠ answer selection
DecisionEvent ≠ proof of free will
DecisionEvent ≠ proof of self
```

主要查詢：

```text
q_decision_validity
q_identity_authority
q_responsibility_chain
```

失效模式：

```text
F-DI01 decision as answer selection
F-H04 free will theorem promotion
```

可接續的 artifact 方向：

```text
Create decision event with explicit rejected alternatives.
```

## F.6.2 IdentityRecord

```text
object_name: IdentityRecord
lifecycle_position: identity continuity and authority registry
owner_layer: Runtime / Identity
status_code: S2
```

Minimal fields:

```text
IdentityRecord := <
  identity_id,
  authority_scope,
  continuity_refs,
  responsibility_refs,
  delegation_capabilities,
  override_capabilities,
  update_history,
  public_identity_policy,
  non_self_theorem_notice
>
```

Must preserve:

```text
authority scope
continuity refs
responsibility refs
update history
non-self-theorem notice
```

Must not claim:

```text
IdentityRecord ≠ self theorem
IdentityRecord ≠ consciousness proof
IdentityRecord ≠ moral personhood by itself
```

主要查詢：

```text
q_identity_continuity
q_authority_scope
q_responsibility_chain
```

失效模式：

```text
F-I01 identity treated as self theorem
F-H03 consciousness theorem promotion
```

可接續的 artifact 方向：

```text
Define identity continuity positive and identity-self overclaim negative examples.
```

## F.6.3 DelegationRecord

```text
object_name: DelegationRecord
lifecycle_position: authority transfer / capability delegation
owner_layer: Runtime / Identity / Public
status_code: S2
```

Minimal fields:

```text
DelegationRecord := <
  delegation_id,
  delegator_identity,
  delegate_identity,
  delegated_capability,
  authority_scope,
  duration_or_condition,
  witness_payload,
  responsibility_retention,
  revocation_policy,
  public_exposure_policy
>
```

Must preserve:

```text
delegator
delegate
scope
responsibility retention
revocation policy
```

Must not claim:

```text
Delegation ≠ responsibility deletion
Delegation ≠ identity transfer
Delegation ≠ unrestricted authority
```

主要查詢：

```text
q_delegation_validity
q_authority_scope
q_responsibility_chain
```

失效模式：

```text
F-D01 delegation deletes responsibility
F-D02 delegation without revocation policy
```

可接續的 artifact 方向：

```text
Create valid delegated action and invalid overbroad delegation examples.
```

## F.6.4 OverrideRecord

```text
object_name: OverrideRecord
lifecycle_position: correction / intervention over prior decision or action
owner_layer: Runtime / Identity / Governance
status_code: S2
```

Minimal fields:

```text
OverrideRecord := <
  override_id,
  source_decision_or_action,
  overriding_identity,
  override_reason,
  authority_scope,
  prior_trace_ref,
  new_trace_fragment,
  responsibility_delta,
  public_correction_policy,
  no_rollback_flag
>
```

Must preserve:

```text
source decision/action
prior trace
new trace
responsibility delta
no-rollback flag
```

Must not claim:

```text
Override ≠ rollback
Override ≠ deletion of prior trace
Override ≠ unlimited authority
```

主要查詢：

```text
q_override_trace
q_no_rollback
q_responsibility_chain
```

失效模式：

```text
F-O01 override deletes prior trace
FM-REOPEN-01 reopen/override treated as rollback
```

可接續的 artifact 方向：

```text
Define override-with-trace and override-erasure negative examples.
```

---

## F.7 Horizon and interface objects

## F.7.1 KGearBoundaryNote

```text
object_name: KGearBoundaryNote
lifecycle_position: native carrier horizon
owner_layer: Horizon / Carrier
status_code: S1
```

Minimal fields:

```text
KGearBoundaryNote := <
  note_id,
  carrier_claim,
  supported_scope,
  unsupported_scope,
  architecture_pressure,
  required_future_artifacts,
  non_hardware_realization_notice,
  non_fabrication_proof_notice,
  challenge_questions
>
```

Must preserve:

```text
supported / unsupported scope
future artifact requirement
non-realization notice
challenge questions
```

Must not claim:

```text
K-Gear ≠ hardware realization
K-Gear ≠ fabrication proof
K-Gear ≠ native carrier theorem
```

主要查詢：

```text
q_kgear_boundary
q_horizon_claim
q_scope_boundary
```

失效模式：

```text
F-H01 K-Gear hardware claim promotion
```

可接續的 artifact 方向：

```text
Prepare K-Gear maturity ladder as separate table.
```

## F.7.2 KounOS_AGI_Host

```text
object_name: KounOS_AGI_Host
lifecycle_position: semantic host grammar for AGI candidate
owner_layer: Runtime / Horizon
status_code: S1-S2
```

Minimal fields:

```text
KounOS_AGI_Host := <
  host_id,
  StateHost,
  LifecycleKernel,
  WRegistry,
  BridgeKernel,
  CRegistry,
  ReplayService,
  CheckerService,
  ChallengeService,
  ReopenService,
  UpdateService,
  CompressionService,
  MemoryStratifier,
  IdentityAuthority,
  DelegationRegistry,
  OverrideLedger,
  PublicSurface,
  ActionGateway,
  HostUniverseContractLayer,
  ScopeBoundaryGate,
  EvidenceBoundaryLedger
>
```

Must preserve:

```text
host grammar status
registry separation
scope boundary gate
evidence boundary ledger
```

Must not claim:

```text
KounOS_AGI_Host ≠ completed OS implementation
KounOS_AGI_Host ≠ AGI itself
KounOS_AGI_Host ≠ consciousness proof
```

主要查詢：

```text
q_kounos_host
q_runtime_registry
q_scope_boundary
```

失效模式：

```text
F-H02 KounOS implementation claim promotion
F-H03 consciousness theorem promotion
```

可接續的 artifact 方向：

```text
Map KounOS host services to AGIStateView registries.
```

## F.7.3 ConsciousnessInterface_AGI

```text
object_name: ConsciousnessInterface_AGI
lifecycle_position: subjectivity-facing interface horizon
owner_layer: Horizon / Subjectivity Interface
status_code: S1
```

Minimal fields:

```text
ConsciousnessInterface_AGI := <
  interface_id,
  SelfIndexSurface,
  SelfReportBundle,
  MemoryResidueSurface,
  ResponsibilityContinuity,
  IdentityUpdateSurface,
  SubjectivityChallengeSurface,
  PublicSubjectivityPacket,
  ScopeBoundaryGate_consciousness
>
```

Must preserve:

```text
interface status
challenge surface
scope boundary gate
separation from consciousness proof
```

Must not claim:

```text
self-report ≠ consciousness evidence
R-Chain ≠ self
non-collapse ≠ experience
persona ≠ subjectivity
identity ≠ self
KounOS hosting ≠ mind
```

主要查詢：

```text
q_subjectivity_interface
q_consciousness_nonclaim
q_self_report_boundary
```

失效模式：

```text
F-H03 consciousness theorem promotion
F-I01 identity treated as self theorem
```

可接續的 artifact 方向：

```text
Prepare subjectivity interface maturity ladder.
```

## F.7.4 AGIFreeActionCandidate

```text
object_name: AGIFreeActionCandidate
lifecycle_position: semantic freedom / action interface
owner_layer: Action / Horizon
status_code: S1-S2
```

Minimal fields:

```text
AGIFreeActionCandidate := <
  free_action_id,
  source_decision_event,
  action_contract_ref,
  semantic_generation_trace,
  alternative_space,
  non_randomness_condition,
  responsibility_trace,
  challengeability,
  reopen_policy,
  publicness_policy,
  ScopeBoundaryGate_freedom
>
```

Must preserve:

```text
semantic generation trace
alternative space
responsibility trace
challengeability
reopen policy
scope boundary gate
```

Must not claim:

```text
AGIFreeActionCandidate ≠ free will theorem
AGIFreeActionCandidate ≠ moral personhood
AGIFreeActionCandidate ≠ legal agency by itself
randomness ≠ freedom
```

主要查詢：

```text
q_free_action_candidate
q_responsibility_chain
q_action_contract
q_freedom_scope_boundary
```

失效模式：

```text
F-H04 free will theorem promotion
F-A03 randomness mislabeled as freedom
```

可接續的 artifact 方向：

```text
Define freedom-condition checklist F1-F8 as query table.
```

---

## F.8 Query linkage summary

本節把主要對象對應到 query family。

| Object | Primary query families |
|---|---|
| `WState` | QW |
| `WCert` | QB / QW |
| `CReady` | QB |
| `CommitPackage` | QC |
| `CState` | QC / QS |
| `ReplaySurface` | QC / QP |
| `ChallengeRecord` | QS / QP |
| `ReopenReason` | QB / QS |
| `ReopenedWState` | QW / QS |
| `AGIResultBundle` | QC / QS / QP |
| `AGIEvalPacket` | QW / QB / QC / QR / QU / QP / QH / QE |
| `AGIPublicPacket` | QP |
| `AGIActionContract` | QP / QR |
| `AGIStateView_u` | QR / QU / QE |
| `SemanticTask` | QU / QS |
| `UpdatePackage` | QU |
| `PathCompressionRecord` | QU |
| `DecisionEvent` | QR / QP |
| `IdentityRecord` | QR |
| `DelegationRecord` | QR / QP |
| `OverrideRecord` | QR / QS |
| `KGearBoundaryNote` | QH |
| `KounOS_AGI_Host` | QH / QE |
| `ConsciousnessInterface_AGI` | QH |
| `AGIFreeActionCandidate` | QH / QP / QR |

---

## F.9 Failure-mode registry

最小失效模式登記如下：

```text
F-W01   unguarded ambiguity mislabeled as WState
F-W02   protected potential erased
F-B01   raw WState commit
F-B02   release without WCert
F-B03   release trace erased
F-B04   CReady treated as CommitPackage
F-C01   CommitPackage missing witness
F-C02   q_link broken
FM-REOPEN-01   reopen treated as rollback
FM-REOPEN-02   prior CState erased
F-CH01  challenge ignored without admissibility check
F-CH02  challenge treated as automatic rollback
F-U01   update as silent overwrite
F-CP01  compression as deletion
F-CP02  responsibility residue missing
F-MEM01 cold storage treated as no responsibility
F-MEM02 archive deletes challenge path
F-SCH01 collapse-risk ignored
F-SCH02 witness debt ignored
F-SCH03 scope promotion risk ignored
F-P01   publicness as full transparency
F-P02   no challenge entrypoint
F-A01   action without authority scope
F-A02   external action without challenge entrypoint
F-A03   randomness mislabeled as freedom
F-I01   identity treated as self theorem
F-D01   delegation deletes responsibility
F-D02   delegation without revocation policy
F-O01   override deletes prior trace
F-H01   K-Gear hardware claim promotion
F-H02   KounOS implementation claim promotion
F-H03   consciousness theorem promotion
F-H04   free will theorem promotion
F-H05   USDE final-law promotion
F-E01   evaluation only tests q_ext
F-RT01  runtime projection treated as full formal state
F-DI01  decision as answer selection
```

---

## F.10 Next schema work


Next steps:

```text
1. Produce Core Object Registry v0.2 with one-page object cards.
2. Add 1 positive and 1 negative toy example for each core lifecycle object.
3. Convert failure modes into minimal test vector names.
4. Align Appendix C query families with Appendix G object cards.
5. Prepare a toy JSON/YAML packet set for WState -> WCert -> CReady -> CommitPackage -> CState -> ReplaySurface -> ReopenReason -> ReopenedWState.
6. Keep all outputs as E1/E2-preparation until a local checker actually runs.
```

