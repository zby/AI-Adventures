# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but this is computationally impossible. Simplicity Theory provides a mathematical breakthrough: it can definitively distinguish meaningful insights from meaningless associations, giving us our first principled framework for recognizing genuine discovery.*

Picture yourself stuck on a problem for weeks, then while making coffee, two unrelated ideas suddenly click together. [Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) tries to reverse-engineer exactly this process: building AI systems that make creative connections by combining facts and filtering for useful insights.

But Gwern's approach has two critical gaps. First, while he can check if ideas are coherent and measure their novelty, he leaves "usefulness" completely undefined. Second, randomly selecting concepts to combine is computationally inefficient—we need smarter targeting.

This is where [Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) becomes relevant. ST solves Gwern's "usefulness" problem definitively—it provides a mathematical framework to distinguish meaningful insights from meaningless associations. ST also improves the exponential search challenge: by first identifying which concepts form puzzles (opportunities for compression gain), it can dramatically narrow the search space before attempting combinations.

## The Framework: Simplicity Theory

[Jean-Louis Dessalles' Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) provides a mathematical approach to recognizing breakthrough insights through an **unexpectedness score**: **U = Cv - C**

Where:
- Cv (generation complexity): Length of the shortest specification the world would need to generate this situation under current causal constraints
- C (description complexity): Length of the shortest description that uniquely identifies the outcome
- U (unexpectedness score): The gap that signals "something structurally significant is happening"

Think of it like walking into a teenager's bedroom and finding it spotless—simple to describe, but based on what you know about teenagers, this should be nearly impossible. That gap signals "something interesting is happening here."

*Note: Unexpectedness alone doesn't determine interest—ST recognizes that domains with personal or social significance amplify our attention to unexpected patterns. But for breakthrough discovery, the unexpectedness component provides the core computational framework.*

### What Makes Insights Valuable: Compression Gain

ST recognizes genuine insights by measuring how much **compression gain** they provide. When we apply the unexpectedness score to candidate insights:

- C (description complexity): How simply can the insight itself be stated? ("variation + selection → adaptation") 
- Cv (generation complexity): How much intellectual preparation and fortunate circumstances were required to produce this connection?

High unexpectedness scores signal **compression gain**—when many separate observations collapse into a single explanatory mechanism, creating both simplicity and power. This is what distinguishes breakthrough insights from meaningless novelty.

We can identify opportunities for compression gain by looking for situations where simple patterns require complex explanations. When you can efficiently describe patterns but explaining *why* those patterns exist requires many separate, complex causal mechanisms, that signals potential for breakthrough—areas where a theoretical insight could collapse many separate explanations into a single mechanism. ST can tell you "adaptation research is ready for a breakthrough" but cannot tell you "combine population theory with heredity."

### Observer-Dependent Complexity: Making ST Practical

The key insight that makes ST computationally tractable is that complexity is always relative to the observer's knowledge. The number sequence "12-22-27-37-38-42" has high complexity for a general observer, but minimal complexity for the person who chose those numbers—it's simply "my numbers." This transforms abstract algorithmic complexity into practical calculations for real systems.



## The Core Improvement: From Blind Search to Targeted Search—But Still Exponential

To see why Simplicity Theory improves but doesn't solve the search problem, consider what different approaches would actually produce:

- **Blind search**: Randomly select articles about "sky color" and "pizza ingredients" → "Blue sky pizza cheese"
- **ST-guided search**: First identify puzzle pieces (Darwin's adaptation observations), then search for missing pieces (finding Malthus)

Simplicity Theory provides a crucial improvement over Gwern's brute-force approach. While Gwern accepts massive computational waste by randomly combining all concepts, ST can first identify which concepts form puzzles, dramatically narrowing the search space. Darwin's success demonstrates this: he recognized his adaptation observations formed a puzzle, then targeted his search for the missing mechanism.

But here's the key limitation: **the search challenge scales exponentially with the number of complementary concepts needed**. Single-concept breakthroughs like Darwin's (puzzle pieces + Malthus) become quite manageable. Multi-concept insights requiring many simultaneous connections remain exponentially challenging.

## What Made Darwin's Insight Special: How ST Explains Breakthrough Discovery

To see how Simplicity Theory's evaluation framework works in practice, let's examine what exactly distinguishes a breakthrough insight from meaningless word association. Note that this is a post-hoc analysis—we're using ST to understand why Darwin's connection was valuable after the fact.

The key insight is recognizing when you can efficiently describe patterns but lack causal mechanisms to explain why those patterns exist—this signals opportunities for compression gain.

Consider what happened in October 1838. Darwin had been wrestling with the mystery of adaptation for years, accumulating observations that defied easy explanation. But crucially, he had first recognized that adaptation itself was deeply unexpected under existing theories.

The widespread fact that organisms are exquisitely fitted to their environments is easy to describe but extraordinarily difficult to explain without evolution. You can summarize the pattern in a few words: "species are well-adapted to their ecological niches." 

But explaining *why* this pattern exists requires invoking separate causal mechanisms for each case—divine creation events, Lamarckian use/disuse, climate-driven modifications. This signals massive opportunity for compression gain, flagging this research direction as ripe for theoretical breakthrough.

Darwin had accumulated observations that all pointed to this same puzzling pattern:

- Geographic variation: Finch beaks across Galápagos islands, mockingbird differences
- Domestication experiments: Pigeon breeding, livestock trait inheritance  
- Fossil succession: Ancient species related but distinct from modern forms
- Biogeographic puzzles: Why similar environments had different species
- Organism-environment fit: Exquisite adaptations everywhere he looked

Each adaptation appeared as a separate puzzle piece. His world-model needed case-by-case explanations—divine creation events, Lamarckian use/disuse, climate shocks—a patchwork requiring increasingly complex explanations.

Then he read Malthus on population growth. Population pressure + resource competition + heritable variation → differential survival → accumulated adaptation over generations.

**Compression gain in action**: Like discovering one master key opens all the locks instead of carrying 50 individual keys. Darwin found the pattern that made thousands of observations suddenly click.

A vast pattern collapsed to a short causal recipe:

Variation + Heredity + Overproduction + Competition → Selection → Cumulative Change

This demonstrates ST's **insight recognition function**. Darwin's breakthrough is easy to describe (the simple causal recipe above) but would be extraordinarily difficult to generate without the prepared mind. The requirements to produce this insight are massive—years of biological observation, exposure to Malthus at the right moment, and the cognitive ability to see the connection. But the insight itself is minimal—a short causal mechanism that explains thousands of observations.

*Note: ST isn't a perfect filter—some high-unexpectedness events will be meaningless curiosities rather than breakthrough opportunities.*

So what does this mean for building real AI discovery systems?

## Where ST Actually Helps: Recognition Over Generation

Simplicity Theory addresses Gwern's two challenges very differently—definitively solving one while making limited progress on the other.

**What ST Solves Completely**: **Insight Recognition**
- ST provides a concrete mathematical framework to distinguish meaningful insights from meaningless associations through compression gain detection
- This definitively solves Gwern's "usefulness" filter problem—we can now computationally evaluate whether a proposed connection represents genuine discovery
- What distinguished Darwin's "population theory + adaptation puzzles" from our hypothetical "blue sky + pizza cheese"? Both involve connecting previously separate concepts and both produce something novel. Yet one launched a scientific revolution while the other is meaningless noise. Darwin's connection achieved compression gain while random word combinations typically create no explanatory value
- [Recent computational work](https://arxiv.org/abs/2307.15453) demonstrates these calculations are tractable through logic programming, moving ST from pure theory toward implementable discovery systems

**What ST Improves But Doesn't Solve**: **Concept Generation**
- ST can identify conceptual puzzles (where simple patterns require complex explanations), signaling compression opportunities and narrowing the search space
- However, ST doesn't solve the fundamental challenge of systematically identifying which specific concepts are worth combining
- ST excels at evaluating proposed combinations but provides minimal guidance for generating them—the crucial middle step of navigating the exponential search space remains largely unsolved

## Implementation Reality: What Can We Actually Build?

Can we build AI that discovers like Darwin did? The question cuts to the heart of whether computational systems can replicate the leap from scattered observations to transformative insight.

**What Exists Now**: The [CompLog framework](https://arxiv.org/abs/2307.15453) provides a working implementation for evaluating proposed connections through compression ratios, moving ST from pure theory toward testable systems.

**Open Research Directions**: Several promising but unvalidated approaches could make ST-based discovery more practical:

*Detecting Compression Opportunities*: Identifying patterns with simple descriptions but complex explanations, flagging high-potential conceptual puzzles. This could work across contexts—scanning research literature for breakthrough opportunities or monitoring personal knowledge management systems (Obsidian, Roam Research, Zettelkasten) to spot when accumulated notes form puzzles ripe for insight. Such systems could combine human concept generation with AI insight recognition—researchers propose connections while AI evaluates compression gain.

A more accessible way to implement this evaluation could be *LLM-Based Unexpectedness Estimation*: using language models to estimate U = Cv - C by prompting for generation complexity ("Given what we knew in 1838, how difficult would Darwin's connection be to generate?") versus description complexity ("How simply can this be stated?"). This could be more accessible than CompLog's formal logic while remaining mathematically grounded, though it's unclear whether LLMs would capture the relationships ST requires.

> If we could detect when concepts form puzzles where simple patterns require complex explanations—signaling compression opportunities—which conceptual puzzles would be most ripe for breakthrough?

What remains beyond current capabilities is the core challenge: systematically generating which concepts to combine in the first place. This requires understanding meaning, abstraction formation, and connecting different fields—core parts of intelligence itself.

## Conclusion

We have some promising theory. Computational approaches are emerging. But lots of experimentation is required to know if this actually works in practice.

If it does? Picture an AI scanning every paper on arXiv in real-time, flagging compression opportunities as they emerge. Your Zettelkasten could highlight when scattered notes form unexpectedness patterns. Browser extensions that show unexpectedness ratings for research papers you read.

Email filters that prioritize high-compression insights. Social media algorithms that surface genuinely unexpected connections instead of engagement bait. Personal knowledge systems that learn your thinking patterns and flag when you're circling around puzzle pieces.

ST could also transform the reinforcement learning phase of LLM training. Mathematical problems are ideal for this approach because they provide objectively verifiable answers—you can automatically check if "42" is correct without human judgment. But developing insight generation capabilities has no equivalent: we typically rely on expensive human preference ratings to distinguish genuinely insightful responses from sophisticated-sounding nonsense. ST's compression gain metrics could fill this gap, providing automatic verification of conceptual breakthroughs and training LLMs to generate genuine insights rather than just fluent text.

Every research tool becomes a discovery engine. The possibilities are endless—if we can make it work.

What will you build?
