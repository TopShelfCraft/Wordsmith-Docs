---
title: Utilities
type: guide
order: 120
---

**Wordsmith** includes some handy utility functions:

- [`isStringy`](#isStringy)


## Utility methods

### `isStringy`

Returns `true` if the provided parameter is string-like, i.e. if it is a string, number, or string-castable Object.

```twig
{% isStringy("foo") %}
# true

{% isStringy(42) %}
# true

{% isStringy(false) %}
# false

{% isStringy(null) %}
# false

{% isStringy(craft.users.one) %}
# true

```
