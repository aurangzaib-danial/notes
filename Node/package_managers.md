
# Package managers
We have two major package managers for node.

1. npm (ships with node)
2. yarn (third party)

I prefer yarn because it's much faster then npm. Also, yarn is integrated with Rails webpacker.

**No matter which package manager we use, all the modules are downloaded from npmjs.com**

All the packages are installed specific to each project inside 'node_modules' folder. 

## How to use other people libraries or in node say 'node_modules'
1. Install package

```shell
yarn add express
```
2. Now require the library in your project.

```js
const express = require('express');
// We provide the name of the package and require finds the folder of the module in 'node_modules' and then loads up its index.js that is its entry point.
```

