---
title: Trimming & Truncation
type: guide
order: 10
---

**Wordsmith** provides several helpful methods for trimming text content.

Wordsmith's trimming & truncation methods include:

- [`chop`](#chop)
- [`hacksaw`](#hacksaw)
- [`trim`](#trim)
- [`trimLeft`](#trimLeft)
- [`trimRight`](#trimRight)


## Truncation


### `chop`

Chops content down to the given `limit` of `paragraphs`, `words`, or `characters`.

Will optionally `append` a string to the end of the chopped content.

Skips over `allowedTags` as instructed.

* `unit` (`'p'`) &mdash; the unit of content to truncate
  - `'paragraphs'`, `'p'`
  - `'words'`, `'w'`
  - `'characters'`, `'c'`   
* `limit` (`1`) &mdash; the number of units to allow
* `append` (`''`) &mdash; a string that will be added to the end of the truncated text
* `allowedTags` (`null`) &mdash; a string indicating what HTML tags are allowed to stay in the content before trimming; all other HTML will be striped. _(When you use `chop` with the `paragraphs` unit, `'<p>'` tags are maintained automatically.)_

```twig
{% set text %}
    <p>She sells seashells by the seashore.</p>
    <p>The shells that she sells are seashells, I'm <em>sure</em>.</p>
    <p>So, if she sells shells she sees on the shore,</p>
    <p>Yes, I say she sells seashore shells, for sure.</p>
{% endset %}

{{ text | chop }}

#  '<p>She sells seashells by the seashore.</p>'

{{ text | chop(limit=2, allowedTags="<em>") }}

#  '<p>She sells seashells by the seashore.</p>
#   <p>The shells that she sells are seashells, I'm <em>sure</em>.</p>'

{{ text | chop(limit=3, unit='w') }}

#  'She sells seashells'

{{ text | chop(limit=2, unit='c') }}

#  'Sh'

```


### `hacksaw`

An alias for `chop`.

_Provided for backwards compatibility, so that Wordsmith can be a drop-in replacement for the [Hacksaw](https://github.com/ryanshrum/hacksaw) plugin._


## Trimming


### trim

Returns a string with whitespace removed from the start and end of the string. Supports the removal of unicode whitespace. Accepts an optional string of characters to strip instead of the defaults.

* `chars` &mdash; characters to strip instead of the defaults

```twig
{{ '  fòôbàř  ' }}

#  'fòôbàř'
```


### trimLeft

Returns a string with whitespace removed from the start of the string. Supports the removal of unicode whitespace. Accepts an optional string of characters to strip instead of the defaults.

* `chars` &mdash; characters to strip instead of the defaults

```twig
{{ '  fòôbàř  ' }}

#  'fòôbàř  '
```


### trimRight

Returns a string with whitespace removed from the end of the string. Supports the removal of unicode whitespace. Accepts an optional string of characters to strip instead of the defaults.

* `chars` &mdash; characters to strip instead of the defaults

```twig
{{ '  fòôbàř  ' }}

#  '  fòôbàř'
```
