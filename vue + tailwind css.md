# vue3 + tailwind css

```shell
npm init vue@latest
cd <your-project-name>
npm install
npm run dev
npm run build
```

# Install Tailwind via npm

```bash
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
```

### Create your configuration files

Next, generate your `tailwind.config.js` and `postcss.config.js` files:

```shell
npx tailwindcss init -p
```

This will create a minimal `tailwind.config.js` file at the root of your project:

It will also create a `postcss.config.js` file that includes `tailwindcss` and `autoprefixer` already configured:

### Configure Tailwind to remove unused styles in production

In your `tailwind.config.js` file, configure the `purge` option with the paths to all of your pages and components so Tailwind can tree-shake unused styles in production builds:

```js
module.exports = {
  content: ['./index.html', './src/**/*.{vue,js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### Include Tailwind in your CSS

Create the `./src/index.css` file and use the `@tailwind` directive to include Tailwind’s `base`, `components`, and `utilities` styles, replacing the original file contents:

```css
/* ./src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Finally, ensure your CSS file is being imported in your `./src/main.js` file:

```js
// src/main.js
import { createApp } from 'vue'
import App from './App.vue'
import './index.css'

createApp(App).mount('#app')
```

------

You’re finished! Now when you run `npm run dev`, Tailwind CSS will be ready to use in your Vue 3 and Vite project.