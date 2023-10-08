# Obfuscated Keyboard Layouts for macOS
[Obfuscated Keyboards](https://github.com/Neelfyn/obfuscated-keyboard-macos) is a bundle of keyboard layouts for macOS. These layouts replace a number of characters of the Latin alphabet with similar looking Greek or Cyrillic characters, making any text perfectly readable to a human, yet unintelligible to a machine.

![Obfuscated Keyboards in menu bar Input menu](/Screenshots/Input_Menu.png?raw=true)

## Installation
Copy `Obfuscated Keyboards.bundle` to `~/Library/Keyboard\ Layouts/` to install it for yourself (or to `/Library/Keyboard\ Layouts/` to install it for all users), then log out and back into your user account. Go to System Settings > Keyboard > Input Sources > Edit… and click + in the bottom left corner. Search for "Obfuscated", and add the layouts you'd like to use with your keyboard.

![Obfuscated Keyboards in Keyboard System Settings](/Screenshots/System_Settings.png?raw=true)

## FAQ
### How does this work?
When you press the `A` key on your keyboard, instead of typing an `A`, you will actually type an `Α`. Don't see the difference? That's because they're identical — but only to your naked eye. For a computer, `A` is a Latin capital letter A (Unicode U+0041), while `Α` is the Greek capital letter Alpha (Unicode U+0391).

Here is a screenshot showing that the word "keyboard" cannot be found in a text entered with an obfuscated keyboard layout, despite clearly being visible to the eye:

![Comparison of text typed with a standard keyboard layout and an obfuscated layout](/Screenshots/TextEdit.png?raw=true)

Below is the the full list of characters that are replaced by Obfuscated Keyboards. Any other letters, numbers, or special characters are not replaced, and will use the same characters as your standard keyboard layout.

| Letter  | Replacement | Unicode character name                         |
| ------- | ----------- | ---------------------------------------------- |
| A       | Α           | GREEK CAPITAL LETTER ALPHA                     |
| B       | Β           | GREEK CAPITAL LETTER BETA                      |
| C       | С           | CYRILLIC CAPITAL LETTER ES                     |
| E       | Ε           | GREEK CAPITAL LETTER EPSILON                   |
| H       | Н           | CYRILLIC CAPITAL LETTER EN                     |
| I       | Ι           | GREEK CAPITAL LETTER IOTA                      | 
| J       | Ј           | CYRILLIC CAPITAL LETTER JE                     |
| K       | Κ           | GREEK CAPITAL LETTER KAPPA                     |
| M       | Μ           | GREEK CAPITAL LETTER MU                        |
| N       | Ν           | GREEK CAPITAL LETTER NU                        |
| O       | Ο           | GREEK CAPITAL LETTER OMICRON                   |
| P       | Ρ           | GREEK CAPITAL LETTER RHO                       |
| T       | Τ           | GREEK CAPITAL LETTER TAU                       |
| X       | Χ           | GREEK CAPITAL LETTER CHI                       |
| Y       | Ү           | CYRILLIC CAPITAL LETTER STRAIGHT U             |
| a       | а           | CYRILLIC SMALL LETTER A                        |
| c       | с           | CYRILLIC SMALL LETTER ES                       |
| e       | е           | CYRILLIC SMALL LETTER IE                       |
| i       | і           | CYRILLIC SMALL LETTER BYELORUSSIAN-UKRAINIAN I |
| j       | ј           | CYRILLIC SMALL LETTER JE                       |
| o       | о           | CYRILLIC SMALL LETTER O                        |
| p       | р           | CYRILLIC SMALL LETTER ER                       |
| x       | х           | CYRILLIC SMALL LETTER HA                       |
| y       | у           | CYRILLIC SMALL LETTER U                        |

These specific letters have been selected because most common fonts use an identical glyph to display their matching replacement character. However, certain fonts may not have a suitable glyph for the replacement character, or may display it differently. In this case, text typed with these layouts may look "off".

### Why would I want to use this?
In some circumstances, a piece of text may need to be readable for a human, but it is undesirable for it to be understood or further processed by a machine. Mixing different character sets makes it difficult for a computer to interpret the contents and meaning of a text, as most software is not designed to handle mismatched characters, despite being able to display them.

For example, some possible uses could include:

* Preventing web content from being indexed in a useful manner, or scraped for an AI training dataset
* Sending someone a message that can be read normally, but cannot be found through a "search" function
* Submitting a form that contains your name, without leaving a record that matches your name exactly
* Bypassing a chatroom's overzealous swear filter that blocks acceptable words
* Preventing a social media app from analyzing the contents of messages or posts for targeted advertising

Please note that Obfuscated Keyboards should not be used for any application where absolute privacy is critical, as it is trivial to defeat the obfuscation through a simple "search and replace" back to the original characters. Instead, Obfuscated Keyboards can be helpful in contexts where data is mass-processed and the user is unlikely to be individually targeted.

### Which keyboard layouts are supported?

* `QWERTY` for English
* `QWERTZ` for German
* `AZERTY` for French
* Russian (experimental — a smaller subset of Cyrillic characters is replaced with Greek and Latin equivalents)

Holding down the `cmd` key (or `cmd` with `shift`) reverts to a standard keyboard index to ensure that shortcuts using replaced letters stay accessible.

**Would you like a different layout to be supported?** Feel free to open an issue requesting it. Pull requests welcome.

**Does a layout produce unexpected results on your keyboard?** Please report the issue. Obfuscated Keyboards has been tested on built-in and external Apple keyboards, which for example treat both left and right `shift` keys as a `left shift` key. Third-party keyboards may have a different behavior.

### How do I know that it works?
Open the macOS Character Viewer (in pretty much any app: Edit menu > Emoji & Symbols, then click the icon in the top right) and type any of the above characters into the Search box. Click the matching search result, and read the description displayed below the character.

For an existing text or document, a quick way to confirm this is to perform a search (e.g. cmd + F) and enter a word using the standard keyboard. The search should return no results.

### What can go wrong?
Besides the fact that anyone who notices the nature of the obfuscation can easily convert the text back to normal characters, you may also want to keep in mind that:

* Obfuscated text cannot be enunciated correctly by screen readers such as VoiceOver, making it inaccessible to visually impaired people.
* The obfuscation relies on the likelihood that words contain one or more characters that will be substitued as described in the tables above. Some words may not contain any of these letters, and will not be obfuscated.
* Replaced characters are not readily available on every operating system. For example, if you create a password containing replaced characters, it may be impossible to enter it in some circumstances, or on other devices.
* These keyboard layouts are a proof-of-concept, and have not been extensively tested.

### Wait, aren't there loads of other Unicode characters? Couldn't we have a keyboard where every character is replaced with a wacky symbol?
Yes, this is technically possible. However, the initial version of Obfuscated Keyboards aims to make text look normal, and avoid a "ransom note" effect.

### How do I uninstall Obfuscated Keyboards?
Delete the `Obfuscated Keyboards.bundle` file from the location you've copied it to (`~/Library/Keyboard\ Layouts/` or `/Library/Keyboard\ Layouts/`) and restart your Mac.
