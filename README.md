# vite-react-ts-tailwind-template April 05, 2022
Basic installation of vite-react with typescript and tailwindcss.

Scope
-
node and npm version
```sh
v16.14.2
8.5.0
```
package.json
```json
{
  "name": "vite-react-ts-tailwind-template",
  "private": true,
  "version": "0.0.0",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^17.0.2",
    "react-dom": "^17.0.2"
  },
  "devDependencies": {
    "@types/react": "^17.0.33",
    "@types/react-dom": "^17.0.10",
    "@vitejs/plugin-react": "^1.0.7",
    "autoprefixer": "^10.4.4",
    "postcss": "^8.4.12",
    "tailwindcss": "^3.0.23",
    "typescript": "^4.5.4",
    "vite": "^2.9.0"
  }
}
```

*You can follow the steps from the [official documentation](https://tailwindcss.com/docs/guides/vite) or follow the steps below to recreate the repo...*

Steps:
-
1. Install vite
```sh
npm create vite@latest folderName
```
2. cd to `folderName` and use the following commands (make sure to use `-p` option to make the postcss.config.js file else you won't see tailwindcss styles applying on reload)
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
3. change your tailwind.config.js file's content to
```js
module.exports = {
  content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
4. add the following to your `index.css`
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
5. make sure that `index.css` is imported on your `main.tsx`/`main.jsx`
```jsx
import { createApp } from 'vue'
import App from './App.vue'
import './index.css'
...
```
6. finally run your project using
```
npm run dev
```
