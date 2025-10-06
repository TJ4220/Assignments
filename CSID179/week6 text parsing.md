``` python
# list-based word and character counts an histogram
import re, random
from collections import Counter
from pathlib import Path
import matplotlib.pyplot as plt
text = Path("story.txt").read_text(encoding="utf-8")
# list of words 
words = re.findall(r"[A-Za-z0-9']+", text.lower())
# character counts 
chars_with_ws = len(text)
chars_without_ws = len(re.sub(r"\s+", "", text))
print(f"Total words: {len(words)}")
print(f"Characters (with whitespace): {chars_with_ws}")
print(f"Characters (without whitespace): {chars_without_ws}")
# word freqs
freqs = Counter(words)
# histogram
TOP_POOL = 50   # consider the top 50 most frequent words
SHOW_N   = 25   # randomly show 25 of those
pool = [w for w, _ in freqs.most_common(TOP_POOL)]
show = random.sample(pool, k=min(SHOW_N, len(pool))) if pool else []
counts = [freqs[w] for w in show]
# save chart
Path("outputs").mkdir(exist_ok=True)
if show:
    plt.figure()
    plt.bar(show, counts)                 # single plot, default styles
    plt.xticks(rotation=45, ha="right")
    plt.title("Randomized Word Frequencies (Step 1)")
    plt.tight_layout()
    plt.savefig("outputs/word_histogram_step1.png")
    plt.close()
    print("Saved: outputs/word_histogram_step1.png")
else:
    print("No words to plot.")
```
