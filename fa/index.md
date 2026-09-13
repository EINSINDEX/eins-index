# Published Snapshot Index — Settlement Window Inventory and Per-Window Rationale

> 中文版 / Chinese: [`index_ZH.md`](index_ZH.md)

> This inventory is the window-level evidence record for the published snapshots under `fa/`.
> Each settlement window carries **exactly one** published snapshot. The inclusion criteria are:
> 1. **Publication scope**: this publication line includes **only settlement windows after local midnight**,
>    i.e. windows whose `computed_at` (converted to UTC) falls in the closed-market band **UTC 16:00–19:00**
>    (local UTC+8 **00:00–03:00**) — the **post-midnight scheduled settlement batch `w2`**; the pre-midnight
>    batch `w1` (UTC 04:00–07:00, local 12:00–15:00) **is outside this publication line and is not published**;
> 2. **Scheduled settlement output**: the window's snapshot has a corresponding output record in the
>    post-midnight scheduled settlement batch (`w2` = UTC 18:30);
> 3. **Time band**: the snapshot `computed_at` (converted to UTC) falls inside the closed-market band above;
> 4. **Parameter version**: `param_ver = l2-2.2-exp`;
> 5. **Consistent membership**: the `membership` block is archived together with the snapshot.

Exclusions and the reasons for them are retained internally by the publisher; per-window reconciliation and exclusion evidence **are not published in this repository**.

## Summary

- Settlement windows: **13**
- Publication scope: **post-midnight settlement windows only** (`w2`, UTC 16:00–19:00)
- Publication line start: **2026-09-01** (windows before it are out of this line)
- Parameter version: `l2-2.2-exp` (all windows)
- Time range: `2026-09-01T02:33:41+08:00` → `2026-09-13T02:31:50+08:00` (local time zone UTC+8)
- Reconciliation (A2): **all pass** (per-window reconciliation evidence is retained internally by the publisher and is not published in this repository)
- Field gaps: none

## Window inventory

| # | ts | computed_at (local) | computed_at (UTC) | batch | top-level weights cap/eco | members | field gaps | A2 |
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

## Per-window rationale (detail)

### 1. `20260901_0241`

- Source snapshot: `snapshot_20260901_0241.json`
- `computed_at`: `2026-09-01T02:33:41+08:00` = `2026-08-31T18:33:41Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260901_0241.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260901_0241.json`; flattened CSV `fa/readable/snapshot_20260901_0241.csv`

### 2. `20260902_0239`

- Source snapshot: `snapshot_20260902_0239.json`
- `computed_at`: `2026-09-02T02:33:38+08:00` = `2026-09-01T18:33:38Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260902_0239.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260902_0239.json`; flattened CSV `fa/readable/snapshot_20260902_0239.csv`

### 3. `20260903_0239`

- Source snapshot: `snapshot_20260903_0239.json`
- `computed_at`: `2026-09-03T02:33:44+08:00` = `2026-09-02T18:33:44Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260903_0239.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260903_0239.json`; flattened CSV `fa/readable/snapshot_20260903_0239.csv`

### 4. `20260904_0238`

- Source snapshot: `snapshot_20260904_0238.json`
- `computed_at`: `2026-09-04T02:33:05+08:00` = `2026-09-03T18:33:05Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260904_0238.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260904_0238.json`; flattened CSV `fa/readable/snapshot_20260904_0238.csv`

### 5. `20260905_0239`

- Source snapshot: `snapshot_20260905_0239.json`
- `computed_at`: `2026-09-05T02:33:10+08:00` = `2026-09-04T18:33:10Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260905_0239.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260905_0239.json`; flattened CSV `fa/readable/snapshot_20260905_0239.csv`

### 6. `20260906_0241`

- Source snapshot: `snapshot_20260906_0241.json`
- `computed_at`: `2026-09-06T02:34:34+08:00` = `2026-09-05T18:34:34Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260906_0241.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260906_0241.json`; flattened CSV `fa/readable/snapshot_20260906_0241.csv`

### 7. `20260907_0233`

- Source snapshot: `snapshot_20260907_0233.json`
- `computed_at`: `2026-09-07T02:31:40+08:00` = `2026-09-06T18:31:40Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260907_0233.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260907_0233.json`; flattened CSV `fa/readable/snapshot_20260907_0233.csv`

### 8. `20260908_0233`

- Source snapshot: `snapshot_20260908_0233.json`
- `computed_at`: `2026-09-08T02:31:26+08:00` = `2026-09-07T18:31:26Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260908_0233.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260908_0233.json`; flattened CSV `fa/readable/snapshot_20260908_0233.csv`

### 9. `20260909_0233`

- Source snapshot: `snapshot_20260909_0233.json`
- `computed_at`: `2026-09-09T02:31:35+08:00` = `2026-09-08T18:31:35Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260909_0233.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260909_0233.json`; flattened CSV `fa/readable/snapshot_20260909_0233.csv`

### 10. `20260910_0232`

- Source snapshot: `snapshot_20260910_0232.json`
- `computed_at`: `2026-09-10T02:31:18+08:00` = `2026-09-09T18:31:18Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260910_0232.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260910_0232.json`; flattened CSV `fa/readable/snapshot_20260910_0232.csv`

### 11. `20260911_0233`

- Source snapshot: `snapshot_20260911_0233.json`
- `computed_at`: `2026-09-11T02:32:00+08:00` = `2026-09-10T18:32:00Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260911_0233.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260911_0233.json`; flattened CSV `fa/readable/snapshot_20260911_0233.csv`

### 12. `20260912_0233`

- Source snapshot: `snapshot_20260912_0233.json`
- `computed_at`: `2026-09-12T02:31:26+08:00` = `2026-09-11T18:31:26Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260912_0233.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260912_0233.json`; flattened CSV `fa/readable/snapshot_20260912_0233.csv`

### 13. `20260913_0233`

- Source snapshot: `snapshot_20260913_0233.json`
- `computed_at`: `2026-09-13T02:31:50+08:00` = `2026-09-12T18:31:50Z` (UTC), inside the closed-market band UTC 16:00–19:00 (local 00:00–03:00, i.e. **after local midnight**)
- Settlement run evidence: post-midnight scheduled settlement batch (window `w2`) has a `snapshot_20260913_0233.json` output record in `daily_w2.log`
- `param_ver`: `l2-2.2-exp`; top-level weights (`fa_influence.w`): capability_merged=0.6, ecosystem_merged=0.4
- Membership: `constituent_count=10`, `universe_rev=46`
- A2 reconciliation: `PASS` (per-window reconciliation evidence is retained internally and is not published in this repository); published JSON `fa/publish_snapshot_20260913_0233.json`; flattened CSV `fa/readable/snapshot_20260913_0233.csv`

## Time series (long table)

`fa/readable/fa_series.csv` concatenates every window in ascending `ts` order; row = (`ts`, `org`),
columns = `ts, org, membership, capability_merged, ecosystem_merged, fa_raw, fa_adj`;
`ts` is the **same window identifier** used by `publish_snapshot_{ts}.json` and `readable/snapshot_{ts}.csv` in this directory, so the files join directly on that key.
13 windows × 12 org = 156 data rows.

Every CSV in this directory is UTF-8 with a byte-order mark (so spreadsheet software opens it correctly) and uses LF line endings, as does every text file in this repository.

## Exclusions (transparency record)

- **All pre-midnight settlement windows are excluded**: the output of the pre-midnight scheduled settlement batch `w1` (UTC 04:00–07:00, local 12:00–15:00) is outside this publication line and is not published.
- Ad-hoc task/deployment snapshots inside the time band that are **not scheduled settlement output**, and timed output falling outside the band, are likewise not counted in this publication line.
- Early snapshots with `param_ver != l2-2.2-exp` are not part of this publication line.
- The itemised exclusion list and the reconciliation evidence are retained internally by the publisher and are not published in this repository.
