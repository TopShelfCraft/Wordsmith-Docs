---
title: Text Statistics & Readability
type: guide
order: 110
---

**Wordsmith** provides several helpful methods for getting statistics about text and/or evaluating its readability.

Wordsmith's statistics/readability methods include:

- [`automatedReadabilityIndex`](#automatedReadabilityIndex)
- [`averageWordsPerSentence`](#averageWordsPerSentence)
- [`colemanLiauIndex`](#colemanLiauIndex)
- [`daleChallReadabilityScore`](#daleChallReadabilityScore)
- [`fleschKincaidReadingEase`](#fleschKincaidReadingEase)
- [`fleschKincaidGradeLevel`](#fleschKincaidGradeLevel)
- [`gunningFogScore`](#gunningFogScore)
- [`readTime`](#readTime)
- [`sentenceCount`](#sentenceCount)
- [`smogIndex`](#smogIndex)
- [`spacheReadabilityScore`](#spacheReadabilityScore)
- [`wc`](#wc)
- [`wordcount`](#wordcount)




## Text Statistics


### `averageWordsPerSentence`

Returns the average number of words per sentence in the text.

```twig
{% set text %}
    I would eat them in a boat.
    And I would eat them with a goat.
    And I will eat them in the rain.
    And in the dark. And on a train!
{% endset %}

{{ averageWordsPerSentence(text) }}

#  6.2
```


### `sentenceCount`

Returns an approximate count of sentences in the text.

(The sentence count returned by this function should be treated as a rough approximation. Extra periods in the text, such as in words like "Mr." or "Mrs.", will prevent the count from being exactly accurate.)

```twig
{% set text %}
    She sells seashells by the seashore.
    The shells that she sells are seashells, I'm sure.
{% endset %}

{{ sentenceCount(text) }}

#  2
```

### `wc`

An alias for [`wordcount`](#wordcount).


### `wordcount`

Counts the number of words inside string. (Returns an _integer_ number.)

`wordcount` strips tags from the provided text, so it will provide a correct value when used on HTML content.

(Bonus: Unlike PHP's `str_word_count`, Wordsmith's `wordcount` is multi-byte-safe and locale-agnostic.)

```twig
{% wordcount('Peter piper picked a peck of pickled peppers.') %}

# 8
```


## Reading Time


### `readTime`

Calculates the units of time required for an average person to read the given passage of text.

(By default, this method assumes a 200 words-per-minute English reading rate and returns the number of minutes needed to read a passage at that rate.)

You can optionally specify your own reading rate, to accommodate a different language or compensate for reading difficulty.

You can also optionally specify a minimum number of units, which serves as a floor for the returned value.

Parameters:

- `rate` (`200`) &mdash; The number of words an average person can read per unit of time.
- `minimum` (`1`) &mdash; The minimum value that will be returned.

```twig
{% set tales %}
    Whan that aprill with his shoures soote
    The droghte of march hath perced to the roote,
    And bathed every veyne in swich licour
    Of which vertu engendred is the flour;
    Whan zephirus eek with his sweete breeth
    Inspired hath in every holt and heeth
    Tendre croppes, and the yonge sonne
    Hath in the ram his halve cours yronne,
    And smale foweles maken melodye,
    That slepen al the nyght with open ye
    (so priketh hem nature in hir corages);
    Thanne longen folk to goon on pilgrimages,
    And palmeres for to seken straunge strondes,
    To ferne halwes, kowthe in sondry londes;
    And specially from every shires ende
    Of engelond to caunterbury they wende,
    The hooly blisful martir for to seke,
    That hem hath holpen whan that they were seeke.
{% endset %}

{{ tales | readTime }}

#  1

{{ readTime(tales, minimum=5) }}

#  5

```


## Readability


### `automatedReadabilityIndex`

Gives the [Automated Readability Index](https://en.wikipedia.org/wiki/Automated_readability_index) of the text, from 0 to 12.


### `colemanLiauIndex`

Gives the [Coleman-Liau Index](https://en.wikipedia.org/wiki/Coleman%E2%80%93Liau_index) of the text, from 0 to 12.


### `daleChallReadabilityScore`

Gives the [Dale-Chall readability](https://en.wikipedia.org/wiki/Dale%E2%80%93Chall_readability_formula) score of the text, from 0 to 10.


### `fleschKincaidReadingEase`

Gives the [Flesch-Kincaid Reading Ease](https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests#Flesch_reading_ease) of the text, from 0 to 100.


### `fleschKincaidGradeLevel`

Gives the [Flesch-Kincaid Grade level](https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests#Flesch%E2%80%93Kincaid_grade_level) of the text, from 0 to 12.


### `gunningFogScore`

Gives the [Gunning-Fog](https://en.wikipedia.org/wiki/Gunning_fog_index) score of the text, from 0 to 19.


### `smogIndex`

Gives the [SMOG Index](https://en.wikipedia.org/wiki/SMOG) of the text, from 0 to 12.


### `spacheReadabilityScore`

Gives the [Spache readability score](https://en.wikipedia.org/wiki/Spache_readability_formula) of the text, from 0 to 5.

_(This scale is not really suitable for measuring readability above grade 4.)_
