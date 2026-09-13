# 发布快照索引 — 结算窗清单与逐窗判定依据

> English: [`index.md`](index.md)

> 本清单为 `fa/` 下发布快照的窗口级判定凭证。每个结算窗 **恰好一份** 发布快照；判定依据：
> 1. **发布范围**：本发布线**只收录本地时间零点之后**的结算窗，即 `computed_at`（转 UTC）
>    落于休市窗 **UTC 16:00–19:00**（本地 UTC+8 **00:00–03:00**）的**零点后定时结算批 `w2`**；
>    本地零点前的结算批 `w1`（UTC 04:00–07:00，本地 12:00–15:00）**不属本发布线，不予公开**；
> 2. **定时结算输出**：该窗快照在零点后定时结算批（`w2` = UTC 18:30）中有对应输出记录；
> 3. **时间带**：快照元信息 `computed_at`（转 UTC）落在上述休市窗区间内；
> 4. **参数版本**：`param_ver = l2-2.2-exp`；
> 5. **成员一致**：`membership` 块随快照存档。

排除项与理由由发布方内部留档；逐窗对拍与排除凭证**不随本仓发布**。

## 汇总

- 结算窗份数：**13**
- 发布范围：**仅本地零点后的结算窗**（`w2`，UTC 16:00–19:00）
- 发布线下限：**2026-09-01**（更早的窗口不属本发布线）
- 参数版本：`l2-2.2-exp`（全部窗口）
- 时间范围：`2026-09-01T02:33:41+08:00` → `2026-09-13T02:31:50+08:00`（本地时区 UTC+8）
- 对拍（A2）：**全部通过**（逐窗对拍凭证由发布方内部留存，不随本仓发布）
- 字段缺口：无

## 逐窗清单

| # | ts | computed_at（本地） | computed_at（UTC） | 结算批 | 顶级权重 cap/eco | 成员 | 字段缺口 | A2 |
|---|---|---|---|---|---|---|---|---|
| 1 | `20260901_0241` | `2026-09-01T02:33:41+08:00` | `2026-08-31T18:33:41Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 2 | `20260902_0239` | `2026-09-02T02:33:38+08:00` | `2026-09-01T18:33:38Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 3 | `20260903_0239` | `2026-09-03T02:33:44+08:00` | `2026-09-02T18:33:44Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 4 | `20260904_0238` | `2026-09-04T02:33:05+08:00` | `2026-09-03T18:33:05Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 5 | `20260905_0239` | `2026-09-05T02:33:10+08:00` | `2026-09-04T18:33:10Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 6 | `20260906_0241` | `2026-09-06T02:34:34+08:00` | `2026-09-05T18:34:34Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 7 | `20260907_0233` | `2026-09-07T02:31:40+08:00` | `2026-09-06T18:31:40Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 8 | `20260908_0233` | `2026-09-08T02:31:26+08:00` | `2026-09-07T18:31:26Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 9 | `20260909_0233` | `2026-09-09T02:31:35+08:00` | `2026-09-08T18:31:35Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 10 | `20260910_0232` | `2026-09-10T02:31:18+08:00` | `2026-09-09T18:31:18Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 11 | `20260911_0233` | `2026-09-11T02:32:00+08:00` | `2026-09-10T18:32:00Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 12 | `20260912_0233` | `2026-09-12T02:31:26+08:00` | `2026-09-11T18:31:26Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |
| 13 | `20260913_0233` | `2026-09-13T02:31:50+08:00` | `2026-09-12T18:31:50Z` | w2 | 0.6/0.4 | INCLUDED 10 / SHADOW 2 |  | PASS |

## 逐窗判定依据（明细）

### 1. `20260901_0241`

- 源快照：`snapshot_20260901_0241.json`
- `computed_at`：`2026-09-01T02:33:41+08:00` = `2026-08-31T18:33:41Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260901_0241.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260901_0241.json`；展平 CSV `fa/readable/snapshot_20260901_0241.csv`

### 2. `20260902_0239`

- 源快照：`snapshot_20260902_0239.json`
- `computed_at`：`2026-09-02T02:33:38+08:00` = `2026-09-01T18:33:38Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260902_0239.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260902_0239.json`；展平 CSV `fa/readable/snapshot_20260902_0239.csv`

### 3. `20260903_0239`

- 源快照：`snapshot_20260903_0239.json`
- `computed_at`：`2026-09-03T02:33:44+08:00` = `2026-09-02T18:33:44Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260903_0239.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260903_0239.json`；展平 CSV `fa/readable/snapshot_20260903_0239.csv`

### 4. `20260904_0238`

- 源快照：`snapshot_20260904_0238.json`
- `computed_at`：`2026-09-04T02:33:05+08:00` = `2026-09-03T18:33:05Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260904_0238.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260904_0238.json`；展平 CSV `fa/readable/snapshot_20260904_0238.csv`

### 5. `20260905_0239`

- 源快照：`snapshot_20260905_0239.json`
- `computed_at`：`2026-09-05T02:33:10+08:00` = `2026-09-04T18:33:10Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260905_0239.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260905_0239.json`；展平 CSV `fa/readable/snapshot_20260905_0239.csv`

### 6. `20260906_0241`

- 源快照：`snapshot_20260906_0241.json`
- `computed_at`：`2026-09-06T02:34:34+08:00` = `2026-09-05T18:34:34Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260906_0241.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260906_0241.json`；展平 CSV `fa/readable/snapshot_20260906_0241.csv`

### 7. `20260907_0233`

- 源快照：`snapshot_20260907_0233.json`
- `computed_at`：`2026-09-07T02:31:40+08:00` = `2026-09-06T18:31:40Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260907_0233.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260907_0233.json`；展平 CSV `fa/readable/snapshot_20260907_0233.csv`

### 8. `20260908_0233`

- 源快照：`snapshot_20260908_0233.json`
- `computed_at`：`2026-09-08T02:31:26+08:00` = `2026-09-07T18:31:26Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260908_0233.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260908_0233.json`；展平 CSV `fa/readable/snapshot_20260908_0233.csv`

### 9. `20260909_0233`

- 源快照：`snapshot_20260909_0233.json`
- `computed_at`：`2026-09-09T02:31:35+08:00` = `2026-09-08T18:31:35Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260909_0233.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260909_0233.json`；展平 CSV `fa/readable/snapshot_20260909_0233.csv`

### 10. `20260910_0232`

- 源快照：`snapshot_20260910_0232.json`
- `computed_at`：`2026-09-10T02:31:18+08:00` = `2026-09-09T18:31:18Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260910_0232.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260910_0232.json`；展平 CSV `fa/readable/snapshot_20260910_0232.csv`

### 11. `20260911_0233`

- 源快照：`snapshot_20260911_0233.json`
- `computed_at`：`2026-09-11T02:32:00+08:00` = `2026-09-10T18:32:00Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260911_0233.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260911_0233.json`；展平 CSV `fa/readable/snapshot_20260911_0233.csv`

### 12. `20260912_0233`

- 源快照：`snapshot_20260912_0233.json`
- `computed_at`：`2026-09-12T02:31:26+08:00` = `2026-09-11T18:31:26Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260912_0233.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260912_0233.json`；展平 CSV `fa/readable/snapshot_20260912_0233.csv`

### 13. `20260913_0233`

- 源快照：`snapshot_20260913_0233.json`
- `computed_at`：`2026-09-13T02:31:50+08:00` = `2026-09-12T18:31:50Z`（UTC），落于休市窗 UTC 16:00–19:00（本地 00:00–03:00，即**本地零点之后**）
- 结算运行证据：零点后定时结算批（窗口 `w2`）在 `daily_w2.log` 中有 `snapshot_20260913_0233.json` 输出记录
- `param_ver`：`l2-2.2-exp`；顶级权重（`fa_influence.w`）：capability_merged=0.6、ecosystem_merged=0.4
- 成员：`constituent_count=10`、`universe_rev=46`
- A2 对拍：`PASS`（逐窗对拍凭证由发布方内部留存，不随本仓发布）；发布 JSON `fa/publish_snapshot_20260913_0233.json`；展平 CSV `fa/readable/snapshot_20260913_0233.csv`

## 时序长表

`fa/readable/fa_series.csv` 按窗口 `ts` 升序拼接全部窗口，行 =（`ts`, `org`），
列 = `ts, org, membership, capability_merged, ecosystem_merged, fa_raw, fa_adj`；
其中 `ts` 与本目录下的 `publish_snapshot_{ts}.json`、`readable/snapshot_{ts}.csv` 使用**同一个窗口标识**，可直接按键连接。
共 13 窗 × 12 org = 156 数据行。

本目录下所有 CSV 均为带 BOM 的 UTF-8（便于表格软件正确打开），换行统一为 LF；本仓全部文本文件亦然。

## 排除项（透明记录）

- **本地零点前的结算窗全部排除**：零点前定时结算批 `w1`（UTC 04:00–07:00，本地 12:00–15:00）的输出不属本发布线，不予公开。
- 时间带内但**非定时结算输出**的同窗任务/部署态快照，以及定时输出但落于时间带外的快照，均不计入本发布线。
- `param_ver != l2-2.2-exp` 的早期快照不属本发布线。
- 逐项排除清单与对拍凭证由发布方内部留存，不随本仓发布。
