# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but this is prohibitively expensive. Simplicity Theory provides a mathematical framework that could address this challenge, offering our first principled approach to computationally evaluating insights—though significant implementation challenges remain.*

Picture yourself stuck on a problem for weeks, then while making coffee, two unrelated ideas suddenly click together. [Gwern's proposal for AI "daydreaming loops"](https://gwern.net/ai-daydreaming) tries to reverse-engineer exactly this process: building AI systems that make creative connections by combining facts and filtering for useful insights.

But Gwern's approach has two critical gaps. First, while he can check if ideas are coherent and measure their novelty, he leaves "usefulness" completely undefined. Second, randomly selecting concepts to combine is computationally inefficient—we need smarter targeting.

This is where [Simplicity Theory](https://simplicitytheory.telecom-paris.fr/) becomes relevant. ST offers a promising mathematical approach to Gwern's "usefulness" problem—providing a theoretical framework to distinguish meaningful insights from meaningless associations. ST addresses one part of the search problem—recognizing when concepts form coherent puzzles (opportunities for compression gain)—but leaves another part unsolved: the systematic generation of which concepts to consider combining in the first place.

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

The key insight that makes ST computationally tractable is that complexity is always relative to the observer's knowledge (Dessalles, 2008; Chater & Vitányi, 2003). This transforms abstract algorithmic complexity into practical calculations for real systems, as demonstrated in computational implementations of ST for relevance detection (Dessalles, 2013).



## The Core Improvement: From Blind Search to Targeted Search—But Still Exponential

To see why Simplicity Theory improves but doesn't solve the search problem, consider what different approaches would actually produce:

- **Blind search**: Randomly select articles about "sky color" and "pizza ingredients" → "Blue sky pizza cheese"
- **ST-guided search**: First identify puzzle pieces (Darwin's adaptation observations), then search for missing pieces (finding Malthus)

Simplicity Theory provides a crucial improvement over Gwern's brute-force approach for puzzle recognition. While Gwern accepts massive computational waste by randomly combining all concepts, ST can first identify which concepts form puzzles, dramatically narrowing the search space for the recognition phase. Darwin's success demonstrates this: he recognized his adaptation observations formed a puzzle, then targeted his search for the missing mechanism.

But here's the key limitation: **the search challenge scales exponentially with the complexity of discovery type**. Darwin-style breakthroughs—where a recognized scientific puzzle needs one key missing piece—become quite manageable. The adaptation mystery was widely acknowledged in Darwin's era; adding Malthus's population pressure mechanism solved a known problem. Multi-puzzle breakthroughs requiring simultaneous recognition and connection of several unrecognized patterns remain exponentially challenging.

## What Made Darwin's Insight Special: A Retrospective Thought Experiment

To illustrate how Simplicity Theory's evaluation framework might work in practice, let's examine what distinguishes a breakthrough insight from meaningless word association. **Important caveat: This is purely retrospective analysis—a thought experiment showing how ST's framework could theoretically apply to known breakthroughs, not evidence that ST would have identified this insight prospectively.** We're fitting Darwin's well-documented discovery to ST's framework after the fact to illustrate the theory's concepts.

The key insight is recognizing when you can efficiently describe patterns but lack causal mechanisms to explain why those patterns exist—this signals opportunities for compression gain.

Consider what happened in October 1838. Darwin had been wrestling with the mystery of adaptation for years, accumulating observations that defied easy explanation. But crucially, he had first recognized that adaptation itself was deeply unexpected under existing theories.

The widespread fact that organisms are exquisitely fitted to their environments is easy to describe but extraordinarily difficult to explain without evolution. You can summarize the pattern in a few words: "species are well-adapted to their ecological niches." 

But explaining *why* this pattern exists requires invoking separate causal mechanisms for each case—divine creation events, Lamarckian use/disuse, climate-driven modifications. This signals massive opportunity for compression gain, flagging this research direction as ripe for theoretical breakthrough.

Darwin had accumulated observations that all pointed to this same puzzling pattern: geographic variation (Galápagos finches), domestication experiments (pigeon breeding), fossil succession, and exquisite organism-environment fit everywhere he looked. Each adaptation appeared as a separate puzzle piece requiring case-by-case explanations—divine creation events, Lamarckian use/disuse, climate shocks—a patchwork of increasingly complex mechanisms.

Then he read Malthus on population growth. Population pressure + resource competition + heritable variation → differential survival → accumulated adaptation over generations.

**Compression gain in action**: Darwin found one mechanism that explained thousands of separate observations. A vast pattern collapsed to a short causal recipe: Variation + Heredity + Overproduction + Competition → Selection → Cumulative Change.

This illustrates ST's insight recognition framework. Darwin's breakthrough appears easy to describe but would be extraordinarily difficult to generate without the prepared mind—years of biological observation, exposure to Malthus at the right moment, and the cognitive ability to see the connection.

So what does this mean for building real AI discovery systems?

## Implementation Reality: What Can We Actually Build?

Simplicity Theory addresses Gwern's two challenges very differently—providing a principled approach to one while making limited progress on the other.

**What ST Addresses Directly**: **Insight Recognition**
- ST provides a concrete mathematical framework to distinguish meaningful insights from meaningless associations through compression gain detection
- This provides a principled approach to Gwern's "usefulness" filter problem—offering a theoretical foundation for evaluating whether a proposed connection represents genuine discovery
- What distinguished Darwin's "population theory + adaptation puzzles" from our hypothetical "blue sky + pizza cheese"? Both involve connecting previously separate concepts and both produce something novel. Yet one launched a scientific revolution while the other is meaningless noise. Darwin's connection achieved compression gain while random word combinations typically create no explanatory value
- [Recent computational work](https://arxiv.org/abs/2307.15453) demonstrates these calculations are feasible in constrained domains through logic programming, though practical implementation for natural language remains an open challenge

**What ST Improves But Doesn't Solve**: **Concept Generation**
- ST addresses puzzle recognition—identifying when existing concepts form coherent patterns that signal compression opportunities
- However, ST leaves unsolved the systematic generation problem: determining which specific concepts are worth considering for combination in the first place
- ST excels at evaluating proposed combinations but provides minimal guidance for generating them—the crucial middle step of navigating the exponential search space remains largely unsolved

Can we build AI that discovers like Darwin did? The question cuts to the heart of whether computational systems can replicate the leap from scattered observations to transformative insight. The path from theoretical framework to working system requires bridging three critical gaps:

### Building Block 1: Validated Concept Combination

**What Works**: Modern LLMs successfully perform creative concept combination when prompted appropriately (see Appendix for empirical evidence). This validates Gwern's basic premise that AI systems can generate novel connections between disparate sources.

**Why This Matters**: Concept combination is the foundation—without it, no discovery system is possible. But raw combination generates mostly noise, creating the filtering challenge that ST aims to solve.

### Building Block 2: The Evaluation Bridge

**The Challenge**: Moving from "can generate combinations" to "can systematically evaluate insights" requires computational implementation of ST's unexpectedness scoring. While LLMs demonstrate basic evaluation capabilities (as shown in the Appendix), they lack the principled framework ST provides.

**Current Status**: Two approaches show promise but face different limitations:

**Formal Logic Route**: The [CompLog framework](https://arxiv.org/abs/2307.15453) demonstrates ST's computational feasibility through compression ratios in formal logic. Proven to work, but requires manual encoding of concepts into logic representations—impractical for natural language knowledge systems.

**LLM Approximation Route**: Using language models to estimate U = Cv - C through computational proxies:
• Cv ≈ negative log-prob under the base LLM (how hard to produce)  
• C ≈ token-compression length or min-description under a lightweight coder (how easy to describe)

This approach works directly with natural language, bypassing CompLog's encoding bottleneck. However, it remains unproven whether LLMs can capture the precise complexity relationships ST requires for systematic filtering at scale.

**Why This Matters**: While LLMs can perform basic insight evaluation (recognizing interesting vs. boring connections), they lack systematic principles for distinguishing breakthrough insights from sophisticated-sounding but ultimately shallow combinations. ST provides the mathematical framework for principled evaluation that could solve Gwern's filtering problem.

### Building Block 3: Discovery Architecture

**The Vision**: Combine validated components into discovery-capable systems:

**Puzzle Detection Systems**: Scan for patterns with simple descriptions but complex explanations—ST's signature of breakthrough opportunities. Applications range from monitoring research literature for emerging conceptual puzzles to analyzing personal knowledge systems (Obsidian, Roam Research) for unexpectedness patterns.

**Hybrid Discovery Systems**: Human concept generation paired with AI insight evaluation—researchers propose connections while AI evaluates compression gain, creating human-AI teams optimized for different aspects of discovery.

**Current Reality**: These remain largely speculative, dependent on solving the evaluation bridge problem first.

### The Remaining Limitation: Multi-Puzzle Complexity

Even with working ST evaluation, different discovery types face different scaling challenges:

**Recognized puzzle + missing piece breakthroughs** like Darwin's (adaptation mystery + population mechanism) could become tractable—the puzzle was already acknowledged, requiring only one key connection.

**Multi-puzzle breakthroughs** requiring simultaneous recognition and connection of several unrecognized patterns remain computationally intractable due to exponential search spaces. For example, Einstein's relativity required recognizing that space-time, mass-energy equivalence, and gravity were all interconnected puzzles that needed to be solved together—not widely acknowledged as connected problems beforehand.

### Implementation Status: Promising but Incomplete

We have **validated components** (concept combination), **theoretical frameworks** (ST evaluation), and **architectural visions** (hybrid discovery systems). The critical missing piece is bridging theory to practice—developing reliable ST-guided filtering that works with natural language knowledge systems.

The most promising path forward involves LLM-based approximation of ST metrics, but substantial empirical work is needed to validate whether this approach can reliably distinguish meaningful insights from sophisticated-sounding noise.

## Applications and Future Directions

## Conclusion

We have promising theory and emerging computational approaches, but significant experimentation is required to determine if this actually works in practice.

If successful, several applications become possible:

**Research Tools**: AI systems could scan research literature for compression opportunities, knowledge management systems could flag when accumulated notes form unexpectedness patterns, and browser extensions could display unexpectedness ratings for papers.

**Information Systems**: Email filters could prioritize high-compression insights, and social media algorithms could surface genuinely unexpected connections rather than engagement-driven content.

**AI Training**: ST could address a fundamental challenge in LLM development. While mathematical problems provide objectively verifiable answers, insight generation typically requires expensive human preference ratings to distinguish genuine insights from sophisticated-sounding nonsense. ST's compression gain metrics could provide automatic verification, enabling training toward genuine discovery rather than just fluent text.

The potential is significant: research tools that actively support discovery rather than just information retrieval. But substantial work remains to validate whether these theoretical frameworks translate into practical systems.

What will you build?
