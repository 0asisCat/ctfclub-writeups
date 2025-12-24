# Bauble Sort
## Difficulty: easy

> When the Starshard Bauble vanished, Tilda Baublenose discovered that the ancient Bauble Registry had been scrambled by lingering festive corruption. Each ornament’s glow flickers out of order, threatening Everlight itself. Only by restoring the proper sequence can Tilda coax the magic back into harmony.

<img width="921" height="998" alt="image" src="https://github.com/user-attachments/assets/2cdd1dea-e6fc-4f52-a79b-51c4f4773d8a" />

## Note: Solved by ChatGPT (Unashamedly admitting)

This is a custom multi-key sorting problem — very common in programming contests and CTF warmups.

Let’s break it down cleanly and then give you a fast, correct solution that works up to N = 500,000.

## What type of problem is this?

Category:
- Sorting with multiple comparison rules
- Data parsing + custom comparator
- Performance-sensitive (large N)

## Enchanted sorting rules (translated to code logic)

Each bauble has:
```
(identifier, sparkle, stability)
```

Sort by:

sparkle → descending `(-sparkle)`

stability → ascending `(stability)`

identifier → ascending alphabetical `(identifier)`

In Python sorting terms, the key is:

```
(-sparkle, stability, identifier)

```

## Efficient strategy (important for big input)

Parse input carefully (string splitting is the trickiest part)

Store tuples

Use Python’s Timsort (fast enough for 500k items)

Avoid slow operations inside loops

## Correct & efficient Python solution
```
import sys

input = sys.stdin.readline  # faster input

N = int(input().strip())
baubles = []

for _ in range(N):
    line = input().strip()
    identifier, rest = line.split(":")
    sparkle_str, stability_str = rest.split(",")
    sparkle = int(sparkle_str.strip())
    stability = int(stability_str.strip())
    baubles.append((identifier, sparkle, stability))

# Sort using the enchanted rules
baubles.sort(key=lambda x: (-x[1], x[2], x[0]))

# Output identifiers only
out = sys.stdout.write
for b in baubles:
    out(b[0] + "\n")
```

## Final
Submit the code and wait for the flag.

Flag: `HTB{b4ubl3_0rd3r_h45_b33n_r3st0r3d}`
