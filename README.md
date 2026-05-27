# New Cipher

A browser-based custom cipher encryptor with reversible character-swapping encryption, advanced key logic, and experimental key generation.

## Features

- Encrypt text using custom keys
- Decrypt encrypted text
- Reverse-engineer compatible keys
- Supports letters and numbers in keys
- Conditional key logic
- Multi-round encryption
- Ignore spaces / punctuation / paragraph flags
- Live encryption mode
- Random key generator
- Entropy + character metrics
- Copy output to clipboard
- Settings saved locally
- Hidden Snake mini-game easter egg

---

## How it works

New Cipher encrypts text by applying swaps across characters using values generated from the key.

Keys can contain:

### Letters
```text
A = 1
B = 2
...
Z = 26
```

Example:

```text
DOG → 4 15 7
```

### Numbers

```text
314159
```

### Multi-digit numbers

```text
(12)(-4)(26)
```

### Flags

| Flag | Meaning |
|---|---:|
| `_` | Ignore spaces |
| `:` | Ignore punctuation |
| `¶` | Ignore paragraph breaks |

Example:

```text
HELLO123_:
```

---

## Conditionals

Conditionals apply shifts only when conditions are met.

Examples:

```text
?V
```

Apply only to vowels

```text
?C
```

Apply only to consonants

```text
?=A,E,I,O,U
```

Apply only to specific letters

```text
!V
```

Apply to everything except vowels

```text
?i(1,3,5)
```

Apply only to positions 1, 3, and 5

---

## Rounds

Repeat the encryption multiple times:

```text
KEY#3
```

Runs 3 rounds.

---

## Extender

Use `-` at the end of the key to repeat the last shift indefinitely.

Example:

```text
AB3-
```

---

## Reverse mode

The reverse function attempts to generate a compatible key from:

- source text
- desired output text

Modes:

- Deep Search
- Quick & Big

---

## Secret Mode

There’s a hidden Snake mini-game.

Desktop:

```text
↑ ↑ ↓ ↓ ← → ← →
```

Mobile:

Enter:

```text
↑↑↓↓←→←→
```

into the input box.

---

## Running locally

Clone:

```bash
git clone https://github.com/YOUR_USERNAME/new-cipher.git
```

Open:

```bash
index.html
```

in your browser.

No dependencies required.

---

## Roadmap

Possible future additions:

- Help panel
- Key export/import
- Encryption presets
- Save encrypted sessions
- Theme customization
- Better reverse-key optimization

---

## Version

Current version:

```text
v1.9
```

---

Made for fun, experimentation, and increasingly complicated cipher chaos.
