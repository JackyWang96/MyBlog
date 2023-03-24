---
title: "TailwindCSS"
date: 2023-02-14T00:55:45+11:00
draft: false
---

### Introduction
Tailwind CSS is a CSS styling library that provides us with all the building blocks we need to build custom designs without using custom styles. 


### Feature
Tailwind will automatically delete all unused CSS when building production files, so its size in the actual production environment is very small, and it is considered to be the CSS style library with the most design sense.


### Installation
```javascript
//Install Tailwind CSS
npm install -D tailwindcss
npx tailwindcss init

//Add the paths to all of your template files in your tailwind.config.js file.
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}

//Add the Tailwind directives to your CSS
@tailwind base;
@tailwind components;
@tailwind utilities;

//Start the Tailwind CLI build process
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```