**Why "Out-of-Distribution" Misses the Point About AI Creativity**

A common worry: LLMs can only remix their training data, so they can't produce genuinely new knowledge. They're stuck "in distribution," unable to make the creative leaps that real discovery requires.

This conflates two different things. Yes, any model samples from some representable space. But discovery doesn't require escaping that space—it requires searching it effectively and recognizing correct answers when found.

Here's a simple counterexample. Take a generator that enumerates well-formed candidates—mathematical proofs, programs, molecular structures. Pair it with a verifier that checks each against fixed criteria: Does this proof derive from the axioms? Does this code compile and pass its tests? Does this molecule satisfy the constraints?

This pair already constitutes a discovery machine. In mathematics, exhaustive enumeration plus a proof checker will eventually produce all theorems of a formal system. **The generator doesn't need intelligence. The verifier doesn't need creativity.** The bottleneck is efficiency and verification quality, not whether candidates come from "outside a distribution." What matters is whether your search space contains the knowledge you seek and whether you can recognize it.

### Where LLMs fit

LLMs are learned heuristic samplers. They guide search toward plausible structures—proofs that look valid, code that looks compilable, molecules that appear chemically sensible. Replace blind enumeration with an LLM and you get intelligent prioritization of promising candidates. With a strong verifier, you can transform plausible guesses into reliable discoveries.

|                      | Weak Verifier                              | Strong Verifier                        |
| -------------------- | ------------------------------------------ | -------------------------------------- |
| Weak Generator       | Nonsense in, nonsense out                  | Slow but real discovery                |
| Strong Generator     | Fluent errors that look convincing         | Practical discovery at useful rates    |

LLMs occupy the bottom row. Their value lies in heuristic search guidance, not in mystical creativity. Progress depends on moving from left to right—building stronger verifiers.

### Implications

**The "in-distribution versus out-of-distribution" framing asks the wrong question.** Discovery happens through exploring combinatorial spaces and filtering for correctness, not through leaps beyond statistical boundaries. Generation plus verification isn't the only approach—reinforcement learning, program synthesis, and evolutionary methods offer different paths—but it suffices to show the constraint isn't fundamental.

The real bottleneck in this paradigm is verification. Many domains lack theorem provers or analyzers rich enough to certify results. Empirical verification can be slow or expensive. Often we can't even specify what "correct" means precisely enough to check it automatically.

The most productive AI-augmented workflows pair models with tight feedback loops: test suites, formal specifications, proof checkers, validated simulators. This benefits both discovery and safety, filtering harmful outputs and aligning incentives toward correctness. Progress requires building stronger verifiers and optimizing for verified discoveries per unit of compute.

### Common objections

*"Enumerating strings can't create anything genuinely new."* Novelty comes from the space you search. If a proof has never been written but exists within your search space, finding it is new knowledge.

*"Verifiers just regurgitate established knowledge."* Verifiers adjudicate. In mathematics they certify logical consequence from axioms. In science they connect hypotheses to measurements. They turn candidate strings into facts.

*"Some truths aren't provable."* True, but that's a limit on what a particular formal verifier can certify, not on generation. It argues for diversified verification methods—formal, empirical, statistical.

*"Generation plus verification isn't how humans are creative."* Perhaps, but that's beside the point. The claim was that LLMs can't be creative because they're stuck in-distribution. This counterexample shows that constraint isn't fundamental.

### The better questions

Instead of asking whether LLMs can "step out of distribution," ask:

- What mechanisms can produce reliable novelty?
- What verifiers can we build or strengthen?
- How do we structure search spaces and feedback loops to enable discovery?

Answer those and new knowledge follows—not by magic, but by method.
