---
title: URL Parsing
type: guide
order: 80
---

**Wordsmith** provides several helpful methods for working with URLs.

The `getUrlParts()` function parses a string as a URL and attempts to return an array of component parts — e.g. protocol, hostname, path, etc.

(Several shortcut filters are also available if you only need to extract one specific part.)

You can also parse the video ID out of YouTube URLs. _(Vimeo URL parsing coming soon.)_

Wordsmith's name parsing methods include:

- [`parseUrl`](#getUrlParts)
- [`urlFragment`](#urlFragment)
- [`urlHost`](#urlHost)
- [`urlPass`](#urlPass)
- [`urlPath`](#urlPath)
- [`urlPort`](#urlPort)
- [`urlQuery`](#urlQuery)
- [`urlScheme`](#urlScheme)
- [`urlUser`](#urlUser)
- [`youtubeId`](#youtubeId)

## URL parsing

### `parseUrl`

Parses a string as a URL and returns a hash of its components:

```twig
{% parseUrl('https://michael@guidesr.us:42/the-answer/?foo=bar#anchor') %}

#  {
#    'scheme' : 'https'
#    'host' : 'guidesr.us'
#    'port' : 42
#    'user' : 'michael'
#    'pass' : null
#    'path' : 'the-answer'
#    'query' : 'foo=bar'
#    'fragment' : 'anchor'
#  }
```

*This function takes after PHP's `parse_url()` method, except that it always includes **all** of the possible components, even if they're empty. Furthermore, the individual components returned by `parseUrl` are string objects, to preserve chainability.* 


### `urlFragment`

Returns the fragment component of a URL. (i.e. the part after a hashmark '#', which usually represents an anchor on the target page.)

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlFragment }}

#  'anchor'
```


### `urlHost`

Returns the host name component of a URL.

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlHost }}

#  'guidesr.us'
```


### `urlPass`

Returns the password component of a URL, or `null` if the URL doesn't specify a password.

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlPass }}

#  ''
```


### `urlPath`

Returns the resource path component of a URL, or `null` if the URL doesn't specify a path.

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlPath }}

#  '/the-answer/'
```


### `urlPort`

Returns the port number component of a URL, or `null` if the URL doesn't specify a port.

_(PHP's `parse_url()` method returns an integer for the port number component. Wordsmith, by contrast, returns a string object, to preserve chainability with other methods.)_

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlPort }}

#  '42'
```


### `urlQuery`

Returns the query string component of a URL, or `null` if the URL doesn't specify a query.

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlQuery }}

#  'foo=bar'
```


### `urlScheme`

Returns the protocol component of a URL (e.g. 'http', 'https').

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlScheme }}

#  'https'
```


### `urlUser`

Returns the user component of a URL, or `null` if the URL doesn't specify a user.

```twig
{{ 'https://michael@guidesr.us:42/the-answer/?foo=bar#anchor' | urlUser }}

#  'michael'
```


### `youtubeId`

Returns the YouTube video ID from a URL, or `null` if the source string isn't a YouTube video URL.

```twig
{{ 'https://www.youtube.com/watch?v=dQw4w9WgXcQ' | youtubeId }}

#  'dQw4w9WgXcQ'
```
