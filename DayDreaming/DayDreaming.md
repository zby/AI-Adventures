# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but faces two problems: exponential search spaces and unreliable LLM evaluation. Simplicity Theory enables a two-phase approach that reduces this complexity while providing principled evaluation criteria: first find concept combinations that form valid puzzles, then search for solutions to those puzzles—offering our first principled architecture for computational discovery.*

Picture yourself stuck on a problem for weeks. Then while making coffee, two unrelated ideas suddenly click together and everything makes sense. That "aha!" moment is what [Gwern wants to reverse-engineer](https://gwern.net/ai-daydreaming) in AI systems.

His approach is elegant: build AI that combines random facts from its knowledge base, then filters the results for useful insights. Think of it as systematic serendipity—instead of waiting for lightning to strike, you create thousands of controlled lightning storms.

But there are two key gaps. First, randomly combining concepts faces exponential search spaces. Second, LLMs can't reliably evaluate the results.

Consider the math: If you have just 1,000 concepts in your knowledge base, there are roughly 500,000 ways to combine pairs. But real breakthroughs often require combining three, four, or more concepts—Darwin needed population pressure + variation + inheritance + time. For 3-concept insights, you're looking at 166 million combinations. For 4-concept insights? Over 41 billion combinations. Most are meaningless noise like "blue sky + pizza ingredients + bicycle gears + quantum mechanics."

Gwern proposes using LLMs to evaluate usefulness, but this creates a second problem: **LLMs can't reliably distinguish genuine insights from sophisticated noise**. Without principled criteria for recognizing genuine insights, you're drowning in combinations that sound profound but lack real compression power.

This is where Simplicity Theory becomes crucial. It offers more than just better evaluation—it provides the principled filtering needed for mathematical decomposition of the search space. Instead of searching all possible combinations at once, we can search hierarchically: find puzzles first, then find their solutions.

Here's how.

## How to Recognize a Breakthrough: Simplicity Theory

Walk into a teenager's bedroom and find it spotless. Easy to describe, right? Just three words: "completely clean room." But given what you know about teenagers, this should be nearly impossible to generate. That gap between "simple to describe" and "hard to explain" signals something interesting is happening.

This intuition is the core of [Simplicity Theory](https://simplicitytheory.telecom-paris.fr/)—Jean-Louis Dessalles' mathematical framework for recognizing breakthrough insights. ST measures this gap with a simple formula:

**U = Cv - C**

Where:
- **C (description complexity)**: How simply can you describe the observation? 
- **Cv (generation complexity)**: How hard would it be for the world to produce this situation?
- **U (unexpectedness score)**: The gap that signals a breakthrough opportunity

When this gap is large, you've found a puzzle worth solving.

The magic happens when insights collapse that gap. Darwin's evolution explained thousands of separate "organism perfectly fits environment" observations with one simple mechanism: variation + selection + inheritance + time. Massive compression gain—many complex explanations became one simple rule.

But here's the crucial limitation: ST can recognize when you've found a good insight, but it can't tell you which concepts to combine in the first place. It's a powerful filter, not a generator. This suggests we need an architecture that maximizes filtering opportunities while minimizing generation costs.

## Why ST Enables a Two-Phase Discovery Architecture

We can use ST to solve both of Gwern's problems through a two-phase approach that reduces search complexity AND provides principled evaluation:

**Phase 1: Search for Valid Puzzles**
- **Search space**: All concept combinations from your knowledge base  
- **Search strategy**: Start with smaller combinations, expand systematically
- **Generation**: Ask LLM: "What puzzle does this combination suggest?"
- **Evaluation**: ST filters for genuine puzzles (high unexpectedness score)
- **Terminate**: When sufficient puzzles found or search budget exhausted

**Phase 2: Search for Insights**  
- **Search space**: For each validated puzzle, all combinations of additional concepts
- **Search strategy**: Start with 0 additional concepts, expand systematically  
- **Generation**: Ask LLM: "What insight explains this puzzle given these concepts?"
- **Evaluation**: ST filters for genuine insights (compression gain)
- **Terminate**: When insight found or search budget exhausted

The key advantage: ST addresses both of Gwern's problems. It provides principled evaluation criteria (distinguishing genuine insights from sophisticated noise), and its filtering in Phase 1 enables mathematical decomposition of the search space. Instead of searching all possible combinations directly, we can split the problem hierarchically.

Here's why this dramatically reduces computational cost:

**Traditional approach**:
- Search all concept combinations for insights directly
- Apply expensive insight generation to every combination up to some size limit

**Two-phase approach**:
- **Phase 1**: Search concept combinations for puzzles  
- **Phase 2**: Search additional concepts for insights, but only for validated puzzles
- **Total cost**: C(n,k1) + (valid_puzzles × C(remaining,k2))

The key insight: **mathematical decomposition reduces total combinations**. Instead of searching C(n,k1+k2) combinations directly, you search C(n,k1) + (valid_puzzles × C(remaining,k2)). Since **valid puzzles are rare**, the second term is much smaller than the original exponential search space.

The advantage compounds as concepts increase:

**Example with 1000 concepts, 4-concept insights (2 for puzzle + 2 for solution):**
- Traditional: C(1000,4) = 41,417,124,750 combinations
- Two-phase: C(1000,2) + (valid_puzzles × C(998,2)) = 499,500 + (valid_puzzles × 497,503)

**How rare are valid puzzles?** Most concept combinations like "bicycle + quantum mechanics" or "pizza + weather patterns" don't suggest meaningful puzzles that meet ST's criteria (high unexpectedness with simple descriptions). Valid puzzles should be genuinely rare—perhaps 0.1% or even 0.01% of combinations.

- If 0.1% form valid puzzles: 499,500 + (500 × 497,503) = ~249 million combinations  
- If 0.01% form valid puzzles: 499,500 + (50 × 497,503) = ~25 million combinations

**The rarer valid puzzles are, the more dramatic the computational advantage becomes.**

**Important limitation**: The two-phase approach dramatically reduces search complexity but doesn't eliminate exponentiality entirely. We're still dealing with exponential growth—just with much better constants and aggressive pruning. The advantage comes from the rarity of valid puzzles, but if your domain has many legitimate puzzles, Phase 2 could still explode combinatorially.

## The Two-Phase Approach in Action: Darwin's Breakthrough

Let's trace how the two-phase approach would work on the adaptation puzzle that led to evolution theory. *(Note: This simulates our algorithm—we're not claiming anyone followed this process.)*

**Phase 1 Complete**: Previous naturalists had identified a validated puzzle: "Why do organisms have traits that perfectly match their environments?" This creates massive unexpectedness under ST criteria—simple to observe (perfect fit everywhere), but should require countless separate explanations given available mechanisms.

**Phase 2: Insight Generation**
Now systematically apply expensive computational resources to this validated puzzle:
- **0 additional concepts**: Try generating insights from puzzle alone
  - "Organisms inherit acquired traits" → ST evaluation: Some compression, insufficient
- **1 additional concept**: Try each remaining concept with the puzzle
  - + "Divine creation" → "God designed perfect fit" → ST evaluation: Some compression, but creates new complexity puzzle (how does the designer work?)
  - + "Population pressure" → "Competition drives selection for fit" → ST evaluation: Massive compression gain!

**Search stops**: Breakthrough insight found at 1 additional concept level.

**The breakthrough**: Population pressure + variation + inheritance creates a simple mechanism explaining thousands of complex observations.

**ST's insight evaluation**: Massive compression gain achieved. What required countless separate explanations now follows from one simple rule.

This demonstrates the two-phase approach: systematic puzzle search identifies valid targets (Phase 1), then systematic insight search focuses computational resources where they matter most (Phase 2). The algorithm would systematically detect validated puzzles and direct search efforts to find the missing insights.

This demonstrates the practical power of hierarchical search over direct search.

## What Can We Actually Build Today?

We have a concrete algorithmic approach, but implementation challenges remain.

**The algorithm is clear**: Two-phase hierarchical search using LLMs for generation and ST for evaluation. Phase 1 searches concept combinations for valid puzzles, Phase 2 searches additional concepts for insights (but only for validated puzzles).

**What already works**: AI can generate creative concept combinations and evaluate puzzles/solutions when prompted appropriately. Modern LLMs successfully perform both tasks—this validates the basic feasibility.

**The implementation challenge**: Building reliable ST approximations that work at scale with natural language concepts.

Two approaches show promise:

**CompLog (Formal Logic Route)**: The [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates that ST's compression calculations actually work computationally. It encodes knowledge as logical predicates, then measures compression ratios to identify unexpected patterns. Proven effective, but requires manually translating natural language concepts into formal logic—impractical for real-world knowledge systems where concepts like "teenager" or "population pressure" resist clean logical encoding.

**LLM Approximation Route**: Use language models to estimate ST's complexity measures directly with natural language. For example, estimating generation complexity (Cv) through negative log-probability under the base model, and description complexity (C) through token compression length. This bypasses CompLog's encoding bottleneck but needs validation at scale.

To validate the basic premise of AI concept combination, we tested whether LLMs could independently discover meaningful connections between Gwern's essay and Simplicity Theory. The result? All five LLMs tested independently discovered the core argument of this very article—that ST could solve Gwern's evaluation problem (see Appendix). This validates that AI daydreaming as a concept works, though it doesn't test the ST complexity approximation approach itself.

The implementation path is clear: build the two-phase system using LLM approximations of ST, then test whether it achieves the predicted computational advantages.

The algorithmic breakthrough is conceptual. The engineering challenge is making it robust and scalable.

## What This Could Enable

If we solve the evaluation problem, several applications become possible:

**Research acceleration**: Instead of manually sifting through literature, AI could flag when papers create genuine compression opportunities—highlighting where breakthrough insights might be hiding.

**Human-AI discovery teams**: Researchers propose connections based on intuition, AI evaluates them using ST's mathematical framework. Each side does what it's best at.

**Better AI training**: Reasoning LLMs like OpenAI's o1 are trained primarily on mathematical problems because they provide verifiable examples at scale—you can automatically check if the answer is correct. But this only improves logical reasoning, not insight generation. ST could provide another source of verifiable training examples focused on insights rather than math. Instead of expensive human ratings for "good insights," ST could provide automatic scoring based on compression gain, enabling AI systems trained specifically for discovery rather than just coherent text generation.

The vision is compelling: research tools that actively support discovery rather than just information storage. But we're still far from practical systems.

## The Path Forward

We have more than just the pieces for a solution to Gwern's discovery problem—we have a concrete algorithmic approach. ST provides mathematical principles for recognizing insights. LLMs can generate concept combinations and evaluate puzzles/solutions. The two-phase architecture dramatically reduces search complexity.

The most promising immediate step: build systems that implement the two-phase approach using language models to approximate ST's complexity calculations, then test whether hierarchical search actually achieves the predicted efficiency gains.

This isn't just theoretical—it's testable and implementable. Start with constrained domains where you can verify results. Build two-phase discovery tools. Test whether ST-guided hierarchical search actually outperforms direct insight generation.

The computational advantage is clear in theory. The question is whether it holds up in practice.

What domain will you test it in first?
