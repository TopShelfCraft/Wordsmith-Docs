---
title: Roman Numerals
type: guide
order: 100
---

**Wordsmith** provides several helpful methods for working with Roman numerals.

Roman numerals may include these symbols:

- I (1)
- V (5)
- X (10)
- L (50)
- C (100)
- D (500)
- M (1000)

(Larger numbers, e.g. numbers form with _apostrophi_ or _vincula_, are not supported.)

Wordsmith's Roman numeral methods include:

- [`lowerCaseRoman`](#lowerCaseRoman)
- [`upperCaseRoman`](#upperCaseRoman)


## Matching modes

You can choose how strict Wordsmith should be when trying to match Roman numeral notation.

In `strict` mode:

- Symbols are to be combined from left to right, high to low values.
- Symbols are not repeated more than 3 times.
- C may b placed after D or M.
- X may be placed before L or C.
- I may be placed before V or X.
- 'MMMCMXCIX' is the largest number supported by `strict` mode.

In `loose` mode, Wordsmith follows the rules of `strict` mode, with the following exceptions:

- Symbols may be repeated more than 3 times.
- There is no more maximum number.

In `loose-order` mode, Wordsmith follows the rules of `loose` mode, with the following exception:

- Symbols may appear in any order.

The default mode is `strict`.


## Roman numeral casing

### `lowerCaseRoman`

Lowercases any Roman numerals found in the string.

Parameters:
- `match_mode` (`'strict'`) &mdash; `'strict'`, `'loose'`, or `'loose-order'`

```twig
{{ 'MCMLIV. Chapter XI: NOT XICA!' | lowerCaseRoman }}

#  "mcmliv. Chapter xi: NOT XICA!"
```
```twig
{{ 'IIXX, XIiX, III, MDcdIII, NOTXI, MMMM' | lowerCaseRoman(matchMode='loose-order') }}

#  "iixx, xiix, iii, mdcdiii, NOTXI, mmmm"
```

### `upperCaseRoman`

Uppercases any Roman numerals found in the string.

Parameters:
- `match_mode` (`'strict'`) &mdash; `'strict'`, `'loose'`, or `'loose-order'`

```twig
{{ 'foo vi bar' | upperCaseRoman }}

#  "a VI b"
```
```twig
{{ 'mcmliv. Chapter xi: Not XiCa!' | upperCaseRoman }}

#  "MCMLIV. Chapter XI: Not XiCa!"
```
