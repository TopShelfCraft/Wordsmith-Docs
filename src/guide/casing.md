---
title: Casing & Capitalization
type: guide
order: 40
---

**Wordsmith** provides several methods for case modification:

- [`apTitleize`](#apTitleize)
- [`camelize`](#camelize)
- [`dasherize`](#dasherize)
- [`entitle`](#entitle)
- [`humanize`](#humanize)
- [`hyphenate`](#hyphenate)
- [`pascalize`](#pascalize)
- [`slugify`](#slugify)
- [`titleize`](#titleize)
- [`underscore`](#underscore)
- [`underscored`](#underscored)
- [`upperCamelize`](#upperCamelize)


## Case Modification

### `apTitleize`

Intelligently up-cases a string as a headline/title using AP capitalization rules.

```twig
{{ 'a tale of two cities' | camelize }}

#  "A Tale of Two Cities"
```

### `camelize`

Returns a camelCase version of the string.

_Trims surrounding spaces, capitalizes letters following digits, spaces, dashes and underscores, and removes spaces, dashes, as well as underscores._

```twig
{{ 'Camel-Case' | camelize }}

#  "camelCase"
```


### `dasherize`

Returns a lowercase and trimmed string separated by dashes.

_Dashes are inserted before uppercase characters (with the exception of the first character of the string), and in place of spaces as well as underscores._

```twig
{{ 'fooBar' | dasherize }}

#  "foo-bar"
```


### `entitle`

Alias for [`apTitleize`](#apTitleize).

_Provided so that Wordsmith can be a drop-in replacement for the [Entitle](https://github.com/experience/entitle.craft-plugin) plugin._ 



### `humanize`

Capitalizes the first word of the string, replaces underscores with spaces, and strips away an '_id' suffix if one is present.

```twig
{{ 'author_id' | humanize }}

#  "Author"
```
```twig
{{ 'some_snake_case_words' | humanize }}

#  "Some snake case words"
```


### `hyphenate`

Alias for [`dasherize`](#dasherize).

_Provided so that Wordsmith can be a drop-in replacement for the [Inflect](https://github.com/lukeholder/craft-inflect) and [Typogrify](https://github.com/nystudio107/craft3-typogrify) plugins._ 


### `pascalize`

Alias for [`upperCamelize`](#upperCamelize).

_Provided so that Wordsmith can be a drop-in replacement for the [Inflect](https://github.com/lukeholder/craft-inflect) and [Typogrify](https://github.com/nystudio107/craft3-typogrify) plugins._ 


### `slugify`

Converts the string into an URL slug.

_This includes replacing non-ASCII characters with their closest ASCII equivalents, removing remaining non-ASCII and non-alphanumeric characters, and replacing whitespace with $replacement. The replacement defaults to a single dash, and the string is also converted to lowercase. The language of the source string can also be supplied for language-specific transliteration._

```twig
{{ 'Using strings like fòô bàř' | slugify }}

#  "using-strings-like-foo-bar"
```

### `titleize`

Returns a trimmed string with the first letter of each word capitalized.

Also accepts an array, $ignore, allowing you to list words you want to leave un-capitalized.

- `ignore` (default provided in config) &mdash; Array of words to ignore when capitalizing

```twig
{{ 'i like to watch television' | titleize }}

#  "I Like to Watch Television"
```

<p class="tip">If you're working with titles in English, you may also be interested in [`apTitleize`](#apTitleize), which is a bit more intelligent and follows AP title capitalization rules.</p>


### `underscore`

Returns a lowercase and trimmed string separated by underscores.

_Underscores are inserted before uppercase characters (with the exception of the first character of the string), and in place of spaces as well as dashes._

```twig
{{ 'TestACase' | underscored }}

#  "test_a_case"
```
 

### `underscored`

Alias for [`underscore`](#underscore).

_Provided for compatibility with Stringy, so that Wordsmith can be a drop-in replacement for the [Typogrify](https://github.com/nystudio107/craft3-typogrify) plugin._


### `upperCamelize`

Returns an UpperCamelCase version of the supplied string.

_It trims surrounding spaces, capitalizes letters following digits, spaces, dashes and underscores, and removes spaces, dashes, underscores._

```twig
{{ 'Upper Camel-Case' | upperCamelize }}

#  "UpperCamelCase"
```

