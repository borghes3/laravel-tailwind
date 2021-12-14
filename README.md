# Add TailwindCSS to your Laravel Project the BEST way
Some basic instructions to quickly create a Laravel project with TailwindCSS installed.
## Step 1 - Create a  Laravel project
Create a fresh installation using the Laravel installer by typing:
__Run this command in the parent directory of your project folder__

```laravel new project-name```

Then hop in the project directory

```cd project-name```

## Step 2  - Install TailwindCSS with npm
Now it's time to install TailwindCSS via node packet manager (NPM) by running the following command:

```npm install tailwindcss```

This will take some time and finally install TailwindCSS as a NodeJS module.

## Step 3 - Setup TailwindCSS in your project
Now it's time to prepare your Laravel project and make sure that it interacts with your Tailwind installation.
1. Open your project folder in your favourite IDE 

2. Open the **```app.css```**  file located in the   **```css```** folder under  **```resources```**. 
Path: ```resources/css/app.css```)

3. Type inside the ```app.css``` file the following:
```
@tailwind  base;
@tailwind  components;
@tailwind  utilities;
```

## Step 4 - Create the TailwindCSS configuration file
Now go back to your terminal and type in what follows:

**```npx tailwind init```**

This will create a ```tailwind.config.js``` file in your root directory. By editing this file you will be able to customize your Tailwind installation .
To add the default features of TailwindCSS to your configuration just add the following line at the beggining of your configuration file:
```const  defaultTheme = require('tailwindcss/defaultTheme');```

Check out more @ https://tailwindcss.com/docs/theme#customizing-the-default-theme

## Step 5 - Add TailwindCSS to PostCSS
Search for the **```webpack.mix.js```** file in the root directory of your project and edit it as follows:
```
const  mix = require('laravel-mix');
const  tailwindcss = require("tailwindcss");

mix.js('resources/js/app.js', 'public/js')
	.postCss('resources/css/app.css', 'public/css', [
		require("tailwindcss"),
]);
```
## Step 6 - Compile TailwindCSS
Now for the last time, go back to your terminal and run:

**```npm install```**

This will compile TailwindCSS and all the changes you made to the configuration file!
Now to actually use Tailwind it's necessary to run:
**```npm run watch```**
a basic command included in the package.json file of a default Laravel installation.
If you did everything correct you shouldn't receive any error and your terminal should look something like this:
![Immagine 2021-12-14 235109](https://user-images.githubusercontent.com/74593180/146092004-c21c4b72-e5d7-40ae-b032-286ec85072fa.png)
