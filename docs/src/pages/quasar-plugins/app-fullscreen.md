---
title: Fullscreen Plugin
---
There are times when you want your website or App to run in fullscreen.
Quasar makes it easy by wrapping the [Web Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API).

::: warning
Please note that the behavior is different depending on the platform the code is running on, due to the fact that there isn't a fixed Web standard for Web Fullscreen API yet.
:::

## Installation
<doc-installation plugins="AppFullscreen" />

## Usage
::: tip
For an exhaustive list of properties and methods, please check out the API section.
:::

``` js
// outside of a Vue file
import { AppFullscreen } from 'quasar'

// Requesting fullscreen mode:
AppFullscreen.request()

// Exiting fullscreen mode:
AppFullscreen.exit()
```

``` js
// inside of a Vue file

// Requesting fullscreen mode:
this.$q.fullscreen.request()

// Exiting fullscreen mode:
this.$q.fullscreen.exit()
```

<doc-example title="AppFullscreen" file="AppFullscreen/Basic" />

::: warning
On some phones this will have little effect:
* For example, on Samsung S4, when App goes into fullscreen, the top bar will slide up but still remain on screen.
* On Nexus phones, on the other hand, like Nexus 5, Android navigation buttons and top bar disappear completely.

It all depends on the Web Fullscreen API support of the platform the code is running on.
:::

### Watching for fullscreen changes

``` vue
<template>...</template>

<script>
export default {
  watch: {
    '$q.fullscreen.isActive' (val) {
      console.log(val ? 'In fullscreen now' : 'Exited fullscreen')
    }
  }
}
</script>
```

## AppFullscreen API
<doc-api file="AppFullscreen" />
