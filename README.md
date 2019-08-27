# Gulp tasker v.1.3.0
> "gulp": "^4.0.2"

#### Content
**[How to launch](#how-to-launch)**  
**[What is this?](#what-is-this)**  
**[Contained tasks](#what-is-this)**  
**[Dependencies](#dependencies)**  
**[License](#license)**

### How to launch:

1. ```git clone```
2. ```yarn``` / ```npm i```
3. ```yarn global add gulp-cli``` / ```npm i gulp-cli -g```
4. ```gulp```
5. Navigate to your localhost address
(default is http://localhost:3000/)

### What is this?
Gulp tasker is an easy editable gulp build with a flexible and convenient choice of the tasks to run.

Some of the tasks are doing the same job, but with a different conditions. Such duplicates are disabled (commented) in ```gulpfile.js```.
For example:
1. If you are using ```pug``` instead of ```html``` — you should disable **html** task and enable **pug**
2. If you do not want to minify your custom ```js``` files — you should disable **js:app-minify** and enable **js:app**

### Current (1.3.0) version contains following tasks:
* **clean**

  Deletes the ```build``` folder

* **images:sprite**

  Creates a sprite from ```.png``` files placed in the ```images/sprites/png``` folder and moves it to the ```build/images/sprites``` folder

* **svg:sprite**

  Creates a sprite from ```.svg``` files placed in the ```images/sprites/svg``` folder and moves it to the ```build/images/sprites``` folder

* **images:minify**

    Minifies all images (and sprites) from the ```dev/images``` folder. Triggered only once per gulp run (can be launched manually)

* **sass:lint**

    Lints all ```.scss``` files at the ```dev/styles``` folder with [stylelint](https://stylelint.io/) using config from ```.stylelintrc```

* **html**

  Copies all ```html``` files from the ```dev``` folder to the ```build``` folder

* **pug**

  Compiles all ```pug``` files from the ```pug/pages``` folder to the ```build``` folder
  
  ```locals: JSON.parse($.fs.readFileSync('content.json', 'utf8'))``` can be enabled for using ```content.json``` as ```locals``` (global variables for pug)

* **css:vendor**

  Merges and minimizes all vendor ```css``` files, which paths are declared in ```gulp/configs/config.js```, and moves the resulting ```vendor.min.css``` file to the ```build/css``` folder

* **sass**

  Compiles, prefixes css properties as indicated in ```gulp/configs/config.js``` and minimizes the ```main.scss``` file from the ```styles``` folder to the ```build``` folder

* **js:vendor**

  Merges and minimizes all vendor ```js``` files, which paths are declared in ```gulp/configs/config.js```, and moves the resulting ```vendor.min.js``` file to the ```build/js``` folder

* **js:app**

  Merges all custom ```js``` files, which paths are declared in ```gulp/configs/config.js```, and moves the resulting ```app.js``` file to the ```build/js``` folder

* **js:app-minify**

  Merges and minimizes all custom ```js``` files, which paths are declared in ```gulp/configs/config.js```, and moves the resulting ```app.min.js``` file to the ```build/js``` folder

* **fonts**

  Copies all files from the ```dev/fonts``` folder to the ```build/fonts``` folder

* **images**

  Copies all files from the ```dev/images``` folder to the ```build/images``` folder, except the ```dev/images/sprites``` folder

* **watch**

  Watches for the specific files and executes needed task on change

* **serve**

  Launches and configures browserSync
  
### Dependencies
You **should** ```yarn upgrade --latest``` / ```npm update && npm audit fix -f``` as *Gulp tasker* will always be ok working with the latest versions of the dependencies, so it is **strongly recommended**.

```
"devDependencies": {
    "@babel/core": "^7.5.5",
    "@babel/preset-env": "^7.5.5",
    "browser-sync": "^2.26.7",
    "child_process": "^1.0.2",
    "del": "~5.1.0",
    "fs": "^0.0.1-security",
    "gulp": "^4.0.2",
    "gulp-autoprefixer": "~7.0.0",
    "gulp-babel": "^8.0.0",
    "gulp-cheerio": "~0.6.2",
    "gulp-concat": "~2.6.1",
    "gulp-concat-css": "~3.1.0",
    "gulp-csso": "^3.0.1",
    "gulp-imagemin": "^6.1.0",
    "gulp-load-plugins": "~2.0.1",
    "gulp-minify": "^3.1.0",
    "gulp-notify": "~3.2.0",
    "gulp-pug": "~4.0.1",
    "gulp-rename": "^1.4.0",
    "gulp-replace": "~1.0.0",
    "gulp-sass": "~4.0.2",
    "gulp-sass-glob": "^1.1.0",
    "gulp-sourcemaps": "~2.6.5",
    "gulp-svg-sprite": "~1.5.0",
    "gulp-svgmin": "~2.2.0",
    "gulp.spritesmith": "^6.10.1",
    "merge-stream": "^2.0.0",
    "stylelint": "^10.1.0",
    "stylelint-config-standard": "^18.3.0",
    "stylelint-order": "^3.0.1"
},
"dependencies": {
    "jquery": "~3.4.1",
    "normalize.css": "~8.0.1"
}
```

### License
Copyright © 2018 - 2019, based on Loftschool 2017 Web Advanced course build.

Licensed under the MIT license.