# algomonster flowchart: How to Read the Decision Tree, Pick the Right Pattern, and Stop Guessing on LeetCode

You read the problem statement twice. It's an array. Or maybe a graph pretending to be an array. You have 45 minutes, and the first 10 are evaporating while you decide between sliding window and DP.

That gap — the one between understanding a problem and knowing which algorithm it wants — is the thing the AlgoMonster flowchart exists to close. It's a decision tree, published openly on AlgoMonster's site, that walks you from a plain-English description of a problem to the specific algorithm you should use.

This article covers what's actually in it, how to walk it without getting lost, what it can't do for you, whether you need to pay to use it, and what every AlgoMonster plan currently costs.

## What the AlgoMonster flowchart actually is

Two node types, and that's the whole vocabulary:

- **Decision nodes (diamonds)** ask a yes/no question about the problem description: *Is it a tree? Is the input sorted? Do you need the kth smallest?*
- **Leaf nodes (purple boxes)** are the algorithms: BFS, Dijkstra's Algorithm, Monotonic Stack, Bitmask DP, Trie, Disjoint Set Union.

You start at the root and answer questions until you land on a leaf. Whatever leaf you land on is the algorithm the problem is asking for. On the site you can click any node to pull up an explanation, and there's a video walkthrough for the whole thing.

AlgoMonster says the tree was built by ex-Googlers and competitive programmers from solving thousands of problems and mapping the recurring decision points. That origin story matters less than the practical effect: it encodes the pattern-selection step that experienced interviewers reward and that most candidates improvise.

One question comes up constantly, and the site answers it directly:

> "Do I memorize this?" — the answer is no. The flowchart is a reference tool. The point is that after routing enough problems through it, you stop needing it.

There's a second, less obvious detail worth knowing. As you click through, the current path gets written into the URL — a parameter containing every decision you've answered, like `graph:no|sorted-search:no|kth-smallest:no`. That means you can bookmark or share a specific route through the tree rather than describing it in a message.

## Walking the flowchart: a worked example

Take a generic problem: "Given a list of flights with prices, find the cheapest route from A to B." Skip the code entirely for a second and just answer questions.

1. **Is it a graph?** Yes — cities are nodes, flights are edges.
2. **Is it a tree?** No, so the tree branch (Divide and Conquer / Tree DP, BFS by level) is closed off.
3. **Is it a DAG problem?** Not necessarily; there might be cycles. That rules out Topological Sort as the primary pattern.
4. **Is it a shortest-path problem?** Yes, that's literally the phrasing.
5. **Is the graph weighted?** Yes — flights have prices.
6. **Leaf node: Dijkstra's Algorithm.**

Total time: about twenty seconds once you're used to the questions. The same route run in your head is more like three minutes of "hmm, could I do this with BFS if I treat prices as..." and then you've burned a third of your interview.

The other thing the walkthrough exposes: most problems die early. If you answer "no" to *is it a graph* and "no" to *is it a tree*, you've eliminated an entire third of the tree immediately. Candidates under pressure tend to search in the opposite direction — starting from the algorithm they know best and reverse-engineering a justification. The tree forces the opposite order.

## The main branches, in one table

The full tree is bigger than any article should reproduce, and it changes as the site adds patterns. These are the routes that come up most often across interviews:

| If the problem looks like this... | Key decision points | Where you land |
| --- | --- | --- |
| Nested structures, cities and routes, dependencies | Is it a graph? → Is it a tree? → shortest path? → weighted? | BFS, DFS, Dijkstra's Algorithm, Topological Sort |
| "Are these all connected?" / union-heavy counting | Connectivity problem? | Disjoint Set Union |
| Ordered or sorted input with a monotonic answer | Sorted input or monotonic answer? | Binary Search |
| Range queries, order statistics, dynamic updates | Dynamic range or order queries? | Ordered Set / Fenwick / Segment Tree |
| Contiguous subarray or substring | Sum/additive? → maintain a valid window? | Prefix Sums, Sliding Window |
| Nearest greater/smaller element, next-warm-day style | Need nearest greater/smaller bounds? | Monotonic Stack |
| kth largest, merge many sorted lists | kth smallest/largest? | Heap / Sorting |
| Linked list manipulation, cycle detection | Linked list? → fast/slow pointers? | Two pointers |
| Fast lookup, counting, grouping | Hash Table / Counting | Hash Table |
| Overlapping intervals | Merge, insert, or scan intervals? | Sorting + Interval Scan |
| Counting ways, optimizing over choices | Is brute force enough? | Brute force / Backtracking, Dynamic Programming |
| Small element set with subsets of state | Subset state? | Bitmask DP |
| Digit or bit tricks, number properties | Math identities / number properties? | Math / Bit Manipulation, Number Theory |

If you'd rather have something you can glance at without a browser tab, third parties have recreated simplified versions — there's a GitHub cheat-sheet PDF explicitly credited as "inspired by AlgoMonster's flowchart," and at least one repo built as a finder for the same purpose. They're reductions, not copies, so treat them as a reminder of the tree rather than a substitute for it.

**👉 [Open the AlgoMonster flowchart and run one of your old problems through it](https://algo.monster/flowchart?fpr=li69)**

## Where people actually get stuck using it

The flowchart is simple to operate and easy to misuse. The failure modes are consistent:

- **Answering questions optimistically.** "Is the input sorted?" — well, it could be. The tree can only route you as well as you read the problem. If you're unsure whether a constraint is relevant, the constraint section of the statement is usually telling you which branch applies.
- **Treating the leaf as the answer.** The tree names the algorithm, not the implementation. You still need the template and the edge cases. This is exactly the gap AlgoMonster's pattern lessons fill — each pattern ships with template code in several languages.
- **Using it before attempting the problem.** The pattern-recognition skill you want is the one you build by failing to identify the pattern first, then checking. Checking is different from routing.
- **Expecting it to cover everything.** The tree's bottom includes a "Specialized / Advanced Pattern" leaf, which is a polite way of saying: not everything fits. It's a map of the common territory, not a proof.

## Is the flowchart free?

The flowchart page itself is publicly reachable — you can browse it, click nodes, and follow a path without hitting a paywall on the tree itself. The video walkthrough on AlgoMonster's site is public too.

What sits behind the subscription is everything the tree points at: the pattern lessons, the code templates, the mapped practice problems, Speedrun mode for timed review, the AI assistant, and the company-specific question banks. The flowchart tells you *which* pattern; the paid content is what teaches it.

There's a free tier with limited sample content, which is enough to judge whether the text-and-diagram teaching style works for you. There's no separate free trial on top of it, and no monthly billing option — annual or lifetime, nothing in between.

**👉 [Start on AlgoMonster's free tier and see whether the format clicks](https://algo.monster?fpr=li69)**

## Every AlgoMonster plan, with current pricing

AlgoMonster's pricing is genuinely simple. There are three tiers and no team or enterprise plan — it's built for one person preparing on their own.

| Plan | What you get | Price | Billing cycle | Get it |
| --- | --- | --- | --- | --- |
| Free | Limited access to a subset of patterns, lessons, and sample problems | $0 | — | [Start free](https://algo.monster?fpr=li69) |
| Pro – Yearly | All patterns, lessons and problems, unlimited AI assistant, unlimited Speedrun, real questions from top tech companies (updated monthly), 500+ lessons across 6 courses, 1,000+ illustrations, 3,000+ editorials, member discount on live bootcamps | $99/year (shown as $8.25/mo, list price $198) | Annual, 12 months of access | [Get Pro Yearly](https://algo.monster/subscribe?fpr=li69) |
| Pro – Lifetime | Everything in the annual plan, plus lifetime updates — one payment, no renewals | $189 (list price $378) | One-time | [Get Pro Lifetime](https://algo.monster/subscribe?fpr=li69) |

Two things to flag before you buy.

First, the prices above are the discounted numbers currently shown on the official signup page, with list prices of $198/year and $378 lifetime. Sales on AlgoMonster rotate, so the number you see at checkout is the number that counts.

Second, if you go looking for pricing secondhand, you'll find numbers that don't match. Several third-party blogs quote a lifetime price in the $150–$459 range and annual prices from $89 to $299 — some of those are stale, some appear to be plain errors. Ratings and review sites also commonly cite roughly 48 patterns, about 230 mapped problems, and 700+ illustrations; those figures come from third-party breakdowns rather than the plan page, so treat them as approximate.

Partner promo codes do float around — one partner page reported that a code stacked an extra 10% on top of the active sale at checkout. Codes expire without warning, so apply yours on the checkout page and check the total before paying.

There's also a note on the signup page that some specialist courses built with external partners, such as Quant Interview Prep, are sold separately.

## Does the flowchart change whether it's worth paying for?

The flowchart is free. It's also the smallest part of what AlgoMonster sells. So the honest question isn't "is the flowchart good" — it is, and it costs nothing — but "does the paid content complete the loop the flowchart starts?"

It does, if your specific gap is pattern selection. You can already write working code in one language, you freeze when a problem doesn't look like anything you've seen, and the minutes you lose are in the first five of the interview. That's the exact failure the tree and its ~48 pattern lessons are built for.

It doesn't, if your gap is volume. Roughly 230 mapped problems is a small number next to LeetCode's 3,000+, and AlgoMonster isn't trying to win that comparison. Most candidates end up using it first for the framework and LeetCode after for reps.

Two more limits worth knowing before you pay:

- Every explanation is text plus interactive diagrams. There is no video library. If you learn by watching someone code, this format will fight you.
- System design coverage is introductory. If you're targeting L5+ loops with a dedicated design round, budget for a separate resource.

The lifetime plan is the one that makes the arithmetic easy. At $189 it's a single payment with no renewal, and it's cheaper than a year of LeetCode Premium. If you expect to interview more than once — a promotion loop, a lateral move, a return to the market in two years — annual access means paying twice for something you'd own outright.

## A six-week routine that uses the flowchart properly

Advice, not gospel, but this is the shape that fits AlgoMonster's own 4–8 week curriculum window:

1. **Weeks 1–2:** Work patterns in order. Attempt each problem for ten minutes before touching anything, *then* run it through the flowchart and note where your instinct diverged from the tree. Those divergences are the whole point.
2. **Weeks 3–4:** Start pushing into LeetCode alongside. Before opening any solution, route the problem through the flowchart out loud. Aim to land on the right leaf in under 90 seconds.
3. **Weeks 5–6:** Add one unfamiliar company's question bank. When you miss, go back and read the pattern lesson rather than re-reading the solution.
4. **Final week:** Use Speedrun to review all 48 patterns in compressed sessions, and quiz yourself with the flowchart alone — cover the leaves and predict them.

The flowchart is the diagnostic tool in that loop, not the curriculum. If you use it only to confirm what you already decided, you've turned it into a decoration.

**👉 [Get lifetime access to AlgoMonster and the full pattern library behind the flowchart](https://algo.monster/subscribe?fpr=li69)**

## FAQ

**Is the AlgoMonster flowchart free to use?**
The flowchart page is publicly available and you can traverse it without a subscription. The pattern lessons, templates, and problem bank the tree points to require a plan.

**Do I need to memorize the flowchart before interviews?**
No, and the site says so explicitly. Use it as a reference until pattern recognition becomes automatic, then stop leaning on it.

**Is there a printable version?**
Not from AlgoMonster itself. Third parties have published simplified cheat sheets and finder tools credited as inspired by it, but they're reductions of the tree and can miss branches.

**Does AlgoMonster have a monthly plan or a free trial?**
No monthly billing and no formal trial. Your options are the free tier with limited content, Pro Yearly, or Pro Lifetime.

**Is the flowchart a replacement for LeetCode?**
No. The flowchart picks the approach; LeetCode gives you volume. The flowchart tells you that the problem is a sliding window. It doesn't make you fast at implementing one.
