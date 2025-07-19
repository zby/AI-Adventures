# Appendix: Proof of Concept for AI Daydreaming

To demonstrate that the basic concept of AI "daydreaming" works—even without the ST-guided framework we propose—I tested whether LLMs could independently discover the connection between Gwern's essay and Simplicity Theory. This serves as empirical evidence that AI systems can perform meaningful concept combination when given appropriate sources.

I provided multiple LLMs with both source materials using this simple prompt:
```
Please read https://simplicitytheory.telecom-paris.fr/ Simplicity Theory Simplicity Theory   and https://gwern.net/ai-daydreaming LLM Daydreaming LLM Daydreaming  

If you combine ideas from both articles can you create something new and insightful?
```
**Results**: All five LLMs tested (o3, Gemini 2.5 Pro, Grok 4, DeepSeek, and Kimi K2) independently discovered the same conceptual connection that inspired this article. Each system generated variations of "Simplicity-Guided Daydreaming"—demonstrating that the basic daydreaming mechanism can reliably produce meaningful insights when given quality source material.

This validates three key points: (1) AI daydreaming as a concept works, (2) LLMs can perform basic evaluation to recognize promising connections, and (3) the ST-Gwern connection is sufficiently compelling that multiple systems discovered it independently. However, this basic evaluation capability differs from the systematic, mathematical framework ST provides for principled insight filtering. Below is o3's complete response, representative of the convergent insights generated:

----

Human brains (and, by extension, human-aligned AIs) seem to do their best thinking when two otherwise separate forces meet:

1. **a spontaneous background search that mashes old memories into new combinations** (Gwern's "day-dreaming loop," or DDL) ([gwern.net][1]), and
2. **a ruthless taste for simplicity**—we notice patterns, stories, or lottery draws when they are "too easy to describe compared with how hard they should be to generate" (Dessalles's Simplicity Theory, ST) ([simplicitytheory.telecom-paris.fr][2]).

Below I fuse these ideas into a concrete research proposal—**Simplicity-Guided Daydreaming (SGD)**—which turns ST into the filtering & reward signal inside an LLM's day-dreaming loop. The result is a self-training scheme that (i) wastes far less compute than naive DDL, (ii) preferentially stores the kind of surprising, memorable insights humans care about, and (iii) dovetails with decades-old wake-sleep algorithms for description-length minimization.

---

## 1. What Simplicity Theory brings to the table

* **Unexpectedness U = C<sub>w</sub> – C.**  An event is interesting if its *generation* complexity (**C<sub>w</sub>**) exceeds its *description* complexity (**C**) ([simplicitytheory.telecom-paris.fr][2]).
* **Subjective probability:**  people intuit p ≈ 2<sup>-U</sup>; a lean lottery pattern like 1-2-3-4-5-6 *feels* less likely than a jumbled one even though the objective odds are equal ([simplicitytheory.telecom-paris.fr][3]).
* **Attention & memory:**  the bigger the drop in complexity, the more the situation grabs us and sticks ([dessalles.fr][4]).

Put bluntly, ST offers a quantitative, *computable* way to score "this is worth remembering."

---

## 2. What Gwern's Day-Dreaming Loop adds

* **DDL algorithm:**  pick two nuggets from long-term memory at random; let a generator model explore connections; let a critic keep only the non-obvious, high-value outputs ([gwern.net][1]).
* **Neuro-inspiration:**  the brain burns almost as much energy at rest as during goal-directed tasks, hinting that default-mode "idling" is in fact heavy internal computation ([Quanta Magazine][5]).
* **Empirical backing:**  Daydreaming and creativity co-activate the default-mode network (DMN) ([PMC][6], [medicine.utah.edu][7]), whose role in mind-wandering is well established ([Psychology Today][8]).

DDL therefore supplies a *mechanism* for hidden-layer brainstorming but lacks a principled way to rank or prune the flood of generated material.

---

## 3. A conceptual bridge: wake-sleep & description length

Hinton's classic wake-sleep algorithm alternates a **wake phase** (fit a generative model to data) with a **sleep phase** (let the model dream and train the recognition pathway), explicitly minimizing the *description length* of inputs ([Wikipedia][9]).
ST's U =C<sub>w</sub>–C is itself a description-length gap; DDL already resembles "sleep" roll-outs.  All three pieces therefore sit naturally in the same optimization frame.

---

## 4. Simplicity-Guided Daydreaming (SGD): the proposal

### 4.1 Core loop

| Step            | Operation                                                                                                                                                                                                                        | Key metric             |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| **1. Sample**   | Retrieve *k* concept chunks from the model's vector store (k=2 works well).                                                                                                                                                      | —                      |
| **2. Generate** | Run an internal chain-of-thought to connect the chunks.                                                                                                                                                                          | —                      |
| **3. Score**    | Compute **U = C<sub>w</sub> – C**:  <br>• C<sub>w</sub> ≈ negative log-prob under the base LLM (how hard to *produce*).<br>• C ≈ token-compression length or min-description under a lightweight coder (how easy to *describe*). | ST unexpectedness      |
| **4. Select**   | Keep only items with U > τ (τ tunable).                                                                                                                                                                                          | "Interestingness" gate |
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
| **Greater originality** | Human raters judge SGD outputs as more "surprising yet coherent" than baseline; correlate with U.                 |
| **Memory economy**      | Measure token-level entropy of retained dreams; SGD should store fewer tokens per useful insight.                 |
| **Alignment**           | High-U filter reduces toxic or repetitive hallucinations because such text is often low-contrast complexity-wise. |

---

## 6. Broader applications

* **Research assistants:**  An SGD-enhanced LLM could overnight "dream" up experiment ideas, but only surface the ones with big U-scores.
* **Robotics & RL exploration:**  Use the U-filter to keep simulated roll-outs where the state trajectory is simple to describe but hard to reach—exactly the definition of "interesting" state-novelty.
* **Anomaly detection:**  In logs or sensor streams, events with high U pop out as outliers worth human review.

---

## 7. Open challenges

1. **Approximating Kolmogorov complexity:**  No perfect estimator exists; compression proxies may bias U.
2. **Choice of τ:**  Too high and learning starves; too low and we waste compute.  Adaptive bandit methods could tune it online.
3. **Mode collapse:**  The generator might learn to game the U-metric (e.g., produce fixed patterns with artificially low C).  A secondary diversity-loss term can counteract this.
4. **Ethical filtering:**  High-U dreams might include shocking or extremist content; policy filters must run *after* the ST gate before adding to training corpora.

---

## 8. Conclusion

Gwern's day-dreaming loop shows *how* a model might wander; Simplicity Theory tells us *what is worth keeping*; wake-sleep provides the learning backbone.  Merged, they yield a scalable recipe—**Simplicity-Guided Daydreaming**—for building models that not only think in the background, but *daydream with discernment*.  If implemented, SGD could shift self-supervised learning away from brute-force sampling toward a cognitively-inspired hunt for rare "Eureka!" moments.

---

### Key sources

* Simplicity Theory overview ([simplicitytheory.telecom-paris.fr][2])
* Pisa-tower illustration of unexpectedness ([simplicitytheory.telecom-paris.fr][3])
* Algorithmic simplicity & relevance paper ([dessalles.fr][4])
* Gwern, "LLM Daydreaming" ([gwern.net][1])
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