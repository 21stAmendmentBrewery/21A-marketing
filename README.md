# UNDERSCORE
This

## Usage

### Prerequisites

### Victor Hugo
This is a boilerplate for using [Hugo](https://gohugo.io/) as a static site generator and [Gulp](https://gulpjs.com/) + [Webpack](https://webpack.js.org/) as your asset pipeline.

Victor Hugo setup to use [PostCSS](http://postcss.org/) and [Babel](https://babeljs.io/) for CSS and JavaScript compiling/transpiling.

This project is released under the [MIT license](LICENSE). Please make sure you understand its implications and guarantees.

Please refer to the Victor Hugo docummentation [Docs](https://github.com/netlify/victor-hugo)

You need to have the latest/LTS [Docs](https://github.com/netlify/victor-hugo) and [npm](https://www.npmjs.com/get-npm) versions installed in order to use Victor Hugo.

Next step, clone this repository and run:

```bash
npm install
```

### Development

While developing your website, use:

```bash
npm start
```

or

```bash
gulp server
```

Then visit http://localhost:3000/ *- or a new browser windows popped-up already -* to preview your new website. BrowserSync will automatically reload the CSS or refresh the whole page, when stylesheets or content changes.

### Static build

To build a static version of the website inside the `/dist` folder, run:

```bash
npm run build
```

To get a preview of posts or articles not yet published, run:

```bash
npm run build-preview
```



## Additions to Victor Hugo

### Netlify CMS
You will need to replace your
[Docs](https://www.netlifycms.org/docs/)

#### Setup
You will need to replace repo with your repo in the site > static > admin> config.yml

```yaml
backend:
  name: github
  repo: kungfukoala/_underscore # Replace with your repo
  branch: master
```

### LostGrid
[Get Started](https://github.com/peterramsing/lost)
[Docs](http://lostgrid.org/docs.html)

### POSTCSS Colour functions
[Docs](https://www.npmjs.com/package/postcss-colour-functions)


Had to add lost and autoprefixer to PostCSS pipeline.
```JavaScript
 lost(), autoprefixer()
```

```JavaScript
// Compile CSS with PostCSS
gulp.task("css", () => (
  gulp.src("./src/css/*.css")
    .pipe(sourcemaps.init())
    .pipe(postcss([cssImport({from: "./src/css/main.css"}), cssnext(), lost(), autoprefixer()]))
    .pipe(sourcemaps.write('./'))
    .pipe(gulp.dest("./dist/css"))
    .pipe(browserSync.stream())
));
```

## Deploying to Netlify

- Push your clone to your own GitHub repository.
- [Create a new site on Netlify](https://app.netlify.com/start) and link the repository.

Now Netlify will build and deploy your site whenever you push to git.

You can also click this button:

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/kungfukoala/_underscore)
