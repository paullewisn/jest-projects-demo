# 🍎🍌 jest-projects-demo 🥦🥕 

Simple demonstration on how to setup the `Jest projects` feature to work with a monorepo. 

`apple`/`banana` could represent applications, and `broccoli`/`carrot` could represent libraries.


````sh
root
 |-- src
 |    |-- apple
 |    |    | -- package.json
 |    |    | -- jest.config.js
 |    |
 |    |-- banana
 |         | -- package.json
 |         | -- jest.config.js
 |
 |-- lib
 |    |-- broccoli
 |    |    | -- package.json
 |    |    | -- jest.config.js
 |    |
 |    |-- carrot
 |         | -- package.json
 |         | -- jest.config.js
 |
 | -- package.json
 | -- jest.config.js
````
Tests are run using the following at the root level:
````sh
$ npm run test
$ npm run test:apple
$ npm run test:banana
$ npm run test:broccoli
$ npm run test:carrot
$ npm run test:src
$ npm run test:lib
````
Which use these commands:
````sh
"test": "jest --projects **/src/** **/lib/**",
"test:apple": "jest --projects **/src/apple",
"test:banana": "jest --projects **/src/banana",
"test:broccoli": "jest --projects **/lib/broccoli",
"test:carrot": "jest --projects **/lib/carrot",
"test:lib": "jest --projects **/lib/**"
"test:src": "jest --projects **/src/**",
````
Alternatively tests can be run at the individual application/library level:
````sh
/src/apple/$ npm run test
````