---
title: Typography
type: guide
order: 20
---

**Wordsmith** provides a nice collection of functions for applying nice web typography treatments to your text, prettifying quotes, avoiding 'widows', etc.

Wordsmith's typography methods include:

- [`amp`](#amp)
- [`caps`](#caps)
- [`typogrify`](#typogrify)
- [`typogrifyFeed`](#typogrifyFeed)
- [`smartypants`](#smartypants)
- [`widont`](#widont)
- [`wrapAmps`](#wrapAmps)
- [`wrapCaps`](#wrapCaps)


## Typography


### `amp`

An alias of [`wrapAmps`](#wrapAmps).

_Provided for backwards compatibility, so that Wordsmith can be a drop-in replacement for the [Typogrify](https://github.com/jamiepittock/craft-typogrify) plugin._


### `caps`

An alias of [`wrapCaps`](#wrapCaps).

_Provided for backwards compatibility, so that Wordsmith can be a drop-in replacement for the [Typogrify](https://github.com/jamiepittock/craft-typogrify) plugin._


### `typogrify`

Typogrify applies a veritable kitchen sink of typographic treatments to beautify your web typography:

- Pretty quotes &mdash; _Smart handling of ‘single’ and “double” curly quotation marks_
- Pretty punctuation
  - _em_ and _en_ dashes, wrapped by `&thinsp;` characters
  - ellipses (…)
  - trademarks (&trade;), copyright (&copy;), and service marks  
  - math symbols (5×5×5=53)
  - fractions (&frac12;)
  - ordinal suffixes (1st, 2nd)
- Smart hyphenation &mdash; _Adds `&shy;` characters into words to enable responsive hyphenation_
- Space control:
    - widow protection
    - gluing values to units
    - forced internal wrapping of long URLs and email addresses
- CSS class wrapping for styling special characters
  - ampersands
  - uppercase words
  - numbers
  - initial quotes & guillemets
  
* `settings` &mdash; An array of ad-hoc settings to override the defaults for this instance of the filter.
  
```twig
{% filter typogrify %}
    On the 1st day of Christmas my "true love" gave to me:
    1/2 of a Patridge(TM) in a pear tree.
{% endfilter %}
```

```twig
{{ 'Mark & Sons: "industry leaders" in... stuff.' | typogrify }}
```

### `typogrifyFeed`

Applies suite of typographic treatments from to beautify your type, but in a way that is appropriate for RSS (or similar) feeds &mdash; i.e. excluding processes that may cause issues in contexts with limited character set intelligence.

* `settings` &mdash; An array of ad-hoc settings to override the defaults for this instance of the filter.

```twig
{% set myFeed = include('feeds/myFeedTemplate') | typogrifyFeed %} 
```
 

### `smartypants`

Parses 'ugly' quotes into smart ‘single’ and “double” curly quotation marks.

_Provided for backwards compatibility, so that Wordsmith can be a drop-in replacement for the [Typogrify](https://github.com/jamiepittock/craft-typogrify) plugin. The `typogrify` function already applies smart quotes._


### `widont`

Replaces the space between the last two words in a string with a `&nbsp;` to prevent widowing.

```twig
{% filter widont %}
    Lorem ipsum dolor sit amet.
{% endfilter %}
```

### `wrapAmps`

Wraps ampersands in `<span class="amp">` so they can be styled with CSS.

- `class` (`'amp'`) &mdash; The class name to apply

```twig
{{ 'Pixel & Tonic' | wrapAmps }}
{{ 'Pixel &amp; Tonic' | wrapAmps }}
```

_(The `typogrify` function applies `wrapAmps` by default, unless you disable it in the settings.)_


### `wrapCaps`

Wraps all-uppercase words in `<span class="caps">` so they can be styled with CSS.

- `class` (`'caps'`) &mdash; The class name to apply

```twig
{{ 'The CIA called the GCHQ about the KGB, but everyone there was MIA.' | wrapCaps }}
```

_(The `typogrify` function applies `wrapCaps` by default, unless you disable it in the settings.)_


## Transliteration

Wordsmith also provides a method for [transliterating](/guide/inflection.html#Transliteration) symbols from other languages into their closest corresponding letters from the current alphabet.

- [`transliterate`](/guide/inflection.html#transliterate)
