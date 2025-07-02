---
mode: 'agent'
description: 'Keep docs/model-comparison.md in sync with the latest Copilot models & premium-request pricing'
tools: ['editFiles', 'fetch']
---

# Goal
Create a comprehensive, user-friendly GitHub Copilot model comparison guide that helps developers choose the right model and plan for their needs.

## Data Collection
1. **Fetch latest model information**:
   * https://docs.github.com/en/copilot/reference/ai-models/supported-ai-models-in-copilot
   * https://docs.github.com/en/copilot/using-github-copilot/ai-models/choosing-the-right-ai-model-for-your-task
   * https://docs.github.com/en/enterprise-cloud@latest/copilot/managing-copilot/monitoring-usage-and-entitlements/about-premium-requests
   * https://docs.github.com/en/copilot/concepts/copilot-billing/understanding-and-managing-requests-in-copilot
   * https://github.blog/ai-and-ml/github-copilot/which-ai-model-should-i-use-with-github-copilot/
   * https://github.blog/ai-and-ml/github-copilot/a-guide-to-deciding-what-ai-model-to-use-in-github-copilot/

2. **Fetch plan comparison data**:
   * https://docs.github.com/en/copilot/get-started/plans-for-github-copilot

## Output: `.github/model-comparison.md`

### Required Sections
1. **Executive Summary** - TL;DR for busy developers
2. **Quick Model Picker** - Decision tree or flowchart for rapid selection
3. **Comprehensive Model Matrix** - Table with:
   - Model name & provider
   - Context window size
   - Latency category (Fast/Balanced/Deep)
   - Premium request multiplier
   - Strengths & best use cases
   - Plan availability
4. **Plan Comparison Table** - Side-by-side feature & pricing comparison
5. **Interactive Request Flow** - Mermaid diagram showing:
   - User prompt → Plan check → Model selection → Billing calculation
   - Fallback behavior when limits exceeded
6. **Practical Examples** - Real scenarios with recommended models
7. **Cost Calculator Guidelines** - Help estimate monthly expenses
8. **Performance Insights** - Speed vs quality trade-offs
9. **Migration Guide** - How to switch between plans/models

### Enhanced Features
- **Emoji categorization** for visual scanning (🏎️ Speed, 🧠 Reasoning, 🖼️ Multimodal, 💰 Cost-effective)
- **Risk indicators** for high-cost models
- **Availability badges** (GA/Preview/Free/Paid)
- **Context warnings** for models with limitations
- **Update metadata** with timestamp and generation model used

### Format Requirements
- Mobile-friendly tables with horizontal scroll
- Collapsible sections for detailed information
- Clear visual hierarchy with consistent formatting
- Cross-references between sections
- Links to official documentation

## Validation Checklist
- [ ] All current models included with accurate multipliers
- [ ] Plan pricing reflects latest changes
- [ ] Examples cover common developer scenarios
- [ ] Mermaid diagram accurately represents request flow
- [ ] Document is accessible and scannable
- [ ] Generated with attribution to AI model used

## Success Metrics
The resulting guide should help developers:
1. Choose appropriate models in <30 seconds for common tasks
2. Understand cost implications before making requests
3. Navigate plan differences confidently
4. Troubleshoot model availability issues