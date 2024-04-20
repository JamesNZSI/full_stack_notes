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
  ```
