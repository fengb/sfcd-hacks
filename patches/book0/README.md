BOOK 0 proof-of-concept
---
![Menu](menu.png)

This is a patch to create a placeholder book. It loads above the existing books to avoid complex menu changes.

### Caveats

- Mostly untested -- I've only gone through the menu and the initial book selection

- Graphics glitch -- when all 5 books are available, the bottom of the selection menu is messed up

- Book 0 saves as book 1 -- most likely part of the bank data. Haven't looked too deep

### Changelog

| Address range | Description |
| --- | --- |
| _NEW BOOK DATA_ |
| `0x038BA000 - 0x0434EFFF` | Copy of book 1's data bytes<ul><li>BANKSD00 => BANKDSD49</li><li>BANKSD01 => BANKDSD4A</li><li>[...]</li><li>BANKSD16 => BANKDSD5F</li></ul>
| `0x00008050 - 0x00008057`<br>`0x0000ad20 - 0x0000b491` | Updated filesystem |
| `0x0000303f`<br>`0x00003209` | Updated file count -- the Jurassic Park phenomenon 😅 |
| `0x0000833e - 0x00008345` | Updated disc date
| _MENU CHANGES_ | _`SFEMAIN.X`_
| `0x01ec6db4 - 0x01ec6df3` | New menu text
| `0x01eb5cb6 - 0x01eb5cc9` | Changed bank load from math lookup table
| `0x01ec6342 - 0x01ec634d`<br>`0x01ec6f00 - 0x01ec6f19` | Insert extra menu item
| `0x01ec5fc3`<br>`0x01ec635d`<br>`0x01ec6371` | Extra menu item - off by one errors
