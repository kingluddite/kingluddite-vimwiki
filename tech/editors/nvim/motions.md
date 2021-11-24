# Motions
## Real lines vs Display Lines
* Turn line numbers on and you will see real lines 
* Display lines wrap (default setting)

| command | Move Cursor                                 |
|---------|---------------------------------------------|
| `j`     | Down one real line                          |
| `gj`    | Down one display line                       |
| `k`     | Up one real line                            |
| `gk`    | Up one display line                         |
| `0`     | To first character of real line             |
| `g0`    | To first character of display line          |
| `^`     | To first nonblank character of real line    |
| `g^`    | To first nonblank character of display line |
| `$`     | To end of real line                         |
| `g$`    | To end of display line                      |

## Move Word Wise
| command | Move Cursor                         |
|---------|-------------------------------------|
| `w`     | Forward to start of next word       |
| `b`     | Backward to start of current word   |
| `e`     | Forward to end of current/next word |
| `ge`    | Backward to end of previous word    | (my markdown plugin overwrites this)


## Tip
| Keystrokes  | What it does                            |
| `eaer<ESC>` | "Append at the end of the current work" |

## word vs WORD
`word`: consists of a sequence of letters, digits, and underscores, or as a sequence of other nonblank characters
`WORD`: (simpler) consists of a sequence of nonblank characters separated with whitespace 

## Text Objects
* Define regions of text by structure
* Vim's text objects consists of two characters, the first which is always either `i` or `a`
  - In general we can say:
    - text objects prefixed with `i` select inside the delimiters (mnemonic: "i as inside")
    - text objects prefixed with `a` select everything including the delimiters (mnemonic: "a as around (or all)")
* Text objects ususally come in pairs: one that acts inside the object and another that acts around the object
* vim's text objects fall into two categories:
  * those that interact with pairs of delimiters (examples: `i)`, `i"`, and `it`)
    - helps to refer to these as `delimited text objects` because they begin/end with matching symbols
  * those that interact with chunks of text (i.e. words, sentences, and paragraphs)
    * helps to refer to these as `bounded text objects` because they are defined by boundaries
    * **note** vim documentation calls them `block` and `non-block` but those names are not helpful
* **GENERAL RULE**
  * `d{motion}` command tends to work well with `aw`, `as`, and `ap`
  * `c{motion}` command works better with `iw`, `is`, and `ip`
    
## Text Objects
| text object  | Selection                  |
|--------------|----------------------------|
| `a)`         | a pair of (parenthesees)   |
| `a}`         | a pair of {braces}         |
| `a]`         | a pair of [brackets]       |
| `a>`         | a pair of <angle brackets> |
| `a'`         | a pair of 'single quotes'  |
| `a"`         | a pair of "double quotes"  |
| ``a``        | a pair of backticks        |
| `at`         | a pair of <xml>tags</xml>  |
| `i)` or `ib` | inside of (parenthesees)   |
| `i}` or `iB` | inside of {braces}         |
| `i]`         | inside of [brackets]       |
| `i>`         | inside of <angle brackets> |
| `i'`         | inside of 'single quotes'  |
| `i"`         | inside of "double quotes"  |
| `i```        | inside of backticks        |
| `it`         | inside of <xml>tags</xml>  |


## Text Objects interact with chunks of text (words, sentences, and paragraphs)
| Keystrokes | Current... | Keystrokes | Current...                 |
| `iw`       | word       | `aw`       | word plus space(s)         |
| `iW`       | WORD       | `aW`       | WORD plus space(s)         |
| `is`       | sentence   | `as`       | sentence plus space(s)     |
| `ip`       | paragraph  | `ap`       | paragraph plus blank lines |

