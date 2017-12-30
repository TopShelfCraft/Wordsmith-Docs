---
title: Introduction
type: guide
order: 0
---

Wordsmith is a blazing fast, multi-byte safe, one-stop text manipulation toolkit for Craft CMS.

### Features

- Trim and truncate text or HTML (by paragraph, word, or character)
- Beautify your typography (smart quotes, widow-prevention, ampersand styling, etc.)
- Change case and inflection
- Transliterate international text 
- Search, count, isolate, and replace substrings
- Parse Emoji, using standard and short names
- Parse Markdown, in several flavors (including Parsedown)
- Parse names to get their parts (e.g. first name, last name, etc.)
- Parse a URL to get its parts (e.g. host name, path, query string, fragment, etc.)
- Get YouTube video ID from a URL
- Match and re-case Roman numerals
- Calculate text statistics like word count, sentence count, and readability
- Tell whether a variable value is string-like
- _...and much more..._


### Usage

All of Wordsmith's methods are available in your Twig templates as **inline filters**, **filter blocks**, or **functions**.

##### INLINE FILTER
```twig
{{ 'Lorem ipsum.' | trim }}
```

##### FILTER BLOCK
```twig
{% filter trim %}
  Lorem ipsum.
{% endfilter %}
```

##### FUNCTION
```twig
{{ trim('Lorem ipsum.') }}
```

As a best practice, I recommend using the **inline filter** and **filter block** style only for methods that return text. For methods that return a number, array object, or other non-string value, using the **function** synatx will probably feel most 'correct'. 

You should also use the **named argument** syntax for providing parameter values when needed.

For example, while you could _technically_ invoke the `chop` method like this:
```twig
{{ text | chop(3, 'w') }}
```

...you should instead explicitly name the arguments, like this:
```twig
{{ text | chop(limit=3, unit='w') }}
```

By using this **named argument** syntax, you don't need to supply all the possible parameters if you aren't using them, _and_ you're guaranteed that your templates will keep working if the API changes.

_For purposes of semantic versioning, the **names** of parameters are guaranteed to not change within a major version, but their order may.)_ 


### List of methods _(abridged)_

 - [`amp`](/guide/typography.html#amp)
 - [`apTitleize`](/guide/casing.html#apTitleize)
 - [`automatedReadabilityIndex`](/guide/statistics.html#automatedReadabilityIndex)
 - [`averageWordsPerSentence`](/guide/statistics.html#averageWordsPerSentence)
 - [`between`](/guide/substrings.html#between)
 - [`camelize`](/guide/casing.html#camelize)
 - [`caps`](/guide/typography.html#caps)
 - [`chop`](/guide/truncation.html#chop)
 - [`colemanLiauIndex`](/guide/statistics.html#colemanLiauIndex)
 - [`daleChallReadabilityScore`](/guide/statistics.html#daleChallReadabilityScore)
 - [`dasherize`](/guide/casing.html#dasherize)
 - [`emojify`](/guide/emoji.html#emojify)
 - [`entitle`](/guide/casing.html#entitle)
 - [`firstName`](/guide/names.html#firstName)
 - [`firstWord`](/guide/substrings.html#firstWord)
 - [`fleschKincaidReadingEase`](/guide/statistics.html#fleschKincaidReadingEase)
 - [`fleschKincaidGradeLevel`](/guide/statistics.html#fleschKincaidGradeLevel)
 - [`givenName`](/guide/names.html#givenName)
 - [`gunningFogScore`](/guide/statistics.html#gunningFogScore)
 - [`hacksaw`](/guide/truncation.html#hacksaw)
 - [`humanize`](/guide/casing.html#humanize)
 - [`hyphenate`](/guide/casing.html#hyphenate)
 - [`isStringy`](/guide/utilities.html#isStringy)
 - [`lastName`](/guide/names.html#lastName)
 - [`lastWord`](/guide/substrings.html#lastWord)
 - [`lowerCaseRoman`](/guide/roman-numerals.html#lowerCaseRoman)
 - [`markdown`](/guide/markdown.html#markdown)
 - [`md`](/guide/markdown.html#md)
 - [`ordinal`](/guide/inflection.html#ordinal)
 - [`ordinalize`](/guide/inflection.html#ordinalize)
 - [`parsedown`](/guide/markdown.html#parsedown)
 - [`parsedownExtra`](/guide/markdown.html#parsedownExtra)
 - [`parseName`](/guide/names.html#parseName)
 - [`parseUrl`](/guide/urls.html#parseUrl)
 - [`pde`](/guide/markdown.html#pde)
 - [`pascalize`](/guide/casing.html#pascalize)
 - [`pluralize`](/guide/inflection.html#pluralize)
 - [`readTime`](/guide/statistics.html#readTime)
 - [`sentenceCount`](/guide/statistics.html#sentenceCount)
 - [`singularize`](/guide/inflection.html#singularize)
 - [`slugify`](/guide/casing.html#slugify)
 - [`smartypants`](/guide/typography.html#smartypants)
 - [`smogIndex`](/guide/statistics.html#smogIndex)
 - [`spacheReadabilityScore`](/guide/statistics.html#spacheReadabilityScore)
 - [`substringAfterFirst`](/guide/substrings.html#substringAfterFirst)
 - [`substringAfterLast`](/guide/substrings.html#substringAfterLast)
 - [`substringBeforeFirst`](/guide/substrings.html#substringBeforeFirst)
 - [`substringBeforeLast`](/guide/substrings.html#substringBeforeLast)
 - [`substringBetween`](/guide/substrings.html#substringBetween)
 - [`substringCount`](/guide/substrings.html#substringCount)
 - [`surname`](/guide/names.html#surname)
 - [`titleize`](/guide/casing.html#titleize)
 - [`typogrify`](/guide/typography.html#typogrify)
 - [`typogrifyFeed`](/guide/typography.html#typogrifyFeed)
 - [`underscore`](/guide/casing.html#underscore)
 - [`underscored`](/guide/casing.html#underscored)
 - [`upperCamelize`](/guide/casing.html#upperCamelize)
 - [`upperCaseRoman`](/guide/roman-numerals.html#upperCaseRoman)
 - [`urlFragment`](/guide/urls.html#urlFragment)
 - [`urlHost`](/guide/urls.html#urlHost)
 - [`urlPass`](/guide/urls.html#urlPass)
 - [`urlPath`](/guide/urls.html#urlPath)
 - [`urlPort`](/guide/urls.html#urlPort)
 - [`urlQuery`](/guide/urls.html#urlQuery)
 - [`urlScheme`](/guide/urls.html#urlScheme)
 - [`urlUser`](/guide/urls.html#urlUser)
 - [`trim`](/guide/truncation.html#trim)
 - [`trimLeft`](/guide/truncation.html#trimLeft)
 - [`trimRight`](/guide/truncation.html#trimRight)
 - [`wc`](/guide/statistics.html#wc)
 - [`widont`](/guide/typography.html#widont)
 - [`wrapAmps`](/guide/typography.html#wrapAmps)
 - [`wrapCaps`](/guide/typography.html#wrapCaps)
 - [`wordcount`](/guide/statistics.html#wordcount)
 - [`youtubeId`](/guide/urls.html#youtubeId)


### Requirements

- [Craft CMS](https://craftcms.com/) 3.0+
- [PHP](http://php.net/downloads.php) 7.0+


### License

Wordsmith is "Postcardware" &mdash; Open-source and free to use... And if it helps you out, please send me a digital 'postcard' and let me know how you're using it. 


### Support

Wordsmith is free and community-supported.

If you'd like to report a bug or make improvements/contributions to the code, please open a [GitHub Issue](https://github.com/TopShelfCraft/Wordsmith/issues) or submit a [Pull Request](https://github.com/TopShelfCraft/Wordsmith/pulls) to the `dev` branch.  

If you'd like to request implementation support or commission a customization for your project, please [email Support](mailto:support@topshelfcraft.com).


### Thanks

Thanks for using **Wordsmith**!
