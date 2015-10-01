# natgeoamazonia

Interactive map of Amazonia for National Geographic. We're planning to use a comibnation of Mapublisher-derived GeoTIFFs, raster layers derived from shapefiles, and the usual client-side Leaflet map/markers/polygons/lines for the core map. And then that will be tied to rich media assets and copy from Nat Geo.

Basic outline is a React app with a Leaflet map, /CSS/HTML, and static assets.

## Translation

Default strings and references (images and tile layers) live in `data/data.js`.
Locale-specific overrides exist as `data/data.en.js`, `data/data.es.js`, and
`data/data.pt.js`. In general, it's possible to override specific keys by
adding content to the locale-specific files. However, for array values (`[]`),
all attributes must be present and kept in sync manually.

To build for a different locale, set `LOCALE=<locale>` before running `npm
start`. Like this:

```bash
$ LOCALE=es npm start
```

## How do I install it?

See `.nvmrc` for the desired version of Node.js.

```bash
npm install
npm start
```

`npm install` will install all node packages listed in package.json.
`npm start` will run grunt (webpack, SASS compilation/ CSS minification, CSS/JS insertion) and start up the webpack-dev-server.

Visit http://localhost:8080/#/ to start exploring the app.

## How do I build it?

```bash
LOCALE=en grunt
```

This will produce `js/bundle.min.js` (and accompanying source map) and
`styles/app.min.css` (and accompanying source map).

## How do I package it?

```bash
LOCALE=en npm run-script dist
```

This will produce `dist/amazonia.tar.gz` containing all assets (unminified)
needed for linking into an external template / build system.


## Dependencies

### Software
TK

### Data
TK

### Static Assets
TK

## How do I deploy a staging version?

### English

```bash
heroku git:remote -r en -a stamen-ngm-amazonia

git push en master

# one-time setting
heroku config:set -r en LOCALE=en
```

### Spanish

```bash
heroku git:remote -r es -a stamen-ngm-amazonia-es

git push es master

# one-time setting
heroku config:set -r es LOCALE=es
```

### Portuguese

```bash
heroku git:remote -r pt -a stamen-ngm-amazonia-pt

git push pt master

# one-time setting
heroku config:set -r pt LOCALE=pt
```

## How do I deploy it to the world?

If this is a live thing in the world, how do we push changes to the live thing?
