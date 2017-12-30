---
title: Name Parsing
type: guide
order: 90
---

**Wordsmith** provides several helpful methods for working with names.

The `parseName()` function parses a string as a name and returns an array of name parts — e.g. first name, last name, etc.

Several shortcut filters are also available if you only need to extract one specific part.

Wordsmith's name parsing methods include:

- [`firstName`](#firstName)
- [`givenName`](#givenName)
- [`lastName`](#lastName)
- [`parseName`](#parseName)
- [`surname`](#surname)

## Name parsing methods

### `firstName`

An alias for [`givenName`](#givenName).


### `givenName`

Parses a string as a name and returns the 'given name' component.

```twig
{{ 'Michael Rog' | givenName }}

# "Michael"

```

### `lastName`

An alias for [`surname`](#surname).


### `parseName`

Parses a string as a name and returns a hash of its components:

```twig
{% parseName('Mr. Erich O. H. C. M. "The First Auteur" von Stroheim, II') %}

#  {
#    'nickname' : 'The First Auteur'
#    'salutation' : 'Mr.'
#    'givenName' : 'Erich'
#    'initials' : 'O. H. C. M.'
#    'surname' : 'Von Stroheim'
#    'surnameBase' : 'Stroheim'
#    'surnameCompound' : 'von'
#    'suffix' : 'II'
#  }
```


### `surname`

Parses a string as a name and returns the 'family name' component.

```twig
{{ 'Michael Rog' | surname }}

# "Rog"

```
