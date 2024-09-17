# GPT-O1-on-QuixBugs
LLMs have long demonstrated remarkable effectiveness in automatic program repair (APR), with OpenAI's ChatGPT being one of the most widely used models in this domain.
Through continuous iterations and upgrades of  GPT-family models, their performance in fixing bugs has already reached state-of-the-art levels.
However, there are few works comparing the effectiveness and variations of different versions of GPT-family models on APR.
In this work, inspired by the recent public release of the GPT-o1 models, we conduct the first study to compare the effectiveness of different versions of the GPT-family models in APR. 
We evaluate the performance of the latest version of the GPT-family models (i.e., O1-preview and O1-mini), GPT-4o, and the historical version of ChatGPT on APR.
We conduct an empirical study of the four GPT-family models against other LLMs and APR techniques on the QuixBugs benchmark from multiple evaluation perspectives, including repair success rate, repair cost, response length, and behavior patterns.
The results demonstrate that O1's repair capability exceeds that of prior GPT-family models, successfully fixing all 40 bugs in the benchmark. 
Our work can serve as a foundation for further in-depth exploration of the applications of GPT-family models in APR.

## Main Results

| **Benchmark problem**               | **O1-preview** | **O1-mini** | **GPT-4o** | **ChatGPT**         | **Codex** | **CIRCLE** | **Standard APR** |
|-------------------------------------|----------------|--------------|------------|----------------------|-----------|------------|------------------|
| bitcount                            | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ✔️        | ✔️         | ❌               |
| breadth-first-search                | ✔️             | ✔️           | ✔️         | ✔️ (2 / 4)            | ❌        | ✔️         | ❌               |
| bucketsort                          | ✔️             | ✔️           | ✔️         | ✔️ (4 / 4)            | ✔️        | ✔️         | ❌               |
| depth-first-search                  | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ✔️        | ❌         | ❌               |
| detect-cycle                        | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ❌        | ✔️         | ✔️               |
| find-first-in-sorted               | ✔️             | ✔️           | ✔️         | ✔️ (2 / 4)            | ✔️        | ✔️         | ❌               |
| find-in-sorted                     | ✔️             | ✔️           | ✔️         | ✔️ (3 / 4)            | ❌        | ✔️         | ❌               |
| flatten                             | ✔️             | ✔️           | ✔️         | ✔️ (4 / 4)            | ✔️        | ✔️         | ❌               |
| gcd                                 | ✔️             | ✔️           | ❌ ✔️       | ❌ (0 / 4) ✔️         | ✔️        | ✔️         | ❌               |
| get-factors                         | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ✔️        | ✔️         | ❌               |
| hanoi                               | ✔️             | ✔️           | ❌ ❌       | ❌ (0 / 4) ✔️         | ✔️        | ✔️         | ❌               |
| is-valid-parenthesization           | ✔️             | ✔️           | ✔️         | ✔️ (2 / 4)            | ✔️        | ❌         | ❌               |
| kheapsort                           | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ✔️        | ❌         | ❌               |
| knapsack                            | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ✔️        | ✔️         | ✔️               |
| kth                                 | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ❌        | ❌         | ❌               |
| lcs-length                          | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ❌        | ✔️         | ❌               |
| levenshtein                         | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ❌        | ✔️         | ✔️               |
| lis                                 | ❌ ✔️          | ❌ ✔️        | ✔️         | ❌ (0 / 4) ❌         | ❌        | ❌         | ✔️               |
| longest-common-subsequence          | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ✔️        | ❌         | ❌               |
| max-sublist-sum                    | ✔️             | ❌ ✔️        | ❌ ✔️      | ❌ (0 / 4) ✔️         | ✔️        | ❌         | ❌               |
| mergesort                           | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ❌        | ✔️         | ✔️               |
| minimum-spanning-tree               | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ❌        | ✔️         | ❌               |
| next-palindrome                     | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ❌        | ✔️         | ❌               |
| next-permutation                    | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ❌        | ✔️         | ❌               |
| pascal                              | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ❌        | ✔️         | ❌               |
| possible-change                     | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ✔️        | ❌         | ❌               |
| powerset                            | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ✔️        | ✔️         | ❌               |
| quicksort                           | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ✔️        | ✔️         | ✔️               |
| reverse-linked-list                 | ✔️             | ✔️           | ✔️         | ✔️ (2 / 4)            | ✔️        | ❌         | ❌               |
| rpn-eval                            | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ❌        | ❌         | ✔️               |
| shortest-path-length                | ❌ ✔️          | ❌ ✔️        | ❌ ✔️      | ✔️ (1 / 4)            | ❌        | ❌         | ❌               |
| shortest-path-lengths               | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ❌        | ❌         | ❌               |
| shortest-paths                      | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ❌        | ❌         | ❌               |
| shunting-yard                       | ✔️             | ✔️           | ✔️         | ✔️ (2 / 4)            | ❌        | ❌         | ❌               |
| sieve                               | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ✔️         | ✔️        | ✔️         | ❌               |
| sqrt                                | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ✔️        | ❌         | ❌               |
| subsequences                         | ✔️             | ✔️           | ✔️         | ✔️ (1 / 4)            | ❌        | ✔️         | ❌               |
| to-base                             | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ✔️        | ❌         | ❌               |
| topological-ordering                | ✔️             | ✔️           | ✔️         | ❌ (0 / 4) ❌         | ❌        | ✔️         | ❌               |
| wrap                                | ✔️             | ✔️           | ❌ ❌      | ❌ (0 / 4) ❌         | ✔️        | ❌         | ❌               |
| **Σ (Solved)**                      | **38 (40)**    | **37 (40)**  | **35 (38)**| **19 (31)**          | **21**   | **23**    | **7**            |

