# Website Starter Project

This is a starter project for static websites, see live demo at [https://sad-engelbart-908f70.netlify.com](https://sad-engelbart-908f70.netlify.com).

The website is built based on the following tech:

- [webpack](https://webpack.js.org/) for building and bundling
- [11ty](https://www.11ty.dev/) static site generator
- [sass](https://sass-lang.com/) CSS pre-processor
- [Bulma](https://bulma.io/) CSS framework
- [Font Awesome](https://fontawesome.com/) Icon Font

The generated scaffold website is pretty basic but includes the following niceties:

- a simple site works out of the box, including example pages created from `.html` and `.md`
- animated navbar that will turn transparent on the start page when fully scrolled up
- favicons in different formats are automatically generated from `src/favicon.svg`, and the generated favicons are included in the generated html
- default footer including contact information, copyright notice and google maps link
- example `_redirect` file is provided for simple deployment to [netlify](https://www.netlify.com/) and using your custom domain name
- cookie banner based on [cookieconsent](https://www.npmjs.com/package/cookieconsent)
- [GTM](https://tagmanager.google.com/#/home) scripts included

## Installation

1. Clone this repo
1. cd into the project directory
1. install dependencies with `npm install`

## Configuration

1. copy the environment configuration with `cp .env.example .env`
1. set the variables in `.env` according to your environment, `ROOT_URL will be used for generating absolute paths in sitemap.xml`
1. configure GTM and your company/contact information in `src/_data/config.js`, which will be used to create a default footer and imprint (the latter in German only, at the moment)

## Development

```
npm start
```

The development server will be available at `http://localhost:8080/`, or on the next free port after `8080`.

Please note that when a new `.html` page is added the development server has to be restarted. This is necessary due to the way the integration between 11ty and webpack is set up. They are completely independent, and webpack treats all `.html` files generated by 11ty as `.html` templates in which webpack will inject some code (using the [HtmlWebpackPlugin](https://webpack.js.org/plugins/html-webpack-plugin/)).

## Deployment Build

```
npm run build
```

Set up web server to serve the `web` directory.
