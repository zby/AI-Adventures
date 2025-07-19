# Daydreaming Machines: Why Gwern's AI Proposal Needs More Than Random Connections

*TL;DR: Gwern's AI "daydreaming" proposal tries to make breakthroughs by randomly combining concepts, but faces two problems: exponential search spaces and unreliable LLM evaluation. Simplicity Theory enables a two-phase approach that reduces this complexity while providing principled evaluation criteria*

Picture yourself stuck on a problem for weeks. Then while making coffee, two unrelated ideas suddenly click together and everything makes sense. That "aha!" moment is what [Gwern wants to reverse-engineer](https://gwern.net/ai-daydreaming) in AI systems. His idea is simple: build AI that mixes random facts from its knowledge base, then filters the results for useful insights. Think of it as creating thousands of controlled lightning storms, hoping for a spark.

But there are two big gaps: **the combinatorial explosion problem** (too many possible combinations) and **the evaluation problem** (LLMs can't reliably tell real insights from clever nonsense).

If you have 1,000 concepts, there are about 500,000 ways to combine pairs. But real breakthroughs often need three, four, or more concepts—like Darwin's theory, which needed population pressure + variation + inheritance + time. For 3-concept insights, you get 166 million combinations. For 4-concept insights? Over 41 billion. Most are just noise, like "blue sky + pizza ingredients + bicycle gears + quantum mechanics." Without a good way to spot real insights, you're drowning in combinations that sound deep but mean nothing.

This is where Simplicity Theory helps. It gives us a mathematical filter for real insights—and lets us break the search into two steps: first, find combinations that form real puzzles; then, search for solutions to those puzzles. This two-phase approach slashes the number of combinations we need to check. Instead of searching every possible combination, we use math to focus only on the combinations that matter, making discovery much more efficient.

## How to Recognize a Breakthrough: Simplicity Theory

Walk into a teenager's bedroom and find it spotless. Easy to describe: "completely clean room." But, knowing teenagers, this should be almost impossible. That gap between "easy to describe" and "hard to explain" signals something interesting. This is the core of [Simplicity Theory](https://simplicitytheory.telecom-paris.fr/)—Jean-Louis Dessalles' framework for spotting breakthroughs. ST measures this gap with a simple formula:

**U = Cv - C**

Where:
- **C (description complexity)**: How simply can you describe the observation? 
- **Cv (generation complexity)**: How hard would it be for the world to produce this situation?
- **U (unexpectedness score)**: The gap that signals a breakthrough opportunity

When the gap is large, you've found a puzzle worth solving. The magic happens when insights close that gap. Darwin's evolution explained thousands of "organism fits environment" observations with one simple mechanism: variation + selection + inheritance + time. Huge compression gain—many complex explanations become one simple rule.

But here's the catch: ST can tell you when you've found a good insight, but not which concepts to combine. It's a powerful filter, not a generator. So, we need an architecture that gives us lots of chances to filter, while keeping the number of combinations low. Instead of generating all possible combinations and filtering for insights, we split the problem: first generate and filter for valid puzzles, then generate and filter for insights that solve those puzzles.

## Why ST Enables a Two-Phase Discovery Architecture

Here's how Simplicity Theory (ST) helps us search smarter, not harder. The algorithm uses ST to cut down the search and give clear evaluation.

**Phase 1: Search for Valid Puzzles**
- Search space: All concept combinations from your knowledge base
- Search strategy: Start with smaller combinations, expand step by step
- Generation: Ask the LLM: "What puzzle does this combination suggest?"
- Evaluation: Use ST to filter for real puzzles (high unexpectedness score)
- Stop: When you have enough puzzles or run out of search budget

**Phase 2: Search for Insights**
- Search space: For each validated puzzle, try all combinations of extra concepts
- Search strategy: Start with zero extra concepts, add more as needed
- Generation: Ask LLM: "What insight explains this puzzle with these concepts?"
- Evaluation: Use ST to filter for real insights (look for compression gain)
- Stop: When you find an insight or run out of search budget

Mathematical decomposition reduces total combinations. Instead of searching C(n, k1+k2) combinations directly, you search C(n, k1) + (valid_puzzles × C(remaining, k2)). Since valid puzzles are rare, the second term is much smaller than the original search space. By splitting the search, you avoid wasting time on combinations that don't matter and focus only on promising areas.

**Example with 1000 concepts, 4-concept insights:**
- Traditional: Direct search of all 4-concept combinations = 41+ billion
- Two-phase: C(1000,2) + (valid_puzzles × C(998,2)) = 499,500 + (valid_puzzles × 497,503)

Most combinations like "bicycle + quantum mechanics" or "pizza + weather patterns" don't make real puzzles. Valid puzzles are rare—maybe 0.1% or 0.01% of combinations.

- If 0.1% form valid puzzles: 499,500 + (500 × 497,503) ≈ 249 million combinations
- If 0.01% form valid puzzles: 499,500 + (50 × 497,503) ≈ 25 million combinations

The rarer valid puzzles are, the bigger the computational savings. This two-phase approach makes the search much smaller, but doesn't remove exponential growth entirely. If your domain has lots of real puzzles, Phase 2 can still get big. The main win comes from the rarity of valid puzzles.

## Hierarchical Search in Action: Darwin's Breakthrough

Let's see how this works with a real example—Darwin's theory of evolution. Imagine running this algorithm on a 19th-century naturalist's knowledge base:

**Phase 1: Puzzle Discovery**
- Concept combination: "Organism traits" + "Environmental conditions"
- LLM puzzle generation: "What puzzle does this combination suggest?"
- Generated puzzle: "Why do organisms have traits that perfectly match their environments?"
- ST evaluation:
  - Description complexity (C): Very simple—"perfect environmental fit observed everywhere"
  - Generation complexity (Cv): Extremely high—would need countless separate design explanations
  - Unexpectedness score (U): Huge gap → Validated puzzle

**Phase 2: Insight Generation**
- Try solving the puzzle with extra concepts:
  - 0 extra concepts: "Organisms inherit acquired traits" → Some compression, but not enough
  - 1 extra concept:
    - + "Divine creation" → "God designed perfect fit" → Some compression, but creates new complexity (how does the designer work?)
    - + "Population pressure" → "Competition drives selection for fit" → Massive compression gain!

The search stops when a breakthrough is found at 1 extra concept. Systematic puzzle identification (Phase 1) focuses your resources. Systematic insight search (Phase 2) finds breakthroughs efficiently. This is the practical power of hierarchical over direct search. The breakthrough: Population pressure + variation + inheritance creates a simple mechanism explaining thousands of complex observations. ST's insight evaluation: Massive compression gain achieved. What required countless separate explanations now follows from one simple rule.

This demonstrates how systematic puzzle identification (Phase 1) focuses computational resources on validated targets, then systematic insight search (Phase 2) efficiently finds breakthroughs—the practical power of hierarchical over direct search.

## What Can We Actually Build Today?

We have a promising algorithm, but real-world use needs practical tools. The outline of a working system is clear, and there are ways to make it smarter with better search tricks. The real challenge is developing robust Simplicity Theory (ST) approximations that work with messy, real-world language. This is the main bottleneck between theory and practical discovery systems.

Three main approaches look promising:

1. **CompLog (Formal Logic Route):** The [CompLog framework](https://arxiv.org/abs/2307.15453) shows that ST's compression math works in practice. It turns knowledge into logical predicates, then measures compression to spot unexpected patterns. This works in controlled tests, but hits a wall: you have to manually convert natural language into logic. Real-world ideas like "teenager" or "population pressure" are too fuzzy and context-dependent for this. CompLog is powerful, but impractical for messy, real-world knowledge.

2. **LLM Approximation Route:** Another option is to use language models to estimate ST's complexity measures directly on natural language. For example, generation complexity (Cv) can be estimated using negative log-probability from the base model, and description complexity (C) using token compression length. This avoids CompLog's manual encoding problem, but needs to be tested at scale. LLMs might let us use ST on real-world concepts, but we need to see if it works reliably.

3. **Direct LLM Evaluation:** A simpler option: just ask an LLM to rate an insight's unexpectedness using ST's formula. For example: "How unexpected is this according to Simplicity Theory?" This isn't perfectly reliable, but might work better than asking if the insight is useful. Sometimes a rough method that works everywhere is better than a precise one that only works in special cases.

**Validation:** To check the basic idea, we tested if LLMs could connect Gwern's essay and Simplicity Theory on their own. All five LLMs tested independently found the core argument of this article—that ST could solve Gwern's evaluation problem (see Appendix). This shows that AI daydreaming works in concept, though it doesn't prove the ST complexity approximation works yet.

**Implementation path:** Build the system using LLM approximations of ST, then test if it gives the predicted computational advantages. The next step is to build the system using LLM approximations of ST, then test if it gives the predicted computational advantages. The big breakthrough is conceptual. The hard part is making it robust and scalable in practice.

## What This Could Enable

If we solve the evaluation problem, new applications become possible.

**Research Tools:**
- AI could scan research papers for compression opportunities.
- Knowledge management systems could flag when your notes form unexpectedness patterns.
- Browser extensions could show unexpectedness ratings for papers.

**Information Systems:**
- Email filters could prioritize high-compression insights.
- Social media could surface genuinely unexpected connections, not just clickbait.

**Better AI Training:**
- Reasoning LLMs like OpenAI's o1 are trained mostly on math problems because they're easy to check automatically. This helps with logic, but not with generating insights.
- ST could provide a new source of verifiable training examples focused on insights, not just correct answers.
- Instead of expensive human ratings for "good insights," ST could score them automatically by compression gain. This could let us train AI for discovery, not just for making sense.

The vision is compelling: research tools that help you discover, not just store, information. But we're still far from practical systems.
