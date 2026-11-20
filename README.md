<p align="center">
  <img src="assets/wave.svg" alt="" width="100%">
</p>

<h3 align="center">three puzzles, rising difficulty</h3>

<p align="center"><sub>no prizes, no leaderboard. each answer has a SHA-256 so you can check yourself without peeking.</sub></p>

<br>

To check an answer, lowercase it and run:

```sh
printf '%s' "your answer" | shasum -a 256
```

<br>

### I. the key is in the waves

A message, enciphered the way people did before computers got involved. The key is one word, and it is hiding somewhere in this page's banner. Spaces are untouched; only letters shift.

```
xdhvr abwmmp ml i vxhzb euwxx ppdx bb uiycvil br jhzjim
```

`ff543eae77a4aa65be9ff69154dd6dda378b429f15743fc50f918d583f5ee568`

<details>
<summary>I give up</summary>

It is a Vigenère cipher. Open the banner's SVG source and read the comment: the key is `tide`. Decrypt each letter by subtracting the key letter (a=0), cycling the key over letters only. The plaintext is *every system is a story about what it refuses to forget*.

</details>

<br>

### II. a number worth counting

How many 8-digit numbers (no leading zero) have digits that sum to exactly 20 and no two neighbouring digits equal?

Answer is a plain integer.

`530f34318d653d9ecb7545c73d773ab0121c0612a58ac833abf7137a4b28a589`

<details>
<summary>I give up</summary>

**187497.** Count by dynamic programming over (position, previous digit, running sum), or just brute-force with a pruned depth-first search: both give the same number.

</details>

<br>

### III. five islanders

Everyone on the island is either a knight, who always tells the truth, or a knave, who always lies. Five of them speak.

> **A:** E is a knave.
> **B:** D and E are the same kind.
> **C:** D and E are different kinds.
> **D:** C and B are different kinds.
> **E:** B and A are the same kind.

Who is what? Answer as five letters in order A to E, `K` for knight and `N` for knave.

`ae2e5e4e4be0241bc975d77ff16af016a2d709487aecb4a5eb4e53386f7383af`

<details>
<summary>I give up</summary>

**KNKKN.** Of the 32 possible assignments exactly one is consistent with all five statements. A shortcut: B and C make opposite claims about the same pair (D, E), so exactly one of B and C is telling the truth, and so exactly one of them is a knight.

</details>

<br>

<p align="center"><sub>the waves keep going</sub></p>
