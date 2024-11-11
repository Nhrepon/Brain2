```php
// tailwind
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

//add the following line into tailwind.config.js:
content: [ "./resources/**/*.blade.php", "./resources/**/*.js", "./resources/**/*.vue", ],

// add the following line into app.css
@tailwind base; @tailwind components; @tailwind utilities;

npm run dev

// add following line into blade file
<!doctype html> <html> <head> <meta charset="utf-8"> <meta name="viewport" content="width=device-width, initial-scale=1.0"> @vite('resources/css/app.css') </head> <body> <h1 class="text-3xl font-bold underline"> Hello world! </h1> </body> </html>
```

