# Installing Tailwind for Laravel projects

## 1. Install Tailwind via npm

For most projects (and to take advantage of Tailwind's customization features), you'll want to install Tailwind via npm.

```bash
# Using npm
npm install tailwindcss
```

## 2. Install the dependencies

Install the dependencies in the local node_modules folder.

```bash
npm install
```

## 3. Compiling

How you actually build your project will depend on the tools that you’re using. Your framework may include a command like `npm run dev` to start a development server that compiles your CSS in the background,

```bash
npm run dev
```

## 4. Add Tailwind to your CSS

Use the `@tailwind` directive to inject Tailwind's `base`, `components`, and `utilities` styles into your CSS:

```css
/* ./resources/css/app.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 5. Configure Tailwind with Laravel Mix

In your webpack.mix.js, add tailwindcss as a PostCSS plugin:

```js
 // webpack.mix.js
  mix.js("resources/js/app.js", "public/js")
    .postCss("resources/css/app.css", "public/css", [
    	require("tailwindcss"),
  ]);
```


## 6. Compile

```bash
npm run dev
```

## 7. Import

Next, import your stylesheet in your main Blade layout (commonly `resources/views/layouts/app.blade.php` or similar) and add the responsive viewport meta tag if it’s not already present:

```html
 <!DOCTYPE html>
  <head>
    <!-- ... --->
	<meta charset="UTF-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
  	<link href="{{ asset('css/app.css') }}" rel="stylesheet">
  </head>
  <!-- ... --->
```

