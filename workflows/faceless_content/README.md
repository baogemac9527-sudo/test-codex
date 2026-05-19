# Douyin Image-Post Workflow（图文版改编落仓）

> 来源参考：`cporter202/automate-faceless-content`（仅借鉴流程，不复制其实现代码）。

## 目标
用于短视频服务团队的“抖音图文批量生产流水线”（4~5 页高密度版）：
- 批量选题
- 自动生成图文卡片文案
- 错误-修复同页表达
- 风格预设一致化（爆款排版）
- 发布前质检
- 复盘回写

## 抖音图文流量机制（执行要点）
1. **封面与首屏决定停留**：第 1 页需明确“人群 + 痛点 + 结果预期”。
2. **高密度信息收益**：每页必须有新信息和可执行动作，避免口号化。
3. **短链路结构**：建议 4~5 页，提升读完率与行动率。
4. **错误-修复同页**：从第 2 页开始，每页同时给出“常见错误 + 修复动作”。
5. **风格一致性**：使用 `skills/douyin_explosive_style/style_presets.json` 统一封面与正文视觉语言。
6. **单一转化动作**：末页仅一个 CTA（评论关键词或私信关键词）。

## 工作流步骤
1. **Topic Intake（选题输入）**
2. **Copy Draft（图文文案草案）**：调用 `prompts/content_pipeline/script_generation.md`
3. **Page Plan（分页拆解）**：调用 `prompts/content_pipeline/shot_breakdown.md`
4. **Style Binding（风格绑定）**：调用 `skills/douyin_explosive_style/style_presets.json`
5. **Compliance Check（合规质检）**
6. **Publishing Pack（发布包）**
7. **Postmortem（复盘）**
8. **Adversarial Eval（对抗优化）**：调用 `workflows/faceless_content/adversarial_eval.md`

## 目录约定
- `workflows/faceless_content/README.md`：流程定义
- `prompts/content_pipeline/script_generation.md`：图文文案生成模板
- `prompts/content_pipeline/shot_breakdown.md`：图文分页拆解模板
- `prompts/content_pipeline/postmortem.md`：图文复盘模板
- `workflows/faceless_content/adversarial_eval.md`：对抗性优化流程
- `prompts/content_pipeline/adversarial_testcases.md`：对抗测试集模板
- `prompts/content_pipeline/robustness_scoring.md`：鲁棒性评分模板
- `skills/douyin_explosive_style/SKILL.md`：爆款排版风格说明
- `skills/douyin_explosive_style/style_presets.json`：风格预设
