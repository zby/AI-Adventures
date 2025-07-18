# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

[Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) brilliantly identifies a core limitation of current AI: the lack of continuous processing that drives human creativity. His vision of AI systems randomly combining facts and filtering for "novelty," "coherence," and "usefulness" tackles an important problem. But his solution has two key gaps: while coherence is checkable and novelty is trivial from an information-theoretic perspective, usefulness remains completely undefined, and the completely random selection of concepts to combine is computationally inefficient.

[Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) offers partial solutions to these challenges: it provides a principled framework for distinguishing breakthrough insights from meaningless novelty (substantially improving the filtering problem), while offering limited guidance for identifying promising research domains—though it doesn't solve the core challenge of systematically generating concept combinations within those domains.

## The Core Problem: Selection and Generation Challenges

To see why these gaps matter, consider what Gwern's proposal would actually produce in practice:

- Random combination: Randomly select articles about "sky color" and "pizza ingredients" → "Blue sky pizza cheese"
- Guided search: Darwin actively seeking mechanisms to explain adaptation, then recognizing Malthus' relevance

Gwern acknowledges this inefficiency problem—he knows random combination would generate millions of meaningless outputs for every valuable connection. His proposal essentially accepts massive computational waste as the price for comprehensive exploration. But even acknowledging the inefficiency, his brute-force approach leaves the core challenge unsolved: **concept combination targeting**—systematically identifying which concepts are worth combining, whether within domains or across them.

While Simplicity Theory helps with insight recognition, this fundamental generation problem remains largely unsolved.

## The Framework: Simplicity Theory's Interest Model

[Jean-Louis Dessalles' Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) centers on an **unexpectedness score**: **U = Cv - C**

Where:
- Cv (generation complexity): Length of the shortest specification the world would need to generate this situation under current causal constraints
- C (description complexity): Length of the shortest description that uniquely identifies the outcome
- U (unexpectedness score): The gap that signals "something structurally significant is happening"

But unexpectedness alone doesn't determine what we find interesting. ST recognizes that interest depends on both **unexpectedness** and **emotional intensity**—the personal or social impact of the domain. Both components matter:

- High unexpectedness in trivial domains (like lottery numbers) generates curiosity but not sustained interest
- High emotional intensity in predictable domains (like routine medical care) generates concern but not breakthrough potential  
- The combination of both—unexpected patterns in high-stakes domains like cancer research, climate solutions, or fundamental physics—creates the conditions where breakthroughs matter most

This dual-component structure means high-value research emerges from either technical surprises (high U) or critical domains (high emotional intensity), and often both simultaneously in mature high-stakes fields where economic filtering ensures remaining problems have high complexity.

**Observer-Dependent Complexity**: The key insight that makes ST computationally tractable is that complexity is always relative to the observer's knowledge. The lottery sequence "12-22-27-37-38-42" has high complexity for a general observer, but minimal complexity for the person who chose those numbers—it's simply "my numbers." This transforms abstract algorithmic complexity into practical cognitive computation for real systems.

Simplicity Theory excels at insight recognition but provides only limited guidance for concept generation. Here's how it works:

**Explanatory Debt Detection**: ST can identify areas where simple patterns require complex explanations, flagging research directions that may be ripe for theoretical breakthrough. When you can efficiently describe patterns but explaining *why* those patterns exist requires many separate, complex causal mechanisms, you have **explanatory debt**. High explanatory debt signals opportunity—when you have simple pattern descriptions but expensive causal explanations, you're ripe for a theoretical breakthrough.

**Insight Recognition**: ST recognizes genuine insights by measuring the unexpectedness of *proposed connections or theories*. When we apply the unexpectedness score to candidate insights:
- C (description complexity): How simply can the insight itself be stated? ("variation + selection → adaptation") 
- Cv (generation complexity): How much intellectual preparation and fortunate circumstances were required to produce this connection?
- High unexpectedness scores signal **compression gain**—simple insights emerging from complex preparation indicate breakthrough discoveries, not random associations

**The Power and Limits of Dual Application**: ST's strength lies in evaluating candidates, not generating them. We can use unexpectedness measurements to identify areas with explanatory debt (flagging promising research directions), then use the same measurements to recognize genuine breakthroughs when they emerge. However, the crucial middle step—systematically generating promising concept combinations—remains largely unsolved. 

ST doesn't tell us that "population pressure" and "heredity" are worth combining rather than "population pressure" and "cloud formation." It can only evaluate such combinations after they're proposed.

Let's see both functions work in history's most famous breakthrough.

## What Made Darwin's Insight Special: How ST Explains Breakthrough Discovery

To see how Simplicity Theory's evaluation framework works in practice, let's examine what exactly distinguishes a breakthrough insight from meaningless word association. Note that this is a post-hoc analysis—we're using ST to understand why Darwin's connection was valuable after the fact.

The key insight is recognizing when you can efficiently describe patterns but lack causal mechanisms to explain why those patterns exist—this is **explanatory debt** in action.

Consider what happened in October 1838. Darwin had been wrestling with the mystery of adaptation for years, accumulating observations that defied easy explanation. But crucially, he had first recognized that adaptation itself was deeply unexpected under existing theories.

The widespread fact that organisms are exquisitely fitted to their environments is easy to describe but extraordinarily difficult to explain without evolution. You can summarize the pattern in a few words: "species are well-adapted to their ecological niches." 

But explaining *why* this pattern exists requires invoking separate causal mechanisms for each case—divine creation events, Lamarckian use/disuse, climate-driven modifications. This creates massive **explanatory debt**, flagging this research direction as ripe for theoretical breakthrough.

Darwin had accumulated observations that all pointed to this same puzzling pattern:

- Geographic variation: Finch beaks across Galápagos islands, mockingbird differences
- Domestication experiments: Pigeon breeding, livestock trait inheritance  
- Fossil succession: Ancient species related but distinct from modern forms
- Biogeographic puzzles: Why similar environments had different species
- Organism-environment fit: Exquisite adaptations everywhere he looked

Each adaptation appeared as a separate puzzle piece. His world-model needed case-by-case explanations—divine creation events, Lamarckian use/disuse, climate shocks—a patchwork requiring increasingly complex explanations.

Then he read Malthus on population growth. Population pressure + resource competition + heritable variation → differential survival → accumulated adaptation over generations.

**Compression gain in action**: A vast pattern (organismal adaptation, divergence, extinction, branching) collapsed to a short causal recipe:

Variation + Heredity + Overproduction + Competition → Selection → Cumulative Change

This demonstrates ST's **insight recognition function**. Darwin's breakthrough is easy to describe (the simple causal recipe above) but would be extraordinarily difficult to generate without the prepared mind. The requirements to produce this insight are massive—years of biological observation, exposure to Malthus at the right moment, and the cognitive ability to see the connection. But the insight itself is minimal—a short causal mechanism that explains thousands of observations.

*Note: ST isn't a perfect filter—some high-unexpectedness events will be meaningless curiosities rather than breakthrough opportunities.*

What distinguished Darwin's "population theory + adaptation puzzles" from our hypothetical "blue sky + pizza cheese"? Both involve connecting previously separate concepts and both produce something novel. Yet one launched a scientific revolution while the other is meaningless noise. The difference lies in **compression gain**—Darwin's connection explains vast patterns through simple mechanisms, while random word combinations typically create no explanatory value.

Recent computational work by [Sileno and Dessalles](https://arxiv.org/abs/2307.15453) suggests these complexity calculations might be tractable through logic programming, moving ST from pure theory toward implementable discovery systems.

So what does this mean for building real AI discovery systems?

## Where ST Actually Helps: Recognition Over Generation

Simplicity Theory addresses one of Gwern's challenges definitively while offering limited help with the other. For **insight recognition**, ST provides a concrete framework through **compression gain** detection—when N distinct observations requiring separate explanations collapse to a single mechanism plus local parameters, the compression ratio quantifies breakthrough value. This definitively solves Gwern's "usefulness" filter problem.

For **concept combination targeting**, ST offers minimal guidance. While the **explanatory debt** framework can flag research areas where simple patterns require complex explanations, it doesn't solve the fundamental challenge of systematically identifying which specific concepts are worth combining. Whether the concepts come from the same domain or different domains, ST excels at evaluating proposed combinations but provides little direction for generating them.

The insight recognition capabilities appear robust. ST provides a concrete test for **compression gain**: when candidate insights compress many separate explanations into unified mechanisms, the compression ratio directly measures breakthrough value. [Recent computational work](https://arxiv.org/abs/2307.15453) demonstrates this calculation is tractable through logic programming.

But the generation problem persists—ST excels at evaluating proposed connections but offers minimal guidance for systematically producing them.

## Implementation Reality: What Can We Actually Build?

The computational feasibility of ST-based discovery systems is more limited than initial claims suggest. While the [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates that ST's complexity calculations can be implemented through logic programming, this only addresses the evaluation phase—we can build systems that detect when a connection creates genuine **compression gain**. This provides a computational solution to Gwern's "usefulness" filter.

However, computing complexity measures is vastly different from building discovery systems. The concept generation bottleneck remains: we still can't systematically determine which concepts are worth combining, whether within domains or across them.

The deepest challenges lie in capabilities that define general intelligence itself: semantic clustering (recognizing that finch beaks, pigeon breeding, and fossil succession belong together thematically), abstraction formation (converting specific observations into general pattern descriptions like "species fit their environments"), meta-cognitive reasoning (understanding when your own explanatory mechanisms are becoming unwieldy), and cross-domain transfer (seeing connections between seemingly unrelated fields like population theory and biological adaptation). 

The practical reality is that we can build evaluation systems that test proposed connections for compression gain, or hybrid systems where humans handle concept generation and AI handles breakthrough recognition. But systematic concept generation—the core of Gwern's challenge—remains beyond current capabilities.

ST provides a principled framework for the recognition phase while offering limited guidance for the generation challenge.

## Conclusion

Gwern's insight about AI needing background processing is brilliant, and he's honest about the computational challenges of random combination. His brute-force approach leaves the core challenge unsolved: **concept combination targeting**—systematically identifying which concepts are worth combining, whether within domains or across them.

Simplicity Theory makes significant progress on insight recognition while offering limited help with concept generation. The framework's **compression gain** detection provides a principled solution to Gwern's undefined "usefulness" filter—we can computationally distinguish breakthrough insights from meaningless associations. CompLog demonstrates this recognition capability is actually implementable.

However, the fundamental challenge remains: systematically generating meaningful concept combinations. ST excels at evaluation but provides minimal guidance for generation. The deepest requirements—semantic clustering, abstraction formation, and cross-domain transfer—represent the same capabilities that define general intelligence itself.

While other approaches like Bayesian inference excel at systematic learning from data streams, ST offers something complementary—a formal framework for detecting the salience of individual breakthrough moments. This makes ST particularly suited to one part of Gwern's original challenge: recognizing when a proposed connection represents genuine insight rather than meaningless novelty.

With computational approaches like CompLog demonstrating feasibility for the evaluation component, we can begin testing hybrid systems where humans generate concepts and AI recognizes breakthroughs. While we're still far from fully automated discovery systems, ST moves us from having no principled framework for insight recognition to having a computationally tractable one. The distinction between mere novelty and genuine insight will ultimately separate truly intelligent systems from sophisticated text generators—and ST provides concrete progress on that fundamental challenge.

**Meta-insight**: Let's apply our own framework here. The core claim—"ST solves insight recognition but not concept generation"—is simple to state (low C) but required analyzing the logical gaps in complex theoretical frameworks (reasonably high Cv). According to our own framework, this should register as a useful clarification!
