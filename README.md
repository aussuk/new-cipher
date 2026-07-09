# New Cipher
A browser-based custom cipher encryptor with reversible character-swapping encryption, advanced key logic, and experimental key generation.

This cipher is NOT secure compared to others as the original input can be found with trial and error, due to characters never being changed, just arranged in another way, so do not use it to keep valuable information.

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
- Character metrics
- Copy output to clipboard
- Settings and presets saved locally
- Hidden mini-game easter egg

The asterisk '*' is for planned but not yet implemented features.

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

Surrounding a number with brackets allows for the possibility for shifts bigger than 26 (using letters) and negative numbers allow shifts in the opposite direction.
 
```text
(12)(-4)(26)
```

These multi-digit/negative numbers can also be all on the same pair of brackets, separating them using commas, which uses up less characters.

```text
(63,-2,900) -- 11 characters

(63)(-2)(900) -- 13 characters
```

### Flags

Using flags on the key gives the possibility to ignore certain characters. Ignoring means that no shift is applied to them and they are dispensable on the encryption and decryption.

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

### Conditionals

Conditionals apply shifts only when conditions are met. The shift that is conditioned is put after the condition.
There are positive conditionals ('apply shift if' - ?) and negative conditionals ('apply shift unless' - !).
In each conditional type there are also two types: letter conditionals (the condition is defined by the current character's **letter**) and index conditionals (the condition is defined by the **index** of the current character).

#### Letter conditionals:

Can be defined by a rule (vowel or consonant), by a specific letter, by a group of letters and a range of letters.

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
?=E
```

Apply to the letter E

```text
?=A,H,W,B
```

Apply only to the letters A, B, H and W

```text
?=E-K
```

Apply to the letters from E to K in the alphabetical order

#### Index Conditionals

The first character has an index of 1 counting up

```text
?i(3)
```

Apply only to the character in position 3

```text
?i(3,5)
```

Apply to the characters in positions 3 and 5

```text
?i(2-7)
```

Apply to the characters in positions from 2 up to 7

```text
?i(>=6)
```

Apply to the characters in positions with an index greater than or equal to 6 (can support >, <, >= and <=)

```text
?ie
```

Apply to the characters in positions of an even number

```text
?io
```

Apply to the characters in positions of an odd number

```text
?i(%3)
```

Apply to the characters in positions divisible by 3 (in jumps of 3)
 
By stacking conditionals you can also make an AND operator like this:

```text
?v?i(>=10)

If character is a vowel AND its index is greater or equal to 10
```

And also an OR operator by using `|`:

```text
?v|?i(>=10)

If character is a vowel OR its index is greater or equal to 10
```

---

### Groups

Using square brackets you can make a group.
Groups behave like normal brackets but are mainly used to apply one argument to many shifts at a time, saving time and key length.

Without grouping:

```text
?C3?C(-2)?CE
```

With grouping:

```text
?C[3,-2,E]
```

It can also be used for more complex [extender](#extender) functionality

```text
123[4,5,6]-
```

That expands to:

```text
123456456456456...
```

---

### Rounds

Using rounds you can run the encryption process multiple times. Set the number of repetitions after the #.
Repeat the encryption multiple times:

```text
KEY#3
```

Runs 3 rounds.

---

### Extender

Use `-` at the end of the key to repeat the final shift for all remaining characters.

Example:

```text
AB3-
```

This example expands the key to 'AB3333333...'

---

## Presets

Presets can be used to save and load specific keys to the device.

How to save presets:

1. Type the desired key in the key box
2. Click the 'Save Preset' button
3. Choose the preset's name

OR

- Type the command '/save [presetname] [key]' in the key box

How to load presets:

1. Click the 'Load Presets' button
2. Choose one of the previously saved presets

OR

- Type the command '/load [presetname]' in the key box

OR

1. In the key box, type @presetname
2. Click Enter

## Reverse mode

The reverse function attempts to generate a compatible key from:

- source text
- desired output text

Modes:

- Deep Search
- Direct Mapping

Deep Search brute-forces keys starting from 0, testing each candidate until a compatible key is found. The downside is that it is really slow and does not work realistically for medium to large inputs.

Direct Mapping uses simple math to determine a compatible key using the formula:

$$\text{shift} = \text{foundIndex} - \text{currentIndex}$$

The downside is that the resulting key length is the same or bigger than the input length.

---

## Secret Mode

There’s a hidden Snake mini-game.

On desktop press the arrow keys in this sequence:

```text
↑ ↑ ↓ ↓ ← → ← →
```

On mobile enter this:

```text
↑↑↓↓←→←→
```

into the input box and press Encrypt.

---

## Running locally

Clone:

```bash
git clone https://github.com/aussuk/new-cipher.git
```

Open `index.html` in your browser.

No dependencies required.

---

## Roadmap

Possible future additions:

- Help panel
- Save encrypted sessions
- Theme customization
- Better reverse-key optimization

---

## Version

Current version:

```text
v1.10
```

This is probably the last major version I am gonna have here but i'll still add small features, more achievements, and fix bugs.
It was fun while it lasted and I still hope it continues like that!

---

Created this cipher in Biology class while I wasn't paying attention... hope this inspires you not to pay attention in class!

I don't have a name for it so if you have a suggestion please notify me.

Credit isn't mandatory but it's really appreciated! :D
