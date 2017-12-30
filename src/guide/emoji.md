---
title: Emoji
type: guide
order: 60
---

**Wordsmith** provides a full service for parsing emoticons and Emoji.

Traditional emoticons are recognized directly from symbol text. For example, the text emoticon `<3` corresponds to the heart Emoji. ❤️

Emoji may also be replaced by name, using their standard names, or using the common "short names" from apps like Slack, GitHub, Campfire, and Basecamp.

Standard names may be expressed as constant-case, snake-case, or camel-case variants: for example, `:POLAND_FLAG:`, `:poland_flag:`, and `:polandFlag:`

Short names are mixed-case and specific to various Emoji: for example, `:flag-pl:` 🇵🇱

By default, the Emoji parser uses the `:` delimiter when replacing Emoji by name, whereas no delimiter is needed for parsing emoticon text. For example, the Emoji parser would replace both `:)` and `:slightly_smiling_face:` with the smiling face Emoji. 🙂

_(Wordsmith's internal character map is currently up-to-date with [Unicode 10.0](https://emojipedia.org/unicode-10.0/) and [Emoji 5.0](https://emojipedia.org/emoji-5.0/).)_

Wordsmith's Emoji methods include:

- [`emojify`](#emojify)


## Emoji cheat sheet

If you're looking for a handy listing of Emoji and their short-names, check out the [Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet/). 

## Emoji parsing


### `emojify`

Replaces occurrences of emoticons and Emoji name codes in a string with the corresponding Emoji characters.

Parameters:
* `nameDelimiter` (default: `':'`) &mdash; Specifies the delimiter to use for recognizing Emoji name codes
* `emoticonDelimiter` (default: `''`) &mdash; Specifies the delimiter to use for recognizing emoticon text

```twig
{% filter emojify %}
    There once was a :) from :flag-pl:.
    He typed on his :computer: and made you a :NEGATIVE_SQUARED_LATIN_CAPITAL_LETTER_A:.
{% endfilter %}

# There once was a 🙂 from 🇵🇱. He typed on his 💻 and made you a 🅰️.
```
```twig
{{ ':us:' | emojify }}

# 🇺🇸
```
```twig
{{ "|dog| |face|:o)|face|" | emojify( nameDelimiter="|", emoticonDelimiter='|face|' ) }}

# 🐶 🐵
```
