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


