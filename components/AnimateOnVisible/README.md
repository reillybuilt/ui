# AnimateOnVisible

Use [vue-observe-visibility](https://github.com/Akryum/vue-observe-visibility) and [animate.style](https://animate.style/) to create animation effects on when elements are visible.

### Installation

1. animate.css (4.1.1)

   - `yarn add animate.css`

2. vue-observe-visibility (0.4.6)

   - `yarn add vue-observe-visibility`
   - create `vue-observe-visibility.js` in /plugins

     ```js
     import Vue from 'vue';
     import VueObserveVisibility from 'vue-observe-visibility';

     Vue.use(VueObserveVisibility);
     ```

   - add `'~/plugins/vue-observe-visibility.js'` to `plugins` in nuxt.config.js

### Usage

#### example

```html
<animate-on-visible class="h-64 w-64 bg-red-600" animation="bounceInLeft" delay="1000">
	<div class="h-64 w-64 bg-green-600"></div>
</animate-on-visible>
```

#### spacing

- Use width and height utility classes on the component to occupy the screen space elements will animate into

#### Props

### `animation`

- Pass a single animation's identifier
  - i.e. `bounce` not `animate__bounce`
- _Type:_ String
- _Default:_ `""`
- _Example usage:_ `animation="fadeInLeft"`

### `delay`

- Delay to apply to animation in milliseconds
- _Type:_ String
- _Default:_ `null`
- _Example usage:_ `delay="1000"`

### `multiple`

- If animation should occur _every_ time element becomes visible in viewport
- _Type:_ Boolean
- _Default:_ `false`

### Notes

- Polyfill for IE support isn't included
- Setting threshold (i.e. trigger at 50% visibility vs 100%) does not apply here since element being animated has no height therefore fires anytime in viewport
- VOV throttling is more flexible than using the utility classes provided by AS to create delays
