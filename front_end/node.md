# Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine.
# 1. modules: fs, path, querystring, http
# 2. Modularization
  ## 2.1 CommonJS
  ```Javascript
    const var = 123
    const fun = (a, b) => {
      return a+b
    }
    module.exports = {
      expName: var
      expFun: fun
    }
    const impJs = require('./file.js')
  ```
  ## 2.2 ECMAScript
  Need to add {'type':'module'} into file package.json
  ```Javascript
    const var = 123
    const fun = (a, b) => {
      return a+b
    }
    export default = {
      expName: var
      expFun: fun
    }
    import impJs from './file.js'
    // or export and import as needed, use the same variable name
    export const expVar = 123
    import {expVar} from './file.js'
  ```
# 3 NPM
  ```shell
    //create standard package.json file
    npm init -y
    //add other package to current project
    npm i package_name
    //delete a package
    npm uni package_name
    //add all dependent packages
    npm I
    //install global package -g
    npm i nodemon -g
  ```
# 4 web suit package Express
  ```Javascript
    const express = require('express')
    const server = express()
    //request for root address
    server.get('/', (req, res)=>{
      res.send('Hello world')
    })
    //all other requests
    server.get('*', (req, res)=>{
      res.status(404)
      res.send('Not exist')
    })
  ```
# 5 CORS
  install cors package
  ```Shell
    npm i cors
  ```
  use cors
  ```Javascript
    const express = require('express')
    const cors = require('cors')
    const server = express()
    server.use(cors())
    //request for root address
    server.get('/', (req, res)=>{
      res.send('Hello world')
    })
  ```
