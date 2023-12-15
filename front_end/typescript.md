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
  ```Typescript
  let numbers : number[] = [1, 2, 3]
  let numbers : Array = [1, 2, 3]
  ```
  ## 2.3 use : (number | null) for combined data type
  ```Typescript
  let n : (number|null) = null
  n = 1
  ```
  ## 2.4 type alias
  ```Typescript
  type NewType = string | number
  let number_string : NewType = 123
  let number_strings : NewType [] = [123, '11', '22', 456]
  ```
# 3. types in function 
  ## 3.1 could be without explicit return data type, the compiler will it
  ```Typescript
  function fn(n:number, b:string):string{
    return number+string
  }
  ```
  ## 3.2 declare function
  ```Typescript
const fn = function fn(n:number, b:string):string{
  return number+string
}
  ```
  ## 3.3 arrow function
  ```Typescript
  const arr = (n:number, b:string):string => {
    return number+string
  }
  ```
  ## 3.4 function type only used with declare function and arrow function
```typescript
  type FnType = (n:number, s:string) => string
  const fn:FnType = (a, b) => {
      return a+b
  }
```
  ## 3.5 optional variable use ? in the function variable list
  ```Typescript
  const fn = (first_name:string, second_name?:string) => {
      if (first_name && second_name)
      console.log(fisrt_name, second_name)
  }
  fn('Indi', 'Jones')
  fn('Indi')
  ```
# 4. Object
```Typescript
let obj:{
  name:string,
  age:number,
  gender:string,
  action:(move:string) => string
} = {
  name:'Indi',
  age:70,
  gender:'Male',
  action(move){
    console.log('take an action of ' + move)
  }
}
```
or
```Typescript
type ObjType = {
  name:string,
  age:number,
  gender:string,
  action:(move:string) => string
}
// create an instance of ObjType
let obj:ObjType = {
  name:'Indi',
  age:70,
  gender:'Male',
  action(move){
    console.log('take an action of ' + move)
  }
}
```
