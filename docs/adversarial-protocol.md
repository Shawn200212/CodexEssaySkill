# GaNS-shaped adversarial iteration protocol

CodexEssaySkill uses a GAN-shaped simulation over instructions, routing policies, cases, and blind
evaluators. It is not neural fine-tuning: there is no gradient, discriminator network, learned model
weight, or convergence guarantee.

## Roles and firewall

| Role | Sees | Must not see |
|---|---|---|
| Generator | One frozen skill, one task, legitimate evidence | Expected answer, issue tags, competitor identity |
| White-box adversary | Skill architecture, prior calibration failures | Generator answer for the case being authored |
| Blind judge | Task, evidence, anonymized response, fixed rubric | Candidate identity, patch history, development round |
| Patch author | Calibration failures and source evidence | Final semantic-holdout diagnoses before candidate freeze |

An earlier challenge set becomes calibration as soon as it informs a patch. A later round must use a
new independently authored validation set. The final semantic holdout is created after the candidate
is frozen and cannot be used to modify that candidate.

## Three deterministic rounds and two semantic calibration patches

Round 1 searched routing weights and mandatory gates over 416 paper-derived train cases, 104
paper-derived validation cases, and synthetic adversarial calibration cases. Its first challenge set
exposed an intact-text preservation weakness, so those cases were not called a final holdout.

Round 2 added two independently authored adversarial sets. Although the mean proxy improved, the
weakest task family regressed. The candidate was rejected and its outputs retained as negative
evidence.

Round 3 reclassified every earlier adversarial set as calibration, introduced a new 16-case
validation set, raised rare-capability floors, and required worst-family non-regression. It selected
generation 62 after 82 generations. These scores measure routing and safety-contract coverage only.

The first semantic comparison produced a 98–99 point ceiling and only a 0.0782-point Codex lead, so
it became Round 4 calibration. Its diagnoses added artifact-first publication craft. A new six-case
comparison then produced a 0.5625-point lead, still below the two-point practical margin, and became
Round 5 calibration. Its diagnoses added bidirectional factual-atom reconciliation and
source-bound specificity. Same-case regeneration verified each patch but never counted as forward
evidence.

## Final semantic forward test

Version 1.2.0 was frozen before an independent author created eight new scenarios. The author could
read the rubric and protocol, but not any skill, earlier case, answer, diagnosis, or mapping. Three
isolated generators each received one candidate skill and the same public evidence packets. Their
responses were randomly relabeled per case. Two judges with no inherited task history independently
applied the frozen twelve-dimension rubric. A difference below two points on the 0–100 weighted scale
is no practical difference; confirmed hard failures are disqualifying.

CodexEssaySkill scored 99.8906, the predecessor `$write-chi-paper` 98.6719, and ClaudeEssaySkill
96.5781. The 3.3125-point Codex–Claude difference exceeded the predeclared two-point margin. All
conditions had zero confirmed hard failures, and no single-judge flag required adjudication.

The benchmark supports only a claim about the named frozen cases, generator, judges, prompts, and
date. It cannot establish universal manuscript quality, scientific truth, conference acceptance, or
human versus AI authorship.
