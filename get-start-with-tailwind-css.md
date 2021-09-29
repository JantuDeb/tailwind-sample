# How to use Tailwind CSS

Created By: Jantu
Date: September 30, 2021

**What is Tailwind CSS**

Tailwind is a utility-first CSS framework, which provides a set of helper classes. By using these classes we can create layout rapidly. If you use Tailwind CSS, you don't need to write different style using media query for different screen sizes. You can use Tailwind's responsive utilities to handle it easily.

**Do we need to use Tailwind CSS?**
So,  It depends we can build a minimal prototype by using Tailwind very fast. The development time is very fast because it comes with plenty of utility classes for everything we need in a project. Although we can achieve this with vanilla CSS.

**How to setting up a project with Tailwind  CSS**

We can use `npm` to  get started with tailwind  or we can use Tailwind CSS , `npm` is preferred way to install Tailwind. 

We can start by creating a project folder, let's name it  `tailwind-sample` . Now we can open this folder in VS code editor.

Now we need to create a *`package.json`* file by using `npm` command in the following way.

 `$ npm init -y` 

Run this command in terminal of your vs code editor. Now we can use `npm` to add dependency to our project.

We start by installing Tailwind CSS using following command.

`$ npm install tailwindcss`

This command will downloaded tailwind CSS and saved it to `node_modules` folder.

We will create a `css/style.css` file and add these @tailwind directive  to import Tailwind’s base, components, and utilities styles.

```css
@tailwind base;

@tailwind components;

@tailwind utilities;
```

The next step is to create a initial Tailwind configuration file by using the following command in project folder.

`$ npx tailwindcss init`

This will create a `tailwind.config.js` in your root folder with the following content.

```jsx
//tailwind.config.js
module.exports = {
  purge: [],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
}
```

Now, we will use `PostCSS` as a build processor for tailwind also we need a additional plugin called `autoprefixer` .

Let's install *PostCSS* and *autoprefixer*  by using following command.

`$ npm install postcss-cli autoprefixer@latest`

Let's create a *PostCSS* configuration file named `postcss.config.js` in our project root folder.

We will add the following content in newly created `postcss.config.js` file.

```jsx
module.exports = {
    plugins: [
        require('tailwindcss'),
        require('autoprefixer'),
    ]
}
```

With this the PostCSS process will perform CSS processing with the tailwindcss and the autoprefixer plugins.

The last step is to create a build script to execute  PostCSS processing for file `css/styles.css`  and it will create a build CSS file in the given location. 

Let's add the following build command  in our  *`package.json` file.*

`"build": "postcss css/styles.css -o build/styles.css"`

To execute this script we need to run the following build command.

`$ npm run build`

So, we have successfully installed and configured Tailwind CSS for our project,  now we can create HTML and start creating our layouts with Tailwind CSS.

Now create a `index.html` in root folder of our project and link the generated `build/styles.css` file to html.

Let's create a card layout using Tailwind CSS

```html
<div class="w-64 rounded-lg shadow-lg text-center bg-indigo-600 text-white p-4">
	<h1 class="text-xl font-bold m-2">This is the card title</h1>
	<p>Lorem ipsum dolor sit amet consectetur adipisicing elit.
  Aliquid amet quaerat eos! Doloremque molestiae voluptate, eos 
  architectoaccusantium atque voluptas sapiente vitae repellat 
  dolores saepe minima. Ratione mollitia magni saepe. </p>

	<button type="submit" class="bg-white text-blue-800 m-4 rounded-md p-2 hover:text-blue-700 hover:bg-gray-200">
	Clicked Me
	</button>
</div>
```

![Untitled](How%20to%20use%20Tailwind%20CSS%202de05ce0118740ccb5858ae9a47e0c21/Untitled.png)

This is the result, you can it's very simple to create this card component using tailwind utility classes.

Now, let me explain each of the classes we have used to create this card.

`w-64`  : this specifies a width of 16rem.

`rounded-lg` : creates a border-radius of 0.5rem.

`shadow-lg` : it created a `box shadow : 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);`

`text-center` : it centers the text, `text-align: center;`

`bg-indigo-600` : this specifies the indigo background color, follow the link to know more about tailwind colors  follow this [**documentation**](https://tailwindcss.com/docs/customizing-colors) 

`text-white` : this specifies `color: white`;

 `p-4` : this specifies `padding:0.5rem;`

To know more about Tailwind CSS follow this tailwind **[docs](https://tailwindcss.com/docs)** 

For reference you can use this sample project from git `[tailwind sample](https://github.com/JantuDeb/tailwind-sample)`

# Conclusion

Tailwind CSS provides you with a set of utility classes which can be used to create you unique and custom design with ease. Tailwind CSS is not opinionated, so you’re completely free in choosing the design of elements and components on your website.
