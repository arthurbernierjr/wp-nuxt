# wp-nuxt

[![npm (scoped with tag)](https://img.shields.io/npm/v/wp-nuxt.svg?style=flat-square)](https://www.npmjs.com/package/wp-nuxt)
[![npm](https://img.shields.io/npm/dt/wp-nuxt.svg?style=flat-square)](https://www.npmjs.com/package/wp-nuxt)
[![CircleCI](https://img.shields.io/circleci/project/github/yashha/wp-nuxt.svg?style=flat-square)](https://circleci.com/gh/yashha/wp-nuxt)
[![Codecov](https://img.shields.io/codecov/c/github/yashha/wp-nuxt.svg?style=flat-square)](https://codecov.io/gh/yashha/wp-nuxt)
[![Dependencies](https://david-dm.org/yashha/wp-nuxt/status.svg?style=flat-square)](https://david-dm.org/yashha/wp-nuxt)
[![js-standard-style](https://img.shields.io/badge/code_style-standard-brightgreen.svg?style=flat-square)](http://standardjs.com)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fyashha%2Fwp-nuxt.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fyashha%2Fwp-nuxt?ref=badge_shield)
[![Netlify Status](https://api.netlify.com/api/v1/badges/4bb695b5-6b46-4c3f-a866-33aaf727570a/deploy-status)](https://app.netlify.com/sites/wp-nuxt/deploys)

[📖 **Release Notes**](./CHANGELOG.md)

## Features

The module adds [WP-API](https://github.com/WP-API/node-wpapi) to your nuxt application.

The size of the library is 49,8 kB minified (14 kB gzipped). [![npm bundle size](https://img.shields.io/bundlephobia/minzip/wpapi.svg)](https://bundlephobia.com/result?p=wpapi)

## Setup

- Add `wp-nuxt` dependency using yarn or npm to your project

- Add `wp-nuxt` to `modules` section of `nuxt.config.js`

```js
{
  modules: [
    // Simple usage
    'wp-nuxt',

    // With options
    ['wp-nuxt', {
      endpoint: 'https://wp.kmr.io/wp-json'
      extensions: true // For additional functions of wpapi-extensions
      /* other options of WP-API */
    }],
 ]
}
```
Info: when you pass `extensions: true` you will have additional functions of [wpapi-extensions](https://github.com/yashha/wpapi-extensions) available. For this you also have to install [WUXT Headless WordPress API Extensions](https://wordpress.org/plugins/wuxt-headless-wp-api-extensions/) on your wordpress sever.

## Usage

You can use the API of [WP-API](https://github.com/WP-API/node-wpapi) using the injected 'app.$wp'. (s. example)

### Example

```js
<script>
export default {
  async asyncData ({ app, store, params }) {
    return { articles: await app.$wp.posts().perPage(10) }
  }
}
</script>
```

## License

[MIT License](./LICENSE)

Copyright (c) [yashha](https://github.com/yashha)


[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fyashha%2Fwp-nuxt.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fyashha%2Fwp-nuxt?ref=badge_large)
