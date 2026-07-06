---
name: insurance-product-explainer
description: This skill should be used when the user sends an insurance product document (PDF, Word, image, or text) and wants to (1) understand the product in plain language suitable for insurance beginners, (2) extract key product highlights, (3) compare with 3-5 competitive products researched from public sources (WeChat articles, web search, insurance blogs), and (4) generate client-ready output in both Markdown and WeChat-friendly formats. Trigger keywords include: 保险产品分析, 产品亮点, 保险评测, 帮我分析这款产品, 这款产品怎么样, 保险小白看得懂, 发给客户看. The skill covers health insurance (医疗险/百万医疗) and critical illness insurance (重疾险).
agent_created: true
---

# Insurance Product Explainer

## Overview

This skill transforms insurance product documents into client-ready highlights written in plain language that insurance beginners can understand. It parses the product document, translates professional jargon into everyday language, researches competitive products from public sources, and produces output suitable for sending directly to clients.

The skill covers two main product categories:
- **医疗险 / 健康险** (health insurance, including 百万医疗, 中端医疗, 高端医疗)
- **重疾险** (critical illness insurance)

---

## When to Use This Skill

Trigger this skill when the user:
- Sends an insurance product document (PDF, Word file, screenshot, or pasted text) and asks to analyze it
- Asks to explain an insurance product in plain language for beginners
- Wants to extract product highlights for client presentation
- Asks for competitive comparison of an insurance product
- Uses phrases like: 帮我分析这款产品 / 这款产品亮点 / 保险小白看得懂 / 发给客户 / 产品评测

---

## Complete Workflow

### Phase 1: Parse the Product Document

1. Read the uploaded document (PDF, Word, image, or pasted text).
2. Identify the product type: 医疗险 or 重疾险.
3. Extract key information using the analysis framework in `references/product-analysis-framework.md`.
4. For each extracted term, consult `references/insurance-terms-glossary.md` to prepare plain-language translations.

### Phase 2: Research Competitive Products

1. Determine the product's market segment using `references/comparison-research-guide.md`.
2. Use web search (and WeChat search when possible) to find 3-5 comparable products currently on the market.
3. Search for: product name + 对比 / 评测 / 怎么样, and broader category keywords (e.g., 百万医疗险 2024 推荐).
4. Prioritize information from: insurance WeChat official accounts (深蓝保, 奶爸保, 慧择, etc.), Zhihu answers, and official insurer websites.
5. Extract comparison data for the dimensions defined in `references/comparison-research-guide.md`.
6. Cross-verify critical numbers (premium, coverage amount, deductible) with at least two sources.

### Phase 3: Extract and Translate Highlights

1. Identify 3-5 key highlights. A highlight qualifies if it:
   - Solves a real customer pain point
   - Has a competitive advantage vs. similar products
   - Can be explained in plain language
2. Translate all professional terms using `references/insurance-terms-glossary.md`.
3. For each highlight, structure as: plain-language title → explanation → competitive advantage → suitable audience.

### Phase 4: Generate Client-Ready Output

1. Produce two versions (as specified by the user, or both by default):
   - **Markdown 底稿版**: Full structured analysis, for internal use and archiving
   - **微信精简版**: Condensed version (500-800 chars), short paragraphs, appropriate emoji, ready to send via WeChat
2. Use the templates in `references/client-output-template.md` as the starting structure.
3. Fill in all sections: product overview, highlights, competitive comparison table, things to note, suitable audience, FAQ.
4. Run through the output checklist in `references/client-output-template.md` before delivering.

---

## Output Format Requirements

### Markdown 底稿版 must include:
- Product overview (30-second summary with concrete example)
- 3-5 key highlights (each with plain-language explanation and competitive advantage)
- Competitive comparison (table format, with 3-5 comparable products)
- Things to note (exclusions, health declaration requirements — be honest)
- Suitable audience (who should consider this, who should not)
- FAQ (2-3 common questions)
- Disclaimer: 具体以保险合同条款为准

### 微信精简版 must:
- Be 500-800 characters
- Use short paragraphs (max 3 lines each)
- Use appropriate emoji (not excessive)
- Highlight the top 3 points only
- End with an open invitation for questions

---

## Reference Files

| File | Purpose | When to Load |
|-----|---------|-------------|
| `references/insurance-terms-glossary.md` | Plain-language translations of insurance jargon | Every use — consult when translating terms |
| `references/product-analysis-framework.md` | Step-by-step framework for extracting product information | Phase 1 — parse the document |
| `references/comparison-research-guide.md` | How to search for and compare with competitive products | Phase 2 — research competitors |
| `references/client-output-template.md` | Output templates for both Markdown and WeChat versions | Phase 4 — generate output |

---

## Important Principles

1. **Honesty builds trust**: Always disclose exclusions and limitations. Hiding them hurts trust when the customer later finds out.
2. **No absolute superiority claims**: Say "Product A has an advantage in X, Product B has an advantage in Y" — not "A is better than B."
3. **Plain language only**: If a sentence still contains words like 保额, 免赔额, 等待期 without explanation, rewrite it.
4. **Numbers speak louder**: Use specific numbers (premium, coverage amount, deductible) rather than vague adjectives like "cheap" or "high coverage."
5. **Cross-verify critical data**: Premium and coverage numbers must be verified against at least two sources before including in client output.

---

## Notes

- If the uploaded document is an image/screenshot, use OCR or visual analysis to extract text before proceeding.
- If the product type is neither 医疗险 nor 重疾险, state this clearly and ask the user whether to proceed with a generic analysis framework.
- If insufficient public information is found for competitive comparison, state this honestly and provide a qualitative analysis based on the product's own features.
- Always include a data source note and disclaimer in the final output.
