# nuxt-web-update-notification [![npm](https://img.shields.io/npm/v/nuxt-web-update-notification.svg)](https://npmjs.com/package/nuxt-web-update-notification)

Detect webpage updates and notify user to reload. support Nuxt.

## Install

```bash
# use yarn (recommend)
yarn add -D nuxt-web-update-notification
# or use npm
npm install --save-dev nuxt-web-update-notification
```

## Example

```js
// nuxt.config.js
export default {
  mode: 'universal',
  env: {
    PATH_TYPE: process.env.PATH_TYPE,
  },
  /*
   ** Nuxt.js modules
   */
  modules: [
    [
      'nuxt-web-update-notification',
      {
        logVersion: true,
        checkInterval: 5 * 60 * 1000, // 5 分钟设置轮询一次
        // 在某些环境下才开启该 Module
        shouldBeEnable: (options) => {
          if (options.env.PATH_TYPE === 'trial') {
            return true;
          }
          return false;
        },
      },
    ],
  ],
};
```

## Thanks

- [plugin-web-update-notification](https://github.com/GreatAuk/plugin-web-update-notification)
- [网页重新部署，通知用户-最佳实践](https://juejin.cn/post/7209234917288886331)
