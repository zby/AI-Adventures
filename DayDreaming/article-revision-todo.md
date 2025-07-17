# Article Revision ToDo: Daydreaming Machines

## Reviewer's Bottom-Line Assessment
**Strong empirical case made**, but logic wobbles in two key areas:
1. Equating "unexpectedness" with "usefulness" 
2. Assuming complexity terms (Cv and C) can be estimated cheaply enough for large-scale search

## Critical Issues to Address

### 🔴 HIGH PRIORITY

#### 1. Fix the "Unexpected = Useful" Equivalence Problem
**Issue**: A coincidence (meeting cousin on random flight) is highly unexpected but rarely useful. Incremental engineering tweaks can be very useful with negligible unexpectedness.

**Action Items**:
- [ ] Add a second filter (actionability or goal-relevance) instead of claiming U alone subsumes usefulness
- [ ] Separate unexpectedness from usefulness in the framework
- [ ] Retain U as a saliency detector, then add a goal-conditioned utility scorer
- [ ] Revise section "Why Unexpectedness Captures Usefulness" to acknowledge this limitation

#### 2. Address Cv Estimation Complexity
**Issue**: Computing generation complexity requires rich world-model - almost as hard as discovery problem itself.

**Action Items**:
- [ ] Clarify how Cv is approximated in practice
- [ ] Point to practical proxies (e.g., model perplexity before vs. after adding a rule)
- [ ] Move away from ideal Kolmogorov length toward implementable measures
- [ ] Acknowledge computational bottlenecks in "Making It Work" section

#### 3. Fix "Negative U for Random Combinations" Claim
**Issue**: If concept pair already carries semantic load ("population growth" + "heritability"), even random pairs can have C << Cv.

**Action Items**:
- [ ] Qualify the claim about negative U for random pairs
- [ ] Note that randomness usually but not always yields low-value links
- [ ] Emphasize that what matters is sampling bias, not randomness per se
- [ ] Revise the comparison table to be more nuanced

### 🟡 MEDIUM PRIORITY

#### 4. Acknowledge Existing Hybrid Search Work
**Issue**: Recent generative-design systems already use bias sampling + discriminators - similar to proposed approach.

**Action Items**:
- [ ] Research recent work on reflection-based LLM agents
- [ ] Find generative design pipelines that use guided generation + compression testing
- [ ] Add section acknowledging this existing lineage
- [ ] Compare/contrast framework with current approaches
- [ ] Strengthen proposal by building on existing work rather than ignoring it

#### 5. Add Empirical Validation Hooks
**Action Items**:
- [ ] Propose small-scale benchmark (e.g., rediscovering Mendelian ratios from pea-plant corpus)
- [ ] Design test for compression criterion
- [ ] Outline how to measure framework effectiveness
- [ ] Add concrete next steps for validation

### 🟢 LOW PRIORITY

#### 6. Strengthen Factual Scaffolding
**The reviewer confirmed these are accurate - just polish**:
- [ ] Add more precise citations for Gwern's three-axis scoring
- [ ] Link to specific Dessalles formula sources
- [ ] Enhance Darwin timeline documentation
- [ ] Cite Shannon's explicit statement about semantics being "irrelevant"

## Feasibility Analysis Framework
**Add discussion of current bottlenecks**:

| Pipeline Stage | Current AI Techniques | Bottleneck |
|----------------|----------------------|------------|
| Track explanatory debt | Knowledge-graph entropy & iterative retrieval | Reliable domain coverage |
| Generate candidate links | Diverse sampling + importance weighting | Scalability to millions of pairs |
| Score compression gain | Approximate Kolmogorov tools, code-length heuristics | Robustness & compute cost |
| Filter for utility | Task-specific reward models, human-in-the-loop | Alignment with human goals |

## Key Sections to Revise

### 1. "Why Unexpectedness Captures Usefulness" 
- [ ] Rename to separate these concepts
- [ ] Add two-stage filtering approach
- [ ] Acknowledge limitations of U alone

### 2. "Making It Work: Guided Generation + Smart Selection"
- [ ] Add practical implementation details
- [ ] Address computational complexity
- [ ] Reference existing hybrid approaches

### 3. Add new section: "Computational Pragmatics"
- [ ] Discuss estimation challenges
- [ ] Propose practical proxies for complexity measures
- [ ] Address scalability concerns

### 4. Conclusion
- [ ] Acknowledge computational challenges more honestly
- [ ] Position as research direction rather than solved problem
- [ ] Reference next steps for empirical validation

## Research to Complete
- [ ] Find 3-5 recent papers on reflection-based LLM agents
- [ ] Research generative design systems using guided search
- [ ] Look up specific examples of compression-based discovery systems
- [ ] Find practical Kolmogorov complexity approximation methods
- [ ] Research "explanatory debt" tracking in current AI systems

## Target Outcome
Transform from "persuasive critique into actionable research blueprint" by addressing logical gaps while preserving the strong empirical case and historical examples that work well. 