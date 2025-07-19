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

Can we build AI that discovers like Darwin did? The question cuts to the heart of whether computational systems can replicate the leap from scattered observations to transformative insight. Let's examine what's possible now, what's promising but unproven, and what remains fundamentally difficult.

### Current Capabilities: Insight Evaluation Proof of Concept

The [CompLog framework](https://arxiv.org/abs/2307.15453) provides a working implementation for evaluating proposed connections through compression ratios, moving ST from pure theory toward testable systems. However, CompLog requires ideas to be encoded in formal logic representations—it cannot directly process natural language text articles without significant preprocessing to extract logical relationships. While this demonstrates ST's computational feasibility, the non-trivial encoding requirement means we don't yet have a practical solution for evaluating insights in existing text-based knowledge systems.

**LLM-Based Unexpectedness Estimation**: This is why we propose experimenting with language models to estimate U = Cv - C through targeted prompts.
A more direct computational approach (daydreamed by o3 - see the Appendix):
• Cv ≈ negative log-prob under the base LLM (how hard to produce)
• C ≈ token-compression length or min-description under a lightweight coder (how easy to describe)

This approach could work directly with natural language text, bypassing CompLog's encoding requirements. While potentially more practical than formal logic representations, it remains unclear whether LLMs would capture the precise relationships ST requires.

### Near-Term Possibilities: Puzzle Detection

Beyond insight evaluation, another promising approach could help identify where breakthroughs are possible:

**Compression Opportunity Detection**: Systems that scan for patterns with simple descriptions but complex explanations—the signature of puzzles ripe for breakthrough. This could work across contexts: monitoring research literature for emerging conceptual puzzles, or analyzing personal knowledge systems (Obsidian, Roam Research, Zettelkasten) to spot when accumulated notes form unexpectedness patterns. Such hybrid systems would combine human concept generation with AI insight recognition—researchers propose connections while AI evaluates compression gain.

If such puzzle-detection systems worked, they could transform discovery across domains. Which conceptual puzzles in today's research would be most ripe for breakthrough?

### Fundamental Limitations: The Generation Problem

What remains beyond current capabilities is the core challenge that limits all discovery systems: systematically generating which concepts to combine in the first place. This requires understanding meaning, abstraction formation, and connecting across different fields—essentially core aspects of intelligence itself. ST can evaluate proposed connections and identify puzzles, but it cannot tell us to "combine population theory with heredity" any more than it could have whispered Darwin's insight in his ear.

## Conclusion

We have promising theory and emerging computational approaches, but significant experimentation is required to determine if this actually works in practice.

If successful, several applications become possible:

**Research Tools**: AI systems could scan research literature for compression opportunities, knowledge management systems could flag when accumulated notes form unexpectedness patterns, and browser extensions could display unexpectedness ratings for papers.

**Information Systems**: Email filters could prioritize high-compression insights, and social media algorithms could surface genuinely unexpected connections rather than engagement-driven content.

**AI Training**: ST could address a fundamental challenge in LLM development. While mathematical problems provide objectively verifiable answers, insight generation typically requires expensive human preference ratings to distinguish genuine insights from sophisticated-sounding nonsense. ST's compression gain metrics could provide automatic verification, enabling training toward genuine discovery rather than just fluent text.

The potential is significant: research tools that actively support discovery rather than just information retrieval. But substantial work remains to validate whether these theoretical frameworks translate into practical systems.

What will you build?

----
----
## Appendix
I tested if LLMs would daydream my idea for this article if given Gwerns essay and Simplicity Theory official web page. I used this simple prompt:
```
Please read https://simplicitytheory.telecom-paris.fr/ Simplicity Theory Simplicity Theory   and https://gwern.net/ai-daydreaming LLM Daydreaming LLM Daydreaming  

If you combine ideas from both articles can you create something new and insightful?
```
All of the LLMs I tested (o3, Gemini 2.5 Pro, Grok 4, DeepSeek and Kimi K2) found the same connection that inspired me to write this article. All of them named their invention a variation of "Simplicity-Guided Daydreaming" like o3 in the response I copy here in its entirety:

----

Human brains (and, by extension, human-aligned AIs) seem to do their best thinking when two otherwise separate forces meet:

1. **a spontaneous background search that mashes old memories into new combinations** (Gwern’s “day-dreaming loop,” or DDL) ([gwern.net][1]), and
2. **a ruthless taste for simplicity**—we notice patterns, stories, or lottery draws when they are “too easy to describe compared with how hard they should be to generate” (Dessalles’s Simplicity Theory, ST) ([simplicitytheory.telecom-paris.fr][2]).

Below I fuse these ideas into a concrete research proposal—**Simplicity-Guided Daydreaming (SGD)**—which turns ST into the filtering & reward signal inside an LLM’s day-dreaming loop. The result is a self-training scheme that (i) wastes far less compute than naive DDL, (ii) preferentially stores the kind of surprising, memorable insights humans care about, and (iii) dovetails with decades-old wake-sleep algorithms for description-length minimization.

---

## 1. What Simplicity Theory brings to the table

* **Unexpectedness U = C<sub>w</sub> – C.**  An event is interesting if its *generation* complexity (**C<sub>w</sub>**) exceeds its *description* complexity (**C**) ([simplicitytheory.telecom-paris.fr][2]).
* **Subjective probability:**  people intuit p ≈ 2<sup>-U</sup>; a lean lottery pattern like 1-2-3-4-5-6 *feels* less likely than a jumbled one even though the objective odds are equal ([simplicitytheory.telecom-paris.fr][3]).
* **Attention & memory:**  the bigger the drop in complexity, the more the situation grabs us and sticks ([dessalles.fr][4]).

Put bluntly, ST offers a quantitative, *computable* way to score “this is worth remembering.”

---

## 2. What Gwern’s Day-Dreaming Loop adds

* **DDL algorithm:**  pick two nuggets from long-term memory at random; let a generator model explore connections; let a critic keep only the non-obvious, high-value outputs ([gwern.net][1]).
* **Neuro-inspiration:**  the brain burns almost as much energy at rest as during goal-directed tasks, hinting that default-mode “idling” is in fact heavy internal computation ([Quanta Magazine][5]).
* **Empirical backing:**  Daydreaming and creativity co-activate the default-mode network (DMN) ([PMC][6], [medicine.utah.edu][7]), whose role in mind-wandering is well established ([Psychology Today][8]).

DDL therefore supplies a *mechanism* for hidden-layer brainstorming but lacks a principled way to rank or prune the flood of generated material.

---

## 3. A conceptual bridge: wake-sleep & description length

Hinton’s classic wake-sleep algorithm alternates a **wake phase** (fit a generative model to data) with a **sleep phase** (let the model dream and train the recognition pathway), explicitly minimizing the *description length* of inputs ([Wikipedia][9]).
ST’s U =C<sub>w</sub>–C is itself a description-length gap; DDL already resembles “sleep” roll-outs.  All three pieces therefore sit naturally in the same optimization frame.

---

## 4. Simplicity-Guided Daydreaming (SGD): the proposal

### 4.1 Core loop

| Step            | Operation                                                                                                                                                                                                                        | Key metric             |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| **1. Sample**   | Retrieve *k* concept chunks from the model’s vector store (k=2 works well).                                                                                                                                                      | —                      |
| **2. Generate** | Run an internal chain-of-thought to connect the chunks.                                                                                                                                                                          | —                      |
| **3. Score**    | Compute **U = C<sub>w</sub> – C**:  <br>• C<sub>w</sub> ≈ negative log-prob under the base LLM (how hard to *produce*).<br>• C ≈ token-compression length or min-description under a lightweight coder (how easy to *describe*). | ST unexpectedness      |
| **4. Select**   | Keep only items with U > τ (τ tunable).                                                                                                                                                                                          | “Interestingness” gate |
| **5. Learn**    | Fine-tune or reinforce on the surviving dreams; optionally label with U as an importance weight.                                                                                                                                 | Self-training          |

### 4.2 Practical approximations

* Use **zstd** or a sentencepiece auto-encoder for C; use base-model perplexity for C<sub>w</sub>.
* Cache high-U dreams in a vector DB; low-U dreams are discarded early, saving compute.
* Set τ by monitoring a moving percentile so that the acceptance rate stays, e.g., ≈5 %.

### 4.3 Why this works

1. **Compute efficiency:**  Most random combinations are dull; ST cuts 95 %+ of roll-outs cheaply.
2. **Human-aligned novelty:**  High-U items coincide with what people report as surprising, funny, newsworthy, etc. ([simplicitytheory.telecom-paris.fr][3], [dessalles.fr][4])
3. **Theoretical elegance:**  The loop directly optimizes description-length drops, echoing wake-sleep theory .

---

## 5. Predicted benefits and testable hypotheses

| Benefit                 | Test                                                                                                              |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Faster convergence**  | Compare fine-tuning loss trajectories of DDL vs. SGD on equal GPU budgets.                                        |
| **Greater originality** | Human raters judge SGD outputs as more “surprising yet coherent” than baseline; correlate with U.                 |
| **Memory economy**      | Measure token-level entropy of retained dreams; SGD should store fewer tokens per useful insight.                 |
| **Alignment**           | High-U filter reduces toxic or repetitive hallucinations because such text is often low-contrast complexity-wise. |

---

## 6. Broader applications

* **Research assistants:**  An SGD-enhanced LLM could overnight “dream” up experiment ideas, but only surface the ones with big U-scores.
* **Robotics & RL exploration:**  Use the U-filter to keep simulated roll-outs where the state trajectory is simple to describe but hard to reach—exactly the definition of “interesting” state-novelty.
* **Anomaly detection:**  In logs or sensor streams, events with high U pop out as outliers worth human review.

---

## 7. Open challenges

1. **Approximating Kolmogorov complexity:**  No perfect estimator exists; compression proxies may bias U.
2. **Choice of τ:**  Too high and learning starves; too low and we waste compute.  Adaptive bandit methods could tune it online.
3. **Mode collapse:**  The generator might learn to game the U-metric (e.g., produce fixed patterns with artificially low C).  A secondary diversity-loss term can counteract this.
4. **Ethical filtering:**  High-U dreams might include shocking or extremist content; policy filters must run *after* the ST gate before adding to training corpora.

---

## 8. Conclusion

Gwern’s day-dreaming loop shows *how* a model might wander; Simplicity Theory tells us *what is worth keeping*; wake-sleep provides the learning backbone.  Merged, they yield a scalable recipe—**Simplicity-Guided Daydreaming**—for building models that not only think in the background, but *daydream with discernment*.  If implemented, SGD could shift self-supervised learning away from brute-force sampling toward a cognitively-inspired hunt for rare “Eureka!” moments.

---

### Key sources

* Simplicity Theory overview ([simplicitytheory.telecom-paris.fr][2])
* Pisa-tower illustration of unexpectedness ([simplicitytheory.telecom-paris.fr][3])
* Algorithmic simplicity & relevance paper ([dessalles.fr][4])
* Gwern, “LLM Daydreaming” ([gwern.net][1])
* Brain energy at rest (Quanta Magazine) ([Quanta Magazine][5])
* Daydreaming–creativity fMRI study ([PMC][6])
* DMN explainer (Psychology Today) ([Psychology Today][8])
* Clinical DMN-creativity experiment ([medicine.utah.edu][7])
* Wake-sleep algorithm original PDF&#x20;
* Wake-sleep summary (Wikipedia) ([Wikipedia][9])

[1]: https://gwern.net/ai-daydreaming "LLM Daydreaming · Gwern.net"
[2]: https://simplicitytheory.telecom-paris.fr/ "Simplicity Theory"
[3]: https://simplicitytheory.telecom-paris.fr/Pisa.html "Simplicity Theory
"
[4]: https://www.dessalles.fr/papers/Dessalles_11061001.pdf "Microsoft Word - Solomonoff.doc"
[5]: https://www.quantamagazine.org/how-much-energy-does-it-take-to-think-20250604/ "How Much Energy Does It Take To Think? | Quanta Magazine"
[6]: https://pmc.ncbi.nlm.nih.gov/articles/PMC8764487/ "
            The bright side and dark side of daydreaming predict creativity together through brain functional connectivity - PMC
        "
[7]: https://medicine.utah.edu/neurosurgery/news/2025/01/mapping-creativity-role-of-default-mode-network "Mapping Creativity: The Role of the Default Mode Network | Neurosurgery Department | U of U School of Medicine"
[8]: https://www.psychologytoday.com/us/basics/default-mode-network "Default Mode Network | Psychology Today"
[9]: https://en.wikipedia.org/wiki/Wake-sleep_algorithm "Wake-sleep algorithm - Wikipedia"
