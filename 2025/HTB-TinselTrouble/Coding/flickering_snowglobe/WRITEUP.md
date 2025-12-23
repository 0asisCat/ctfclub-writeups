# Flickering Snowglobe
## Difficulty: very easy

> "The Great Snowglobe once pulsed with calm, steady light, guiding Everlight Eve from atop Sprucetop Tower. Since the Starshard Bauble fled, its glow now stutters and fractures, breaking harmony into jittery bursts. Tilda studies the flicker log, counting each break in the Snowglobe’s rhythm."

<img width="930" height="941" alt="image" src="https://github.com/user-attachments/assets/a4dabc96-ad98-48ac-a21e-f8afa31162e4" />

## Note: Solved by ChatGPT (Unashamedly admitting)

This is a classic run-length / segment counting problem.
You’re counting how many times the character changes in the string, plus the first segment.

## Key insight (simple & fast)

A stable segment starts:

at position `0`

every time `S[i] != S[i-1]`

So the answer is:

```
1 + number of character changes
```


This works in O(N) time and O(1) extra space — safe up to `10^6`.

## Corrected Python solution

Your given code skeleton only reads n and prints it.
Here is the fixed and complete version:

```
# read length (not strictly needed, but included per spec)
n = int(input().strip())

# read pulse string
s = input().strip()

# edge case
if n == 0:
    print(0)
    exit()

# count segments
segments = 1
for i in range(1, n):
    if s[i] != s[i - 1]:
        segments += 1

print(segments)
```

## Example walk-through

Input:
```
10
...--***.-
```

Comparisons:

```
. . . - - * * * . -
        ↑   ↑     ↑   ↑
```

Character changes = 4
Segments = `1 + 4 = 5`

Output:
```
5
```
## Ultra-short alternative (Pythonic)

If you want the most concise solution:
```
n = int(input())
s = input().strip()
print(sum(1 for i in range(n) if i == 0 or s[i] != s[i-1]))
```
Complexity

Time: O(N)

Memory: O(1)

Handles maximum input size safely.

## Final
Submit the code and wait for the flag to appear.

Flag:`HTB{th3_fl1ck3r1ng_g03s_0n_4_3v3r}`
