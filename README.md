# WAYS TO INCLUDE ALPINE IN YOUR PROJECT
**Alpine js is a rugged, minimal framework for composing JavaScript behavior in your markup. Think of it like jQuery for the modern web.**

**This is a documentation of the ways in which you can include Alpine into your project.**

**There are two different ways to to do this which are:**
**1. Including it through a cdn(content delivery network) using a script tag.**
**2. Importing it as a module.**

**Either way is perfectly valid. It all depends on the project's needs and the developer's taste.**




# Include Through CDN:
**This is by far the simplest way to get started with Alpine. Include the following script tag in the head of your HTML page.**
## <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>


> [!IMPORTANT]
> Don't forget the "defer" attribute in the <script> tag.

> [!TIP]
> Notice the @3.x.x in the provided CDN link. This will pull the latest version of Alpine version 3. 

> For stability in production, it's recommended that you hardcode the latest version in the CDN link.
> ## <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.14.1/dist/cdn.min.js"></script>


> [!NOTE]
> Note that you will still need to define a component with x-data in order for any Alpine.js attributes to work.




# As a Module:
**Please follow step by step, line by line.**

**If you prefer the more robust approach, you can install Alpine via NPM and import it into a bundle.**

**Run the following command to install it:**
## npm install alpinejs


**Create a new folder, name it src and create an app.js file into that folder. Then in that app.js file, you can now import Alpine into your bundle and initialize it by adding this block of code:**

> import Alpine from 'alpinejs'
 
> window.Alpine = Alpine
 
> Alpine.start()


> [!NOTE]
> The window.Alpine = Alpine bit is optional, but is nice to have for freedom and flexibility. Like when tinkering with Alpine from the devtools for example.
>
> If you imported Alpine into a bundle, you have to make sure you are registering any extension code IN BETWEEN when you import the Alpine global object, and when you initialize Alpine by calling Alpine.start().
>
> Ensure that Alpine.start() is only called once per page. Calling it more than once will result in multiple "instances" of Alpine running at the same time.

**Well that's not all! :smile:**

**Now you need to install more dev dependencies, I recommend a package like laravel mix**

> [!TIP]
> Laravel Mix, a package developed by Laracasts creator Jeffrey Way, provides a fluent API for defining webpack build steps for your Laravel application using several common CSS and JavaScript pre-processors. 
> Though Laravel Mix was originally built for Laravel projects, it of course may be used for any type of application.

**The next step will be to install Laravel mix:**
## npm install laravel-mix --save-dev


**Then create a mix configuration file using:**
## touch webpack.mix.js
> [!NOTE]
> If this step does not work, it may be because the touch command is not installed for your cli. The touch command is basically used to create a file without any content.
> To install touch for your command line interface, run:
> ### npm install touch-cli -g

> [!IMPORTANT]
> webpack.mix.js is your configuration layer on top of webpack. Most of your time will be spent here.


**In your project's root, create a new folder named dist, then define your configuration by opening webpack.mix.js and add the following block of code:**
### // webpack.mix.js

### let mix = require('laravel-mix');

### mix.js('src/app.js', 'dist').setPublicPath('dist');

> [!NOTE]
> What the last line does is to tell mix to go to your src/app.js file and compile it down into the dist directory.


**Next step: Compile**
**We are now ready to bundle our assets. Laravel mix provides a command-line program called 'mix' which triggers the appropriate webpack build. Give it a run now by running the following command:**
## npx mix


### Quite complicated right? but congrats, you just created your first bundle.
### Create an HTML file, and load your script using:
## <script defer src="/dist/app.js"></script>


**Voila, start building something using Alpine.js**


**I hope this has been very useful in propelling your alpine.js journey, I would also love feedbacks too**
**I would appreciate stars and follows on this repo and my profile (github.com/XBanTs) and also feel free to share.**
**I'm avaialable on social platforms like X(Twitter) through the user: @XBanTs_**
**Let's connect and innovate, cheers!** 
**By Ayo "XBanTs" Oyewo.**

