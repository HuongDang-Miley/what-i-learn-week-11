# Tuesday
## Method
A method is a function that's property on an object. In this eg. bark and speak is methods
~~~
const human = function(myName, MyAge, MyNationality){
    return{
        name: myName,
        age: MyAge,
        isVietnamese: MyNationality,
        speak: function() {
            return `My name is ${this.name}`          
        }
    }
}
~~~
in example above. human.speak() is a method
## this
* a short way of my current object.
* is only used inside the object.
~~~
const newPerson = function (name, age, single) {
    return {
        name,
        age,
        single,
        marry: function(newPerson) {
            this.single = false. //-> this.single refers to single property of current newPerson
            newPerson.single = false //-> newPerson.single refer to single property of another newPerson
        },
        divorce: function(newPerson) {
            this.single = true
            newPerson.single = true
        }
    }
}

~~~
# Wednesday
## Ray()
* Use pascal case aka capital the first letter
* A function create an object and has multiple methods in it
* Any variable is assigned to a Ray will has all the key and method of that ray
* Array is object with hidden key. In another word key is the index

~~~
const Ray = function (){
    return {
     length: 1
    } 
 
 }
 const num = Ray()
 num; //-> {length: 1}
~~~
# Thursday
## filter():
* From the original array, return a new array, in which every new element passes the helper function.
* Helper function MUST return a boolean.
<br/>
Eg: return a new array with only even number:
~~~
const nums = [1, 2, 3, 4, 5]
~~~

Helper function: check if a number is even
~~~
const isEven = function (num) {
    return num % 2 === 0
}
~~~
Manually: Use manualFilter function
~~~
const manualFilter = function (array, func) {
    const newArr = []
    for (const element of array) {
        if (func(element) === true)
        newArr.push(element)
    }
    return newArr
}

const onlyEven1 = manualFilter(nums, isEven)
onlyEven1 //-> [2,4]
~~~
filter(): A built-in method for array, still require helper function, but don't need manualFilter function
~~~
const onlyEven2 = nums.filter(isEven)
onlyEven2 //-> [2,4]
~~~
Note: Way to use helper function return false.
Eg: Return odd number only, use isEven()
~~~
const onlyOdd = nums.filter(function(num){
    // return isEven(num) === false
    // or
    return !isEven(num)
})
onlyOdd; //-> [1,3,5]
~~~

## map()
* Create a new array from the original array. Every new element is transformed by a helper function
<br/>
Eg: make a new array in which each element is the length of every word in words array
~~~
const words = ['hello', 'hi']
~~~
Helper function: A function transform ONLY one element in the array
~~~
const length = function (str) {
    return str.length
}
~~~
Solve us manual mapping
~~~
const manualMap = function (arr, func) {
    const newArr = []
    for (const element of arr) {
        const transformedElement = func(element)
        newArr.push(transformedElement)
    }
    return newArr
}

const wordLength1 = manualMap(words, length)
wordLength1 //-> [5,2]
~~~

Solve use map() method
~~~
const wordLength2 = words.map(length)
wordLength2 //-> [5,2]
~~~

## forEach()
* Do something to every element in an array (aka run a helper function on every element in that array)
* DOES NOT return a new array aka. doesn't show anything.
* Usage: write and read from file, print number on website, etc (not as use as often as map)
<br/>
Eg: capitalize every word in an array. Do not return any new array

~~~
const words = ['hello', 'hi']
~~~
Helper function: capitalize a string

~~~
const capitalize = function(str) {
    console.log(str.toUpperCase())
}
~~~

Use manual way
~~~
const manualForEach = function (arr, func) {
    for (const element of arr) {
        func(element) //-> HELLO, HI
    }
}

const printCap1 = manualForEach(words, capitalize)
printCap1; // undefined because helper function does not return anything
~~~
Use forEach()
~~~
const printCap2 = words.forEach(capitalize)
printCap2;  // undefined because helper function does not return anything
~~~
