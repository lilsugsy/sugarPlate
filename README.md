
![alt text](https://raw.githubusercontent.com/lilsugsy/sugarPlate/main/sugarplate.jpg)

# :candy: SugarPlate 
A boilerplate for developing creative websites using javascript

## Getting Started
You need to have Node.js and npm installed in your machine, these are our only dependencies to run the project locally.


```bash
# Clone the project.
git clone https://github.com/lilsugsy/sugarPlate.git

# Install npm depedencies.
npm install

# Configure .env variables and run the website.
npm start
```

## Adding Pages
To add a page to the website, you need to do the following... 

### Add route
Using Express.js, you can define your routes and query in the main file.<br>
Add a route via the app.js file, passing through the data you need. Here is an example:

```js
app.get('/about', (request, response) => {
  request.prismic.api.query('', { pageSize : 100 }).then(({ results }) => {
    const about = find(results, { type: 'about' })

    const standard = get(results, request)

    response.render('pages/about', { about, ...standard })
  })
})
```
### Add view
When routing the url, you can choose the view you would like to render. You can create a new view in the "views/pages" folder. A good tip is to extend a base layout that has been set up.

## Adding/modifying styles

### Architecture
It is recomended to use the [7-1 Sass architecture](https://sass-guidelin.es/#the-7-1-pattern):

### Example
The CSS/SASS is stored in the 'styles' folder. Each page should have it's own folder. You can create as many folders as you like. We recommend the following:
- styles
  - index.scss
  - base
    - fonts.scss
    - global.scss
    - reset.scss
  - utils
    - functions.scss
  - pages
    - home
      - home.scss
      - home_gallery.scss
      - home_component_2.scss
      - etc..
    - about
      - about.scss
      - about_gallery.scss
      - etc..

### Adding to the main index.scss file
Using the above file structure, it makes it nice and simple to modify, manage and maintain your code. Once you have added your files/styles, you can import them into the main index.scss at the root of the 'styles' folder. Here is an example of what your index.scss file should look like:


```scss
@import './base/fonts';
@import './base/global';
@import './base/reset';

@import './pages/home/home';
@import './pages/home/home_gallery';
@import './pages/home/home_component_2';

@import './pages/about/about';
@import './pages/about/about_gallery';
```


## Languages and Tools
<p align="left"> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> <a href="https://pugjs.org" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/pug.svg" alt="pug" width="40" height="40"/> </a> <a href="https://sass-lang.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/sass/sass-original.svg" alt="sass" width="40" height="40"/> </a> <a href="https://webpack.js.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/d00d0969292a6569d45b06d3f350f463a0107b0d/icons/webpack/webpack-original-wordmark.svg" alt="webpack" width="40" height="40"/> </a> <a href="https://expressjs.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg" alt="express" width="40" height="40"/> </a> <a href="https://prismic.io/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/prismicio/awesome-prismic/master/media/logo.svg" alt="express" width="40" height="40"/> </a> </p>
