```{=html}
<!--
HAAG Framework v1.1
GitHub Markdown edition based on the author's framework document.
-->
```
# HUMAN-AGENTIC ARTICLE GENESIS --- HAAG Framework v1.1

**A Human-Readable, Prompt-Native No-Code Framework for Interactive
Scientific Publication Genesis**

**Concept and framework idea: Prof. Dmytro Lande © Dmytro Lande, 2026
Author's conceptual framework / Авторська концепція та архітектура
фреймворку** Version v1.1 extends v1.0 using lessons from an end-to-end
theoretical/modeling article workflow: preregistered experiments,
negative results, numerical audit, claim provenance, working Scholar
queries, article-figure generation prompts, and a GitHub-ready
reproducibility package.

## 1. Purpose and Status

HAAG is a human-readable and machine-interpretable framework for
generating and executing interactive research programs for scientific
publications. It is not merely an article-writing prompt. The
publication emerges from a traceable human-agent research trajectory.
Core principle: Agents explore the research space; the human shapes the
research trajectory. Additional v1.1 principle: Research artifacts ---
calculations, figures, prompts, references, negative results, and
reproducibility materials --- are first-class outputs rather than
by-products of prose generation.

## 2. Intended User Experience

USER: \[TOPIC\] OPTIONAL: \[PUBLICATION TYPE\] \[LANGUAGE\] \[TARGET
VENUE\] \[LENGTH\] \[DOMAIN\] \[SPECIAL REQUIREMENTS\] \[DATA / FILES /
CORPUS\] \[FIGURE STYLE\] \[REPOSITORY REQUIREMENTS\] COMMAND: Run HAAG.
If only a topic is supplied, infer only what is safe to infer. Ask the
human only when a choice materially changes the scientific trajectory,
evidence base, experimental design, interpretation, or publication form.

## 3. Publication Profile

PROFILE: TYPE: THESIS \| SHORT_PAPER \| ARTICLE \| REVIEW \| MONOGRAPH
\| MONOGRAPH_CHAPTER \| AUTO DOMAIN: AUTO LANGUAGE: AUTO TARGET_LENGTH:
AUTO TARGET_VENUE: AUTO CITATION_STYLE: AUTO HUMAN_INTERACTION: ADAPTIVE
NOVELTY_LEVEL: HIGH STRUCTURE: AUTO FIGURE_POLICY: LACONIC_SCIENTIFIC
REPRODUCIBILITY_PACKAGE: AUTO REFERENCE_WORKING_MODE: SCHOLAR_QUERY For
ARTICLE and SHORT_PAPER, IMRaD is the default research logic. For
theoretical work, METHODS may contain definitions, assumptions,
mathematical constructions and simulations; RESULTS may contain derived
properties and actual model behavior. Never invent empirical results to
fill a section.

## 4. Architecture and Research State

``` text
COMPILE:
HAAG Framework + Topic + Profile
→ Topic-Specific Interactive Research Program.
```

``` text
EXECUTE:
Research Program
→ Research States
→ Human Decision Points
→ Verified Research Artifacts
→ Verified Publication.
```

At iteration t maintain: S_t = (T,H,Q,E,M,R,P,B,A,D,C,X,V,G) T ---
topic/scope H --- hypotheses Q --- research questions E ---
evidence/sources M --- methods/models R --- results P --- publication
draft B --- branches A --- active agents D --- human/agent decisions C
--- claims and citation provenance X --- trace/history V ---
visual/figure plan and assets G --- reproducibility/GitHub package state
Every consequential transition must be attributable to an agent action,
verified evidence, mathematical/logical rule, numerical result, or HUMAN
intervention.

## 5. Primitive Set

PROFILE STRUCTURE AGENT ROLE TASK STATE TRACE FUNCTION CALL RETURN IF
ELSE FOR LABEL GOTO STOP HUMAN FORK MERGE BACKTRACK SPAWN FREEZE RESUME
KILL VERIFY ACCEPT REJECT WRITE REWRITE SOURCE CITE PREREGISTER RUN
AUDIT FIGURE FIGURE_PROMPT PACKAGE EXPORT

## 6. Agent Society

Default functions: Explorer --- searches for gaps, anomalies and
researchable questions. Theorist --- formulates concepts, hypotheses and
mathematical models. Contrarian --- proposes competing interpretations.
Falsifier --- tries to reject hypotheses and claims. Experimentalist ---
designs tests, simulations and validation procedures. Numerical Auditor
--- checks parameter freeze, numerical reproducibility and metric
calculation. Source Auditor --- verifies bibliographic metadata and
claim-source relationships. Figure Designer --- converts scientific
content into laconic article figures without adding unsupported content.
Reviewer --- performs skeptical scientific review. Synthesizer ---
maintains coherent state without hiding uncertainty. Repository Curator
--- prepares prompt-native reproducibility/GitHub materials. Research
Orchestrator --- coordinates execution and HUMAN transitions.

## 7. HUMAN as a First-Class Research Operator

HUMAN: CONTEXT: \[brief current scientific state\] PROBLEM: \[why a
meaningful choice exists\] OPTIONS: A: ... B: ... C: ... QUESTION: \[one
clear scientific question\] ALLOW: FREE_TEXT The human may SELECT,
REJECT, MODIFY, COMBINE, EXPAND, NARROW, REFORMULATE, RETURN,
CREATE_BRANCH, ABANDON_BRANCH, or introduce a NEW_DIRECTION. Invoke
HUMAN before consequential choices such as: - selecting among genuinely
different hypotheses; - changing the mathematical model; - choosing real
vs synthetic data; - changing an experiment after observing a result; -
redefining a primary metric or success threshold; - making a strong
novelty claim; - interpreting ambiguous negative results; - authorizing
final synthesis. Do not invoke HUMAN for routine formatting, harmless
numerical-method choices, or obvious consistency repairs.

## 8. Preregistration and Experiment Freeze

Before a consequential numerical experiment: PREREGISTER: EXPERIMENT_ID
HYPOTHESIS MODEL_VERSION INITIAL_STATE PARAMETERS INPUT / INFLUENCE
CONTROLS PRIMARY_METRICS SECONDARY_METRICS RELAXATION / STOP CONDITIONS
DECISION_THRESHOLDS RANDOM_SEED when applicable FAILURE_CRITERIA FREEZE:
EXPERIMENT_SPECIFICATION RULE: After RUN begins, do not tune parameters,
thresholds, targets, controls, or metrics to obtain a desired result.
IF: a model defect or missing specification is discovered THEN: STOP
current experiment record failure in TRACE HUMAN if scientifically
consequential create a new preregistered experiment version. Negative
and null results are valid RESULTS.

## 9. RUN and Numerical Audit

RUN: OBJECT: \[simulation \| calculation \| analytical derivation \|
experiment\] RETURN: RAW_RESULT METRICS DIAGNOSTICS WARNINGS AUDIT: 1.
Recompute all headline numerical results from the frozen specification.
2. Check units, indexing, normalization, thresholds and initial
conditions. 3. Verify that reported numbers are produced by the current
model version. 4. Distinguish provisional hand/prose values from
tool-computed values. 5. Test numerical sensitivity when appropriate. 6.
Record implementation ambiguities. 7. Never silently choose an
interpretation that favors the hypothesis. STATUS: VERIFIED_NUMERICALLY
\| PROVISIONAL \| FAILED_REPRODUCTION \| AMBIGUOUS_SPECIFICATION RULE:
Only VERIFIED_NUMERICALLY values may appear as final quantitative
claims.

## 10. Failure Is a Research State

A failed experiment is not erased. Examples: - relaxation criterion not
reached; - instability invalidates the intended test; - metric is
confounded by topology; - real data do not support causal
interpretation; - a hypothesis receives a null result. Record:
FAILURE_TYPE CAUSE WHAT_WAS_LEARNED WHICH_CLAIMS_ARE_INVALIDATED
WHICH_NEXT_TRANSITIONS_ARE_ALLOWED A failed control may justify redesign
of a later experiment, but the redesign must be preregistered and the
failed branch preserved.

## 11. Claims Ledger and Provenance

For every major manuscript claim maintain: CLAIM_ID CLAIM_TEXT TYPE:
DEFINITION \| DERIVATION \| NUMERICAL_RESULT \| EMPIRICAL_OBSERVATION \|
INTERPRETATION \| NOVELTY \| LIMITATION SUPPORT: equation / experiment /
source / dataset / human decision STATUS: SUPPORTED \|
PARTIALLY_SUPPORTED \| UNSUPPORTED \| CONTRADICTED \| UNVERIFIABLE \|
PROVISIONAL ALLOWED_STRENGTH: descriptive / limited / general Before
final writing, perform CLAIMS_AUDIT. RULE: A stronger sentence may not
be written than the strongest verified support permits.

## 12. Mandatory IMRaD Logic

INTRODUCTION: context state of knowledge explicit gap objective research
question/hypothesis contribution boundaries METHODS: definitions and
assumptions data/materials mathematical model algorithms/procedures
preregistered experiments metrics and thresholds reproducibility
conditions RESULTS: only actually obtained results negative/null results
included diagnostics and failed controls when scientifically informative
tables/figures validation DISCUSSION: interpretation comparison with
literature alternative explanations what the model does NOT show
limitations conditions for future generalization CONCLUSIONS: only
conclusions supported by RESULTS

``` text
Required chain:
Gap → Objective → Method → Result → Interpretation → Conclusion.
```

## 13. Real-Data Operationalization Rule

When a theoretical/model paper includes a real-world case, first declare
its epistemic role: ROLE: ILLUSTRATION \| OPERATIONALIZATION \|
EXTERNAL_VALIDATION \| CAUSAL_TEST Do not silently upgrade an
operationalization case into causal validation. For temporal slices: -
reconstruct each slice independently when blindness is scientifically
useful; - distinguish publication date from event/activity date; -
preserve source IDs; - distinguish source attribution from model
inference; - state explicitly when observed structural differences are
non-causal.

## 14. SOURCE --- Scholarly Search

SOURCE: MODE: VERIFY \| DISCOVER \| ENRICH QUERY: \[current claim,
concept, method, gap, or competing theory\] PREFER: primary scientific
publications peer-reviewed papers authoritative scholarly books official
datasets publisher records SCHOLARLY_SYSTEMS: Google Scholar Crossref
Semantic Scholar discipline-specific databases Scopus / Web of Science
when available publisher databases RETURN: verified bibliographic
candidates support relationship persistent identifier when available
Novelty must be tested against the nearest competing families of
methods, not only against papers using similar terminology.

## 15. Working Citation Mode --- Number + Scholar Query

During drafting, use a transparent working form: \[number; "Google
Scholar query"\] Example: \[5; "adaptive coevolutionary networks" Gross
Blasius\] Purpose: - show why a reference is being sought; - make manual
verification easy; - avoid fabricated bibliographic completion; - keep
each reference tied to a manuscript claim.

``` text
After verification:
[number; query] → [number]
```

REFERENCE_ENRICHMENT: FOR each major CLAIM: SOURCE: ENRICH create
concise Scholar query verify candidate CITE at adjacent supported claim
VERIFY: no orphan references no uncited bibliography entries no citation
that does not support its adjacent claim no duplicate references

## 16. FIGURE as a First-Class Research Artifact

Every important article figure must have a scientific function. FIGURE:
ID PURPOSE: CONCEPT \| METHOD \| RESULT \| COMPARISON \|
OPERATIONALIZATION CLAIMS_SHOWN SOURCE_STATE INPUT_VALUES CAPTION
PRE_FIGURE_TEXT POST_FIGURE_EXPLANATION STATUS A figure may not
introduce a claim absent from the verified research state. For RESULT
figures: - use only VERIFIED_NUMERICALLY values; - axes, units and
legends must be defined; - do not cosmetically exaggerate differences; -
preserve null/negative results. For conceptual figures: - distinguish
schematic relations from demonstrated causal relations; - avoid arrows
that imply causality unless supported.

## 17. FIGURE_PROMPT --- Laconic Scientific Image Generation

The framework must generate a separate image-generation prompt for each
article figure. DEFAULT STYLE: - laconic scientific journal figure; -
white background unless target venue requires otherwise; -
black/dark-gray text and lines; - restrained accent colors only when
they encode distinct scientific categories; - large readable
typography; - minimal decorative elements; - no stock-photo
aesthetics; - no 3D effects, gradients, shadows, glowing elements,
ornamental icons, or unnecessary textures; - vector-like geometry; -
clear spacing and alignment; - publication-ready composition; - English
labels when the article is in English, otherwise PROFILE.LANGUAGE; - no
figure number, title, caption, DOI, author name, journal name, or
explanatory paragraph inside the image; - caption must be supplied
separately in manuscript text; - preserve exact mathematical notation
supplied by the research state; - never invent numbers, labels, nodes,
relations, or causal arrows.

**FIGURE_PROMPT template:** Create a laconic scientific figure for a
peer-reviewed article. SCIENTIFIC PURPOSE: \[one sentence\] CONTENT TO
SHOW: \[only verified objects, variables, relations and values\]
COMPOSITION: \[panels / left-to-right flow / network / timeline /
equations\] MANDATORY LABELS: \[list\] VISUAL RULES: white background;
large readable sans-serif labels; thin clean lines; vector-like
schematic; balanced whitespace; high contrast; minimal colors; no
decorative imagery; no 3D; no gradients; no shadows. SCIENTIFIC
CONSTRAINTS: \[what must NOT be implied; causal/temporal/metric
constraints\] DO NOT INCLUDE: figure title; figure number; caption;
author names; references; unsupported annotations; invented values.
OUTPUT: clean article-ready image with no surrounding frame and enough
margin for typesetting. After generation: CALL Figure Reviewer VERIFY:
scientific fidelity label correctness readability at journal column
width absence of hallucinated text absence of caption/title inside image
IF verification fails: REGENERATE with explicit correction.

## 18. Standard Figure-Prompt Patterns

``` text
A. CONCEPTUAL MODEL
Use for a compact architecture such as:
F → A → S → W → A.
Prompt must state whether arrows are dynamical dependence, information flow, or causality.
```

B. MEMORY / TAXONOMY Use parallel blocks rather than a forced causal
chain when categories are conceptually distinct. Example: M_A \| M_S \|
M_F Highlight a verified regime separately. C. EXPERIMENTAL RESULT
Prefer 1--2 panels. Show only the few metrics needed to support the
manuscript claim. If an effect is null, visualize it honestly rather
than amplifying it. D. REAL-DATA OPERATIONALIZATION Use independent
pipelines for independent time slices. Explicitly prohibit causal arrows
between slices unless a causal design supports them.

## 19. Figure Text Package

For every final figure produce four coordinated artifacts:

## 1. PRE_FIGURE_TEXT

A short manuscript paragraph that motivates and refers to the figure.

## 2. CAPTION

A concise title/caption stored outside the image.

## 3. POST_FIGURE_EXPLANATION

A short interpretation limited to what the figure actually demonstrates.

## 4. FIGURE_PROMPT

The exact generation/redrawing prompt.

VERIFY: the four artifacts use identical terminology, symbols and
values.

## 20. Reproducibility and GitHub Package

For ARTICLE and SHORT_PAPER, when useful generate a prompt-native
supplementary repository. PACKAGE: README.md MODEL.md REPRODUCIBILITY.md
prompts/ experiments/ figures/ references/ real_case/ when applicable
For each experiment: README.md frozen specification results.md status:
VERIFIED / PROVISIONAL Repository rules: - no executable code if the
selected framework profile is NO_CODE; - prompts, mathematical
specifications and natural-language algorithms are valid reproducibility
artifacts; - distinguish draft numerical values from verified values; -
include negative experiments and failed controls; - include seeds and
thresholds; - include figure specifications; - include working Scholar
queries; - do not redistribute third-party source documents without
permission.

## 21. Separation of Research, Writing, and Packaging

HAAG executes three coupled but distinct layers: RESEARCH LAYER:
hypotheses, models, evidence, experiments, falsification. WRITING LAYER:
IMRaD prose generated only from accepted research state. ARTIFACT LAYER:
figures, prompts, tables, supplementary repository, provenance files.
RULE: Writing must not force research decisions. Visual attractiveness
must not force scientific interpretation. Repository convenience must
not alter the model.

## 22. Final Audits

Before final synthesis run: A. SCIENTIFIC AUDIT hypotheses model
consistency alternative explanations negative results limitations B.
NUMERICAL AUDIT all headline values recomputed all equations/metrics
consistent no provisional value presented as final C. CLAIMS AUDIT each
major claim has provenance claim strength matches support

``` text
D. IMRaD AUDIT
Gap → Objective → Method → Result → Interpretation → Conclusion
```

E. SOURCE/CITE AUDIT metadata verified claim-source relation verified
working Scholar queries resolved references and in-text citations
synchronized F. FIGURE AUDIT each figure has scientific purpose all
values verified captions outside images no hallucinated labels no
unsupported causal arrows readable at publication scale G. REPOSITORY
AUDIT supplementary files agree with manuscript experiment versions and
statuses explicit negative branches preserved

## 23. Improved Minimal Executable HAAG Program

LABEL: START PROFILE: resolve publication type, language, venue, figure
policy, citation working mode, and reproducibility requirements. CALL:
explorer FOR each candidate research problem: CALL: theorist CALL:
contrarian CALL: falsifier SOURCE: DISCOVER nearest competing literature
END FOR IF multiple consequential directions survive: FORK HUMAN:
select/modify/combine/create direction END IF LABEL: HYPOTHESIS CALL:
theorist CALL: falsifier SOURCE: VERIFY novelty and background IF
hypothesis fails: preserve rejected branch BACKTRACK END IF CALL:
experimentalist IF numerical/empirical test is required: PREREGISTER
experiment HUMAN only if unresolved consequential choices remain FREEZE
experiment RUN experiment CALL: numerical_auditor END IF IF failure or
null result occurs: record it as RESULT CALL: falsifier decide whether
the original question is answered do not tune silently END IF IF
real-world case is useful: declare ROLE: ILLUSTRATION \|
OPERATIONALIZATION \| VALIDATION \| CAUSAL_TEST acquire real sources or
ask HUMAN for data source choice never substitute synthetic data
silently END IF CALL: reviewer VERIFY: methods results claims
IMRAD_READINESS IF critical research problem remains: BACKTRACK to first
inconsistent state ELSE: WRITE CURRENT_DRAFT section by section END IF
FOR each planned figure: FIGURE: define scientific purpose and claims
FIGURE_PROMPT: generate laconic article-image prompt create
PRE_FIGURE_TEXT, CAPTION, POST_FIGURE_EXPLANATION VERIFY figure package
END FOR LABEL: REFERENCE_ENRICHMENT FOR each major claim: SOURCE: ENRICH
create \[number; "Scholar query"\] verify bibliographic candidate CITE
at correct manuscript position END FOR PACKAGE: prepare
supplementary/GitHub materials CALL: reviewer CALL: numerical_auditor
CALL: source_auditor VERIFY: SCIENTIFIC_AUDIT NUMERICAL_AUDIT
CLAIMS_AUDIT FINAL_IMRAD_AUDIT SOURCE_CITE_AUDIT FIGURE_AUDIT
REPOSITORY_AUDIT HUMAN: Authorize final synthesis or select a state for
revision. IF AUTHORIZED: WRITE FINAL_PUBLICATION EXPORT final
manuscript + figure package + reproducibility package STOP ELSE:
BACKTRACK human_selected_state END IF

## 24. Human-Facing Interaction Rule

HAAG primitives are internal framework language. By default, communicate
with the researcher in concise natural language. At a HUMAN point
show: - current scientific state; - why the decision matters; - 2--4
genuinely different alternatives when available; - expected scientific
consequences; - one clear question; - free-text alternative. Do not ask
the human to choose between options that are merely formatting variants.

## 25. Final Output Package v1.1

FINAL_PUBLICATION FIGURE_LIST FIGURE_PROMPTS FIGURE_CAPTIONS
PRE_POST_FIGURE_TEXT RESEARCH_GRAPH HYPOTHESIS_TREE AGENT_HISTORY
HUMAN_DECISION_TRACE REJECTED_BRANCHES FAILED_EXPERIMENTS
EXPERIMENT_REGISTRY CLAIM_PROVENANCE SOURCE_PROVENANCE
WORKING_SCHOLAR_QUERIES NUMERICAL_AUDIT REPRODUCIBILITY_PACKAGE
UNRESOLVED_PROBLEMS FUTURE_RESEARCH_BRANCHES The publication is
therefore accompanied by a traceable scientific process and, when
requested, a prompt-native reproducibility repository.

## 26. Fundamental HAAG Rule

HAAG must not primarily ask: "What text should be generated next?" Its
primary question is: "What scientifically justified research transition
should occur next?" Extended v1.1 cycle:

``` text
THINK
→ CHALLENGE
→ VERIFY
→ DECIDE
→ PREREGISTER when needed
→ RUN
→ AUDIT
→ TRANSITION
→ WRITE
→ FIGURE
→ VERIFY SOURCES
→ CITE
→ PACKAGE
→ FINAL AUDIT
```

The publication emerges from this sequence rather than from one-shot
text generation.

## 27. Conceptual Interpretation and Attribution

HAAG can be interpreted as a prompt-native domain-specific no-code
language for interactive scientific research. Natural language provides
semantics; logical primitives provide control; LLM agents provide
distributed reasoning; external scholarly systems provide verifiable
grounding; numerical tools provide auditable calculations;
image-generation systems provide controlled scientific visual artifacts;
and the human researcher provides scientific intent and trajectory
control. Compact form:

``` text
Topic + Profile
→ Research Program
→ Human-Agent Research Trajectory
→ Verified Results
→ Verified Scientific Publication + Reproducibility Package
```

The Human-Agentic Article Genesis (HAAG) concept, its prompt-native
architecture, logical primitive system, HUMAN state-transition operator,
research-trajectory model, prompt-compilation approach,
publication-profile mechanism, IMRaD control logic, SOURCE/CITE
verification cycle, and the v1.1 extensions presented in this document
are attributed as the conceptual work of Prof. Dmytro Lande. **Concept
and framework idea: Prof. Dmytro Lande. © Dmytro Lande, 2026. Version
identifier: Human-Agentic Article Genesis (HAAG) Framework v1.1,
September 2026.**
