# GreenPad Keywords

This repository manages syntax-highlighting keyword files (`.kwd`) for the GreenPad text editor.

The main GreenPad source tree is managed in `..\GreenPad`. For the editor itself, see `..\GreenPad\README.md`.

## Contents

- `type\*.kwd`: keyword definitions for each language or file format
- Scope: major languages as well as newer and niche languages, to be expanded over time

## About `.kwd` Files

GreenPad uses `.kwd` files to define syntax highlighting. The files in this repository are intended to be placed in GreenPad's `release\type\` directory.

The basic format is:

```text
1111
/*
*/
//
keyword1
keyword2
...
```

- Line 1: four flag digits
- Line 2: block comment start token
- Line 3: block comment end token
- Line 4: line comment start token
- Line 5 and later: one keyword per line

## Flag Details

The first line is a four-digit flag string:

```text
CaseSensitive EnSingleQuote EnDoubleQuote EnEscape
```

Each digit is typically `1` to enable the behavior or `0` to disable it.

| Position | Name | Meaning |
|---|---|---|
| 1 | `CaseSensitive` | Keywords are matched case-sensitively when set to `1`; when set to `0`, matching is case-insensitive. |
| 2 | `EnSingleQuote` | Treat text enclosed in single quotes (`'...'`) as quoted string content. |
| 3 | `EnDoubleQuote` | Treat text enclosed in double quotes (`"..."`) as quoted string content. |
| 4 | `EnEscape` | Recognize escape sequences inside quoted strings. |

For example, C-like languages typically use `/* ... */` and `//`, while Python commonly uses `""" ... """` and `#`, depending on how the highlighting file is authored.
