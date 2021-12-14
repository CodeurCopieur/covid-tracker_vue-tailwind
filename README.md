# Vue 3 + Vite

Dans ce projet, nous utiliserons Vue.js et Tailwind pour créer une application de suivi simple

## Setup Tailwind in a Vue 3

- npm init vite
- project name : ...
- select a framework : ...
- cd folder
- yarn install
- yarn add -D tailwindcss@latest postcss@latest autoprefixer@latest
- npx tailwindcss init -p
- tailwind.config.js > content : './index.html', './src/**/*{vue,js,ts,jsx,tsx}'
- touch src/index.css : <br>
  @tailwind base; <br>@tailwind components; <br>@tailwind utilities;
- main.js : import "./index.css"
- npm i vue-router@4
- yarn run dev
