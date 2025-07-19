# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but this is computationally absurd. Simplicity Theory provides a mathematical framework that could actually work—offering our first principled approach to evaluating insights, though major implementation challenges remain.*

Picture yourself stuck on a problem for weeks. Then while making coffee, two unrelated ideas suddenly click together and everything makes sense. That "aha!" moment is what [Gwern wants to reverse-engineer](https://gwern.net/ai-daydreaming) in AI systems.

His approach is elegant: build AI that combines random facts from its knowledge base, then filters the results for useful insights. Think of it as systematic serendipity—instead of waiting for lightning to strike, you create thousands of controlled lightning storms.

But there's a fatal flaw. Randomly combining concepts is computationally absurd.

Consider the math: If you have just 1,000 concepts in your knowledge base, there are roughly 500,000 ways to combine pairs. But real breakthroughs often require combining three, four, or more concepts—Darwin needed population pressure + variation + inheritance + time. Now you're looking at hundreds of millions of combinations, most of which are meaningless noise like "blue sky + pizza ingredients + bicycle gears."

Gwern proposes using LLMs to evaluate usefulness, and this does work for basic filtering (as we've shown experimentally). But LLM-based evaluation lacks systematic principles—it can distinguish obviously good ideas from obviously bad ones, but struggles with the crucial middle ground where breakthrough insights often live. Without principled criteria for recognizing genuine insights, you're still drowning in sophisticated-sounding but ultimately shallow combinations.

This is where Simplicity Theory becomes crucial. It offers a mathematical framework for the one thing Gwern's missing: distinguishing breakthrough insights from meaningless associations. While it doesn't solve the search problem entirely, it could make AI discovery systems actually feasible.

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

## Why ST Improves Gwern's Approach—But Doesn't Solve Everything

ST transforms random concept-shuffling into targeted puzzle-solving:

**Gwern's approach**: Try millions of combinations → "sky color + pizza ingredients + bicycle gears"
**ST-guided approach**: Find puzzles first → "Why do organisms fit environments so perfectly?" → search for missing pieces

This is dramatically more efficient. Instead of blindly combining concepts, you identify areas where simple patterns need complex explanations—then search for the insight that could collapse that complexity.

Darwin exemplifies this: He recognized that perfect organism-environment fit was a massive puzzle (simple to observe, hard to explain), then found the missing piece (Malthus's population pressure) that made it all click.

But ST faces a crucial limitation: **different types of breakthroughs have different computational costs.**

**Single-puzzle breakthroughs** like Darwin's can become tractable—the adaptation mystery was widely recognized, requiring one key connection.

**Multi-puzzle breakthroughs** remain computationally intractable. Einstein's relativity required recognizing that space-time, mass-energy, and gravity were interconnected puzzles that needed solving together. Nobody saw that connection coming.

## Proof of Concept: How ST Would Have Evaluated Darwin's Breakthrough

Let's trace how ST's framework applies to history's most famous breakthrough. *(Note: This is retrospective analysis—we're not claiming ST would have predicted this insight.)*

**October 1838**: Darwin had been collecting puzzling observations for years. Galápagos finches with different beaks, pigeon breeders creating dramatic variations, fossil sequences showing change over time. Each needed its own explanation—a patchwork of complex mechanisms.

**The puzzle**: Perfect organism-environment fit everywhere you look. Simple to describe, but based on available mechanisms (divine creation, use/disuse, climate), should require countless separate explanations.

**The breakthrough moment**: Reading Malthus on population pressure. Suddenly, one simple mechanism—variation + inheritance + overproduction + competition—explained everything.

**ST's evaluation**: Massive compression gain. Thousands of observations collapsed into one explanatory rule. High unexpectedness score (simple to state, took humanity millennia to discover).

This is exactly what ST identifies: when many complex explanations can collapse into one simple mechanism. But here's the key—Darwin had already recognized the puzzle. ST helped him evaluate the solution, not find it.

This points to what we can actually build today.

## What Can We Actually Build Today?

The honest answer: we have promising pieces, but no complete system yet.

**What already works**: AI can generate creative concept combinations. Modern LLMs successfully connect disparate ideas when prompted appropriately—this validates Gwern's basic premise.

**What we need**: A reliable way to evaluate which combinations represent genuine insights versus sophisticated noise. This is where ST becomes crucial.

**The current gap**: While ST provides the theoretical framework for evaluation, we haven't built practical systems that can reliably implement it at scale.

Two approaches show promise:

**CompLog (Formal Logic Route)**: The [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates that ST's compression calculations actually work computationally. It encodes knowledge as logical predicates, then measures compression ratios to identify unexpected patterns. Proven effective, but requires manually translating natural language concepts into formal logic—impractical for real-world knowledge systems where concepts like "teenager" or "population pressure" resist clean logical encoding.

**LLM Approximation Route**: Use language models to estimate ST's complexity measures directly with natural language. For example, estimating generation complexity (Cv) through negative log-probability under the base model, and description complexity (C) through token compression length. This bypasses CompLog's encoding bottleneck but remains unproven at scale.

Interestingly, we tested this second approach: we asked LLMs to combine Gwern's essay with Simplicity Theory concepts and see what insights emerged. The result? They independently discovered the core argument of this very article—that ST could solve Gwern's evaluation problem (see Appendix). This suggests LLM-based concept combination paired with principled evaluation frameworks might actually work.

The path forward likely involves hybrid systems: LLMs generate combinations, ST-guided evaluation filters them, humans verify the results.

But even with working ST evaluation, we face fundamental scaling limits. Darwin-style breakthroughs—where the puzzle is already recognized—could become manageable. Einstein-style breakthroughs that require recognizing multiple interconnected puzzles simultaneously remain computationally intractable.

The bottom line: we have theory, we have pieces, but substantial experimentation is needed to determine if this actually works at scale.

## What This Could Enable

If we solve the evaluation problem, several applications become possible:

**Research acceleration**: Instead of manually sifting through literature, AI could flag when papers create genuine compression opportunities—highlighting where breakthrough insights might be hiding.

**Human-AI discovery teams**: Researchers propose connections based on intuition, AI evaluates them using ST's mathematical framework. Each side does what it's best at.

**Better AI training**: Currently, training AI on "good insights" requires expensive human ratings. ST could provide automatic scoring, enabling AI systems trained specifically for discovery rather than just coherent text generation.

The vision is compelling: research tools that actively support discovery rather than just information storage. But we're still far from practical systems.

## The Path Forward

We have the pieces for a solution to Gwern's discovery problem. ST provides mathematical principles for recognizing insights. LLMs can generate concept combinations. The missing piece is reliable evaluation at scale.

The most promising approach: build systems that approximate ST's compression calculations using language models, then test whether they can consistently distinguish breakthrough insights from sophisticated noise.

This isn't just theoretical—it's testable. Start with constrained domains where you can verify results. Build evaluation tools. Test whether ST-guided filtering actually improves on pure LLM evaluation.

The question isn't whether this is theoretically possible. The question is when someone will build it.

What domain will you start with?
