# Discipline Adapters

Use these adapters to adjust the material-type structure. The skill can handle any discipline; if no exact adapter exists, infer the closest pattern from the material's concepts, methods, evidence, and audience.

## Philosophy

Philosophy materials are not handled as information summaries. Their center is the relation between problems, concepts, arguments, objections, replies, textual basis, and interpretive traditions.

Default philosophy structure:

```markdown
## 1. Problem
## 2. Core Concepts And Distinctions
## 3. Thesis And Argument Reconstruction
## 4. Objections, Counterexamples, And Replies
## 5. Scholarly Discussion
## 6. Understanding Points
## References
```

Reading rules:

- Identify the philosophical question: what is being answered, clarified, defended, or rejected?
- Define key terms before evaluating arguments.
- Reconstruct the main argument as conclusion, premises, inferential links, and hidden assumptions.
- Separate objections from replies.
- For original or classical texts, track concept, passage-level argument, and interpretive traditions. Use short quotations only when wording matters, and explain the role of the quotation immediately.
- For analytic philosophy papers, track premise-conclusion structure, counterexamples, objections, replies, and scope.
- For history of philosophy, track textual basis, interpretive route, prior controversy, and the author's intervention.
- For ethics and political philosophy, track normative principles, cases, counterexamples, and application boundaries.
- Evaluate only through concepts, argument structure, textual basis, or scholarly controversy; avoid personal reaction.

## Course Notes And Primary-Text Courses

Use this adapter for lecture sequences, textbook-based courses, classical-text courses, legal or canonical-text courses, and other recurring instructional materials.

Default structure:

```markdown
## 1. [First major problem or argument node]
## 2. [Next problem or argument node]
## 3. [Continue in the controlling source's order]
## Scholarly Discussion
## Understanding Points
## References
```

Reading rules:

- Let the lecture or syllabus define the session boundary, but let the most coherent source control the internal order when the slide order is only presentational.
- If the user designates a primary textbook, monograph, article, statute, canonical text, or reading packet as the main line, extract its section order, main claim, subclaims, textual/evidential basis, reasoning steps, and tensions before drafting.
- Keep classroom examples, slide bullets, and local notes as examples or emphasis within the relevant argument node.
- Do not write the final note as a report about source handling. Make the concept, problem, author, institution, method, or historical process the grammatical subject.
- If short primary-source quotations are useful, place them inside the relevant explanation and immediately explain how the quoted wording advances the concept or argument.
- Use section summaries, concept tables, or diagrams only where they genuinely reduce cognitive load.

## Humanities And Social Sciences

Prioritize:

- research question or interpretive problem
- conceptual vocabulary
- theoretical framework
- school, tradition, or debate
- evidence type
- method and source base
- contribution and limits

Do not merely list authors. Organize by themes, positions, methods, historical stages, or debates.

## History

Prioritize:

- historical problem
- chronology and periodization
- actors and institutions
- source base
- causal explanation
- contingency and turning points
- historiographical debate
- what the account explains and leaves open

Do not collapse history into a timeline. Use chronology only when it explains change.

## Literature And Cultural Studies

Prioritize:

- text type and literary form
- narrative structure or poetic sequence
- voice, perspective, and rhetoric
- imagery, motifs, symbols, and genre conventions
- historical, cultural, and intertextual context
- interpretive debates

For classic or canonical literature, preserve form and sequence. For non-classic literary or cultural essays, foreground theme, social stakes, and rhetorical strategy.

## Law And Policy

Prioritize:

- legal or policy question
- governing rule, standard, or framework
- facts, institutional setting, or policy background
- exceptions, thresholds, and conditions
- interpretive dispute
- application to cases or scenarios
- consequences, risks, and limits

Separate rule, interpretation, application, and evaluation. Do not treat a policy preference as legal authority.

## Education And Psychology

Prioritize:

- research or practice problem
- theoretical construct
- population and setting
- method or intervention
- measures and evidence
- findings
- limitations and transferability
- implications for learning, assessment, or practice

Keep the difference between descriptive findings, causal claims, and practical recommendations visible.

## Medicine, Public Health, And Life Sciences

Prioritize:

- clinical, biological, or public-health problem
- population, organism, mechanism, or pathway
- study design and evidence quality
- outcome measures
- findings
- uncertainty, limitations, and risk
- practical or research implications

Avoid giving medical advice. Preserve uncertainty and scope conditions.

## AI And Technical AI Materials

Separate:

- problem definition
- method or mechanism
- model/system architecture
- data and evaluation
- claimed contribution
- limits and failure modes
- application scenario
- social, ethical, or governance implications

Avoid conflating benchmark performance with product value, social impact, or philosophical importance.

For landmark technical papers, explicitly preserve:

- the central replacement or design claim
- the core formula or algorithmic operation, if present
- architecture blocks and information flow
- complexity or efficiency comparisons
- dataset and benchmark setup
- headline results and what they actually prove
- ablation findings
- stated limitations and later boundary conditions

Do not let later industry narratives overwhelm what the original paper actually demonstrated.

## Business And Management

Separate:

- managerial problem
- theory or framework
- evidence or case basis
- mechanism of value creation
- organizational conditions
- managerial implications
- boundary conditions and risks

For case material, distinguish what happened, why it happened, what the author claims it shows, and what can actually be generalized.

## Finance And Asset Pricing

Use for financial economics, investments, corporate finance theory, asset pricing, portfolio theory, derivatives, market efficiency, and risk-return models.

Separate:

- pricing or allocation problem
- investor, firm, or market assumptions
- risk measure and return measure
- equilibrium or no-arbitrage mechanism
- mathematical relationship or pricing equation
- economic interpretation of each term
- empirical or practical implications
- assumptions, limits, and later critiques

For theoretical finance papers, preserve:

- the model's setup and decision variables
- the distinction between individual optimization and market equilibrium
- whether risk is total risk, diversifiable risk, systematic risk, downside risk, or another measure
- whether the result depends on a risk-free asset, borrowing/lending, homogeneous expectations, market clearing, or frictionless markets
- what the theorem predicts and what it does not test empirically

Do not translate every finance paper into generic managerial advice. Keep the mathematical economics structure visible.

## AI And Business Overlap

Track six layers together:

- technical capability
- business problem
- organizational workflow
- value creation
- data/governance risk
- implementation boundary

Do not treat AI strategy writing as pure technical writing. Do not treat product claims as proven research findings.
