NodeJs, Tailwind, Ejs

1- $ npm init -y
 Result :: Create "package.json" file.

2- $ npm install express
3- $ npm install ejs
4- $ npm install nodemon --save-dev
5- $ npm install -D tailwindcss@latest   @tailwindcss/typography@latest   @tailwindcss/forms@latest   @tailwindcss/aspect-ratio@latest   @tailwindcss/line-clamp@latest    postcss@latest    autoprefixer@latest

6- $ npx tailwindcss init
    Result :: Create "tailwind.config.js" file

7- Delete "main": "index.js" from package.json file and add this line in to "script" section.
    Result ::
        "scripts": {
            "start": "nodemon server.js"
        }
8- Create "saver.js" in root folder and add this lines in to this file:
            const express = require("express");
            const app = express();
            const path = require("path");

            app.set('view engine', 'ejs');
            app.set('views', path.join(__dirname, 'views'));
            app.use('/assets', express.static('assets'));
            app.get("/", (req, res) => {
                res.render('index', {});

            })
            app.listen(3000, () => {
                console.log('Running on port 3000');
            });

9- Create "views" folder in root and Create 3 file in this filder:

    use content from "https://tailblocks.cc"
    -------index.ejs:
        
        <!DOCTYPE html>
        <html lang="en">

        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Node tailwind ejs</title>
            <link rel="stylesheet" href="../assets/styles.css">
        </head>

        <body>
            <%- include('header')%>
                <section>
                    <div class="text-center text-green-400">
                        <h2>
                            I hope this tutorial has helped you.
                            <br>
                            With respect.
                        </h2>

                        <hr>
                        <p class="bg-indigo-500 text-white m-5 p-5">
                            Javad Haiderpour.
                            <br>
                            jheidarpour@gmail.com
                        </p>
                    

                    </div>
                </section>
                <%- include('footer')%>
        </body>

        </html>

    -------header.ejs:

        <header class="text-gray-600 body-font">
        <div class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center">
        <a class="flex title-font font-medium items-center text-gray-900 mb-4 md:mb-0">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-10 h-10 text-white p-2 bg-indigo-500 rounded-full" viewBox="0 0 24 24">
            <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path>
            </svg>
            <span class="ml-3 text-xl">Tailblocks</span>
        </a>
        <nav class="md:ml-auto flex flex-wrap items-center text-base justify-center">
            <a class="mr-5 hover:text-gray-900">First Link</a>
            <a class="mr-5 hover:text-gray-900">Second Link</a>
            <a class="mr-5 hover:text-gray-900">Third Link</a>
            <a class="mr-5 hover:text-gray-900">Fourth Link</a>
        </nav>
        <button class="inline-flex items-center bg-gray-100 border-0 py-1 px-3 focus:outline-none hover:bg-gray-200 rounded text-base mt-4 md:mt-0">Button
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-1" viewBox="0 0 24 24">
            <path d="M5 12h14M12 5l7 7-7 7"></path>
            </svg>
        </button>
        </div>
    </header>


    -------footer.ejs:
        <footer class="text-gray-600 body-font">
        <div class="container px-5 py-8 mx-auto flex items-center sm:flex-row flex-col">
        <a class="flex title-font font-medium items-center md:justify-start justify-center text-gray-900">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-10 h-10 text-white p-2 bg-indigo-500 rounded-full" viewBox="0 0 24 24">
            <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path>
            </svg>
            <span class="ml-3 text-xl">Tailblocks</span>
        </a>
        <p class="text-sm text-gray-500 sm:ml-4 sm:pl-4 sm:border-l-2 sm:border-gray-200 sm:py-2 sm:mt-0 mt-4">© 2020 Tailblocks —
            <a href="https://twitter.com/knyttneve" class="text-gray-600 ml-1" rel="noopener noreferrer" target="_blank">@knyttneve</a>
        </p>
        <span class="inline-flex sm:ml-auto sm:mt-0 mt-4 justify-center sm:justify-start">
            <a class="text-gray-500">
            <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-5 h-5" viewBox="0 0 24 24">
                <path d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"></path>
            </svg>
            </a>
            <a class="ml-3 text-gray-500">
            <svg fill="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-5 h-5" viewBox="0 0 24 24">
                <path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"></path>
            </svg>
            </a>
            <a class="ml-3 text-gray-500">
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-5 h-5" viewBox="0 0 24 24">
                <rect width="20" height="20" x="2" y="2" rx="5" ry="5"></rect>
                <path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37zm1.5-4.87h.01"></path>
            </svg>
            </a>
            <a class="ml-3 text-gray-500">
            <svg fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="0" class="w-5 h-5" viewBox="0 0 24 24">
                <path stroke="none" d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"></path>
                <circle cx="4" cy="4" r="2" stroke="none"></circle>
            </svg>
            </a>
        </span>
        </div>
    </footer>

10- Create "assets" folder in root and "styles.css" in this folder for output tailwind css file.
11- Create "styles" folder in root and "tailwindcss.css" in this folder for output tailwind css file. enter this line in to this file:
    @tailwind base;
    @tailwind components;
    @tailwind utilities;

12- Add this line in to "script" section in to " package.json" file:
    Result ::
        "scripts": {
            "start": "nodemon server.js",
            "build-tail": "NODE_ENV=production tailwindcss build -i styles/tailwindcss.css -o assets/styles.css"
        } 
13- Add this lines in to "tailwind.config.js" file:
    content: [
                './views/*.{html,js,ejs}',
            ],
14- $ npm run build-tail
15- $ npm start
16- look localhost:3000 in browser.
    If some classes in Tailwind don't work (such as "text-center" class)
    Run "npm install" again
17- Good luck