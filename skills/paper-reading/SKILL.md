---
name: paper-reading
description: Explain a research paper through author background, the original abstract with explanation, a flowchart of the paper's logic and method, and its actual results. Use when the user wants to read, understand, or discuss a specific paper.
---

# Paper Reading

Read the actual paper, including relevant appendices, and inspect the key figures and tables before explaining it. Prefer the user's uploaded paper and identify its version. If the full text is unavailable, try an accessible author-provided copy; if still blocked, explain the limitation and request the PDF rather than reconstructing the paper from its title or summaries.

Explain in the user's language. Use exactly the following four sections, in this order. Keep source links and paper page, section, figure, or table references beside the claims they support. Deliver the reading in the conversation unless the user requests a file. Do not add separate review, implementation, or experiment-planning stages.

## 1. Authors and Research Background

Introduce the main authors, their affiliations at publication, and relevant previous work. Verify background using the paper, author or institution pages, and original publications. Identify joint first authors or project leads only when explicitly stated. Separate current affiliations from those printed in the paper.

Explain how the team's prior research connects to this paper. Focus on relevant expertise rather than a long biography. Do not infer individual contributions from author order or treat reputation as evidence that the results are correct. State when a biographical detail cannot be verified.

## 2. Original Abstract and Explanation

Locate the abstract in the paper itself. For a user-provided paper, reproduce the complete abstract verbatim in a clearly marked quotation. Preserve its original language and wording; only normalize PDF line breaks and layout-induced word splits. Visually verify uncertain extraction instead of silently correcting the author's text. For other sources, reproduce the full abstract only when permitted; otherwise provide its source location, a permitted excerpt, and an explicitly labeled explanation.

After the quotation, explain the problem, data or supervision, proposed method, and claimed results using the full paper. Define important terms with concrete examples. Keep the author's wording separate from translation, paraphrase, and interpretation. Explain scope qualifiers such as "zero-shot" or "fully automatic" using the actual experimental setup.

## 3. Paper Logic and Method Flow

Trace the research question, shortcomings of existing approaches, proposed solution, and how it is tested. Use a readable Mermaid flowchart and explain the input, operation, output, and purpose of each major step. Label the diagram as your synthesis unless reproducing a paper figure.

Separate data generation, training, and deployment when they differ. Distinguish learned models, pretrained components, controllers, privileged information, and inputs available at deployment. Adapt the diagram to the paper's actual structure; do not invent a procedural pipeline for a theoretical or empirical study. Include equations and implementation details only when they help the reader understand the mechanism.

## 4. Results: What the Paper Actually Demonstrates

Present the key original figures or a faithful table of reported results, with figure/table identifiers. Explain the tasks, baselines where provided, metrics, sample sizes, and conditions. Label any percentages or other quantities you calculate from the paper's values.

Explain what each main result and ablation supports. Separate simulation from hardware results, individual tasks from complete long-horizon performance, and familiar environments from genuinely held-out environments. Distinguish measured evidence from the authors' explanations and your interpretation. Do not invent missing baselines, uncertainty estimates, or numerical values from unreadable plots.

Within this section, state the demonstrated contribution, practical limits, failure cases, and claims not established by the experiments. Flag material inconsistencies in counts or settings without silently choosing a corrected value. Preserve the paper's scope rather than turning limited evidence into a general guarantee.
