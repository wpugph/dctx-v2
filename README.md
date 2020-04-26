# DCTx Version 2

Repository for the DCTx project.

## Project Details

- Final Site URL - https://dctx.ph/
- [Staging](https://jcnew-dctx1.pantheonsite.io/)
- [Figma](https://www.figma.com/file/ZP2wEI8IdAEWVr3pPFL8fW/DCTx-Landing-Page-04012020?node-id=0%3A1)
- [Local Export](https://drive.google.com/open?id=1oAF1XCvdLwLGzvSCTDuVb9rCYMAiYqlu) - Choose the most recent export.

_Local SSL is required!_

## Getting Started

### Prerequisites

- Install [Local by Flywheel](https://localwp.com/) for local development.
- Download and Install [Composer](https://getcomposer.org/download/)
- Because theme is bundled with Gulp, basic knowledge of the command line and the following dependencies are required: either [Yarn](https://yarnpkg.com) or [Node](https://nodejs.org) (recommended version `10.x`), [Gulp CLI](https://github.com/gulpjs/gulp-cli) (`npm install -g gulp-cli`), and [Bower](https://bower.io/) (`npm install -g bower`).

### Development

1. Once you've set up your local, run `composer install` inside `wp-content`, this will install all needed plugins by the website.
2. If you need to add a plugin, search in [WordPress Packagist](https://wpackagist.org/) and add to `composer.json` in the `required` part, and run `composer install` again. Do not do `composer update` instead in the `wp-content` folder run `rm composer.lock` before you run `composer install`.

```
	"require": {
		"wpackagist-plugin/gutenberg": "7.8.1",
		"wpackagist-plugin/name-of-plugin-here: "Version"
	},
```

3. Activate the DCTx-V2 theme in the dashboard. Then setup Gulp.
4. From the command line, change directories to `dctx-v2`

```bash
cd themes/dctx-v2
```

5. Install theme dependencies (use either Yarn or NPM)

Yarn

```bash
yarn install && bower install
```

NPM

```bash
npm install && bower install
```

### Branching and Dev Flow

1. When adding your own changes\features, create a branch from `master` using either `hotfix` or `feature` like so: `git checkout -b feature\jc-feature-name`
2. Once you're done adding your changes, create a PR and request a review.

### Gulp Tasks

From the command line, type any of the following to perform an action (make sure you are inside of the theme folder):

`gulp watch` - Automatically handle changes to CSS, JS, SVGs, and image sprites. Also kicks off BrowserSync.

`gulp icons` - Minify, concatenate, and clean SVG icons.

`gulp i18n` - Scan the theme and create a POT file.

`gulp sass:lint` - Run Sass against WordPress code standards.

`gulp js:lint` - Run Javascript against WordPress code standards.

`gulp scripts` - Concatenate and minify javascript files.

`gulp sprites` - Generate an image sprite and the associated Sass (sprite.png).

`gulp styles` - Compile, prefix, combine media queries, and minify CSS files.

`gulp` - Runs the following tasks at the same time: i18n, icons, scripts, styles, sprites.
