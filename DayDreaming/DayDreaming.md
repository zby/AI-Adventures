# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but faces two problems: exponential search spaces and unreliable LLM evaluation. Simplicity Theory enables a two-phase approach that reduces this complexity while providing principled evaluation criteria: first find concept combinations that form valid puzzles, then search for solutions to those puzzles—offering our first principled architecture for computational discovery.*

Picture yourself stuck on a problem for weeks. Then while making coffee, two unrelated ideas suddenly click together and everything makes sense. That "aha!" moment is what [Gwern wants to reverse-engineer](https://gwern.net/ai-daydreaming) in AI systems.

His approach is elegant: build AI that combines random facts from its knowledge base, then filters the results for useful insights. Think of it as systematic serendipity—instead of waiting for lightning to strike, you create thousands of controlled lightning storms.

But there are two key gaps: the **combinatorial explosion problem** (exponential search spaces from random concept combinations) and the **evaluation problem** (LLMs can't reliably distinguish genuine insights from sophisticated noise).

Consider the math: If you have just 1,000 concepts in your knowledge base, there are roughly 500,000 ways to combine pairs. But real breakthroughs often require combining three, four, or more concepts—Darwin needed population pressure + variation + inheritance + time. For 3-concept insights, you're looking at 166 million combinations. For 4-concept insights? Over 41 billion combinations. Most are meaningless noise like "blue sky + pizza ingredients + bicycle gears + quantum mechanics."

Without principled criteria for recognizing genuine insights, you're drowning in combinations that sound profound but lack real compression power.

To solve the combinatorial explosion problem and evaluation problem, we need principled evaluation criteria AND a way to mathematically decompose the search space. Simplicity Theory provides the first piece—principled evaluation criteria. But our key insight is that ST's filtering capabilities enable the second piece: mathematical decomposition of the search space through a two-phase approach. Instead of searching all possible combinations at once, we can search hierarchically: find puzzles first, then find their solutions.

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

This limitation actually points to the solution: if ST excels at filtering but not generation, we should structure our search to maximize filtering opportunities. Instead of generating all possible concept combinations and filtering for insights directly, we can split the problem hierarchically—first generate and filter for valid puzzles, then generate and filter for insights that solve those puzzles.

## Why ST Enables a Two-Phase Discovery Architecture

Here's how ST solves both problems through hierarchical search that reduces complexity AND provides principled evaluation:

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

The key advantage: ST provides principled evaluation criteria, and its Phase 1 filtering enables splitting the problem hierarchically instead of searching all combinations directly.

Here's why this dramatically reduces computational cost:

The key insight: **mathematical decomposition reduces total combinations**. Instead of searching C(n,k1+k2) combinations directly, you search C(n,k1) + (valid_puzzles × C(remaining,k2)). Since **valid puzzles are rare**, the second term is much smaller than the original search space.

**Example with 1000 concepts, 4-concept insights:**
- Traditional: Direct search of all 4-concept combinations = 41+ billion 
- Two-phase: C(1000,2) + (valid_puzzles × C(998,2)) = 499,500 + (valid_puzzles × 497,503)

**How rare are valid puzzles?** Most concept combinations like "bicycle + quantum mechanics" or "pizza + weather patterns" don't suggest meaningful puzzles that meet ST's criteria (high unexpectedness with simple descriptions). Valid puzzles should be genuinely rare—perhaps 0.1% or even 0.01% of combinations.

- If 0.1% form valid puzzles: 499,500 + (500 × 497,503) = ~249 million combinations  
- If 0.01% form valid puzzles: 499,500 + (50 × 497,503) = ~25 million combinations

**The rarer valid puzzles are, the more dramatic the computational advantage becomes.**

**Important limitation**: The two-phase approach dramatically reduces search complexity but doesn't eliminate exponentiality entirely. We're still dealing with exponential growth—just with much better constants and aggressive pruning. The advantage comes from the rarity of valid puzzles, but if your domain has many legitimate puzzles, Phase 2 could still explode combinatorially.

## Hierarchical Search in Action: Darwin's Breakthrough

Let's simulate how hierarchical search would discover and solve the adaptation puzzle that led to evolution theory. *(Note: This simulates our algorithm applied to 19th-century naturalist knowledge—we're not claiming anyone followed this process.)*

**Phase 1: Puzzle Discovery**
Starting with the naturalist knowledge base, systematically combine concepts:
- **Concept combination**: "Organism traits" + "Environmental conditions"
- **LLM puzzle generation**: "What puzzle does this combination suggest?"
- **Generated puzzle**: "Why do organisms have traits that perfectly match their environments?"
- **ST evaluation**: 
  - Description complexity (C): Very simple—"perfect environmental fit observed everywhere"
  - Generation complexity (Cv): Extremely high—would require countless separate design explanations
  - Unexpectedness score (U): Massive gap → **Validated puzzle**

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

This demonstrates how systematic puzzle identification (Phase 1) focuses computational resources on validated targets, then systematic insight search (Phase 2) efficiently finds breakthroughs—the practical power of hierarchical over direct search.

## What Can We Actually Build Today?

We have a concrete algorithmic approach, but implementation challenges remain.

**The algorithm is clear**: hierarchical search using LLMs for generation and ST for evaluation. Phase 1 finds valid puzzles, Phase 2 finds insights for those puzzles.

**The implementation challenge**: Building reliable ST approximations that work at scale with natural language concepts.

Two approaches show promise:

**CompLog (Formal Logic Route)**: The [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates that ST's compression calculations actually work computationally. It encodes knowledge as logical predicates, then measures compression ratios to identify unexpected patterns. Proven effective, but requires manually translating natural language concepts into formal logic—impractical for real-world knowledge systems where concepts like "teenager" or "population pressure" resist clean logical encoding.

**LLM Approximation Route**: Use language models to estimate ST's complexity measures directly with natural language. For example, estimating generation complexity (Cv) through negative log-probability under the base model, and description complexity (C) through token compression length. This bypasses CompLog's encoding bottleneck but needs validation at scale.

To validate the basic premise, we tested whether LLMs could independently discover meaningful connections between Gwern's essay and Simplicity Theory. All five LLMs tested independently discovered the core argument of this article—that ST could solve Gwern's evaluation problem (see Appendix). This validates that AI daydreaming works conceptually, though it doesn't test the ST complexity approximation approach itself.

The implementation path: build the system using LLM approximations of ST, then test whether it achieves the predicted computational advantages.

The algorithmic breakthrough is conceptual. The engineering challenge is making it robust and scalable.

## What This Could Enable

If we solve the evaluation problem, several applications become possible:

**Research acceleration**: Instead of manually sifting through literature, AI could flag when papers create genuine compression opportunities—highlighting where breakthrough insights might be hiding.

**Human-AI discovery teams**: Researchers propose connections based on intuition, AI evaluates them using ST's mathematical framework. Each side does what it's best at.

**Better AI training**: Reasoning LLMs like OpenAI's o1 are trained primarily on mathematical problems because they provide verifiable examples at scale—you can automatically check if the answer is correct. But this only improves logical reasoning, not insight generation. ST could provide another source of verifiable training examples focused on insights rather than math. Instead of expensive human ratings for "good insights," ST could provide automatic scoring based on compression gain, enabling AI systems trained specifically for discovery rather than just coherent text generation.

The vision is compelling: research tools that actively support discovery rather than just information storage. But we're still far from practical systems.

## The Path Forward

We have a concrete algorithmic approach: ST provides mathematical principles for recognizing insights, LLMs handle generation and basic evaluation, and the architecture dramatically reduces search complexity.

The path forward: build systems using LLM approximations of ST, then test whether hierarchical search achieves the predicted efficiency gains. Start with constrained domains where you can verify results.

The computational advantage is clear in theory. The question is whether it holds up in practice.

What domain will you test it in first?
