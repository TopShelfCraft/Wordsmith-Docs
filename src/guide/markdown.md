---
title: Markdown
type: guide
order: 70
---

**Wordsmith** provides a full and multi-flavored suite of Markdown parsing functions:

- [`markdown`](#markdown)
- [`md`](#md)
- [`parsedown`](#parsedown)
- [`parsedownExtra`](#parsedownExtra)
- [`pde`](#pde)


## Markdown flavors

The following "flavors" of Markdown are supported:

- `original` &mdash; The default when using Craft's `md`/`markdown` filters.
- `gfm` &mdash; [GitHub-flavored Markdown](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown)
- `gfm-comment` &mdash; [GitHub-flavored Markdown](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown), with newlines converted to `<br>` tags. _(Useful for parsing comments as inline text)_
- `extra` &mdash; [Markdown Extra](https://michelf.ca/projects/php-markdown/extra/), provided by [Parsedown Extra](https://github.com/erusev/parsedown-extra)
- `yii-extra` &mdash; Markdown Extra, provided by Yii's internal Markdown parser. _(This flavor doesn't fully implement the Markdown Extra spec, so using the Parsedown-powered `extra` flavor is recommended. This option is provided to parallel the functionality of using the "extra" flavor of Craft's built-in Markdown parser.)_



## Parsing Markdown


### `markdown`

Parses text through Markdown.

* `flavor` (`'gfm'`) &mdash; Your desired flavor of Markdown syntax
* `inlineOnly` (`false`) &mdash; Parse only inline elements (useful for one-line descriptions)

_This function attempts to override Craft's built-in `markdown` filter, in order to provide the superior Parsedown-powered `'extra'` flavor._

### `md`

Alias for [`markdown`](#markdown).

_This function attempts to override Craft's built-in `md` filter, in order to provide the superior Parsedown-powered `'extra'` flavor._


### `parsedown`

Alias for [`markdown(flavor='gfm')`](#markdown).

* `inlineOnly` (`false`) &mdash; Parse only inline elements (useful for one-line descriptions)

_Provided so that Wordsmith can be a drop-in replacement for the [Parsedown](https://github.com/pixelandtonic/Parsedown) or [Craft 3 Parsedown](https://github.com/luwes/craft3-parsedown) plugins._


### `parsedownExtra`

Alias for [`markdown(flavor='extra')`](#markdown).

* `inlineOnly` (`false`) &mdash; Parse only inline elements (useful for one-line descriptions)

_Provided so that Wordsmith can be a drop-in replacement for the [Parsedown](https://github.com/pixelandtonic/Parsedown) or [Craft 3 Parsedown](https://github.com/luwes/craft3-parsedown) plugins._

### `pde`

Alias for [`parsedownExtra`](#markdown)

_Provided so that Wordsmith can be a drop-in replacement for the [Parsedown](https://github.com/pixelandtonic/Parsedown) or [Craft 3 Parsedown](https://github.com/luwes/craft3-parsedown) plugins._
