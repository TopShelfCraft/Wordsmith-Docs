---
title: Substrings
type: guide
order: 50
---

**Wordsmith** provides several helpful methods for working with parts of strings.

Wordsmith's substring methods include:

- [`between`](#between)
- [`firstWord`](#firstWord)
- [`lastWord`](#lastWord)
- [`substringAfterFirst`](#substringAfterFirst)
- [`substringBeforeFirst`](#substringBeforeFirst)
- [`substringAfterLast`](#substringAfterLast)
- [`substringBeforeLast`](#substringBeforeLast)
- [`substringCount`](#substringCount)


## First/Last helpers


### `firstWord`

Returns the first word in the source string, or `null` if there are no words in the source string.

(For the purposes of this method, a "word" means a group of characters. The returned word may include punctuation, and (depending on your text) it may or may not be a 'real' word.

```twig
{{ 'Donald! J. Trump' | firstWord }}

# "Donald!"
```


### `lastWord`

Returns the last word in the source string, or `null` if there are no words in the source string.

(For the purposes of this method, a "word" means a group of characters. The returned word may include punctuation, and (depending on your text) it may or may not be a 'real' word.

```twig
{{ 'Gin, lime, Chartreuse, maraschino' | lastWord }}

# "maraschino"
```


## Substring extraction

### `between`

Returns the substring between `start` and `end`, if found, or an empty string.
An optional offset may be supplied, from which to begin the search for the `start` delimiter.

```twig
{{ 'Peter piper picked a peck of pickled peppers.' | between( start='piper', end='pickled' ) }}

# " picked a peck of "
```

### `substringAfterFirst`

Gets the substring after the first occurrence of a separator.
(If the separator isn't found in the source string, `null` is returned.)
	 
```twig
{{ 'Peter piper picked a peck of pickled peppers.' | substringAfterFirst('p') }}

# "iper picked a peck of pickled peppers."
```

### `substringBeforeFirst`

Gets the substring before the first occurrence of a separator.
(If the separator isn't found in the source string, `null` is returned.)
	 
```twig
{{ 'Peter piper picked a peck of pickled peppers.' | substringBeforeFirst('p') }}

# "Peter "
```

### `substringAfterLast`

Gets the substring after the last occurrence of a separator.
(If the separator isn't found in the source string, `null` is returned.)
	 
```twig
{{ 'Peter piper picked a peck of pickled peppers.' | substringAfterLast('p') }}

# "ers."
```

### `substringBeforeLast`

Gets the substring before the last occurrence of a separator.
(If the separator isn't found in the source string, `null` is returned.)
	 
```twig
{{ 'Peter piper picked a peck of pickled peppers.' | substringBeforeLast('p') }}

# "Peter piper picked a peck of pickled pep"
```


### `substringCount`

Counts occurrences of the substring in the source string.
	 
```twig
{{ 'Peter piper picked a peck of pickled peppers.' | substringCount('p') }}

# 8
```
