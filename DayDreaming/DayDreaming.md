# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

[Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) brilliantly identifies a core limitation of current AI: the lack of continuous processing that drives human creativity. His vision of AI systems randomly combining facts and filtering for "novelty," "coherence," and "usefulness" tackles an important problem. But his solution has two key gaps: while coherence is checkable and novelty is trivial from an information-theoretic perspective, usefulness remains completely undefined, and the completely random selection of concepts to combine is computationally inefficient.

[Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) addresses these gaps, though with different levels of success: it provides a principled framework for distinguishing breakthrough insights from meaningless novelty (closing the filtering gap), while offering guidance—but not a complete solution—for targeting high-potential concept combinations (narrowing the targeting gap).

## The Core Problem: Selection and Generation Challenges

To see why these gaps matter, consider what Gwern's proposal would actually produce in practice:

- Random combination: Randomly select articles about "sky color" and "pizza ingredients" → "Blue sky pizza cheese"
- Guided search: Darwin actively seeking mechanisms to explain adaptation, then recognizing Malthus' relevance

Gwern acknowledges this inefficiency problem—he knows random combination would generate millions of meaningless outputs for every valuable connection. His proposal essentially accepts massive computational waste as the price for comprehensive exploration. But even acknowledging the inefficiency, his brute-force approach leaves the core problem unsolved: how do you make the search tractable?

The real challenge requires both smarter targeting of promising combinations and better recognition of which connections actually create interesting breakthroughs.

## The Framework: Simplicity Theory's Interest Model

[Jean-Louis Dessalles' Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) provides the answer through a dual-component model: **Interest = f(U, Emotional_Intensity)**

Where **U = Cv - C** (the unexpectedness score):
- Cv (generation complexity): Length of the shortest specification the world would need to generate this situation under current causal constraints
- C (description complexity): Length of the shortest description that uniquely identifies the outcome
- U (unexpectedness score): The gap that signals "something structurally significant is happening"

And **Emotional_Intensity** captures the personal/social impact of the domain—including high-stakes areas like cancer research, climate solutions, or fundamental physics.

This dual structure means high-value research emerges from either technical surprises (high U) or critical domains (high emotional intensity), and often both simultaneously in mature high-stakes fields where economic filtering ensures remaining problems have high complexity.

**Observer-Dependent Complexity**: The key insight that makes ST computationally tractable is that complexity is always relative to the observer's knowledge. The lottery sequence "12-22-27-37-38-42" has high complexity for a general observer, but minimal complexity for the person who chose those numbers—it's simply "my numbers." This transforms abstract algorithmic complexity into practical cognitive computation for real systems.

We can use Simplicity Theory in both Domain Targeting and Insight Recognition.

**Function 1 - Domain Targeting**: Identifies domains worth investigating by measuring the unexpectedness of *current observations and patterns*:

When we apply the unexpectedness score to existing phenomena:
- C (description complexity): How simply can we describe the observed pattern? 
- Cv (generation complexity): How complex are the causal mechanisms needed to explain why this pattern exists?
- High unexpectedness scores signal **explanatory debt**—simple patterns requiring complex explanations flag domains ripe for theoretical breakthrough

**Explanatory debt** occurs when you can efficiently catalog observations into recognizable patterns, but explaining *why* those patterns exist requires many separate, complex causal mechanisms. High explanatory debt signals opportunity—when you have simple pattern descriptions but expensive causal explanations, you're ripe for a theoretical breakthrough.

Combined with **domain importance** (high emotional intensity prioritizes cancer research, climate solutions, fundamental physics), this targets where breakthroughs matter most.

**Function 2 - Insight Recognition**: Recognizes genuine insights by measuring the unexpectedness of *proposed connections or theories*:

Here we apply the unexpectedness score to candidate insights:
- C (description complexity): How simply can the insight itself be stated? ("variation + selection → adaptation") 
- Cv (generation complexity): How much intellectual preparation and fortunate circumstances were required to produce this connection?
- High unexpectedness scores signal **compression gain**—simple insights emerging from complex preparation indicate breakthrough discoveries, not random associations

**The Power of Dual Application**: This is why ST works where other approaches fail. We're not randomly searching—we use unexpectedness measurements to systematically identify where to look (Function 1), then use the same measurements to recognize genuine breakthroughs when they emerge (Function 2). 

## What Made Darwin's Insight Special: How ST Explains Breakthrough Discovery

To see how Simplicity Theory's dual functions work in practice, let's examine what exactly distinguishes a breakthrough insight from meaningless word association.

The key insight is recognizing when you can efficiently describe patterns but lack causal mechanisms to explain why those patterns exist—this is **explanatory debt** in action.

Consider what happened in October 1838. Darwin had been wrestling with the mystery of adaptation for years, accumulating observations that defied easy explanation. But crucially, he had first recognized that adaptation itself was deeply unexpected under existing theories.

The widespread fact that organisms are exquisitely fitted to their environments is easy to describe but extraordinarily difficult to explain without evolution. You can summarize the pattern in a few words: "species are well-adapted to their ecological niches." 

But explaining *why* this pattern exists requires invoking separate causal mechanisms for each case—divine creation events, Lamarckian use/disuse, climate-driven modifications. This creates massive **explanatory debt**, flagging this domain as ripe for theoretical breakthrough—demonstrating ST's **domain targeting function**.

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

## Where ST Actually Helps: Targeting and Recognition
Simplicity Theory's Interest model addresses both phases of Gwern's challenge through its dual-component structure. For targeting, ST provides guidance in two ways: **explanatory debt** detection (high unexpectedness scores from simple descriptions requiring complex explanations) AND domain prioritization (high emotional intensity in high-stakes fields). This combination is crucial—using unexpectedness alone would miss important problems in mature domains, while emotional intensity alone would lack precision. 

Economic filtering in mature high-stakes domains creates a powerful convergence—the most important unsolved problems necessarily have high complexity, making breakthroughs inherently high-unexpectedness events.

The insight recognition problem appears genuinely solved. ST provides a concrete test for **compression gain**: when N distinct observations requiring separate explanations collapse to a single mechanism plus local parameters, the compression ratio quantifies breakthrough value. [Recent computational work](https://arxiv.org/abs/2307.15453) demonstrates this calculation is actually tractable through logic programming.

## Implementation Reality: What Can We Actually Build?

While ST provides a principled framework for improving AI discovery, we need to be honest about current computational feasibility. The [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates that ST's complexity calculations can be implemented through logic programming—we can actually build systems that detect when a connection creates genuine **compression gain**. This addresses Gwern's "usefulness" filter with computational precision.

ST's **explanatory debt** framework provides guidance for where to search, but doesn't solve the core targeting problem. We can identify domains where current theories require complex explanations for simple patterns, but systematically finding the right concept combinations remains largely unsolved. 

How do you algorithmically decide that "population pressure" and "heredity" are worth combining rather than "population pressure" and "cloud formation"?

The deepest challenges lie in capabilities we haven't cracked: semantic clustering (recognizing that finch beaks, pigeon breeding, and fossil succession belong together thematically), abstraction formation (converting specific observations into general pattern descriptions like "species fit their environments"), meta-cognitive reasoning (understanding when your own explanatory mechanisms are becoming unwieldy), and cross-domain transfer (seeing connections between seemingly unrelated fields like population theory and biological adaptation). 

These challenges require the kind of flexible reasoning, abstraction, and semantic understanding that defines general intelligence itself.

The practical reality is that we can build hybrid systems where humans handle concept generation and AI handles **compression gain** testing, or systems that work within constrained domains where concept relationships are well-defined. But fully automated discovery systems are still far beyond current capabilities. 

ST helps us recognize breakthroughs and provides principled guidance for search, but the fundamental problem of generating meaningful concept combinations at scale remains as hard as ever.



## Conclusion

Gwern's insight about AI needing background processing is brilliant, and he's honest about the computational challenges of random combination. But his brute-force approach leaves core problems unsolved: how to intelligently target promising concept combinations and how to recognize genuine insights when they emerge.

Simplicity Theory's complete Interest model addresses both gaps more comprehensively than initially apparent. The dual-component framework (unexpectedness + emotional intensity) provides principled targeting through **explanatory debt** detection AND domain prioritization, while economic filtering in high-stakes fields creates natural convergence zones where breakthroughs are most likely. 

CompLog demonstrates that insight recognition through **compression gain** detection is computationally feasible. However, fundamental challenges remain: systematically identifying concept combinations, scaling beyond constrained domains, and the broader semantic understanding required for cross-domain insight generation.

While other approaches like Bayesian inference excel at systematic learning from data streams¹, ST offers something unique—a formal framework for detecting the salience of individual events and breakthrough moments. This makes it particularly suited to Gwern's original challenge: how do you recognize when a random connection has produced genuine insight rather than meaningless novelty?

With computational approaches like CompLog demonstrating feasibility, we can begin testing simplified versions of this framework on constrained discovery tasks. While we're still far from Darwin-like insights, the framework has moved from pure theory toward something potentially testable. The distinction between mere novelty and genuine insight will ultimately separate truly intelligent systems from sophisticated text generators. What we've outlined here combines theoretical framework with practical implementation—building on both information theory and cognitive science to make AI "daydreaming" a systematic discovery process rather than brute-force search.

**Meta-insight (or: When Your Framework Becomes Self-Aware)**: Let's apply our own medicine here. The core claim—"use Simplicity Theory to make AI discovery less random"—is delightfully simple to state (low C) but required synthesizing papers across cognitive science, information theory, and AI research (reasonably high Cv). So according to our own framework, this should register as genuinely interesting! Though we suspect Simplicity Theory would also flag "use quantum mechanics to optimize pizza delivery routes" as potentially breakthrough material, so perhaps we shouldn't get too excited.

¹ **Alternative Path: Bayesian Model Selection** - While Simplicity Theory provides our primary framework for insight detection, Bayesian model inference offers a complementary approach to the same fundamental goal of finding meaningful patterns through compression. The Bayesian framework implements an automatic preference for simpler models through "Bayesian Occam's Razor"—complex models that can explain too many different outcomes are naturally penalized because they spread their predictive probability too thinly. This connects to Simplicity Theory through the Minimum Description Length (MDL) principle, showing that both approaches ultimately seek to minimize the total length needed to describe both the model and the data it explains. For AI implementation, this suggests potential hybrid architectures: Bayesian methods for systematic learning and model updating, paired with ST-like mechanisms for real-time salience detection.
