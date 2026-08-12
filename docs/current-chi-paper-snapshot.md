# Current chi-paper source snapshot

## English

This public record describes the current CHI-focused chi-paper source snapshot held in the
private CodexEssaySkill-core repository. It is a status and provenance update, not a new public
benchmark release.

- Snapshot date: 2026-08-13
- Source SHA-256: 2F40D48F1F05D23D20B5714485595D4719EA5856913AF541D143D68418CA9063
- Relation to CodexEssaySkill 1.2.0: a parallel, current CHI source snapshot. It neither replaces
  the frozen 1.2 candidate nor inherits the frozen benchmark score.

The current source adds dated CHI and SIGCHI compliance guidance, instruction-level safeguards for
claim and evidence handling, standard-library document tools, and unit tests. At synchronization,
five tool tests passed. A separately recorded six-case, one-run routing and safety smoke test
obtained the expected outcome for each case.

That smoke test is not a generalization estimate, a manuscript-quality score, a comparison with
another system, or evidence of publication outcomes. The v1.2 benchmark remains frozen and its
scope is unchanged.

This public repository deliberately does not contain the executable current Skill source,
third-party PDFs, document-QA files, manuscript-derived artifacts, raw candidate answers, blind
keys, rater material, or external corpus data.

## 中文

本公开记录说明保存在私有 CodexEssaySkill-core 仓库中的当前 CHI 定向 chi-paper 源码快照。
它是一次状态与来源记录更新，不是新的公开基准发布。

- 快照日期：2026-08-13
- 源码 SHA-256：2F40D48F1F05D23D20B5714485595D4719EA5856913AF541D143D68418CA9063
- 与 CodexEssaySkill 1.2.0 的关系：这是并行维护的当前 CHI 源码快照；它既不替代已经冻结的
  1.2 候选版本，也不继承该版本的冻结基准分数。

当前源码包含带日期的 CHI 与 SIGCHI 合规指引、主张与证据处理的指令级保护、标准库文档工具
以及单元测试。本次同步时，五项工具测试均通过；另有一次六案例、单轮的路由与安全冒烟测试，
每项均得到预期结果。

该冒烟测试不是泛化率、论文质量分数、与其他系统的比较，也不能支持任何录用或发表结果。
v1.2 基准仍保持冻结，其适用范围没有改变。

此公开仓库刻意不包含当前可执行 Skill 源码、第三方 PDF、文档 QA 文件、论文衍生材料、原始
候选回答、盲评键、评审材料或外部语料数据。
