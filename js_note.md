# Combine of string

const name = 'John';
const age = 30;

console.log('My name is ' + name + 'and I am ' + age); // old fasion
console.log(`My name is ${name}, and I am {age}`)


# Manipule str

const s = 'Hello World';

s.length == 11

s.toUpperCase()

s.toLowerCase()

s.substing(0, 5) == 'Hello'

s.split(' ') == ['hello', 'world']
s.split will create a array


# Arrays

const number = new Array(1,2,3); //old fasion

const fruit = ['apples', 'oranges', 1, null, true ];

fruits[5] = 'grapes'; //add 5th

fruits.push('mangos'); //add to the end

fruit.unshift('pears'); //add to beginning

fruits.pop(); //delete the last one

Array.isArray(fruit) //true

fruits.indexOf('oranges') //2, not from 0


# Object

const person = {
    firstName: 'John',
    lastNamee: 'Doe',
    age: 30,
    hobbies: ['music', 'movies', 'sports']
    address:{
        street: '50 main st',
        city: 'NY',
        state: 'MA'
    }
}

person.hobbies[1] == 'movies';
person.address.city == 'NY';

const {firstName, lastName, address: {city}} = person;

person.email = 'john@gg.com' // add email to person


# Objets in Array

const todos = [
    {
        id: 1,
        text: '222',
        isCompleted: true
    },
    {
        id: 2,
        text: ' bose',
        isCompleted: true
    },
    {
        id: 3,
        text: 'ye',
        isCompleted: false
    },
];

todos[1].text == 'bose';

const todoJson = JSON.stringify(todos); // transform array to JSON


# For

for (let i = 0; i < 10; i++) {
    ...
}

for (let todo of todos) {
    todo.text
}


# ForEach, map, filter

todos.forEach(function(todo) {
    todo.text
});

const todoText = todos.map(function(todo) {
    return todo.text;
});

const todoCompleted = todos.filter(function(todo) {
    return todo.isCompleted === true
}).map(function(todo) {
    return todo.text;
});


# Conditions

const color = x > 10 ? 'red' : 'blue';

switch(color) {
    case 'red':
        do stuff;
        break;
    default:
        do stuff;
        break;
}


# Functions

function addNums(num1 = 1, num2 = 1) {
    const num3 = num1 + num2;
    return num3
}

## Arraw functions!

const addNum = (num1 = 1, num2 = 1) => {num1 + num2}

todos.forEach((todo) => console.log(todo.text))


# Constructor function

// ES5
function Person(firstName, lastName, dob) {
    this.firstName = firstName;
    this.lastName = lastName;
    this,dob = new Date(dob);
    this.getBirthYear = function() {
        return this.dob.getFullYear()
    }
    this.getFullName = function() {
        return `${this.firstName} ${this.lastName}`;
    }
}

Person.prototype.getBirthYear = function() {
    return this.dob,getFullYear();
}


// ES6
// we create a class

class Person {
    constructor(firstName, lastName, dob) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.dob = new Date(dob);
    }
    getBirthYear() {
        return this.dob.getFullYear();
    }
}

// Instantiate object
const person1 = new Person('John', 'Doe', '4-3-1980');

console.log(person2.dob.getFullYear()); // 1980


# DOM

window is the highest Objet
document object

// Single element
document.querySelector('h1');//always select the fist one
document.querySelector('.container');
document.querySelector('#id');

// Multiple element
document.querySelectorAll('.item')

// loop
const items = document.querySelectorAll('.item')
items.forEach((item) => console.log(item));

items.remove(); // delete all items
items.lastElementChild.remove(); // delete last one
items.firstElementChild.textContent = 'Hello'; // same to innerText
items.children[1].innerText = 'Brad';
items.lastElementChild.innerHtml = '<h1>hi</h1>'

const btn = document.querySelector('.btn');
btn.style.backgroud = 'red';

btn.addEventListener('click', (e) => {
    e.preventDefault(); // prevent default behavior, bcs if it is a submit btn, console log will just flash for 0.0001s
    console.log('click');
    e.target //select whole tag
    e.target.id //select id
    document.querySelector('#my-form').style.background = '#ccc';
    document.querySelector('body').classList.add('bg-dark');
    docuemnt.querySelector('.items').lastElementChild.innerHTML = '<h1>hello</h1>'
});

myform.addEventListener('submit', onSubmit);

function onSubmit(e) {
    e.preventDefault();

    if(nameInput.value === '' || emailInput.value === '') {
        msg.classList.add('error')
        msg.innerHTML = 'Please enter fields';
        setTimeout(() => msg.remove(), 3000);
    } else {
        const li = document.creatElement('li');
        li.appendChild(document.createTextNode(`${} : ${}`));
        userList.appendChild(li)
        console.log('sended');
        nameInput.value = '';
        emailInput.value = '';
    }
}
