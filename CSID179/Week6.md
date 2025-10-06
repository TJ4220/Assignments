# Week 6 Text Parsing
```python
import re
from collections import Counter
from pathlib import Path
import matplotlib
matplotlib.use("Agg")  # save image to a file without opening a window
import matplotlib.pyplot as plt
story_path = Path("story.txt")
out_dir = Path("outputs")
out_dir.mkdir(exist_ok=True)
chart_path = out_dir / "word_histogram.png"
# read the story text
if not story_path.exists():
    raise FileNotFoundError("story.txt is not here. please add it next to this file")
text = story_path.read_text(encoding="utf-8")
if not text.strip():
    raise ValueError("story.txt is empty. please paste the story text")
# make a list of words
# lower case words so Hello and hello count the same
# keep letters digits and the apostrophe so cant stays one word
words = re.findall(r"[A-Za-z0-9']+", text.lower())
# count characters
# with spaces and new lines
chars_with_space = len(text)
# without any white space
chars_no_space = len(re.sub(r"\s+", "", text))
print("STEP 1 list")
print("total words:", len(words))
print("characters with space:", chars_with_space)
print("characters without space:", chars_no_space)
# make a dict of word to count
freqs = Counter(words)
print("\nSTEP 2 dictionary top ten")
for w, c in freqs.most_common(10):
    print(f"{w:>12} : {c}")
# save a bar chart of the top thirty words
top = freqs.most_common(30)
if top:
    labels = [w for w, _ in top]
    counts = [c for _, c in top]
    plt.figure()
    plt.bar(labels, counts)
    plt.xticks(rotation=45, ha="right")
    plt.title("Top thirty words")
    plt.tight_layout()
    plt.savefig(chart_path)
    plt.close()
    print("\nsaved chart to:", chart_path)
else:
    print("\nno words to plot")
# find phone numbers and emails with regex
phone_re = re.compile(r"""
    (?:\+?\d{1,3}[\s.\-]?)?      # optional country code
    (?:\(\d{3}\)|\d{3})          # area code
    [\s.\-]?\d{3}[\s.\-]?\d{4}   # local number
""", re.VERBOSE)
email_re = re.compile(r"[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}")
phones = phone_re.findall(text)
emails = email_re.findall(text)
combined = phones + emails
print("\nSTEP 3 regex")
print("phones:", phones)
print("emails:", emails)
print("combined list:", combined)
# make hotmail emails from usernames
# take the part before the at sign
hotmails = [e.split("@", 1)[0] + "@hotmail.com" for e in emails]
print("\nSTEP 4 hotmail list")
print(hotmails)
print("\nDone.")
```
