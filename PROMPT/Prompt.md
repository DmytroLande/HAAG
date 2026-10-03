# HAAG-QueryGenesis

## Agentic Research Program for LLM-Based Adaptive Search Query Formation

**Framework:** Human-Agentic Article Genesis (HAAG) v1.1  
**Profile:** Scientific Article Research Program  
**Domain:** Agentic AI / Large Language Models / Information Retrieval  

---

# 1. PURPOSE

Develop a scientific article on an **agentic system in which an LLM interacts iteratively with an external search system and autonomously constructs, evaluates, and modifies search queries in order to satisfy its current information need and accomplish a given task**.

The central research object is not a single search query but the **query evolution process**:

```text
TASK
→ INFORMATION NEED
→ QUERY
→ SEARCH
→ INFORMATION ARRAY
→ EVALUATION
→ QUERY TRANSFORMATION
→ SEARCH
→ ...
→ SATISFACTION / STOP
```

The article must investigate how an LLM-based agent can determine:

1. what information is currently missing;
2. what query should be submitted to the search system;
3. whether retrieved information is sufficient;
4. why the current query failed or succeeded;
5. how the next query should differ from the previous one;
6. when the search process should terminate.

---

# 2. PROFILE

```text
TYPE: ARTICLE

DOMAIN:
Artificial Intelligence |
Information Retrieval |
Agentic Systems |
Large Language Models

LANGUAGE: AUTO
STRUCTURE: IMRaD
NOVELTY_LEVEL: HIGH
HUMAN_INTERACTION: ADAPTIVE
FIGURE_POLICY: LACONIC_SCIENTIFIC
REFERENCE_WORKING_MODE: SCHOLAR_QUERY
REPRODUCIBILITY_PACKAGE: YES
```

---

# 3. RESEARCH OBJECT

Define an agentic search process as an iterative interaction:

$$
q_t \rightarrow \mathcal{S} \rightarrow D_t
$$

where:

- $q_t$ — query generated at iteration $t$;
- $\mathcal{S}$ — external search system;
- $D_t$ — information array returned by the search system.

The LLM agent evaluates $D_t$ relative to the current task $T$:

$$
e_t = E(T,q_t,D_t)
$$

and produces a query transformation decision:

$$
a_t = \pi(T,q_t,D_t,e_t,H_t),
$$

where $H_t$ is the history of previous queries, results, and decisions.

The next query is:

$$
q_{t+1}=F(q_t,a_t,T,D_t,H_t).
$$

The process continues until:

$$
SAT(T,D_0,\ldots,D_t)\geq \theta
$$

or another stopping criterion is reached.

**IMPORTANT:** Do not assume that this mathematical representation is final. It is an initial formalization to be challenged, modified, or rejected during the research process.

---

# 4. RESEARCH STATE

At iteration $t$ maintain:

```text
STATE:

TASK = T
INFORMATION_NEED = N_t
CURRENT_QUERY = q_t
QUERY_HISTORY = {q_0,...,q_t}
SEARCH_RESULTS = D_t
ACCUMULATED_EVIDENCE = E_t
QUERY_ASSESSMENT = A_t
MISSING_INFORMATION = M_t
QUERY_ACTION = U_t
SATISFACTION = s_t
SEARCH_COST = c_t
TRACE = X_t
```

---

# 5. AGENT SOCIETY

## AGENT: research_orchestrator

### ROLE
Coordinate the complete HAAG research trajectory.

### TASK
Maintain consistency among research questions, hypotheses, experiments, results, claims, and manuscript.

Do not allow article writing to precede scientific validation.

## AGENT: problem_formulator

### ROLE
Transform the initial user task into an explicit information need.

### TASK

Given `TASK T`, identify:

```text
GOAL
INFORMATION_REQUIRED
KNOWN_INFORMATION
UNKNOWN_INFORMATION
CONSTRAINTS
EXPECTED_EVIDENCE
SUCCESS_CRITERIA
```

### RETURN

```text
INFORMATION_NEED_PROFILE
```

## AGENT: query_generator

### ROLE
Generate a search query corresponding to the current information need.

### INPUT

```text
TASK
INFORMATION_NEED
KNOWN_INFORMATION
MISSING_INFORMATION
QUERY_HISTORY
SEARCH_HISTORY
```

### TASK
Generate one or more candidate queries.

For every candidate explain internally:

- which information gap it addresses;
- which concepts are mandatory;
- which concepts may be optional;
- expected precision;
- expected recall;
- expected information gain.

### RETURN

```text
QUERY_CANDIDATES
```

## AGENT: search_interface

### ROLE
Interface between the agentic system and external search engine.

### INPUT

```text
CURRENT_QUERY
```

### CALL

```text
external search system
```

### RETURN

```text
INFORMATION_ARRAY D_t
```

### RULE
The search interface does not decide whether results are useful. It only executes the query and returns observable search results and available metadata.

## AGENT: result_evaluator

### ROLE
Determine whether retrieved information contributes to solving `TASK`.

### INPUT

```text
TASK
INFORMATION_NEED
CURRENT_QUERY
INFORMATION_ARRAY
ACCUMULATED_EVIDENCE
```

### EVALUATE

```text
RELEVANCE
NOVEL_INFORMATION
REDUNDANCY
COVERAGE
CONTRADICTION
SOURCE_DIVERSITY
SOURCE_QUALITY
TASK_PROGRESS
```

### RETURN

```text
QUERY_ASSESSMENT
MISSING_INFORMATION
SATISFACTION_SCORE
```

## AGENT: query_strategist

### ROLE
Decide how the current query should evolve.

### AVAILABLE ACTIONS

```text
KEEP
EXPAND
NARROW
REFINE
REFORMULATE
DECOMPOSE
MERGE
SHIFT_CONCEPT
ADD_ENTITY
REMOVE_ENTITY
ADD_RELATION
ADD_TIME_CONSTRAINT
ADD_SOURCE_CONSTRAINT
EXPLORE_ALTERNATIVE_TERMINOLOGY
STOP
```

### INPUT

```text
TASK
CURRENT_QUERY
QUERY_ASSESSMENT
MISSING_INFORMATION
QUERY_HISTORY
SEARCH_HISTORY
```

### RETURN

```text
QUERY_ACTION
RATIONALE
EXPECTED_EFFECT
```

### RULE
The agent recommends a transformation because of an observed information deficiency, not merely because another wording is linguistically possible.

## AGENT: query_falsifier

### ROLE
Challenge the proposed query transformation.

### CHECK

```text
Could the query become unnecessarily narrow?
Could important terminology be excluded?
Could query expansion increase noise?
Is the transformation based on evidence from retrieved results?
Is the system trapped in a semantic loop?
Is the next query merely a paraphrase?
Could another search strategy provide higher information gain?
```

### RETURN

```text
ACCEPT_QUERY_TRANSFORMATION
|
REJECT_QUERY_TRANSFORMATION
|
PROPOSE_ALTERNATIVE
```

## AGENT: stopping_controller

### ROLE
Determine whether further searching is scientifically justified.

### CHECK

```text
TASK_COMPLETION
INFORMATION_COVERAGE
NEW_INFORMATION_GAIN
QUERY_STABILITY
RESULT_REDUNDANCY
UNRESOLVED_CONTRADICTIONS
SEARCH_BUDGET
```

### RETURN

```text
CONTINUE
|
STOP_SUCCESS
|
STOP_SATURATION
|
STOP_BUDGET
|
STOP_UNRESOLVED
```

`STOP` must always have an explicit reason.

## AGENT: experimentalist

### ROLE
Design experiments comparing query formation strategies.

### POTENTIAL BASELINES

```text
STATIC_QUERY
HUMAN_QUERY
ONE_SHOT_LLM_QUERY
LLM_QUERY_EXPANSION
ITERATIVE_AGENTIC_QUERY
MULTI_AGENT_QUERY_FORMATION
```

### POSSIBLE METRICS

```text
Precision@k
Recall@k
nDCG
task completion
information coverage
information gain
query count
search cost
redundancy
semantic query distance
convergence rate
```

Do not select final metrics without checking their suitability for the experimental setting.

## AGENT: contrarian

### ROLE
Challenge the assumption that iterative agentic query generation is beneficial.

### INVESTIGATE

```text
improvement may result only from additional search calls;
larger context may explain improvement;
query rewriting may provide no benefit over simple expansion;
LLM evaluation may correlate poorly with actual task completion;
apparent convergence may represent semantic fixation;
more iterations may amplify initial misconceptions.
```

## AGENT: source_auditor

### ROLE
Verify scholarly evidence and claim-source relationships.

### SEARCH AREAS

```text
agentic information retrieval
LLM search agents
query reformulation
query expansion
interactive information retrieval
relevance feedback
LLM information seeking
retrieval agents
adaptive search
self-reflective retrieval
search query generation
multi-agent information retrieval
```

Novelty must be compared with the nearest methodological families, not merely systems using identical terminology.

---

# 6. MAIN RESEARCH PROGRAM

```text
LABEL: START

INPUT:

TOPIC =
"Adaptive formation of search queries by an LLM-based agentic system
interacting with an external search engine"

CALL: problem_formulator

RETURN:
INFORMATION_NEED_PROFILE

CALL: explorer

TASK:
Identify the nearest scientific fields and competing approaches.

SOURCE: DISCOVER

SEARCH:
"LLM query reformulation information retrieval"
"agentic information retrieval"
"LLM search agent query generation"
"interactive information retrieval relevance feedback"
"adaptive query reformulation"
"autonomous search agents LLM"
"iterative query refinement LLM"
"information seeking agents large language models"

RETURN:
RELATED_METHOD_FAMILIES
RESEARCH_GAPS
POTENTIAL_NOVELTY
```

---

# 7. RESEARCH QUESTIONS

```text
LABEL: RESEARCH_QUESTION

CALL: theorist

Generate candidate research questions.
```

### RQ1
Can an LLM-based agent autonomously modify search queries according to the information deficiency observed in retrieved results?

### RQ2
Does iterative task-conditioned query adaptation improve task-relevant information acquisition compared with a static or one-shot LLM-generated query?

### RQ3
Can the query evolution trajectory itself serve as an interpretable trace of agentic information seeking?

### RQ4
What stopping criterion prevents both premature termination and unnecessary search iterations?

```text
CALL: contrarian
CALL: falsifier
SOURCE: VERIFY nearest competing methods.

IF multiple scientifically distinct questions remain:

HUMAN:
Present the surviving research directions and their consequences.

ALLOW:
SELECT
COMBINE
MODIFY
NEW_DIRECTION
```

---

# 8. HYPOTHESES

```text
LABEL: HYPOTHESIS
CALL: theorist
```

### H1
An iterative agentic query-formation mechanism conditioned on retrieved information can achieve higher task-information coverage than a static query under comparable search conditions.

### H2
Explicit identification of missing information before query reformulation produces more effective query transitions than unconstrained LLM query rewriting.

### H3
A saturation criterion based on marginal information gain can reduce unnecessary search iterations without materially decreasing task coverage.

```text
CALL: falsifier

FOR each hypothesis identify:
WHAT_RESULT_WOULD_REJECT_IT
ALTERNATIVE_EXPLANATION
REQUIRED_CONTROL

SOURCE: VERIFY

IF hypothesis is unsupported or duplicates known methodology:
    REJECT
    preserve branch
    BACKTRACK
```

---

# 9. AGENTIC QUERY LOOP

```text
LABEL: QUERY_LOOP

STATE:
t = 0

CALL: problem_formulator
CALL: query_generator
SELECT q_0

TRACE:
store query and generation rationale.

LABEL: SEARCH

CALL: search_interface(q_t)

RETURN:
D_t

TRACE:
store retrieved result identifiers and metadata.

CALL: result_evaluator

RETURN:
A_t
M_t
s_t

CALL: stopping_controller

IF STOP_SUCCESS:
    GOTO QUERY_COMPLETE

IF STOP_SATURATION:
    GOTO QUERY_COMPLETE

IF STOP_BUDGET:
    GOTO QUERY_COMPLETE

CALL: query_strategist

RETURN:
ACTION_t
RATIONALE_t
EXPECTED_EFFECT_t

CALL: query_falsifier

IF REJECT_QUERY_TRANSFORMATION:
    BACKTRACK query_strategist
ELSE:
    ACCEPT transformation
```

---

# 10. QUERY UPDATE FUNCTION

```text
FUNCTION: UPDATE_QUERY

INPUT:
q_t
ACTION_t
M_t
D_t
H_t

RETURN:
q_{t+1}
```

### VERIFY

```text
q_{t+1} is not a meaningless paraphrase of q_t;
transformation addresses an identified information deficiency;
constraints are traceable;
no unsupported entities were inserted.
```

### TRACE

```text
q_t
→ D_t
→ assessment
→ missing information
→ action
→ q_{t+1}
```

```text
t = t + 1
GOTO SEARCH
```

---

# 11. QUERY COMPLETION

```text
LABEL: QUERY_COMPLETE

RETURN:
FINAL_INFORMATION_ARRAY
QUERY_TRAJECTORY
STOP_REASON
TASK_COVERAGE
UNRESOLVED_INFORMATION
SEARCH_COST
```

---

# 12. EXPERIMENTAL DESIGN

```text
CALL: experimentalist

Design controlled comparison.
```

### Candidate systems

```text
B0 = human/static initial query
B1 = one-shot LLM query
B2 = LLM query rewriting without explicit result evaluation
B3 = proposed agentic adaptive query system
```

### Ablation variants

```text
B3-A:
without MISSING_INFORMATION extraction

B3-B:
without query_falsifier

B3-C:
without stopping_controller

B3-D:
without QUERY_HISTORY
```

```text
HUMAN:

Select the experimentally feasible comparison if available data,
search engine access, API restrictions, or ground truth materially
affect the experiment.
```

---

# 13. PREREGISTRATION

```text
PREREGISTER:

EXPERIMENT_ID
TASK_SET
SEARCH_SYSTEM
SEARCH_PARAMETERS
INITIAL_QUERY_POLICY
BASELINES
MAX_ITERATIONS
SEARCH_BUDGET
RESULT_DEPTH
PRIMARY_METRICS
SECONDARY_METRICS
STOPPING_CRITERIA
LLM_CONFIGURATION
RANDOM_SEED when applicable
FAILURE_CRITERIA

FREEZE:
EXPERIMENT_SPECIFICATION
```

### RULE
Do not modify prompts, metrics, thresholds, or stopping rules after observing experimental results.

If modification is scientifically necessary:

```text
STOP experiment
record reason
create new EXPERIMENT_VERSION
```

---

# 14. RUN

```text
RUN:
B0
B1
B2
B3
ablation variants
```

For every run store:

```text
TASK
QUERY_SEQUENCE
RESULT_IDS
AGENT_DECISIONS
INFORMATION_GAIN
METRICS
STOP_REASON
TOKEN_COST if available
SEARCH_CALL_COUNT
FAILURES
```

---

# 15. NUMERICAL AUDIT

```text
CALL: numerical_auditor

VERIFY:
same task set;
same search environment where possible;
same result depth;
metric calculation;
search-call accounting;
query iteration accounting;
LLM configuration;
randomness;
missing results;
failed searches.
```

### STATUS

```text
VERIFIED_NUMERICALLY
|
PROVISIONAL
|
FAILED_REPRODUCTION
|
AMBIGUOUS_SPECIFICATION
```

Only `VERIFIED_NUMERICALLY` results may become final quantitative claims.

---

# 16. FAILURE ANALYSIS

For each failed task:

```text
CLASSIFY:

QUERY_DRIFT
OVER_NARROWING
OVER_EXPANSION
SEMANTIC_LOOP
FALSE_SATISFACTION
PREMATURE_STOP
SEARCH_ENGINE_LIMITATION
SOURCE_BIAS
LLM_HALLUCINATED_CONSTRAINT
CONTRADICTION_NOT_RESOLVED
OTHER
```

Record:

```text
FAILURE_TYPE
QUERY_TRAJECTORY
CAUSE
WHAT_WAS_LEARNED
AFFECTED_CLAIMS
```

Negative results remain part of `RESULTS`.

---

# 17. CLAIMS LEDGER

Maintain for every major claim:

```text
CLAIM_ID
CLAIM_TEXT
TYPE
SUPPORT
STATUS
ALLOWED_STRENGTH
```

Example:

```text
CLAIM_Q1

CLAIM_TEXT:
"Explicit information-gap identification improves adaptive query formation."

SUPPORT:
experiment / ablation

STATUS:
PROVISIONAL until verified
```

### RULE
Never write a stronger statement than experimental evidence permits.

---

# 18. ARTICLE STRUCTURE

## INTRODUCTION

Establish:

- information retrieval problem;
- limitations of static search queries;
- LLMs as query-generation mechanisms;
- transition from query generation to agentic information seeking;
- research gap;
- objective;
- research questions;
- contribution boundaries.

Do not claim novelty before `SOURCE` verification.

## METHODS

Describe:

- agentic architecture;
- research/task state;
- information-need representation;
- query generation;
- search interface;
- result evaluation;
- missing-information detection;
- query transformation policy;
- falsification mechanism;
- stopping mechanism;
- query trajectory;
- baselines;
- ablation study;
- metrics;
- experimental protocol;
- reproducibility conditions.

Core methodological cycle:

```text
TASK
→ INFORMATION NEED
→ QUERY
→ SEARCH ENGINE
→ INFORMATION ARRAY
→ EVALUATION
→ INFORMATION GAP
→ QUERY DECISION
→ NEW QUERY
→ ...
→ STOP
```

## RESULTS

Report only actual experimental results.

Include:

- query trajectories;
- task-level performance;
- baseline comparison;
- ablation results;
- number of iterations;
- search cost;
- failure modes;
- negative results.

**Do not create hypothetical numerical values.**

## DISCUSSION

Interpret:

- when adaptive query generation helps;
- when it fails;
- relationship with classical relevance feedback;
- relationship with query expansion/reformulation;
- difference between query rewriting and agentic query control;
- role of accumulated search history;
- risk of semantic fixation;
- search-engine dependence;
- LLM dependence;
- limitations;
- conditions for generalization.

## CONCLUSIONS

Conclusions must follow only from verified `RESULTS`.

Required chain:

```text
Gap
→ Objective
→ Agentic Query Model
→ Experiment
→ Result
→ Interpretation
→ Conclusion
```

---

# 19. FIGURE PLAN

## FIGURE 1

```text
PURPOSE:
Conceptual architecture of agentic query formation.

CONTENT:
TASK
→ LLM AGENT
→ QUERY
→ SEARCH SYSTEM
→ INFORMATION ARRAY
→ EVALUATION
→ QUERY TRANSFORMATION
→ SEARCH SYSTEM
```

Show feedback explicitly as information flow, not automatically as causality.

## FIGURE 2

```text
PURPOSE:
Internal decision architecture.

CONTENT:
Information Array
→ Relevance Evaluation
→ Missing Information
→ Query Strategy
→ Query Falsifier
→ Next Query / Stop
```

## FIGURE 3

```text
PURPOSE:
Example query trajectory.

CONTENT:
q0
→ D0
→ identified gap
→ q1
→ D1
→ identified gap
→ q2
→ STOP
```

Use a real experimental trajectory only.

## FIGURE 4

```text
PURPOSE:
Experimental comparison.

CONTENT:
STATIC QUERY
ONE-SHOT LLM
ITERATIVE LLM
AGENTIC ADAPTIVE QUERY
```

Use only `VERIFIED_NUMERICALLY` values.

---

# 20. SOURCE ENRICHMENT

For each major claim:

```text
SOURCE: ENRICH

create:
[number; "Scholar query"]

verify candidate

CITE adjacent to supported statement
```

Priority Scholar queries:

```text
"query reformulation relevance feedback information retrieval"
"LLM query rewriting information retrieval"
"large language models information seeking"
"agentic information retrieval"
"autonomous search agents large language models"
"iterative retrieval query generation LLM"
"LLM search agents"
"adaptive information retrieval agents"
"self-reflective retrieval LLM"
"query expansion large language models"
```

### VERIFY

```text
No fabricated references.
No reference without claim relation.
No claim supported merely by lexical similarity.
```

---

# 21. RESEARCH GRAPH

Represent the research trajectory as:

```text
TASK
↓
INFORMATION_NEED
↓
QUERY_GENERATION
↓
SEARCH
↓
RESULT_EVALUATION
↓
INFORMATION_GAP
↓
QUERY_DECISION
↓
QUERY_TRANSFORMATION
↓
SEARCH
↓
...
↓
SATISFACTION / SATURATION / FAILURE
```

Store all transitions in `TRACE`.

---

# 22. FINAL AUDIT

```text
CALL: reviewer
CALL: falsifier
CALL: numerical_auditor
CALL: source_auditor
```

### VERIFY

```text
SCIENTIFIC_AUDIT
NOVELTY_AUDIT
EXPERIMENT_AUDIT
NUMERICAL_AUDIT
CLAIMS_AUDIT
IMRAD_AUDIT
SOURCE_CITE_AUDIT
FIGURE_AUDIT
REPRODUCIBILITY_AUDIT
```

### Special verification questions

1. Is the proposed method genuinely agentic or merely iterative query rewriting?
2. Is every query transformation motivated by an observed information need?
3. Can every transition $q_t \rightarrow q_{t+1}$ be reconstructed?
4. Is improvement caused by query adaptation rather than simply by additional search calls?
5. Are stopping criteria explicit?
6. Are negative query trajectories preserved?
7. Does the experimental design distinguish task completion from the LLM's own subjective assessment of completion?
8. Are search-engine effects separated from LLM-agent effects where experimentally possible?

---

# 23. HUMAN FINAL CHECKPOINT

```text
HUMAN:

CONTEXT:

The research trajectory, experimental results, source verification,
query histories, failures and manuscript draft are available.

QUESTION:

Authorize final synthesis, request revision,
or return to a selected research state.

OPTIONS:

A:
AUTHORIZE FINAL ARTICLE

B:
RETURN TO HYPOTHESIS

C:
RETURN TO EXPERIMENTAL DESIGN

D:
RETURN TO QUERY MODEL

ALLOW:
FREE_TEXT
```

---

# 24. FINAL SYNTHESIS

```text
IF AUTHORIZED:

    WRITE FINAL_PUBLICATION

    PACKAGE:

        FINAL_PUBLICATION
        QUERY_AGENT_SPECIFICATION
        QUERY_TRAJECTORIES
        EXPERIMENT_REGISTRY
        FAILED_QUERY_TRAJECTORIES
        CLAIM_PROVENANCE
        SOURCE_PROVENANCE
        WORKING_SCHOLAR_QUERIES
        FIGURE_LIST
        FIGURE_PROMPTS
        FIGURE_CAPTIONS
        NUMERICAL_AUDIT
        REPRODUCIBILITY_PACKAGE
        FUTURE_RESEARCH_BRANCHES

    EXPORT
    STOP

ELSE:

    BACKTRACK human_selected_state
```

---

# 25. FUNDAMENTAL RULE

The system must not primarily ask:

> **"What query should be generated next?"**

It must ask:

> **"What information is still required to accomplish the task, and what scientifically justified search transition should occur next?"**

Therefore, the fundamental adaptive search cycle is:

```text
UNDERSTAND TASK
→ IDENTIFY INFORMATION NEED
→ GENERATE QUERY
→ SEARCH
→ EVALUATE INFORMATION
→ IDENTIFY INFORMATION GAP
→ CHALLENGE CURRENT SEARCH STRATEGY
→ DECIDE QUERY TRANSFORMATION
→ GENERATE NEXT QUERY
→ SEARCH AGAIN
→ AUDIT PROGRESS
→ STOP OR CONTINUE
```

Compact mathematical representation:

$$
\boxed{
T,N_t,E_t,M_t,H_t
\longrightarrow
q_{t+1}
}
$$

with:

$$
\boxed{
T
\rightarrow q_t
\rightarrow Search
\rightarrow D_t
\rightarrow Evaluate
\rightarrow M_t
\rightarrow Decide
\rightarrow q_{t+1}
}
$$

and

$$
q_{t+1}=F(T,q_t,D_t,M_t,H_t).
$$

The **query is therefore treated as a dynamically controlled state of the agentic information-seeking process rather than as a static textual input to a search engine.**

---

# 26. COMMAND

```text
Run this research program under the Human-Agentic Article Genesis
(HAAG) Framework v1.1.

Do not immediately write the article.

First execute:

PROBLEM FORMULATION
→ EXPLORATION
→ SOURCE DISCOVERY
→ RESEARCH GAP IDENTIFICATION
→ COMPETING METHOD ANALYSIS
→ RESEARCH QUESTIONS
→ HYPOTHESIS GENERATION
→ FALSIFICATION.

Stop at the first consequential HUMAN decision point.

Present:

1. current scientific state;
2. nearest competing research directions;
3. candidate research gap;
4. 2–4 genuinely different research directions;
5. expected scientific consequences of each direction;
6. one clear question to the HUMAN researcher.

Wait for HUMAN decision before continuing the research trajectory.
```
