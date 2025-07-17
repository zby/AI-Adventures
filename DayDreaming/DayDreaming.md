# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

[Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) brilliantly identifies a core limitation of current AI: the lack of continuous processing that drives human creativity. His vision of AI systems randomly combining facts and filtering for "novelty," "coherence," and "usefulness" tackles an important problem. But his solution has two key gaps: while coherence is checkable and novelty is trivial from an information-theoretic perspective, usefulness remains completely undefined, and the completely random selection of concepts to combine is computationally inefficient.

[Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) addresses these gaps, though with different levels of success: it provides a principled framework for distinguishing breakthrough insights from meaningless novelty (closing the filtering gap), while offering guidance—but not a complete solution—for targeting high-potential concept combinations (narrowing the targeting gap).

## The Core Problem: Selection and Generation Challenges

To see why these gaps matter, consider what Gwern's proposal would actually produce in practice:

- Random combination: Randomly select articles about "sky color" and "pizza ingredients" → "Blue sky pizza cheese"
- Guided search: Darwin actively seeking mechanisms to explain adaptation, then recognizing Malthus' relevance

Gwern acknowledges this inefficiency problem—he knows random combination would generate millions of meaningless outputs for every valuable connection. His proposal essentially accepts massive computational waste as the price for comprehensive exploration. But even acknowledging the inefficiency, his brute-force approach leaves the core problem unsolved: how do you make the search tractable?

The real challenge requires both smarter targeting of promising combinations and better recognition of which connections actually create explanatory breakthroughs.

## The Framework: Simplicity Theory's Insight Detector

[Jean-Louis Dessalles' Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) provides the answer: **an event is genuinely interesting when it has low descriptive complexity but high causal complexity.**

**U = Cv - C**

Where:
- Cv (generation complexity): Length of the shortest specification the world would need to generate this situation under current causal constraints
- C (description complexity): Length of the shortest description that uniquely identifies the outcome
- U (unexpectedness): The gap that signals "something structurally significant is happening"

If producing a situation ordinarily requires a long, contingent chain of circumstances (high Cv), but you can describe it concisely (low C), that gap demands explanation. Your mind flags it as requiring theory revision.

**Observer-Dependent Complexity**: The key insight that makes ST computationally tractable is that complexity is always relative to the observer's descriptive resources and current knowledge. The lottery sequence "12-22-27-37-38-42" has high complexity for a general observer, but minimal complexity for the person who chose those numbers—it's simply "my numbers." This observer-dependency transforms abstract algorithmic complexity into psychologically realistic cognitive computation, making ST a practical framework for real systems operating under resource constraints.

**ST's Dual Discovery Functions**: Simplicity Theory serves two complementary roles in discovery systems, both using the same unexpectedness measure (U = Cv - C) but applied to different targets:

**Function 1 - Domain Targeting**: Identifies domains ripe for breakthrough by detecting **explanatory debt**—situations where you can efficiently describe patterns but explaining *why* those patterns exist requires many separate, complex causal mechanisms. Here we calculate U for the *observed patterns themselves*:
- C (description): Low - patterns are easy to describe ("species fit their environments")  
- Cv (generation): High - current theories need complex, separate explanations for each case
- High U signals theoretical gaps worth investigating

**Function 2 - Insight Recognition**: Recognizes genuine insights by measuring **compression gain**. Here we calculate U for the *proposed connection or insight*:
- C (description): Low - the insight itself can be stated simply ("variation + selection → adaptation")
- Cv (generation): High - producing this insight required vast preparation and fortunate circumstances  
- High U signals breakthrough discoveries, not random associations

The key insight: we apply the same formula to different targets. First, to flag domains where simple descriptions require complex explanations. Then, to recognize when simple explanations emerge from complex intellectual work.

## What Made Darwin's Insight Special: How ST Explains Breakthrough Discovery

To see how Simplicity Theory's dual functions work in practice, let's examine what exactly distinguishes a breakthrough insight from meaningless word association.

The key insight is recognizing when you can efficiently describe patterns but lack causal mechanisms to explain why those patterns exist—what we call **explanatory debt**. Explanatory debt occurs when you can catalog observations into recognizable patterns, but explaining *why* those patterns exist requires many separate, complex causal mechanisms. High explanatory debt signals opportunity: when you have simple pattern descriptions but expensive causal explanations, you're ripe for a theoretical breakthrough that explains the patterns through a single underlying mechanism.

Consider what happened in October 1838. Darwin had been wrestling with the mystery of adaptation for years, accumulating observations that defied easy explanation. But crucially, he had first recognized that adaptation itself was deeply unexpected under existing theories.

The widespread fact that organisms are exquisitely fitted to their environments is easy to describe but extraordinarily difficult to explain without evolution. You can summarize the pattern in a few words: "species are well-adapted to their ecological niches." But explaining *why* this pattern exists requires invoking separate causal mechanisms for each case—divine creation events, Lamarckian use/disuse, climate-driven modifications. The gap between simple description and complex explanation creates massive unexpectedness (U), flagging this domain as ripe for theoretical breakthrough—this demonstrates ST's **domain targeting function**.

Darwin had accumulated observations that all pointed to this same puzzling pattern:

- Geographic variation: Finch beaks across Galápagos islands, mockingbird differences
- Domestication experiments: Pigeon breeding, livestock trait inheritance  
- Fossil succession: Ancient species related but distinct from modern forms
- Biogeographic puzzles: Why similar environments had different species
- Organism-environment fit: Exquisite adaptations everywhere he looked

Each adaptation appeared as a separate puzzle piece. His world-model needed case-by-case explanations—divine creation events, Lamarckian use/disuse, climate shocks—a patchwork requiring increasingly complex explanations.

Then he read Malthus on population growth. Population pressure + resource competition + heritable variation → differential survival → accumulated adaptation over generations.

**Insight recognition in action**: A vast pattern (organismal adaptation, divergence, extinction, branching) collapsed to a short causal recipe:

Variation + Heredity + Overproduction + Competition → Selection → Cumulative Change

This demonstrates ST's **insight selection function**. Darwin's breakthrough is easy to describe (the simple causal recipe above) but would be extraordinarily difficult to generate without the prepared mind. The requirements to produce this insight are massive—you need years of biological observation, exposure to Malthus at the right moment, and the cognitive ability to see the connection. But the insight itself is minimal—a short causal mechanism that explains thousands of observations.

Now we can see how ST's framework operates in different contexts:

**Domain targeting**: Widespread organismal adaptation 
- Easy to describe: "species fit their environments"
- Hard to explain: requires separate divine creation events for each case
- High unexpectedness → flags domain for investigation

**Insight selection**: Population theory + adaptation connection
- Easy to describe: simple causal mechanism (variation + selection)
- Hard to generate: required vast preparation (years of biological puzzles) + chance encounter with Malthus
- High unexpectedness → signals genuine compression breakthrough

**Outside ST's scope**: Meeting cousin on random flight
- Easy to describe: coincidental encounter  
- Hard to generate: low probability event
- High unexpectedness but no explanatory target → ST's framework doesn't help us

However, the "just curiosity" case isn't entirely derivative—such random encounters can lead to discovery of coordination or unexpected connections that later prove meaningful.

What distinguished Darwin's "population theory + adaptation puzzles" from our hypothetical "blue sky + pizza cheese"? Both involve connecting previously separate concepts and both produce something novel. Yet one launched a scientific revolution while the other is meaningless noise. The difference lies in compression gain—Darwin's connection explains vast patterns through simple mechanisms, while random word combinations typically create no explanatory value.

Recent computational work by [Sileno and Dessalles](https://arxiv.org/abs/2307.15453) suggests these complexity calculations might be tractable through logic programming, moving ST from pure theory toward implementable discovery systems.

## Where ST Actually Helps: Targeting and Recognition

Simplicity Theory makes specific contributions to both phases of Gwern's challenge, though with different levels of success. For concept targeting, ST offers principled guidance rather than a complete solution—prioritizing concepts that appear frequently in high explanatory-debt contexts where simple patterns require complex explanations. This narrows the search space considerably, though it doesn't solve the fundamental targeting problem of systematically identifying which concepts should be combined.

The insight recognition problem, however, appears genuinely solved. ST provides a concrete test for compression gain: when N distinct observations requiring separate explanations collapse to a single mechanism plus local parameters, the compression ratio quantifies breakthrough value. [Recent computational work](https://arxiv.org/abs/2307.15453) demonstrates this calculation is actually tractable through logic programming. Without systematic attention to explanatory debt, even semantically meaningful combinations typically produce surface-level associations rather than compression-creating insights.

## Implementation Reality: What Can We Actually Build?

While ST provides a principled framework for improving AI discovery, we need to be honest about current computational feasibility. The [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates that ST's complexity calculations can be implemented through logic programming—we can actually build systems that detect when a connection creates genuine compression gain. This addresses Gwern's "usefulness" filter with computational precision.

ST's explanatory debt framework provides guidance for where to search, but doesn't solve the core targeting problem. We can identify domains where current theories require complex explanations for simple patterns, but systematically finding the right concept combinations remains largely unsolved. How do you algorithmically decide that "population pressure" and "heredity" are worth combining rather than "population pressure" and "cloud formation"?

The deepest challenges lie in capabilities we haven't cracked: semantic clustering (recognizing that finch beaks, pigeon breeding, and fossil succession belong together thematically), abstraction formation (converting specific observations into general pattern descriptions like "species fit their environments"), meta-cognitive reasoning (understanding when your own explanatory mechanisms are becoming unwieldy), and cross-domain transfer (seeing connections between seemingly unrelated fields like population theory and biological adaptation). These challenges require the kind of flexible reasoning, abstraction, and semantic understanding that defines general intelligence itself.

The practical reality is that we can build hybrid systems where humans handle concept generation and AI handles compression testing, or systems that work within constrained domains where concept relationships are well-defined. But fully automated discovery systems are still far beyond current capabilities. ST helps us recognize breakthroughs and provides principled guidance for search, but the fundamental problem of generating meaningful concept combinations at scale remains as hard as ever.



## Conclusion

Gwern's insight about AI needing background processing is brilliant, and he's honest about the computational challenges of random combination. But his brute-force approach leaves core problems unsolved: how to intelligently target promising concept combinations and how to recognize genuine insights when they emerge.

Simplicity Theory closes the filtering gap with principled selection criteria (compression detection) and narrows the targeting gap by suggesting focus on explanatory debt, though significant generation challenges remain. CompLog provides early evidence that complexity calculation—arguably the hardest part of the filtering puzzle—might be implementable. However, major challenges persist: converting raw observations into structured predicates that ST can process, scaling beyond constrained domains, and systematically identifying which concepts should be combined. We've solved insight recognition but only partially addressed concept targeting.

While other approaches like Bayesian inference excel at systematic learning from data streams¹, ST offers something unique—a formal framework for detecting the salience of individual events and breakthrough moments. This makes it particularly suited to Gwern's original challenge: how do you recognize when a random connection has produced genuine insight rather than meaningless novelty?

With computational approaches like CompLog demonstrating feasibility, we can begin testing simplified versions of this framework on constrained discovery tasks. While we're still far from Darwin-like insights, the framework has moved from pure theory toward something potentially testable. The distinction between mere novelty and genuine insight will ultimately separate truly intelligent systems from sophisticated text generators. What we've outlined here combines theoretical framework with practical implementation—building on both information theory and cognitive science to make AI "daydreaming" a systematic discovery process rather than brute-force search.

**Meta-insight**: In a delicious bit of recursive validation, this article demonstrates ST's insight recognition by... using ST to evaluate whether the ST-Gwern connection itself counts as genuine insight. (Yes, we're basically asking the theory to grade its own homework.)

The connection exhibits exactly the high unexpectedness (U) that ST identifies as breakthrough:

- **C (description)**: Low - "ST's compression detection solves Gwern's usefulness filtering problem"  
- **Cv (generation)**: High - required stumbling across Gwern's specific computational challenges, deep-diving into Dessalles' cognitive framework, and that "aha!" moment recognizing the conceptual mapping between "usefulness" and "compression gain"

High U = Cv - C suggests genuine insight rather than random word association. The connection wasn't obvious (otherwise Gwern would have mentioned it), yet once stated it's simple and explains the core filtering challenge. This circular reasoning—using ST to recognize that applying ST meets ST's own criteria for valuable insight—is either elegantly self-validating or hilariously self-serving, depending on your tolerance for theoretical recursion.

---

¹ **Alternative Path: Bayesian Model Selection** - While Simplicity Theory provides our primary framework for insight detection, Bayesian model inference offers a complementary approach to the same fundamental goal of finding meaningful patterns through compression. The Bayesian framework implements an automatic preference for simpler models through "Bayesian Occam's Razor"—complex models that can explain too many different outcomes are naturally penalized because they spread their predictive probability too thinly. This connects to Simplicity Theory through the Minimum Description Length (MDL) principle, showing that both approaches ultimately seek to minimize the total length needed to describe both the model and the data it explains. For AI implementation, this suggests potential hybrid architectures: Bayesian methods for systematic learning and model updating, paired with ST-like mechanisms for real-time salience detection.