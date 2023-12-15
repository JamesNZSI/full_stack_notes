# 1. main idea
  typescript: javascript with data type
  it will check the data types and alert you while coding.
  typescript will compile a .ts file and generate a .js file containing the code converted into raw javascript
# 2. basic grammar
  ## 2.1 use : number after variable to indicate the data type
  ```Typescript
  let n : number = 1
  ```
  ## 2.2 use : number[] indicate a list of number, use : Array indicate a list of number as well
  let numbers : number[] = [1, 2, 3]
  let numbers : Array = [1, 2, 3]
  ## 2.3 use : (number | null) for combined data type
  let n : (number|null) = null
  n = 1
  ## 2.4 type alias
  type NewType = string | number
  let number_string : NewType = 123
  let number_strings : NewType [] = [123, '11', '22', 456]
# 3. types in function 
  ## 3.1 could be without explicit return data type, the compiler will it
function fn(n:number, b:string):string{
  return number+string
}
  ## 3.2 declare function
const fn = function fn(n:number, b:string):string{
  return number+string
}
  ## 3.3 arrow function
const arr = (n:number, b:string):string => {
  return number+string
}
  ## 3.4 function type only used with declare function and arrow function
```typescript
  type FnType = (n:number, s:string) => string
  const fn:FnType = (a, b) => {
    return a+b
  }
```
