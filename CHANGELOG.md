# Changelog
## v1.10:
- Made the saving system work (just needed to remove one line :P);
- Fixed a bug which prevented index conditionals from working correctly;
- Added achievements for using certain features and finding the secret mini-game, with a toast notification system to celebrate unlocks;
- Added a way to save specific keys using presets with @;
- Commands can be used in the key box to delete, save, load and list;
- Added even MORE achievements;
- Statistics panel is now toggleable in the settings;
- Added Achievements panel;
- Added a secret developer mode using a certain combination of keys to unlock very serious information;
- Added the possiblity to have multiple numbers inside brackets
- Added groups.
  
## v1.9:
- Added a key strength meter that evaluates the complexity of the key based on various factors (length, character variety, use of conditionals, etc.);
- Added character & key metrics such as entropy rating and movable character count;
- Added Live Encryption option to automatically update the output in real time;
- Added saving to settings to localStorage so that user preferences persist across sessions;
- Removed key strength meter because it wasn't good enough;
- Saving doesn't work so I might create a Github repo for this. (future me talking—I can't believe I actually did it!).

## v1.8:
- Updated the index-based conditionals to be more intuitive;
- Added extender customization option to repeat the last shift indefinitely;
- Updated the reverse button's to support extenders and letters;
- Updated the reverse outputs to show the time taken to find the key;
- Changed way to enter sectret mode in mobile;
- Changed support for mobile in the easter egg because it wasnt working.

## v1.7:
- Came back like a chad ready to add more stuff;
- Updated the Update Log (I know, crazy right?);
- Changed the ignore-paragraph flag symbol from 'p' to '¶';
- Added a easter egg if the user presses a specific combination of the arrow keys;
- Added support of snake game to mobile;
- Removed Herobrine.

## v1.6:
- Made shifting possible an indeterminate amount of times using brackets (n);
- Made Reverse method more efficient;
- Added more Key customization options: Rounds (#n), Positive Conditionals (?) and Negative Conditionals (!);
- Implemented a help panel with usage instructions and examples;
- Delayed the addition of the help panel due to being too complex;
- Tweaked Random Key generation logic to include new features.

## v1.5:
- Added reverse button to create key based on input-output text;
- Changed monospacefont to a more modern sans-serif;
- Changed auto-encrypt shortcut "Ctrl/Cmd+Enter" to "Shift+Enter";
- Added simple button animation on click.

## v1.4:
- Tweaked the random key generator to vary the number of characters (not just 5);
- Added options to encryption/decryption to ignore spaces (_), punctuation (:), or paragraphs (p).

## v1.3:
- Copy to clipboard feature for output text;
- Added "Random Key" generator button (5 letter/number key);
- Versatile multi-line text box (use Ctrl/Cmd+Enter to encrypt when editing multiple lines).

## v1.2:
- Added decryption functionality.

## v1.1:
- Improved UI with responsive design;
- "Enter" key triggers encryption automatically.

## v1.0:
- Encryption logic implemented;
- Key that supports both numbers and letters.
