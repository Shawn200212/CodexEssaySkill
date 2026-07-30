# CodexEssaySkill 1.2 evaluation report

## Outcome first

On the frozen Publication-Craft-12 v3 benchmark, CodexEssaySkill 1.2.0 scored **99.8906/100**,
compared with **98.6719** for the predecessor `$write-chi-paper` and **96.5781** for the captured
ClaudeEssaySkill baseline. Its **3.3125-point** lead over ClaudeEssaySkill exceeded the predeclared
**2.0-point** practical margin. Every condition had zero confirmed hard-failure cases.

The supported claim is `HIGHER_ON_FROZEN_BENCHMARK`. Nothing in this evaluation estimates conference
acceptance, scientific truth, plagiarism, or AI authorship.

## Final protocol

| Property | Frozen value |
|---|---|
| Candidate | CodexEssaySkill 1.2.0 |
| Candidate tree SHA-256 | `6f7805f16107ec0a24f3f7512c42fb914f500c65e7e39feeba6141df08bdbdb0` |
| Cases | 8 newly authored synthetic evidence packets |
| Conditions | ClaudeEssaySkill, `$write-chi-paper`, CodexEssaySkill |
| Generator runs | 1 per condition and case; 24 responses total |
| Judges | 2 model-assisted judges with no inherited task history |
| Rubric | 12 weighted dimensions, integer 0–4 anchors |
| Hard gates | 13 |
| Primary score | case-balanced weighted mean, rescaled to 0–100 |
| Practical margin | Codex minus Claude ≥2.0 points and no excess confirmed hard failures |
| Post-holdout patching | forbidden |

An independent holdout author could read the frozen rubric and protocol but not any candidate skill,
earlier case, answer, mapping, or diagnosis. Each generator received one skill and the public case
packets only. A fixed-seed script changed the R1/R2/R3 mapping separately for every case. Judges could
read the anonymized bundle, rubric, and protocol only.

## Aggregate results

| Condition | Score | Codex difference | Confirmed hard failures |
|---|---:|---:|---:|
| CodexEssaySkill 1.2.0 | **99.8906** | — | 0 |
| `$write-chi-paper` | 98.6719 | +1.2187 | 0 |
| ClaudeEssaySkill | 96.5781 | **+3.3125** | 0 |

There were no single-judge hard-failure flags and no overall-score disagreements of two or more
anchor levels. Mean absolute judge disagreement was **0.0903** on the 0–4 dimension scale, indicating
high agreement for this run.

## Dimension profile

| Dimension (0–4) | Codex | `$write-chi-paper` | Claude |
|---|---:|---:|---:|
| Publication thesis | **4.0000** | **4.0000** | 3.7500 |
| Claim–evidence–scope | **4.0000** | 3.8125 | 3.8125 |
| Epistemic calibration | **4.0000** | 3.8125 | 3.6875 |
| Paradigm and construct fidelity | **4.0000** | **4.0000** | 3.8125 |
| Method, unit, and analysis alignment | **4.0000** | 3.9375 | 3.8750 |
| Comparisons and alternatives | 3.9375 | **4.0000** | 3.8750 |
| Null/failure/harm preservation | **4.0000** | 3.9375 | **4.0000** |
| Agency and labor | **4.0000** | **4.0000** | **4.0000** |
| Voice and stance | **4.0000** | **4.0000** | 3.9375 |
| Precision and accessibility | **4.0000** | 3.9375 | 3.9375 |
| Provenance integrity | **4.0000** | **4.0000** | 3.9375 |
| Artifact fit and actionability | **4.0000** | **4.0000** | 3.8750 |

The dimension pattern is consistent with—but does not by itself prove—the intended v1.2 mechanism:
bidirectional factual-atom reconciliation helped retain evidence coordinates while the artifact-first
contract kept the result reader-facing. Codex's only non-perfect aggregate dimension was comparisons
and alternatives (3.9375), so even this high score should not be read as a universal ceiling.

## Why two earlier comparisons were rejected

| Candidate | Cases | Codex | Claude | Difference | Disposition |
|---|---:|---:|---:|---:|---|
| 1.0.0 | 8 | 99.0313 | 98.9531 | +0.0782 | calibration; below margin |
| 1.1.0 | 6 | 98.0417 | 97.4792 | +0.5625 | calibration; below margin |
| **1.2.0** | **8 fresh** | **99.8906** | **96.5781** | **+3.3125** | higher on frozen benchmark |

The 1.0 set exposed an evaluation ceiling and three publication-craft gaps. The 1.1 set then exposed
an omitted role-count coordinate and an unprovided contextual detail in a participatory RtD vignette.
Those sets became calibration as soon as they informed a patch. The v1.2 same-case re-test verified
the patch behavior, but only the newly authored v3 set tested forward generalization.

## Observable prose demonstration

The deterministic audit of the synthetic before/after fixture is a passage locator, not an authorship
test. In the original 79-word generic paragraph it found two empty-value phrases, one vague cluster,
and one proof-force marker. In the revised 261-word passage, empty-value and vague-cluster counts fell
to zero. It still flagged “did not establish” as a proof marker and a proposed “should” sentence as a
universal marker—useful evidence that deterministic scans produce false positives and require human
interpretation. Both audit outputs explicitly report `NOT_MEASURED_AND_NOT_INFERABLE` for authorship.

## Limits

- Eight synthetic cases and one run per condition produce a bounded comparison, not a population
  estimate.
- The judges were model-assisted, not human CHI reviewers; multi-model and human replication remain
  useful follow-up work.
- Evidence-packet fidelity does not establish that evidence from a real manuscript is true or
  complete.
- A high writing score cannot compensate for a weak research contribution, invalid study, missing
  ethics work, or false citation.
- Detector evasion and “AI percentage” were deliberately excluded because they cannot support an
  authorship inference.
