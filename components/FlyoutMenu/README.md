# FlyoutMenu

A flyout menu with transitions and utiities to show dropdown menu content.

See UI variants on [TailwindUI](https://tailwindui.com/components/marketing/elements/flyout-menus)

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

### Usage

#### Slots

1. Use slot to pass in menu items

```html
<nuxt-link to="" class="-m-3 p-3 flex items-start rounded-lg hover:bg-gray-50 transition ease-in-out duration-150">
	<!-- icon -->
	<svg class="flex-shrink-0 h-6 w-6 text-indigo-600"></svg>
	<!-- text -->
	<div class="ml-4">
		<p class="text-base font-medium text-gray-900">Header</p>
		<p class="mt-1 text-sm text-gray-500">Lorem ipsum dolor sonor tebet gipsum espor conum exemplar magnifico.</p>
	</div>
</nuxt-link>
```

### Notes

- Using v-click-outside as a plugin rather than a directive because it will likely be used in other components as well
