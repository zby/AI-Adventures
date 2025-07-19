# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but faces two problems: exponential search spaces and unreliable LLM evaluation. Simplicity Theory enables a two-phase approach that reduces this complexity while providing principled evaluation criteria: first find concept combinations that form valid puzzles, then search for solutions to those puzzles—offering our first principled architecture for computational discovery.*

Picture yourself stuck on a problem for weeks. Then while making coffee, two unrelated ideas suddenly click together and everything makes sense. That "aha!" moment is what [Gwern wants to reverse-engineer](https://gwern.net/ai-daydreaming) in AI systems.

His approach is elegant: build AI that combines random facts from its knowledge base, then filters the results for useful insights. Think of it as systematic serendipity—instead of waiting for lightning to strike, you create thousands of controlled lightning storms.

But there are two key gaps. First, randomly combining concepts faces exponential search spaces. Second, LLMs can't reliably evaluate the results.

Consider the math: If you have just 1,000 concepts in your knowledge base, there are roughly 500,000 ways to combine pairs. But real breakthroughs often require combining three, four, or more concepts—Darwin needed population pressure + variation + inheritance + time. For 3-concept insights, you're looking at 166 million combinations. For 4-concept insights? Over 41 billion combinations. Most are meaningless noise like "blue sky + pizza ingredients + bicycle gears + quantum mechanics."

Gwern proposes using LLMs to evaluate usefulness, but this creates a second problem: **LLMs can't reliably distinguish genuine insights from sophisticated noise**. Without principled criteria for recognizing genuine insights, you're drowning in combinations that sound profound but lack real compression power.

This is where Simplicity Theory becomes crucial. It offers more than just better evaluation—it enables a fundamentally different search architecture that breaks the exponential explosion into manageable phases AND provides mathematical criteria for recognizing genuine insights. Instead of searching all possible combinations at once, we can search compositionally: find puzzles first, then find their solutions.

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

But here's the crucial limitation: ST can recognize when you've found a good insight, but it can't tell you which concepts to combine in the first place. It's a powerful filter, not a generator.

This solves Gwern's core problem: distinguishing meaningful insights from sophisticated noise. While an LLM might find both "Darwin's evolution" and "blockchain-powered meditation apps" equally novel and coherent, ST provides mathematical criteria. Real insights create compression gain—they explain more with less. Random combinations typically don't.

The key insight that makes ST practical: complexity is always relative to what you already know. This transforms abstract mathematical theory into concrete calculations that real systems can perform.

## Why ST Enables a Two-Phase Discovery Architecture

ST solves both of Gwern's problems through a two-phase approach that reduces search complexity AND provides principled evaluation:

**Phase 1: Find Valid Puzzles**
- Generate 2-concept combinations from your knowledge base
- Ask LLM: "What puzzle does this combination suggest?"
- **Verify with ST**: Does this create a genuine puzzle (high unexpectedness score)?
- **Key insight**: ST can distinguish real puzzles from pseudo-puzzles that just sound intriguing

**Phase 2: Solve Validated Puzzles**  
- For each validated puzzle, add one new concept at a time
- Ask LLM: "Does this solve the puzzle?"
- **Verify with ST**: Does the LLM explanation create compression gain (collapse complexity)?
- **Key insight**: ST can distinguish real insights from sophisticated-sounding but shallow explanations

This solves the evaluation problem that pure LLM approaches can't handle. While an LLM might rate "Why do teenagers keep messy rooms?" and "Why do organisms fit environments perfectly?" as equally interesting puzzles, ST provides mathematical criteria: the second creates massive unexpectedness (simple to observe, should be nearly impossible to explain with available mechanisms), while the first doesn't.

Here's why this dramatically reduces search space:

**Traditional approach** for 10 concepts, 3-concept insights:
- Search space: C(10,3) = 120 combinations
- All evaluated simultaneously

**Two-phase approach**:
- **Phase 1**: C(10,2) = 45 combinations → find valid puzzles
- **Phase 2**: For each puzzle, try 8 remaining concepts
- **Total search**: 45 + (valid_puzzles × 8)

The key insight: **valid puzzles are rare**. Most concept pairs don't form genuine puzzles under ST's criteria. If only 3 out of 45 combinations create valid puzzles, your total search becomes 45 + (3 × 8) = 69 evaluations instead of 120.

But the advantage compounds exponentially as concepts increase:

**For 100 concepts, 4-concept insights:**
- Traditional: C(100,4) = 3.9 million combinations  
- Two-phase: C(100,2) = 4,950 + (valid_puzzles × 98 remaining concepts)
- If 1% form valid puzzles: 4,950 + (50 × 98) = 9,850 evaluations

That's a **400x reduction** in search space.

This works because real insights have compositional structure. Darwin didn't randomly combine four concepts—he first recognized the adaptation puzzle (organisms perfectly fit environments), then found the missing piece (Malthus's population pressure) that solved it.

The approach transforms random concept-shuffling into targeted puzzle-solving:

**Gwern's approach**: Try millions of combinations → "sky color + pizza ingredients + bicycle gears"
**Two-phase approach**: Find puzzles first → "Why do organisms fit environments so perfectly?" → search for missing pieces → "population pressure + competition"

**Important limitation**: The two-phase approach dramatically reduces search complexity but doesn't eliminate exponentiality entirely. We're still dealing with exponential growth—just with much better constants and aggressive pruning.

As the knowledge base grows or we seek more complex insights (4+ concepts), the search space can still become intractable. The advantage comes from the rarity of valid puzzles, but if your domain has many legitimate puzzles, Phase 2 could still explode combinatorially.

This makes the approach most promising for constrained domains where puzzle density is manageable.

## The Two-Phase Approach in Action: Darwin's Breakthrough

Let's trace how the two-phase approach would work on history's most famous breakthrough. *(Note: This shows the algorithm's logic—we're not claiming Darwin followed this process.)*

**Phase 1: Puzzle Detection**
Darwin had been collecting puzzling observations for years. Consider this concept combination:
- **Concepts**: "organism traits" + "environmental conditions"
- **LLM puzzle question**: "What puzzle does this combination suggest?"
- **LLM response**: "Why do organisms have traits that perfectly match their environments?"
- **ST evaluation**: High unexpectedness score (simple pattern to observe: perfect fit everywhere, but should require countless separate explanations given available mechanisms)

**Validated puzzle identified**: Perfect organism-environment fit requires explanation.

**Phase 2: Solution Search**
Now search for concepts that could solve this puzzle:
- **Puzzle + "divine creation"** → No compression gain (just pushes explanation back)
- **Puzzle + "use and disuse"** → Some compression, but doesn't explain precision
- **Puzzle + "population pressure"** → Massive compression gain!

**October 1838**: Reading Malthus on population pressure provides the missing piece. One simple mechanism—variation + inheritance + overproduction + competition—explains thousands of observations.

**ST's solution evaluation**: Massive compression gain. Many complex explanations collapsed into one simple rule. High unexpectedness score (simple to state, took humanity millennia to discover).

This is exactly what the two-phase approach identifies: valid puzzles in Phase 1, then compression-creating solutions in Phase 2. The key insight—Darwin had recognized the puzzle through careful observation, but the algorithmic approach could systematically detect such puzzles in concept combinations.

This demonstrates the practical power of compositional search.

## What Can We Actually Build Today?

We have a concrete algorithmic approach, but implementation challenges remain.

**The algorithm is clear**: Two-phase compositional search using LLMs for generation and ST for evaluation. Phase 1 finds valid puzzles, Phase 2 searches for solutions.

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

The most promising immediate step: build systems that implement the two-phase approach using language models to approximate ST's complexity calculations, then test whether compositional search actually achieves the predicted efficiency gains.

This isn't just theoretical—it's testable and implementable. Start with constrained domains where you can verify results. Build two-phase discovery tools. Test whether ST-guided compositional search actually outperforms brute-force combination generation.

The computational advantage is clear in theory. The question is whether it holds up in practice.

What domain will you test it in first?
