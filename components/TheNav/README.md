# TheNav

Nav bar framework.

### Dependencies

1. [v-click-outside](https://github.com/ndelvalle/v-click-outside#readme) (3.1.2)

   - `yarn add v-click-outside`
   - create `v-click-outside.js` in /plugins

   ```js
   import Vue from 'vue';
   import vClickOutside from 'v-click-outside';

   Vue.use(vClickOutside);
   ```

   - add `'~/plugins/v-click-outside.js'` to `plugins` in nuxt.config.js
