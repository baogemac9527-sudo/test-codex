# Adversarial Optimization Workflow（对抗性优化流程）

## 目的
在图文发布前执行“攻击-评测-修复”闭环，降低抖音图文在真实流量中的失效风险。

## 流程
1. **生成对抗测试集**
   - 使用 `prompts/content_pipeline/adversarial_testcases.md`
   - 产出 12+ 场景化攻击用例。

2. **执行模拟评测**
   - 将文案在各攻击场景下做人工/模型联合评估。
   - 记录失败信号：点击下降、页间流失、互动下降、CTA 模糊等。

3. **鲁棒性评分**
   - 使用 `prompts/content_pipeline/robustness_scoring.md`
   - 输出总分、维度分、失败TOP、修复计划。

4. **修复与回归**
   - 依据 P0/P1/P2 修改封面、分页、CTA、合规表述。
   - 至少回归 1 轮，确保关键失败项收敛。

## 通过门槛（建议）
- robustness_score >= 75
- 不存在合规高风险项
- CTA 清晰度维度 >= 80
- 页间关键流失点（2->3 或 3->4）有明确修复方案
