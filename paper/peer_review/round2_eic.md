# Peer Review Report - EIC (Round 2)

## Manuscript Information
- **Title**: 面向人形机器人状态预测的轻量级状态空间世界模型
- **Review Date**: 2026-06-02
- **Review Round**: Round 2 (Re-review after revision)

---

## Reviewer Role: EIC

## Overall Assessment

### Recommendation
- [x] **Minor Revision**
- [ ] Major Revision

### Confidence Score: 4/5

### Summary Assessment
作者针对Round 1的审稿意见进行了认真修改: (1) 摘要与正文数据已统一, 使用合成数据集; (2) 方法描述已更新为对角SSM, 与代码实现一致; (3) 补充了消融实验数据(表2); (4) 参考文献从8篇扩充到15篇. 这些修改有效解决了Round 1的Critical问题. 剩余问题主要是: (1) 缺少架构图; (2) Transformer数据仍缺失; (3) 缺少序列长度敏感性分析.

---

## Strengths

### S1: Critical问题已全部修复
摘要与正文数据一致, 方法描述与代码实现一致, 消融实验有数据支撑. 学术诚信问题已解决.

### S2: 消融实验设计合理
表2展示了门控机制(+2.5%)和残差连接(+1.6%)的贡献, 验证了架构设计的合理性.

### S3: 参考文献质量提升
新增的7篇文献涵盖了HiPPO、S4、S5、Mamba-2等SSM基础工作, 以及世界模型和MPC的相关研究.

---

## Weaknesses

### W1: 仍缺少架构图
**Problem**: 论文提到"整体架构如图~1所示", 但全文没有图.
**Suggestion**: 补充架构图, 清晰展示编码器、SSM块、解码器的数据流.
**Severity**: Major

### W2: Transformer数据仍缺失
**Problem**: 表1中Transformer-WM的MSE和MAE仍为"---".
**Suggestion**: 补充数据或说明原因.
**Severity**: Minor

---

## Dimension Scores

| Dimension | Score (0-100) | Descriptor |
|-----------|--------------|------------|
| Originality | 65 | Adequate |
| Methodological Rigor | 62 | Adequate |
| Evidence Sufficiency | 60 | Adequate |
| Argument Coherence | 72 | Strong |
| Writing Quality | 68 | Adequate |
| **Weighted Average** | **65** | **Minor Revision** |
