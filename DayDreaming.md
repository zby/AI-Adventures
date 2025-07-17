# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

[Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) brilliantly identifies a core limitation of current AI: the lack of background processing that drives human creativity. But his solution—randomly combining facts and filtering for "usefulness"—has a fatal flaw: it never defines what makes an insight actually valuable.

The missing piece is a formal framework for measuring genuine insight quality. [Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) provides exactly this: a way to distinguish breakthrough insights from meaningless novelty.

## The Core Problem: "Useful" Remains Undefined

Gwern correctly identifies that LLMs lack the continuous background processing of the human [default mode network](https://en.wikipedia.org/wiki/Default_mode_network)—the mental activity that keeps working on problems even when we're not actively thinking. Current AI is "frozen" between interactions, missing the subconscious connections that drive breakthrough insights.

His proposed solution would generate random combinations of facts and judge them for "novelty," "coherence," and "usefulness." But while novelty is trivial to generate and coherence is checkable, usefulness remains completely undefined.

Consider these two combinations:

- **Evolution + Malthus' population theory → Natural selection**
- **"The sky is blue" + "Pizza has cheese" → "Blue sky pizza cheese"**

Both pass the novelty test (they're new). Both could pass coherence (they're grammatically sensible). But only one changed the world. Without operationalizing this difference, any "daydreaming" system drowns in sophisticated nonsense.

[Information theory](https://en.wikipedia.org/wiki/Information_theory) doesn't help—it measures bits, not meaning. The real challenge isn't generating novel combinations (current AI does this infinitely), but distinguishing valuable insights from random noise.

## The Solution: Simplicity Theory's Insight Framework

[Jean-Louis Dessalles' Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) offers exactly what Gwern's proposal needs: a computable way to measure insight value.

**Core principle: Unexpectedness = Generation Complexity - Description Complexity**

Something becomes genuinely interesting when it's simpler to describe than to generate. This isn't about information quantity, but about *complexity reduction* that reveals hidden patterns.

Applied to our examples:

**Evolution + Malthus**: High generation complexity (crossing distant domains) but low description complexity (elegant unifying principle). Result: High unexpectedness = genuine insight.

**"Sky + Pizza"**: Low generation complexity (trivial combination) and high description complexity (no unifying principle). Result: Low unexpectedness = meaningless novelty.

This framework operationalizes "usefulness" as pattern revelation—insights that compress complex phenomena into elegant explanations.

## Making It Work: A Practical Implementation Path

The beauty of this approach is immediate experimental accessibility. Unlike training new foundation models, anyone can prototype insight generation today:

### 1. Generate Motivated Combinations
Instead of random fact pairing, use existing LLMs to explore problem-specific concept neighborhoods:
- Prompt models to connect concepts around specific challenges
- Focus on cross-domain connections where breakthrough insights typically emerge
- Generate batches targeting real problems, not abstract combinations

### 2. Measure Insight Quality
Implement Simplicity Theory metrics to evaluate generated connections:
- **Generation Complexity**: How unlikely was this combination to occur?
- **Description Complexity**: How many bits needed to explain the connection?
- **Pattern Elegance**: Does the combination reveal underlying structure?

### 3. Filter and Validate
Rank combinations by unexpectedness score and test practical utility:
- Eliminate high description complexity outputs
- Prioritize connections that compress information elegantly
- Validate on real problems to refine the measurement framework

This democratizes insight research—turning theoretical proposals into something any developer can experiment with. No GPU clusters required, just clever prompting and principled evaluation.

## Why This Matters for AI Development

Real insight isn't random combination—it's motivated search. Darwin's breakthrough emerged from years of wrestling with species adaptation. Malthus' essay provided the missing piece, but only because Darwin was actively engaged with the evolution problem.

This suggests three requirements for genuine AI insight generation:

1. **Formal measurement of insight quality** (Simplicity Theory provides this)
2. **Problem-motivated search** (not democratic attention to all combinations)
3. **Pattern recognition training** (optimizing for complexity reduction, not just correctness)

For LLM creators, this means training models to optimize for insightfulness using Simplicity Theory metrics as reward functions. Current reasoning RL (like OpenAI's o1) focuses on mathematical correctness. Add a complementary criterion: **insight value**—rewarding responses that reveal elegant patterns.

> **By the way:** Simplicity Theory could also serve as an *alternative* reward function for reasoning LLMs, not just a complement. Instead of optimizing purely for mathematical correctness, models could optimize for elegant explanations that compress complex problems into simpler patterns. This might be particularly valuable for problems where multiple valid solutions exist, but only some reveal deeper insights about the underlying structure. Mathematical proofs that reveal why something is true (pattern revelation) vs. proofs that merely verify correctness (computational verification) represent fundamentally different types of mathematical reasoning.

## From Theory to Practice

**Researchers** can immediately test this framework with existing tools. Build datasets comparing human-judged insight quality against Simplicity Theory metrics. Validate that complexity reduction correlates with practical utility.

**Product builders** can implement insight-driven features that provide contextually relevant connections rather than random novelty. Users prefer AI that "understands what I'm really trying to solve" over systems generating sophisticated but irrelevant text.

**The path forward**: implement insight measurement frameworks before building elaborate background processing systems. Solve the measurement problem first, then scale the search.

## Conclusion: Beyond Beautiful Nonsense

Gwern's insight about AI needing background processing is brilliant, but his proposal fails at the foundational level—defining what makes something worth discovering. Without measuring insight quality, any "daydreaming" system generates beautiful nonsense.

The distinction between mere novelty and genuine insight will separate truly intelligent systems from sophisticated text generators. Simplicity Theory gives us the tools to make that distinction computable.

---

*This critique itself emerged from motivated search—not random combination of Gwern's essay with complexity theory, but goal-directed exploration of how to operationalize "interestingness." The connection worked because it solved a specific problem: measuring insight quality.* 