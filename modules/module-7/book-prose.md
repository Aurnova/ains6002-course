# Module 7 Book Prose

## Interpretability and stakeholder explanation

What explanations are appropriate for different audiences?

### Professional Scenario

You are advising **an analytics team choosing a predictive [model](../../glossary.md#model) for an operational decision**. The immediate task is to decide what evidence would make a recommendation credible, what [risks](../../glossary.md#risk) remain unresolved, and what should happen next. The module's work product is: **predictive modeling report with [baseline](../../glossary.md#baseline) comparison, [validation](../../glossary.md#validation) evidence, and model card focused on interpretability and stakeholder explanation: Produce a feature-importance or counterfactual explanation memo.**.

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

Return to the professional situation for this module: You are advising **an analytics team choosing a predictive model for an operational decision**. The immediate task is to decide what evidence would make a recommendation credible, what risks remain unresolved, and what should happen next. The module's work product is: **predictive modeling report with baseline comparison, validation evidence, and model card focused on interpretability and stakeholder explanation: Produce a feature-importance or counterfactual explanation memo.**. The team should not begin by selecting the most sophisticated tool. First, rewrite the situation as a decision: **what must be decided, by whom, using which evidence, and under which constraints?** That sentence establishes the boundary of the analysis.

Next, create an inspectable baseline. For this module, a useful baseline should make **Problem framing: define the decision, population, workflow, or system boundary before choosing a method.** visible rather than hiding it inside an unsupported conclusion. Preserve the starting data or case facts, record the initial result, and identify the assumption most likely to change the recommendation. Then make one controlled comparison using **Baseline discipline: compare the proposed AI-enabled approach with an existing process, simple rule, or manual review pattern.**. Holding the other [conditions](../../glossary.md#condition) fixed is what lets a reviewer interpret the difference.

Finally, connect the evidence to action. Use **Evidence quality: separate measured results from assumptions, anecdotes, vendor claims, and synthetic-data artifacts.** to explain why the observed result matters in the scenario, then state a limitation. The appropriate conclusion is conditional: recommend a next step only if the evidence clears a named threshold or review gate. This pattern—decision, baseline, controlled comparison, limitation, next gate—is the same structure expected in the assignment and rubric.

### Comprehension Check

Before continuing, be able to answer: What is the baseline? What single factor changes? Which evidence would reverse the recommendation? What does the exercise leave unknown?

## Authoritative Reading Bridge

- [scikit-learn Model Evaluation](https://scikit-learn.org/stable/modules/model_evaluation.html) — Metrics, scoring, validation, and error analysis.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — Risk framing for predictive systems in practice.

Use one specific section, control, example, or definition from these sources to qualify the worked example above. The complete curated [list](../../glossary.md#list) and source-use expectations are in [Authoritative Readings and Resources](../../resources.md).
<!-- END COURSE EXPERIENCE REMEDIATION -->
<!-- BEGIN SUBJECT-MATTER LESSON -->
## Subject-Matter Lesson

Interpretability is not one property. A coefficient describes an additive model [parameter](../../glossary.md#parameter), permutation importance measures the increase in held-out error after a feature is disrupted, and a local explanation allocates one prediction relative to a reference. These quantities answer different questions and should not be presented as causal effects.

Correlated features create ambiguity because either [variable](../../glossary.md#variable) can carry similar predictive information. Permuting one may leave its partner intact and understate the shared signal; coefficients can become unstable or split weight. Importance can also reflect leakage, missingness patterns, or historical inequity rather than a legitimate decision basis.

The lab fits a standardized linear predictor and compares absolute coefficients with held-out permutation error increases. Students should add a duplicate of one feature and observe how both explanation types change while predictive performance may remain stable. A stakeholder explanation should state the model, population, data period, reference, method, uncertainty, and known limitations, then connect the result to an allowed decision rather than implying that changing a feature will cause the prediction to change in the real world.
<!-- END SUBJECT-MATTER LESSON -->
