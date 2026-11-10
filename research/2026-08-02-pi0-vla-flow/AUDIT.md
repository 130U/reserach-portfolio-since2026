# π₀ 双语读书笔记审计 / Bilingual Reading Note Audit

审计日期 / Audit date: 2026-08-02
Scope: the Chinese and English Markdown reading notes.

## 1. Reading sources

The Chinese and English Markdown files are the published reading editions. `SOURCES.yaml` records their primary references.

## 2. 双语结构审计 / Bilingual structure audit

| Check | 中文 | English | Result |
|---|---:|---:|---|
| Total lines | 806 | 806 | Pass |
| Ordered section anchors | 57 | 57 | Exact order match |
| Display-equation blocks | 31 | 31 | Count and structure match |
| External source links | 27 | 27 | URL order match |
| Main chapters | 15 | 15 | One-to-one |
| Source and verification appendices | 2 | 2 | One-to-one |

Translation policy: one-to-one means semantic-block alignment, not rigid
sentence-for-sentence translation. Every paired block preserves the same facts,
numbers, formulas, evidence identity, causal direction, and qualifications.

## 3. 关键事实一致性 / Critical-fact consistency

The following were checked in both languages:

- roughly 3B PaliGemma + roughly 300M action expert + roughly 3.3B total;
- \(H=50\) physical action steps and \(K=10\) Euler integration steps;
- 20 Hz: execute 16 steps and replan after about 0.8 s;
- 50 Hz: execute 25 steps and replan after about 0.5 s;
- more than 10,000 hours, roughly 903M proprietary timesteps, seven robot configurations, and 68 broad tasks;
- 9.1% as a sampling-mixture weight, not the raw share of elapsed data;
- 1/5/10-hour adaptation experiments and 5–20-minute long-task demonstrations.

## 4. 必须保留的证据边界 / Mandatory evidence boundaries

1. π₀ is Physical Intelligence’s first generalist policy and the defining start
   of its π-series; it is not the first VLA or embodied-intelligence paper.
2. Claims such as “first,” “largest,” or “new SOTA” remain author claims and
   retain “to our knowledge” or equivalent wording.
3. The 0.75–1.00 direct-prompting range is an approximate reading of Figure 7,
   not an exact numerical table.
4. “Above 50%” in the complex-task discussion is partial progress, not complete
   task success.
5. `zero-shot` in v1 does not mean the broader task family was absent from
   pretraining; v4 uses `direct prompting` / `out-of-box`.
6. Forward Euler numerically integrates the learned vector field. It does not
   prove that ten steps recover a paired demonstration action.
7. The paper uses \(\tau=0\) for noise and \(\tau=1\) for action. Current openpi
   code uses the reverse time convention and negative integration steps; the two
   are equivalent under \(t=1-\tau\).
8. Eighteen dimensions describe the paper-era padded cross-robot interface.
   Current `Pi0Config` defaults to `action_dim=32`; the main derivation therefore
   keeps the action dimension generic as \(d\).
9. WAM is treated as an emerging, nonstandard label. The π₀-versus-WM/WAM
   section is marked as interpretation, not as a result established by π₀.
10. The experiments validate the complete recipe but do not cleanly identify
    the causal contribution of VLM scale, Flow Matching, data scale,
    post-training, and systems engineering separately.

## 5. Repository checks

Both reading editions preserve their section anchors, equations, source order and evidence qualifications. Relative links resolve to the materials in this repository. The research note is a dated interpretation of the cited paper and code snapshots; its formulas and historical source boundaries are maintained together.
