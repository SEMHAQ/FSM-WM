# Peer Review Report — EIC (Re-Review After Fixes)

## Manuscript Information
- **Title**: 面向人形机器人状态预测的轻量级状态空间世界模型
- **Manuscript ID**: CTA-2026-XXXX
- **Review Date**: 2026-06-03
- **Review Round**: Round 14 (Revised)

---

## Reviewer Information

### Reviewer Role
Editor-in-Chief (EIC), 控制理论与应用 (Control Theory & Applications)

### Reviewer Identity
Prof. Zhang, Associate Editor for Control Theory & Applications. Expertise in model predictive control, robot dynamics, and real-time control systems.

### Review Focus
Journal fit, originality, overall quality, significance for the control engineering community.

---

## Overall Assessment

### Recommendation
- [x] **Minor Revision** — Minor revisions needed, no re-review after revision

### Confidence Score
4 — Mostly within my area of expertise, high confidence

### Summary Assessment
This paper proposes SSM-WM for humanoid robot state prediction, combining S4D-style diagonal SSM with Mamba-style gated blocks and integrating it into an MPC framework. The revised version has addressed the critical data inconsistency issue, with all numerical values now consistent between text and tables. The ablation studies now include p-values and effect sizes, strengthening the methodological rigor. The MuJoCo R² discussion has been improved with comparative analysis against other methods. The synthetic dataset discussion has been revised to avoid circular reasoning.

The paper makes a solid contribution to the control engineering community, demonstrating real-time world model capabilities with 7.3x speedup over LSTM and 5.1Hz/2.1Hz MPC control frequencies. The statistical reporting is now comprehensive, with 5-seed experiments, paired t-tests, confidence intervals, and Cohen's d effect sizes.

However, the originality remains incremental (combination of existing techniques), and the paper could benefit from additional references and a novel experiment to demonstrate SSM's unique capabilities. The MuJoCo R² of 0.592, while comparable to other methods, still limits practical applicability claims.

---

## Strengths (Updated)

### S1: Critical Data Inconsistency Fixed
The text-table data inconsistency has been resolved. All numerical values in the text now match the corresponding tables. This was the most critical issue and its fix significantly improves the paper's credibility.

### S2: Comprehensive Statistical Reporting
The ablation studies now include p-values and Cohen's d effect sizes (e.g., gating mechanism: p=0.012, d=1.7). This level of statistical rigor is exemplary for the control engineering literature.

### S3: Improved MuJoCo R² Discussion
The revised discussion now: (1) compares R² across methods (SSM-WM: 0.592, LSTM: 0.566, Transformer: 0.528, Mamba: 0.598), (2) contextualizes the low R² as a task-specific challenge rather than a model limitation, and (3) provides concrete improvement directions.

### S4: Revised Synthetic Dataset Discussion
The discussion now explicitly acknowledges that the synthetic dataset's near-linear dynamics may favor LSTM, and clearly states that MuJoCo results are more representative of real robot scenarios. This avoids the circular reasoning identified by the Devil's Advocate.

### S5: Reworded "First" Claim
The "first" claim has been reworded to focus on application novelty ("系统研究了基于SSM的世界模型在人形机器人状态预测中的应用") rather than architecture novelty. This is more accurate and defensible.

---

## Weaknesses (Updated)

### W1: Originality Remains Incremental
**Problem**: While the "first" claim has been reworded, the core contribution is still a combination of existing techniques (S4D + Mamba gating) applied to a new domain.
**Why it matters**: For a top-tier journal, this level of originality may be insufficient. However, for 控制理论与应用, this is acceptable.
**Suggestion**: Consider adding a novel experiment (e.g., threshold function comparison: soft vs hard vs garrote) to demonstrate that the learned behavior goes beyond the generic operator.
**Severity**: Minor

### W2: Limited Reference Count
**Problem**: The paper has 28 references (24 English + 4 Chinese), which is below the typical threshold for comprehensive coverage (>40 sources).
**Why it matters**: Missing recent works on diffusion models for dynamics, graph neural networks for robot state prediction, and neural ODE for continuous dynamics.
**Suggestion**: Add 10-15 more references to recent relevant works.
**Severity**: Minor

### W3: Embedded Hardware Discussion Missing
**Problem**: All inference time measurements are on RTX 3090 GPU. The paper does not discuss expected performance on embedded hardware (Jetson, ARM).
**Why it matters**: Real robots typically use embedded processors, not desktop GPUs.
**Suggestion**: Add a paragraph discussing expected performance characteristics on embedded platforms.
**Severity**: Minor

---

## Dimension Scores (Updated)

| Dimension | Score (0-100) | Descriptor | Notes |
|-----------|--------------|------------|-------|
| Originality (20%) | 68 | Adequate | Incremental but defensible for target journal; reworded claim is accurate |
| Methodological Rigor (25%) | 80 | Strong | Critical data issue fixed; ablation studies now include p-values and effect sizes |
| Evidence Sufficiency (25%) | 78 | Strong | Data consistency fixed; MuJoCo R² discussion improved; still needs more references |
| Argument Coherence (15%) | 82 | Strong | Circular reasoning fixed; logical flow is clear |
| Writing Quality (15%) | 78 | Strong | Data inconsistency fixed; reference typo fixed; still has placeholder author names |
| **Weighted Average** | **77.2** | **Minor Revision** | |

---

## Remaining Issues for Next Revision

1. **Add more references** (10-15 recent works) to reach >40 sources
2. **Add embedded hardware discussion** in Section 5.1
3. **Replace placeholder author names** on title page
4. **Consider adding threshold function comparison experiment** to boost originality

---

*End of EIC Re-Review Report*
