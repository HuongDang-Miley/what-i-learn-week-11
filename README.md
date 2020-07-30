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


Eg: return a new array with only even number:
~~~
const nums = [1, 2, 3, 4, 5]
~~~

Helper function:
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
* Note: Way to use helper function return false.
Eg: Return odd number only, use isEven()
~~~
const onlyOdd = nums.filter(function(num){
    // return isEven(num) === false
    // or
    return !isEven(num)
})
onlyOdd; //-> [1,3,5]
~~~

