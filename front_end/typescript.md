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
  // another way to define function type
  exist(place:string):void
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
## 4.1 Optional property in an object, use ? to indicate a property is optional
```Typescript
type ObjType = {
  name:string,
  age?:number,
  gender:string,
  action?:(move:string) => string
}
// create an instance of ObjType without age property
let obj:ObjType = {
  name:'Indiana',
  age:70
  gender:'Male'
}
// invoke optional function
obj.action && obj.action('run')
obj.age && obj.age.toString()
//optional chaining, works on any may not exist property
obj.age?.toString()
obj.action?.()
```
# 5. Interface
define the structure(the restriction of properties) of a type of objects, similar to the Interface in Java.
```Typescript
interface IPerson = {
  name:string
  height:number
}
// only have the properties in the interface
const person: IPerson = {
  name:'Indi',
  height:190
}
```
## 5.1 interface extend
```Typescript
interface IStudent extends IPerson = {
  profession:string
}
const s: IStudent = {
  name:'Indiana',
  height:190,
  profession:'student'
}
//use type to implement similar function as interface extend
//use & symbol, the difference between | and & is easy to understand
type TPerson = {
  name:string
  height:number
}
type TStudent = {
  profession:string
} & TPerson
const st: TStudent = {
  name:'Indiana',
  height:190,
  profession:'student'
}
```
# 6 tuple 
constrain array length and item types
```Typescript
let arr: [number, string] = [190, 'Indi']
```
# 7 Object literal
can be used to represent enumerate type
```Typescript
type Gender = 'Male' | 'Female'
```
# 8 Enumerate
use object literal is more common
```Typescript
//use indices 0, 1... to represent the item value
enum Gender{
  Male,
  Female
}
function hairStyle(gender: Gender){
  console.log(gender + ' hair styles')
}

hairStyle(Gender.Male)
```
```Typescript
//use specified values, the implicit value will be one plus the previous one
enum Gender{
  Male = 1,
  // will be the same as Female = 2
  Female
}
// or
enum Gender{
  Male = 'male',
  Female = 'female'
}
```
