# GPT-O1-on-QuixBugs
This is the repository for [**Can GPT-O1 Kill All Bugs? An Evaluation of GPT-Family LLMs on QuixBugs**](https://arxiv.org/abs/2409.10033).

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

## Response Length

```
import tiktoken

def num_tokens_from_string(string: str, encoding_name: str) -> int:
    """Returns the number of tokens in a text string."""
    encoding = tiktoken.get_encoding(encoding_name)
    num_tokens = len(encoding.encode(string))
    return num_tokens

with open('temp.txt', 'r') as file:
    data = file.read()

b = num_tokens_from_string(data, "cl100k_base")
print(b)
```

| **Benchmark Problem**          | **O1-preview** | **O1-mini** | **GPT-4o** |
|--------------------------------|----------------|--------------|-------------|
| bitcount                       | 1846           | 1172         | 647         |
| breadth-first-search           | 1179           | 1015         | 780         |
| bucketsort                     | 1540           | 710          | 669         |
| depth-first-search             | 1620           | 738          | 667         |
| detect-cycle                   | 1518           | 719          | 757         |
| find-first-in-sorted           | 2099           | 1406         | 820         |
| find-in-sorted                 | 2159           | 912          | 785         |
| flatten                        | 987            | 856          | 487         |
| gcd                            | 1393           | 822          | 456         |
| get-factors                    | 1109           | 932          | 553         |
| hanoi                          | 1826           | 1262         | 726         |
| is-valid-parenthesization      | 878            | 578          | 770         |
| kheapsort                      | 1282           | 1203         | 1078        |
| knapsack                       | 1722           | 1029         | 904         |
| kth                            | 1848           | 1171         | 472         |
| lcs-length                     | 1345           | 927          | 589         |
| levenshtein                    | 1485           | 914          | 727         |
| lis                            | 1612           | 896          | 597         |
| longest-common-subsequence     | 1299           | 875          | 710         |
| max-sublist-sum               | 1423           | 1370         | 485         |
| mergesort                      | 575            | 1017         | 1438        |
| minimum-spanning-tree          | 1386           | 1346         | 903         |
| next-palindrome                | 1215           | 1057         | 1658        |
| next-permutation               | 1642           | 931          | 817         |
| pascal                         | 1778           | 798          | 692         |
| possible-change                | 940            | 860          | 798         |
| powerset                       | 1642           | 1128         | 563         |
| quicksort                      | 760            | 691          | 281         |
| reverse-linked-list            | 1062           | 1005         | 342         |
| rpn-eval                       | 1638           | 1097         | 415         |
| shortest-path-length           | 814            | 1097         | 768         |
| shortest-path-lengths          | 2035           | 1263         | 432         |
| shortest-paths                 | 1130           | 1244         | 495         |
| shunting-yard                  | 2104           | 1329         | 573         |
| sieve                          | 1432           | 1067         | 511         |
| sqrt                           | 931            | 812          | 268         |
| subsequences                   | 1557           | 653          | 363         |
| to-base                        | 968            | 1015         | 281         |
| topological-ordering           | 1497           | 2755         | 390         |
| wrap                           | 1374           | 752          | 383         |
| **Average**                    | 1450.07        | 1086.90      | 654.07      |

## Response Time (Time for O1 to think)
| **Benchmark problem**              | **O1-preview** | **O1-mini** | **GPT-4o** |
|------------------------------------|----------------|--------------|------------|
| bitcount                           | 17s            | < 5s        | ~          |
| breadth-first-search                | 27s            | < 5s        | ~          |
| bucketsort                         | 18s            | < 5s        | ~          |
| depth-first-search                  | 9s             | < 5s        | ~          |
| detect-cycle                       | 23s            | < 5s        | ~          |
| find-first-in-sorted              | 31s            | 11s         | ~          |
| find-in-sorted                    | 18s            | < 5s        | ~          |
| flatten                            | 19s            | < 5s        | ~          |
| gcd                                | 8s             | < 5s        | ~          |
| get-factors                        | 16s            | < 5s        | ~          |
| hanoi                              | 15s            | 7s          | ~          |
| is-valid-parenthesization         | 10s            | < 5s        | ~          |
| kheapsort                         | 30s            | 6s          | ~          |
| knapsack                           | 38s            | 5s          | ~          |
| kth                                | 28s            | 10s         | ~          |
| lcs-length                         | 12s            | < 5s        | ~          |
| levenshtein                       | 18s            | < 5s        | ~          |
| lis                                | 51s            | 38s         | ~          |
| longest-common-subsequence        | 15s            | 42s         | ~          |
| max-sublist-sum                   | 21s            | 6s          | ~          |
| mergesort                          | 17s            | < 5s        | ~          |
| minimum-spanning-tree              | 28s            | 10s         | ~          |
| next-palindrome                    | 53s            | 8s          | ~          |
| next-permutation                   | 23s            | 7s          | ~          |
| pascal                             | 33s            | 8s          | ~          |
| possible-change                   | 14s            | < 5s        | ~          |
| powerset                           | 23s            | < 5s        | ~          |
| quicksort                          | 11s            | < 5s        | ~          |
| reverse-linked-list                | 14s            | < 5s        | ~          |
| rpn-eval                           | 16s            | 5s          | ~          |
| shortest-path-length               | 16s            | 7s          | ~          |
| shortest-path-lengths              | 13s            | < 5s        | ~          |
| shortest-paths                     | 21s            | < 5s        | ~          |
| shunting-yard                      | 17s            | < 5s        | ~          |
| sieve                              | 15s            | 8s          | ~          |
| sqrt                               | 10s            | 5s          | ~          |
| subsequences                       | 47s            | < 5s        | ~          |
| to-base                            | 20s            | < 5s        | ~          |
| topological-ordering               | 18s            | 6s          | ~          |
| wrap                               | 21s            | < 5s        | ~          |
| **Average**                        | 19.82s         | 7.02s       | ~          |

## Mention
All results can be found in gpt_quixbugs.txt

## Citation
```
@misc{hu2024gpto1killbugs,
      title={Can GPT-O1 Kill All Bugs? An Evaluation of GPT-Family LLMs on QuixBugs}, 
      author={Haichuan Hu and Ye Shang and Guolin Xu and Congqing He and Quanjun Zhang},
      year={2024},
      eprint={2409.10033},
      archivePrefix={arXiv},
      primaryClass={cs.SE},
      url={https://arxiv.org/abs/2409.10033}, 
}
```
