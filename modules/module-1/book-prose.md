# Module 1 Book Prose

## Prediction tasks and data framing

What decision is the [model](../../glossary.md#model) actually supporting?

### Professional Scenario

You are advising **an analytics team choosing a predictive model for an operational decision**. The immediate task is to decide what evidence would make a recommendation credible, what [risks](../../glossary.md#risk) remain unresolved, and what should happen next. The module's work product is: **predictive modeling report with [baseline](../../glossary.md#baseline) comparison, [validation](../../glossary.md#validation) evidence, and model card focused on prediction tasks and data framing: Frame a supervised learning task from raw business or research data.**.

The available lab data is deliberately limited: synthetic tabular observations with [features](../../glossary.md#feature), labels, train/test split, baseline score, and error slices. Treat it as a proxy for reasoning and method practice, not as proof that a real [deployment](../../glossary.md#deployment) is ready. A graduate-level submission must distinguish between what the proxy exercise demonstrates and what would still require institutional data, stakeholder review, and operational testing.

### Core Concepts

- **Problem framing:** define the decision, population, workflow, or system boundary before choosing a method.
- **Baseline discipline:** compare the proposed AI-enabled approach with an existing process, simple rule, or manual review pattern.
- **Evidence quality:** separate measured results from assumptions, anecdotes, vendor claims, and synthetic-data artifacts.
- **Failure modes:** identify where the system can fail technically, operationally, legally, ethically, or socially.
- **Deployment readiness:** connect metrics to decision thresholds, [monitoring](../../glossary.md#monitoring), escalation, and rollback.

## Why This Module Matters

In **AINS6002: [Machine Learning](../../glossary.md#machine-learning) & Predictive Modeling**, this module contributes to the larger course arc by requiring students to turn a domain problem into an inspectable technical artifact. The standard is not "the [notebook](../../glossary.md#notebook) ran." The standard is that another reviewer can understand the decision, reproduce the reasoning, and challenge the assumptions.

### Method Pattern

1. State the stakeholder decision in one sentence.
2. Identify the evidence source and why it is adequate or inadequate.
3. Produce a baseline result using the lab or an equivalent transparent method.
4. Compare one alternative design, threshold, policy, or model.
5. Document false positives, false negatives, unintended incentives, and operational constraints.
6. Recommend a next action: continue research, run a controlled pilot, redesign the system, or stop.

### Failure Modes To Check

- **Measurement mismatch:** the metric optimizes something adjacent to, but not identical with, the real decision.
- **Context [loss](../../glossary.md#loss):** important operational or human factors are absent from the data.
- **[Automation](../../glossary.md#automation) bias:** users may over-trust a score, classification, or recommendation.
- **Equity and access risk:** affected groups may experience different error rates or burdens.
- **[Governance](../../glossary.md#governance) gap:** no one owns monitoring, escalation, or rollback after launch.

## Study Questions

1. What decision does the module artifact support?
2. What does the proxy lab evidence prove, and what does it not prove?
3. Which baseline or manual process should the AI-enabled approach be compared against?
4. Which stakeholder would object to the recommendation, and on what grounds?
5. What monitoring signal would tell you the system is failing after deployment?

<!-- BEGIN COURSE EXPERIENCE REMEDIATION -->
## Worked Example: From Evidence to a Decision

Return to the professional situation for this module: You are advising **an analytics team choosing a predictive model for an operational decision**. The immediate task is to decide what evidence would make a recommendation credible, what risks remain unresolved, and what should happen next. The module's work product is: **predictive modeling report with baseline comparison, validation evidence, and model card focused on prediction tasks and data framing: Frame a supervised learning task from raw business or research data.**. The team should not begin by selecting the most sophisticated tool. First, rewrite the situation as a decision: **what must be decided, by whom, using which evidence, and under which constraints?** That sentence establishes the boundary of the analysis.

Next, create an inspectable baseline. For this module, a useful baseline should make **Problem framing: define the decision, population, workflow, or system boundary before choosing a method.** visible rather than hiding it inside an unsupported conclusion. Preserve the starting data or case facts, record the initial result, and identify the assumption most likely to change the recommendation. Then make one controlled comparison using **Baseline discipline: compare the proposed AI-enabled approach with an existing process, simple rule, or manual review pattern.**. Holding the other [conditions](../../glossary.md#condition) fixed is what lets a reviewer interpret the difference.

Finally, connect the evidence to action. Use **Evidence quality: separate measured results from assumptions, anecdotes, vendor claims, and synthetic-data artifacts.** to explain why the observed result matters in the scenario, then state a limitation. The appropriate conclusion is conditional: recommend a next step only if the evidence clears a named threshold or review gate. This pattern—decision, baseline, controlled comparison, limitation, next gate—is the same structure expected in the assignment and rubric.

### Comprehension Check

Before continuing, be able to answer: What is the baseline? What single factor changes? Which evidence would reverse the recommendation? What does the exercise leave unknown?

## Authoritative Reading Bridge

- [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course) — Interactive explanations of core predictive-modeling concepts.
- [scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html) — Authoritative implementation and evaluation guidance.

Use one specific section, control, example, or definition from these sources to qualify the worked example above. The complete curated [list](../../glossary.md#list) and source-use expectations are in [Authoritative Readings and Resources](../../resources.md).
<!-- END COURSE EXPERIENCE REMEDIATION -->
<!-- BEGIN SUBJECT-MATTER LESSON -->
## Subject-Matter Lesson

A prediction task is not defined by a [dataset](../../glossary.md#dataset) alone. It needs a unit of analysis, a target, a prediction time, an action, and an evaluation horizon. “Predict churn” is incomplete until the team states whose churn, as of which date, over what future window, and what intervention follows. Features must be available at prediction time; labels must represent the outcome rather than the action taken in response to an earlier score.

Target leakage occurs when a feature contains information created after the outcome or through the labeling process. It can yield impressive held-out metrics even when a model cannot operate prospectively. The lab constructs a post-outcome code that closely mirrors the target and compares it with legitimate pre-decision measurements. The leaky model should look dramatically better, which is evidence of a broken task definition rather than a breakthrough.

Students should draw a timeline for every candidate feature and remove the leakage [variable](../../glossary.md#variable) before changing [algorithms](../../glossary.md#algorithm). A complete framing also names the cost of false positives and false negatives, the current baseline process, excluded populations, and an abstention or escalation path. Model selection begins only after those decisions are explicit.
<!-- END SUBJECT-MATTER LESSON -->
