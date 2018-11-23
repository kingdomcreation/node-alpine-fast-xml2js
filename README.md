# Base image 
Just another base image of `node:alpine` with npm package `fast-xml2js` pre-installed globally.

## Instructions

In your app you can reference the package directly like

```javascript
var parseString = require('fast-xml2js').parseString
```

If you have fast-xml2js in your **package.json** dependencies, you must link it in your Dockerfile before running npm install like

```Dockerfile
RUN npm link fast-xml2js
RUN npm install
```

The package was added to `/usr/local/lib/node_modules/` and requires no other dependencies to parse *XML* into a valid *JSON* object. The function `parseString` is a in-place replacement of xml2js parseString. 

For more information check out [fast-xml2js](https://www.npmjs.com/package/fast-xml2js) and [xml2js](https://www.npmjs.com/package/xml2js) for more details.

| Software      | Version 
|---------------|-----------
| Node.js       | 8.12.0
| Yarn          | 1.12.3
| fast-xml2js   | 1.0.8
