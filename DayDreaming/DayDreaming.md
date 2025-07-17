# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

[Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) brilliantly identifies a core limitation of current AI: the lack of continuous processing that drives human creativity. His vision of AI systems randomly combining facts and filtering for "novelty," "coherence," and "usefulness" tackles an important problem. But his solution has two key gaps: while coherence is checkable and novelty is trivial from an information-theoretic perspective, usefulness remains completely undefined, and the completely random selection of concepts to combine is computationally inefficient.

The missing pieces are both smarter generation and principled selection. [Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) provides exactly this: a framework for both targeting high-potential concept combinations and distinguishing breakthrough insights from meaningless novelty.

## The Core Problem: Both Generation and Selection Need Fixing

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

## What Made Darwin's Insight Special?

To see how this framework applies, let's examine what exactly distinguishes a breakthrough insight from meaningless word association. 

The key insight is recognizing when you can efficiently describe patterns but lack causal mechanisms to explain why those patterns exist—what we call **explanatory debt**. Explanatory debt occurs when you can catalog observations into recognizable patterns, but explaining *why* those patterns exist requires many separate, complex causal mechanisms. High explanatory debt signals opportunity: when you have simple pattern descriptions but expensive causal explanations, you're ripe for a theoretical breakthrough that explains the patterns through a single underlying mechanism.

Consider what happened in October 1838. Darwin had been wrestling with the mystery of adaptation for years, accumulating observations that defied easy explanation. But crucially, he had first recognized that adaptation itself was deeply unexpected under existing theories.

The widespread fact that organisms are exquisitely fitted to their environments is easy to describe but extraordinarily difficult to explain without evolution. You can summarize the pattern in a few words: "species are well-adapted to their ecological niches." But explaining *why* this pattern exists requires invoking separate causal mechanisms for each case—divine creation events, Lamarckian use/disuse, climate-driven modifications. The gap between simple description and complex explanation creates a massive puzzle, flagging this domain as ripe for theoretical breakthrough.

Darwin had accumulated observations that all pointed to this same puzzling pattern:

- Geographic variation: Finch beaks across Galápagos islands, mockingbird differences
- Domestication experiments: Pigeon breeding, livestock trait inheritance  
- Fossil succession: Ancient species related but distinct from modern forms
- Biogeographic puzzles: Why similar environments had different species
- Organism-environment fit: Exquisite adaptations everywhere he looked

Each adaptation appeared as a separate puzzle piece. His world-model needed case-by-case explanations—divine creation events, Lamarckian use/disuse, climate shocks—a patchwork requiring increasingly complex explanations.

Then he read Malthus on population growth. Population pressure + resource competition + heritable variation → differential survival → accumulated adaptation over generations.

**The breakthrough moment**: A vast pattern (organismal adaptation, divergence, extinction, branching) collapsed to a short causal recipe:

Variation + Heredity + Overproduction + Competition → Selection → Cumulative Change

This connection is extraordinarily significant. Darwin's insight is easy to describe (the simple causal recipe above) but would be extraordinarily difficult to generate without the prepared mind. The requirements to produce this insight are massive—you need years of biological observation, exposure to Malthus at the right moment, and the cognitive ability to see the connection. But the insight itself is minimal—a short causal mechanism that explains thousands of observations.

Here's the puzzle: Why was this connection earth-shaking rather than just another random word pairing? What distinguished Darwin's "population theory + adaptation puzzles" from our hypothetical "blue sky + pizza cheese"? 

Both involve connecting previously separate concepts. Both produce something novel. Yet one launched a scientific revolution while the other is meaningless noise.

## How Simplicity Theory Recognizes Genuine Insights

Simplicity Theory provides the answer by measuring something specific: **compression gain**. When Darwin connected population pressure to adaptation, he didn't just create another random association. He achieved massive compression of explanatory complexity.

The key insight for AI: Simplicity Theory serves dual functions in discovery systems. First, it identifies domains ripe for breakthrough by detecting patterns with high unexpectedness—situations that are easy to describe but hard to explain under current theories. Second, it recognizes genuine insights by measuring compression gain when new connections suddenly explain many previously separate observations under one short generative scheme.

## The Dual Functions of Simplicity Theory in Discovery

We're proposing Simplicity Theory for both discovery targeting and insight selection, using the same unexpectedness measure for different purposes. This dual application leverages ST's core strength: detecting when simple descriptions require complex generation processes.

**The Two-Stage Reality**: A complete discovery system needs:
1. **Domain targeting** (ST-based): "This pattern has high unexpectedness, flagging the domain as ripe for breakthrough"
2. **Insight selection** (ST-based): "This connection has high unexpectedness, indicating genuine compression of explanatory complexity"

Note that both stages use Simplicity Theory's unexpectedness measure, but applied to different targets: first to identify promising domains for investigation, then to recognize valuable insights within those domains.

Consider these examples:

**Domain: Widespread organismal adaptation**
- Unexpectedness (U): Very High (easy to describe, hard to explain)
- ST Function: Domain targeting (flags this area for investigation)
- Result: Darwin focuses on adaptation puzzles

**Insight: Population theory + adaptation connection**
- Unexpectedness (U): Very High (simple mechanism, vast compression)
- ST Function: Insight selection (recognizes breakthrough)
- Result: Natural selection theory

**Event: Meeting cousin on random flight**
- Unexpectedness (U): Very High
- ST Function: Neither (surprising but no explanatory compression)
- Result: Curious coincidence, not scientific insight

**How the dual ST functions work together**: Domain targeting identifies areas where current theories require complex explanations for simple patterns—signaling theoretical gaps. Insight selection recognizes when new connections achieve massive compression—signaling breakthrough discoveries. Both functions detect the same underlying signature: the gap between description simplicity and generation complexity.

**The key advantage**: This approach directly targets the compression patterns that characterize genuine scientific discovery. Rather than relying on separate heuristics for "where to look" and "what to keep," both functions emerge from the same information-theoretic principle.

**Remaining limitation**: While ST can identify promising domains and recognize valuable insights, it doesn't guarantee that insights will be practically useful for specific goals. A complete discovery system might need additional goal-conditioned evaluation, but ST provides the crucial foundation for distinguishing meaningful discoveries from random novelty.

## How the Framework Would Discover Natural Selection

Rather than just explaining Darwin's historical breakthrough, let's demonstrate how an AI system using our framework would systematically discover natural selection.

### Step 1: Building Explanatory Debt (The Prepared Mind)

Consider how Darwin accumulated explanatory debt: He could accurately describe finch beak variations across islands—short thick beaks on seed-rich islands, long thin beaks where nectar-feeding was common. This descriptive knowledge compressed many observations into recognizable patterns. But *why* did these patterns exist? Each required a separate causal story: "God designed each beak for its environment" or "Beaks stretched through use and were inherited."

Our AI system encounters the same observational patterns that puzzled Darwin. Each observation requires separate explanation in the current world model. The system's representation grows increasingly complex: divine creation events for each species, climate-driven adaptations for each environment, use/disuse mechanisms for each trait change. High explanatory debt accumulates.

Framework trigger: When you can describe patterns efficiently but explaining *why* those patterns exist requires many separate causal mechanisms, the system flags this domain as "ripe for compression."

### Step 2: Guided Concept Combination

The system identifies concepts appearing frequently in high-debt explanatory contexts:
- Heredity (breeding experiments, family resemblances)
- Variation (individual differences within species)
- Population dynamics (group sizes, resource limits)
- Environmental pressures (food scarcity, predation, climate)

Rather than random combination, the framework prioritizes connecting concepts that appear in multiple hard-to-explain observations.

### Step 3: Recognition and Compression Testing

When the system combines "population pressure + heritable variation + differential survival," it tests for compression gain:

Before: Track N distinct adaptive traits across species. Each requires separate causal story. Total complexity ≈ N × k parameters.

After: Single mechanism—"populations produce more offspring than can survive + heritable traits affect survival odds + differential survival accumulates over generations" explains all N observations. Complexity collapses to: base mechanism + local environmental parameters.

The more adaptation puzzles in the database, the bigger the compression gain. With thousands of observations, the significance becomes overwhelming.

### The Crucial Distinction: Insight vs. Meaningless Novelty

Now we can distinguish breakthrough insights from random combinations:

**Type: Darwin's Insight**
- Generation (Cv): Very High (prepared mind + vast observations)
- Description (C): Very Low (elegant causal rule)
- Unexpectedness (U): Massive positive
- Result: Revolutionary theory

**Type: Typical Random Output**
- Generation (Cv): Low (simple selection)
- Description (C): High (arbitrary specifics)
- Unexpectedness (U): Usually negative
- Result: Meaningless novelty

**Type: Semantically-loaded pairs**
- Generation (Cv): Variable
- Description (C): Variable
- Unexpectedness (U): Sometimes positive
- Result: Rarely compressive

**Why random combination usually fails**: Most random pairings are easy to produce (simple selection process) but hard to compress meaningfully (arbitrary word combinations). However, if concept pairs already carry semantic relationships—like "population growth" + "heredity"—even random combinations can occasionally yield insights.

**The real issue isn't randomness per se, but sampling bias**: What matters is whether the generation process is guided toward concepts that appear in explanatory gaps. Without systematic attention to where current theories struggle most, even semantically meaningful combinations produce surface-level associations rather than compression-creating insights.

**Computational reality**: Random search could theoretically find breakthrough insights, but the search space is prohibitively large. Darwin's discovery required both the prepared mind (explanatory debt context) and guided attention to promising concept combinations.

## From Theory to Implementation: Early Experiments with CompLog

While our analysis demonstrates how Simplicity Theory could guide AI discovery systems, a crucial question remains: can these complexity calculations actually be implemented at scale? Recent work by Sileno and Dessalles offers preliminary evidence that this might be possible.

Their [CompLog framework](https://arxiv.org/abs/2307.15453) represents an early experimental attempt to implement Simplicity Theory principles for computational systems. Rather than remaining purely theoretical, CompLog uses Answer Set Programming (ASP)—a form of logic programming that can systematically search through possible solutions to complex problems—to compute approximations of the complexity measures that could drive insight detection.

### Key Implementation Breakthroughs

**Tractable Complexity Calculation**: CompLog solves the core computational challenge by implementing complexity estimation through systematic logical searches. Instead of the intractable full Kolmogorov complexity, the system computes cognitively realistic approximations that capture what human observers actually detect.

**Explanatory Debt Tracking**: The framework distinguishes between **causal** and **descriptive** relations between predicates (basic logical statements about objects and their properties), weighted by complexity. This directly addresses our "explanatory debt tracking problem"—the system can systematically monitor which observations require increasingly complex causal explanations versus simple descriptive patterns.

**Retrospective and Predictive Analysis**: CompLog computes both retrospective ("Why is this observation surprising?") and predictive ("What should we expect to observe?") measures of unexpectedness. This maps directly to the prepared mind/insight detection cycle we described for Darwin's discovery.

**Real Applications**: The system demonstrates concrete capabilities like generating relevant descriptions and handling logical operations (disjunction, negation)—exactly the kind of sophisticated reasoning needed for scientific insight.

### What This Suggests for AI Discovery Systems

CompLog's preliminary results suggest our proposal might be more than speculative. Where we identified computational challenges, CompLog offers potential approaches:

- **"Estimating complexity terms at scale"** → ASP-based complexity computation (in constrained domains)
- **"Tracking explanatory debt across large knowledge bases"** → Weighted causal/descriptive relations (for structured knowledge)
- **"Avoiding combinatorial explosion"** → Cognitively realistic approximations rather than full search (within limitations)

The experiment suggests that Simplicity Theory might be implementable without requiring omniscient world models or exponential search spaces. By using human-like cognitive approximations rather than perfect algorithmic complexity, such systems could potentially become computationally tractable while preserving essential compression-detection capabilities.

### The Knowledge Representation Bottleneck

However, CompLog's power comes with a significant constraint: **it requires carefully structured predicate relationships, not raw text processing**. The system works with explicit causal and descriptive relations between predicates, weighted by complexity values. You can't simply feed it Wikipedia articles and expect Darwin-like insights to emerge.

This limitation is actually quite significant for real-world implementation:

**What CompLog needs**: 
```
3 :: dog. 3 :: cat. 3 :: bird.
4 :: eagle. 4 :: tiger. 4 :: pigeon.
causal_relation(population_pressure, competition, 7).
descriptive_relation(finch, bird, 2).
```

**What it can't handle**: Raw text like "Darwin observed that finch beaks varied across the Galápagos islands, with thick beaks on seed-rich islands and thin beaks where nectar-feeding was common."

This means the "prepared mind" problem—accumulating explanatory debt around specific domains—still requires sophisticated natural language processing to convert observations into the structured predicates that CompLog can work with. The framework solves the complexity calculation problem but doesn't address the knowledge representation challenge.

**Implication for AI Discovery**: A complete system would need two major components:
1. **Text-to-Logic Translation**: Converting natural language observations into structured logical relationships that the system can analyze
2. **CompLog-based Insight Detection**: Using ST to identify compression opportunities in the structured knowledge

The first component remains an open challenge, but CompLog demonstrates that the second is computationally feasible.

**Validation Path**: CompLog provides a starting point for testing aspects of our framework on constrained discovery tasks—potentially rediscovering simple patterns like Mendelian ratios from structured agricultural data, or identifying periodic regularities in historical datasets. While far from the Darwin-like insights we envision, these experiments could help validate whether compression-detection principles work in practice and identify the key bottlenecks for scaling up.

## Making It Work: Guided Generation + Smart Selection

The crucial insight from the Darwin case is that breakthrough discoveries require a prepared cognitive state—a mind loaded with explanatory debt around specific problem domains. But implementing this faces significant computational challenges.

### Remaining Implementation Challenges

While CompLog solves core complexity calculation problems, significant challenges remain for full-scale discovery systems:

**The Scaling Problem**: While CompLog demonstrates tractable complexity estimation for constrained domains, scaling to millions of concept combinations across vast knowledge bases remains challenging. How do you maintain the cognitive realism that makes ST work while handling the scope of real scientific discovery?

**The Domain Integration Problem**: CompLog handles logical relations well, but integrating across heterogeneous domains (biological, physical, mathematical) requires more sophisticated world models. How do you enable cross-domain insights when each field has different complexity patterns?

**The Search Strategy Problem**: Even with efficient complexity calculation, the space of possible concept combinations grows exponentially. How do you search this space intelligently without either missing breakthrough insights or drowning in computational cost?

**Open Questions**:
- How can CompLog's ASP-based approach scale to real scientific knowledge bases?
- Can the causal/descriptive distinction be maintained across domain boundaries?
- How do you balance exploration vs. exploitation when the payoff structure is unknown?
- What hybrid architectures best combine ST-based insight detection with domain-specific reasoning?

CompLog provides the computational foundation, but translating this to full-scale AI discovery systems requires integrating it with existing AI techniques—reflection-based agents, generative design systems, knowledge graph analysis.

## Alternative Path: Bayesian Model Selection

While Simplicity Theory provides our primary framework for insight detection, it's worth noting that Bayesian model inference offers a complementary approach to the same fundamental goal of finding meaningful patterns through compression.

The Bayesian framework implements an automatic preference for simpler models through what's called "Bayesian Occam's Razor"—complex models that can explain too many different outcomes are naturally penalized because they spread their predictive probability too thinly. This connects to Simplicity Theory through the Minimum Description Length (MDL) principle, a mathematical framework showing that both approaches ultimately seek to minimize the total length needed to describe both the model and the data it explains.

For AI implementation, this suggests potential hybrid architectures: Bayesian methods for systematic learning and model updating, paired with ST-like mechanisms for real-time salience detection. The choice may depend on whether you're building systems for continuous learning (Bayesian strength) or breakthrough insight detection (ST strength).

Our focus on Simplicity Theory reflects its particular suitability for the "Aha!" moment detection that Gwern's proposal requires, but a complete discovery system might benefit from both approaches.

## Conclusion

Gwern's insight about AI needing background processing is brilliant, and he's honest about the computational challenges of random combination. But his brute-force approach leaves core problems unsolved: how to intelligently target promising concept combinations and how to recognize genuine insights when they emerge.

**Partial but promising progress**: Simplicity Theory offers both generation guidance (target explanatory gaps) and selection criteria (compression detection), and CompLog provides early evidence that complexity calculation—arguably the hardest part of the puzzle—might be implementable. However, significant challenges remain: converting raw observations into structured predicates that ST can process, scaling beyond constrained domains, and integrating across heterogeneous knowledge bases. We've sketched a path toward insight detection but haven't solved the broader knowledge structuring problem.

**Why Simplicity Theory matters specifically**: While other approaches like Bayesian inference excel at systematic learning from data streams, ST offers something unique—a formal framework for detecting the salience of individual events and breakthrough moments. This makes it particularly suited to Gwern's original challenge: how do you recognize when a random connection has produced genuine insight rather than meaningless novelty?

**Ready for initial experiments**: With CompLog providing an experimental foundation, we can begin testing simplified versions of this framework on constrained discovery tasks—perhaps rediscovering basic patterns in structured datasets or testing compression-detection on prepared examples. While we're still far from Darwin-like insights, the framework has moved from pure theory toward something that might eventually be empirically testable.

**The bigger picture**: The distinction between mere novelty and genuine insight will ultimately separate truly intelligent systems from sophisticated text generators. What we've outlined here combines theoretical framework with practical implementation—building on both information theory and cognitive science to make AI "daydreaming" a systematic discovery process rather than brute-force search.

*This article itself emerged from motivated search—gaps identified in Gwern's computational proposal generated the drive to find concepts that could address those specific limitations, leading to the connection with Dessalles' cognitive framework.*