---
title: Inflection & Transliteration
type: guide
order: 30
---

**Wordsmith** provides multi-language methods for dealing with noun inflection.

Inflection is available for these locales:
- `en` (English) _(default)_
- `es` (Spanish)
- `fr` (French)
- `nb` (Norwegian Bokmal)
- `pt` (Portuguese)
- `tr` (Turkish)

Wordsmith's inflection and transliteration methods include:

- [`ordinal`](#ordinal)
- [`ordinalize`](#ordinalize)
- [`pluralize`](#pluralize)
- [`singularize`](#singularize)
- [`transliterate`](#transliterate)

## Singulars/Plurals

### `pluralize`

When used without an explicit quantity, `pluralize` returns the plural form of the given word.

When used _with_ a quantity, `pluralize` returns the correct singular or plural form of the given word, for the provided quantity and language.

- `quantity` (`2`) &mdash; The quantity of objects
- `locale` (`en`) &mdash; The language to use for inflection

```twig
{{ 'plugin' | pluralize }}

#  plugins
```

```twig
3 {{ 'plugin' | pluralize( qty=3 ) }}

#  "3 plugins"
```

```twig
{{ pluralize('child', qty=1) }}

#  "child"
```

```twig
{{ pluralize('child', qty=100) }}

#  "children"
```

```twig
{{ pluralize('el', locale='es') }} {{ pluralize('hijo', locale='es') }}

#  "los hijos"
```

### `singularize`

Returns the singular form of the given word.

```twig
{{ 'matrices' | singularize }}

#  "matrix"
```

```twig
{{ singularize('mamás', locale='es') }}

#  "mamá"
```

## Ordinals

### `ordinal`

Returns the ordinal suffix that corresponds to the given number.
_(Uses English ordinalization rules)._

```twig
{{ 1 | ordinal }}

#  "st"
```

```twig
{{ 2 | ordinal }}

#  "nd"
```

```twig
{{ 3 | ordinal }}

#  "rd"
```

```twig
{{ 4 | ordinal }}

#  "th"
```


### `ordinalize`

Returns the ordinalized variant of the given number.
_(Uses English ordinalization rules)._

```twig
{{ 1 | ordinalize }}

#  "1st"
```

```twig
{{ 42 | ordinalize }}

#  "42nd"
```

```twig
{{ 103 | ordinalize }}

#  "103rd"
```

```twig
{{ 4 | ordinalize }}

#  "4th"
```


## Transliteration


### `transliterate`

// TODO


## Case Modification

Wordsmith also provides several methods for [case modification](/guide/casing.html), including: 

- [`camelize`](/guide/casing.html#camelize)
- [`dasherize`](/guide/casing.html#dasherize)
- [`humanize`](/guide/casing.html#humanize)
- [`hyphenate`](/guide/casing.html#hyphenate)
- [`pascalize`](/guide/casing.html#pascalize)
- [`slugify`](/guide/casing.html#slugify)
- [`titleize`](/guide/casing.html#titleize)
- [`underscore`](/guide/casing.html#underscore)
- [`underscored`](/guide/casing.html#underscored)
- [`upperCamelize`](/guide/casing.html#upperCamelize)

