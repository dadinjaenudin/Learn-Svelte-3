---
tags: Web/Mobile Programming
---

# Learn Svelte.js 3

> This is about learning Svelte if you are not familiar with Svelte please go to [https://svelte.dev](https://) I hope you will enjoy it as I do. 

### :memo: Where do I start?
1. Start learn svelte locally go to [https://svelte.dev](https://) and see the quickstart guide.

```javascript=1
npx degit sveltejs/template my-svelte-project
# or download and extract 
cd my-svelte-project

npm install
npm run dev
```
3. Start learn svelte Online go to [https://stackblitz.com/](https://) choose Svelte to start new editor.
![](https://i.imgur.com/6UPPJw0.png)


### :memo: Chapter 1 - Up and Running with Svelte.js

* 01 - Variable and scope
```javascript=1
var author ="Dadin Jaenudin"
function getName(){
    var author = "Zaky Altamish"
    // Local Scope
    console.log('Inside function author name is ', author) 
}
// Global Scope
console.log("Outside function author is",author)
getName()
```

* 02 - Hoisting
```javascript=1
function getName(){
    return name
    var name = "Dadin jaenudin"
}
// undefined
console.log(getName())
```

* 03 - let keyword
```javascript=1
// global scope
let globalName = "Dadin Jaenudin"
if (true) {
    // Local scope only accessible inside if statement
    let localName= "Zaky altamish"
    console.log("localname ", localName)
    console.log("globalname, ", globalName)
}
console.log("globalname,",globalName)
//this will get error localName is not defined
console.log("localname ",localName)
```
```javascript=1
// Re-declaration of let variable
var x =20
var x =30
console.log(x)

let y = 50
// this will get error 
// (plugin commonjs) SyntaxError: Identifier 'y' has already been declared
let y = 60
console.log(y)
```

* 04 - const keyword
```javascript=1
// Assingment to constant keyword
const name ="Dadin Jaenudin"
console.log(name)

// this will get error 
// Uncaught TypeError: Assignment to constant variable.
name = "Zaky Altamish"

```
```javascript=1
// Re-declaration to constant keyword
const name = "Dadin Jaenudin"
// SyntaxError: Identifier 'name' has already been declared (3:6)
const name = "Zaky Altamish"
```

```javascript=1
// const Keyword with Object
const program = {
    "name":"Svelete 2"
}
console.log("Program Name :",program.name)
program.name="Svelte 3"
console.log("Program Name :", program.name)
program.name = {}
console.log("Program Name :",program.name)
```

* 05 - Template literals
```javascript=1
// Template literals in ES5
var text = 'Hello Dadin Jaenudin \n' + 'Welcome to Svelte 3'
console.log(text)
```
![](https://i.imgur.com/Z2qaFGS.png)

```javascript=1
// Template literals in ES6
var text = `Hello Dadin
Welcome to Svelte 3`;
console.log(text)
```
![](https://i.imgur.com/542HhfH.png)


* 06 - string interpolation
```javascript=1
// String Interpolation in ES5
var a = 10
var b = 20
let str = "The sum of " + a + " and " + b + " is " + (a+b) + ".";
console.log(str)
```
![](https://i.imgur.com/Tq4sWqV.png)

```javascript=1
// String Interpolation in ES6
var a = 20
var b = 20
let str = `The sum of ${a} and ${b} is ${a+b} .`
console.log(str)
```
![](https://i.imgur.com/IQjqZeq.png)

* 07 - Arrow function
```javascript=1
// Arrow Function
const getName = () => "Dadin Jaenudin"; // use single body when we have single statement
console.log(getName());
```

```javascript=1
// Multiline Arrow function
const getPrice = (price,discount) => {
    let totalValue = price - price * (discount / 100);
    return totalValue;
}
console.log(getPrice(10,20));
```
* 08 - Spread operataor
```javascript=1
// Spread Operator Array Concatination
const arr1 = [1,2,3,4,5]
const arr2 = [6,7,8,9,10]
const totalArr = [...arr1, ...arr2]
console.log(totalArr)
```
![](https://i.imgur.com/k8yFzBm.png)

```javascript=1
// Spread Operator in a function call
function totalSum(num1,num2,num3,num4){
    console.log(num1+num2+num3+num4)
}
let numbers = [1,2,3,4]
totalSum(...numbers)
```

* 09 - Rest operator
```javascript=1
// Rest Operator us in Arguments
function calculateArgLength(...args) {
    console.log("Argumens :",args)
    console.log("Lenght   :",args.length)
}
calculateArgLength("1","2","3","4")
calculateArgLength("Dadin","Zaky","Amel")
```
![](https://i.imgur.com/8Vl2Nu8.png)

```javascript=1
// Rest operatior for assigning the rest of the items of array
let arr = ["Svelte", "React", "Vue", "Angular"]
let [programming1, programming2, ...others] = arr
console.log("Programming 1 :",programming1)
console.log("Programming 2",programming2)
console.log("Others :", others)
```
![](https://i.imgur.com/w3aSo4d.png)

* 10 - Destructuring
```javascript=1
// De-Structuring of Array
let arr = ["Svelte", "React", "Vue", "Angular"]
let [programming1, programming2, , programming4] =arr
console.log("Programming 1 : ", programming1)
console.log("Programming 2 : ", programming2)
console.log("Programming 4 : ", programming4)
```
![](https://i.imgur.com/kPGSfhe.png)

```javascript=1
// De-Structuring of Object
let obj = {
    name : "Dadin",
    age  : 30,
    role : "Developer"
}
let {name, age} = obj
console.log("Name : ",name)
console.log("Age  : ",age)
```
![](https://i.imgur.com/7WanD1U.png)

```javascript=1
// destructuring to get remaining properties of an array
let obj = {
    name: "Nikhil",
    age: 29,
    role: "developer",
    language: "Svelte"
}
let { name, age, …other } = obj
console.log(other)
```
![](https://i.imgur.com/05O6MyE.png)


* 11 - setup using degit
```javascript=1

npx degit sveltejs/template learn-svelte3
# or download and extract 
cd learn-svelte3

npm install
npm run dev

In Chapter 2 we will edit src\App.svelte in your project
```

### :memo: Chapter 2 - Create and Edit component

* 01 - First Component
```javascript=1
<script>
	let name = "Dadin Jaenudin"
</script>

<style>
	h1{
		color: red	
	}
</style>

<h1> Hello {name} </h1>
```
* 02 - String Methods
```javascript=1
<script>
	let str = "Hello SVELTE world";
</script>

<div>Actual String : {str}</div>
<div>Uppercase String :{str.toUpperCase()}</div>
<div>Lowercase String :{str.toLowerCase()}</div>
<div>Sub-string       :{str.substr(0,12)}</div>
```
![](https://i.imgur.com/9FdXmiQ.png)

* 03 - Date Methods
```javascript=1
<script>
	var today = new Date();
</script>
<h4>ISO time format : {today.toISOString()} </h4>
<h4>UTC time format : {today.toUTCString()}</h4>
<h4>Local date format : {today.toLocaleString()}</h4>
<h4>Curreng date format (DD/MM/YYYY)
{today.getDate()}/{today.getMonth()+1}/{today.getFullYear()}
<h4>
```
![](https://i.imgur.com/OdONL4A.png)

* 04 - Src Attributes
```javascript=1
<script>
let url = 'https://dummyimage.com/150/09f.png/fff';
</script>
<img src={url}>
```

* 05 - Alt Attributes
```javascript=1
<script>
     let url = '';
</script>
<img src={url} alt="image of svelte">

```
* 06 - Disabled Attributes
```javascript=
<script>
	let isDisable=true
</script>
<button>Enabled Button</button>
<button disabled={isDisable}>Disabled Button</button>
```
![](https://i.imgur.com/1tgb8Cx.png)

* 07 - Title Attributes
```javascript=
<script>
	let author = 'Author of this book is Nikhil karkra';
</script>
<h1 title={author}>Learn Svelte 3</h1>

```
* 08 - Svelte css demo
```javascript=
<style>
  h1 {
    text-align: center;
    padding: 1em;
    color: orange;
    margin: 0 auto;
    background: #5c2e86;
  }
  .green {
    color: green;
    text-align: center;
  }
  p {
    font-size: 20px;
    color: red;
    text-align: center;
  }
  :global(body) {
    /* this will apply to <body> */
    background: yellow;
  }
</style>

<div>
  <h1>Svelte styles with CSS</h1>
  <p>I am enjoying learning</p>
  <p class="green">Svelte css is scoped by default</p>
</div>

```
* 09 - Svelte css in js demo
```javascript=
npm install emotion
```

Create file src\styles.js
```javascript=
import emotion from "emotion/dist/emotion.umd.min.js";
const { css } = emotion;

const ORANGE = "#ffa500";
const RED = "red";
const WHITE = "white";

export const heading = css`
  background-color: ${ORANGE};
  color: ${WHITE};
`;

export const Button = css`
  border: none;
  color: white;
  padding: 14px 28px;
  cursor: pointer;
  background-color: ${ORANGE};
  &:hover {
    background-color: ${RED};
  }
`;

```

src\App.svelte
```javascript=
<div>
  <h1 class={heading}>My style is from CSS-in-JS</h1>
  <button class={Button}>Hover over me</button>
</div>

```

### :memo: Chapter 3 - Reactive Declaration

* 01 - Without Reactive
```javascript=
<script>
	let counter = 0;
	// Without reactive
	let counterSquare = counter*counter;
	function clickHandler(){
		counter += 1
	}
</script>
<button on:click={clickHandler}>Click me</button>
<div>Square of {counter} is {counterSquare}</div>
<div>You have clicked {counter} times</div>

```
* 03 - Reactive Declaration
```javascript=1
<script>
	let counter = 0;
	// Reacative declaration
	$:counterSquare = counter*counter;
	function clickHandler(){
		counter += 1
	}
</script>
<button on:click={clickHandler}>Click Me</button>
<div>Square of {counter} is {counterSquare}</div>
<div>You have clicked {counter} times</div>
```
![](https://i.imgur.com/gcka6nI.png)

* 04 - Reactive Statement

```javascript=1
// Normal Reactive
<script>
	let counter = 0;
	$:counterSquare = counter*counter;
	function clickHandler(){
		counter += 1
	}
</script>
<button on:click={clickHandler}>Click me</button>
<div>Square of {counter} is {counterSquare}</div>
<div>You have clicked {counter} times</div>
```
```javascript=
// Reactive Conditionl Statement
<script>
	let counter = 0;
	$:if(counter%2 === 0){
		console.log('Counter is even with value ',counter)
	} else {
		console.log('Counter is even with value', counter)
	}
	function clickHandler(){
		counter += 1
	}
</script>
<button on:click={clickHandler}>Click Me</button>
```
```javascript=
// Reactive Multiple statement
<script>
	let counter = 0;
	// Reactive multiple statement
	$:{
		console.log('Your counter value is')
		console.log(counter)
       }
       
	function clickHandler(){
		counter += 1
	}
</script>
<button on:click={clickHandler}>Click me</button>
<div>You have clicked {counter} times</div>

```

* 05 - Reactive Array
```javascript=
// Reactive with immutable array method

<script>
  let evenNumber = [0, 2, 4, 6, 8, 10];
  function clickHandler() {
	// find last number value in array + 2  
	let newNumber = evenNumber[evenNumber.length - 1] + 2;
	console.log("newNumber ",newNumber)
	// Inisialisasi evenNumber with value NewNumber
	evenNumber = [...evenNumber, newNumber]; // with assignment
	console.log("evenNumber ", evenNumber)
  }
</script>

<button on:click={clickHandler}>Add even number</button>
<h1>{evenNumber}</h1>

```
![](https://i.imgur.com/WMexT6A.png)

```javascript=
// Reactive with mutable array method
<script>
	let evenNumber = [0,2,4,6,8,10];
	function clickHandler(){
		// get last value in array
		let newNumber = evenNumber[evenNumber.length-1]+2
		// just assignment to evenNumber but will not display 
		evenNumber.push(newNumber)
		console.log('evenNumber ',evenNumber)
	}
</script>

<button on:click={clickHandler}>Add even number</button>
<h1>{evenNumber}</h1>

```
![](https://i.imgur.com/sUzVVjM.png)


* 06 - Import and export in javascript
```javascript=
// Default export
export default {
    programmingList : ['Svelte', 'React', 'Vue', 'Angular'],
    helloSvelteHandler : () => {
        return "Hello Svelte"
    },
    bookDetails : {
        name: 'Svelte 3',
        author: 'Nikhil Karkra'
    }
}

// Import file
import Utilities from 'fileThree.js'
console.log(Utilities)

// Export Individually
export const programmingList = ['Svelte', 'React', 'Vue', 'Angular']
export const helloSvelteHandler =()=>{
    return "Hello Svelte"
}
export const bookDetails = {
    name: 'Svelte 3',
    author: 'Nikhil Karkra'
}

// Export together
const programmingList = ['Svelte', 'React', 'Vue', 'Angular']
const helloSvelteHandler = () => {
    return "Hello Svelte"
}
const bookDetails = {
    name: 'Svelte 3',
    author: 'Nikhil Karkra'
}

export { programmingList, helloSvelteHandler, bookDetails }

// Normal Import
import { programmingList, helloSvelteHandler, bookDetails } from 'fileOne.js'
console.log(programmingList)
console.log(helloSvelteHandler())
console.log(bookDetails)

```

* 07 - Svelte component nesting
```javascript=
// App.svelte
<script>
	import Child from './Child.svelte';
</script>
<h3>Hey, I am from Parent component</h3>
<Child/>

// Child.svelte
<h3>Hello, I am from Child component</h3>

```
![](https://i.imgur.com/DJqeZuj.png)

* 08 - Parent to child component communication
##### With default props
```javascript=

// App.svelte
<script>
	import Card from './Card.svelte';
</script>
<Card />

// Card.svelte
<script>
  export let imageUrl = 'https://i.pravatar.cc/200?u=a042581f4e290267047';
  export let name = 'John Smith';
  export let role = 'Developer';
</script>
<div class="card">
  <img src={imageUrl} alt={name}>
  <h1>{name}</h1>
  <p>{role}</p>
</div>
<style>
.card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    max-width: 200px;
    font-family: arial;
    padding: 10px;
    text-align: center;
    margin:auto
 }
 p{
   color: grey;
   font-size: 18px;
  }
 img{
    width:100%
  }

</style>

```
##### With  props
```javascript=
// App.svelte
<script>
	import Card from './Card.svelte';
</script>
<Card
     imageUrl ='https://i.pravatar.cc/200?u=a042581f4e290267048'
     name='Nikhil karkra'		
     role='Full Stack developer'		
/>

// Card.svelte
<script>
    export let imageUrl;
    export let name;
    export let role;
</script>
<div class="card">
  <img src={imageUrl} alt={name}>
  <h1>{name}</h1>
  <p>{role}</p>
</div>
<style>
.card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    max-width: 200px;
    font-family: arial;
    padding: 10px;
    text-align: center;
    margin:auto
 }
 p{
   color: grey;
   font-size: 18px;
  }
 img{
    width:100%
  }

</style>

```

### With spread props
```javascript=
// App.svelte
<script>
    import Card from './Card.svelte';
    let user ={
        imageUrl :'https://i.pravatar.cc/200?u=a042581f4e290267048',
        name:'Nikhil karkra',		
        role:'Full Stack developer'
    } 

</script>
<Card imageUrl={user.imageUrl} name={user.name} role={user.role}/>
<Card {...user}/>

// Card.svelte
<script>
  export let imageUrl = "https://i.pravatar.cc/200?u=a042581f4e290267047";
  export let name = "John Smith";
  export let role = "Developer";
</script>

<style>
  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    max-width: 200px;
    font-family: arial;
    padding: 10px;
    text-align: center;
    margin: auto;
  }
  p {
    color: grey;
    font-size: 18px;
  }
  img {
    width: 100%;
  }
</style>

<div class="card">
  <img src={imageUrl} alt={name} />
  <h1>{name}</h1>
  <p>{role}</p>
</div>
```

### :memo: Chapter 4 - If, Each 
#### 01 - If in JS

```javascript=
<style>
.btn {
    border: none;
    color: white;
    padding: 14px 28px;
    font-size: 16px;
    cursor: pointer;
    background: #ff3e00;
}
</style>
<script>
	let str = 'Please sign in'
	let status = "sign-out"
	let btn = 'Sign in'
	$: if (status === 'sign-in') {
		str = 'Signed in successfully'
		btn = 'Sign out'
	}
	function loginHandler(){
		status = 'sign-in'
	}
</script>
<h4>{str}</h4>
<button on:click={loginHandler} class="btn">{btn}</button>

```

#### 02 - If in HTML
```javascript=
<style>
.btn {
    border: none;
    color: white;
    padding: 14px 28px;
    font-size: 16px;
    cursor: pointer;
	background:#ff3e00;
}
</style>
<script>
	 let showText = false
	 function showHandler(){
		 showText = true
	 }
</script>
<button class="btn" on:click={showHandler}>Click me to show text</button>
{#if showText}
 <h4>Hurray!! you have successfully run the if block in markup</h4>
{/if}

```
#### 03 - Else in JS
```javascript=
<style>
	.btn {
    border: none;
    color: white;
    padding: 14px 28px;
    font-size: 16px;
    cursor: pointer;
     background:#ff3e00;
}
</style>
<script>
	let status = false
	let str =''
	$:if(status){
		str = 'Hurray !! you are Authorized for this application'
	} else {
		str = 'You are not Authorized for this application'
	}
	function statusHandler(){
		status = true
	}
</script>
<h4>{str}</h4>
{#if !status}
  <button class="btn" on:click={statusHandler}>Click here to authorized</button>
{/if}

```

#### 04 - Else in HTML
```javascript=
<script>
  let status = false;
  function ageHandler() {
    status = !status;
  }
</script>

<style>
  .btn {
    border: none;
    color: white;
    padding: 14px 28px;
    font-size: 16px;
    cursor: pointer;
    background: #ff3e00;
  }
  h5 {
    color: red;
  }
</style>

{#if status}
  <h4>Welcome back to the application</h4>
  <h5>You have 10 new messages</h5>
  <button class="btn" on:click={ageHandler}>Logout</button>
{:else}
  <h4>You Must login to see the application</h4>
  <button class="btn" on:click={ageHandler}>login</button>
{/if}

```

#### 05 - If else in JS
```javascript=
<script>
	let age = 10
	let status = ''
	$:if(age >19){
		status = 'Adult'
	} else if(age >10 && age <19){
			status = 'Teenager'			
	} else {
		status = 'Child'
	}
</script>
<h4>My age is {age} and my status is {status}</h4>

```

#### 06 - If Else in HTML
```javascript=
<script>
  let age = 15;
</script>

{#if age > 19}
  <h4>Your age is {age} and you are Adult</h4>
{:else if age > 10 && age < 19}
  <h4>Your age is {age} and you are Teenager</h4>
{:else}
  <h4>Your age is {age} and you are Child</h4>
{/if}

```

#### 07 - Ternary operator
```javascript=
<style>
.btn {
  border: none;
  color: white;
  padding: 14px 28px;
  cursor: pointer;
}
.active {background-color: #4CAF50;} 
.inactive {background-color: #f44336;} 
</style>
<script>
	let isActive = true
</script>
<button class='btn {isActive ? 'active':'inactive'}'>Button</button>

```

#### 08 - Each loop without keyed
```javascript=
<script>
	let movies = [
		'The Shawshank Redemption',
		'The Godfather',
		'The Dark Knight',
		'12 Angry Men',
		'Schindler List'
	]
</script>
<h3>Top 5 Movies based on IMDB rating.</h3>
{#each movies as movie, index}
<p>{index+1} - {movie}</p>
{/each}
```
![](https://i.imgur.com/K3UTxi5.png)

#### 09 - Each loop with keyed
``` javascript
// App.svelte
<script>
  import Movie from "./Movie.svelte";
  let moviesList = [
    { id: 1, name: "The Shawshank Redemption" },
    { id: 2, name: "The Godfather" },
    { id: 3, name: "The Dark Knight" },
    { id: 4, name: "12 Angry Men" },
    { id: 5, name: "Schindler List" }
  ];
  function deleteHandler() {
    moviesList = moviesList.slice(1);
  }
</script>

<button on:click={deleteHandler}>Delete Movie from start</button>

<!--{#each moviesList as item}-->
{#each moviesList as item (item.id)}
  <Movie data={item} />
{/each}

// Movie.svelte
<script>
  export let data;
  const movie = data;
</script>

<p>{movie.name}</p>

```
![](https://i.imgur.com/Nbqa0eD.png)

### :memo: Chapter 5 - Event
#### 01 - Click Event
```javascript=
<script>
	let counter = 0
	function countHandler(){
		counter++
	}
</script>

<h4>Counter: {counter}</h4>
<button on:click={countHandler}>
	Click here to Increment the counter
</button>

```
![](https://i.imgur.com/yhf0FsL.png)

#### 02 - Keyup Event
```javascript=
<script>
	let name=""
	function inputHandler(event){
		name=event.target.value
	}
</script>
{#if name.length>0}
<h3>My name is {name}</h3>
{/if}
<input type="text" on:keyup={inputHandler} placeholder="Enter you Name"/>

```
![](https://i.imgur.com/5ZGnS9P.png)

#### 03 - Change Event
```javascript=
<script>
	let country = 'Australia'
	function changeHandler(event){
		country = event.target.value
	} 
</script>
{#if country}
<h4>You have selected the {country}</h4>
{/if}
<select on:change={changeHandler}>
	<option value="Australia">Australia</option>
	<option value="India">India</option>
	<option value="United States">United States</option>
</select>

```
![](https://i.imgur.com/PX1c8Vr.png)

#### 04 - Focus blur Event
```javascript=
<script>
	let STATUS = ''
	function focusHandler(){
		STATUS = 'FOCUS'
	} 
	function blurHandler(){
		STATUS = 'BLUR'
	}
</script>
{#if STATUS === 'FOCUS'}
<h4>Focus triggered</h4>
{:else if STATUS === 'BLUR'}
<h4>Blur triggered</h4>
{:else}
<h4>Click inside the input field to focus</h4>
{/if}

<input type="text" on:focus={focusHandler} on:blur={blurHandler}/>

```
#### 05 - Inline Event
```javascript=
<script>
	let counter = 0
	let name =""
</script>

<!-- Below code is an  example Using inline function without event parameter-->
<h4>Counter: {counter}</h4>
<button on:click={()=>counter++}>
	Click 
</button>

<!-- Below code is an example Using inline function with event parameter-->
<div>
{#if name.length>0}
    <h3>My name is {name}</h3>
{/if}
    <input type="text" on:keyup={(event)=>name=event.target.value} placeholder="Enter you Name"/>
</div>

```
#### 06 - PreventDefault Event Modifier
```javascript=
<script>
function navigationHandler(){
	alert("we have stopped you navigation")
}
</script>
<a href="http://google.com/" on:click|preventDefault={navigationHandler}>Google</a>

```

#### 07 - stopPropagation Event Modifier
```javascript=
<style>
	.innerBox{
		height:20px;
		width:300px;
		background:orange;
		padding:20px
	}
	.outerBox{
		height:100px;
		width:350px;
		background:lightblue;
		padding:20px
	}
</style>
<script>
function outerFunc(){
	alert("outerFunc called")
}
function innerFunc(){
	alert("innerFunc called")
}
</script>
<div class="outerBox" on:click="{outerFunc}">DIV 2
    <div class="innerBox" on:click="{innerFunc}">DIV 1</div>
</div>
```
![](https://i.imgur.com/Anj9ugl.png)

#### 08 - Once Event Modifier
```javascript=
<script>
let counter = 0
function counterHandler(){
	counter++
}
</script>
<h4>Count is {counter}, the result only one click</h4>
<button on:click|once={counterHandler}>
	Click for counter
</button>

```

#### 09 - Child to parent Communication
```javascript=
// App.svelte
<script>
import ModalComponent from './ModalComponent.svelte'
let showModal = false
</script>
<button class="btn success" on:click={()=>showModal = true}>Open Modal</button>
{#if showModal}
<ModalComponent
  headerText="Svelte Modal !!"
  bodyText="This Modal is a child component. Triggered from parent and on click of Close button it will dispatch an event to parent handler and that close the modal"
  on:closeEvent={()=>{showModal = false}}
></ModalComponent>
{/if}

// ModalComponent.svelte
<!------------------>
<!-------Style------>
<!------------------>
<style>
.modal {
    display: block; position: fixed; z-index: 1; padding-top: 100px; 
    left: 0; top: 0; width: 100%; height: 100%; 
    overflow: auto;background-color: rgb(0, 0, 0); background-color: rgba(0, 0, 0, 0.4); 
}
.modal-content {
    background-color: #fefefe; margin: auto;
    padding: 20px;border: 1px solid #888; width: 80%;
}
.btn {
    border: none;color: white; padding: 14px 28px;font-size: 16px;cursor: pointer;
}
.danger { background-color: #f44336;} 
.danger:hover { background: #da190b;}
.text-right { text-align: right; }
</style>

<!------------------>
<!-----Javacript---->
<!------------------>
<script>
 import {createEventDispatcher} from 'svelte';
 const dispatch = createEventDispatcher()
 export let headerText;
 export let bodyText;
 function closeHandler() {
    dispatch('closeEvent')
  }
</script>

<!--------------->
<!-----Markup---->
<!--------------->
<div id="myModal" class="modal">
 <div class="modal-content">
  <header>
   <strong>{headerText}</strong>
  </header>
  <p>{bodyText}</p>
  <footer class="text-right">
 <button class="btn danger" on:click={closeHandler}>Close</button>
 </footer>
 </div>
</div>

```
![](https://i.imgur.com/mLsj80M.png)

#### 10 - Event Forwarding
```javascript=
// App.svelte
<script>
	import Parent from './Parent.svelte';
	function handleMessage(event) {
		alert(event.detail.text);
	}
</script>
<Parent on:message={handleMessage}/>

// Parent.svelte
<script>
	import Child from './Child.svelte';
</script>
<Child on:message/>

// Child.svelte
<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  function msgHandler() {
    dispatch("message", {
      text: "Your event message received!"
    });
  }
</script>

<button on:click={msgHandler}>Forward your event</button>

```

### :memo: Chapter 6 - Text, Checkbox, Radio, Media, Form
#### 01 - Text Input Demo
```javascript=
<script>
	let username = '';
	function inputHandler(event){
		username = event.target.value
	}
</script>
<input type="text" id="username" 
 placeholder ="Type your username" 
 value={username} on:input={inputHandler}
>
<h4>{username}</h4>
```
![](https://i.imgur.com/sjgdLhX.png)

#### 02 - Text Input binding
```javascript=
<script>
	let username = '';
</script>
<input  type="text" id="username" 
		placeholder ="Type your username" 
		bind:value={username}
>
<h4>{username}</h4>

```
![](https://i.imgur.com/zP5jcLd.png)

#### 03 - Number Input Demo
```javascript=
<script>
	function numberHandler(event){
		let data = event.target.value
		console.log(typeof data)
		console.log(data+2)
	}
</script>
<input type="number" id="orignal_price" on:input={numberHandler}>

```
![](https://i.imgur.com/hOXbaOf.png)

#### 04 - Number Input binding
```javascript=
<script>
	let price;
	let discount;
</script>
<h3>Discount Calculator</h3>
<label>Price</label>
<input type="number" id="price" bind:value={price}>
<label>Discount</label>
<input type="number" id="discount" bind:value={discount}>
{#if price && discount}
<h4>After discount, You have to pay {price - (price*(discount/100))}</h4>
{/if}

```
![](https://i.imgur.com/7a4cTGb.png)

#### 05 - Checkbox checked binding
```javascript=
<style>
	button{
		background:orange;
		color:white;
	}
	button:disabled{
		background:#cdcdcd;
	}
</style>
<script>
	let policy_accepted = false;
</script>
<label>
	<input type=checkbox id="policy_accepted" bind:checked={policy_accepted}>
	i have read and accept the privacy policy.
</label>

<button disabled={!policy_accepted}>Submit</button>

```
![](https://i.imgur.com/YWlsOda.png)

#### 06 - Radio checked binding
```javascript=
<script>
  let gender;
  let skills = [];
  let genderList = ["Male", "Female", "Other"];
  let skillList = ["Svelte", "Python", "React", "Angular"];
  let disable = true;
  $: if (gender && skills.length) {
    disable = false;
  }
</script>

<h4>Select you Gender</h4>
{#each genderList as list}
  <label>
    <input type="radio" name="gender" bind:group={gender} value={list} />
    {list}
  </label>
{/each}

<h4>Select you skills</h4>
{#each skillList as skill}
  <label>
    <input type="checkbox" bind:group={skills} value={skill} />
    {skill}
  </label>
{/each}
<button
  disabled={disable}
  on:click={() => alert(`Your Gender is ${gender} and your skills are ${skills}`)}>
  Submit
</button>

```
![](https://i.imgur.com/yG4sJ9p.png)

#### 07 - Content editable innerHTML binding
```javascript=
<style>
[contenteditable] {
 padding: 0.5em; border: 1px solid #eee; border-radius: 4px;
}
</style>
<script>
let text = '<p>I fell in love</p>';
</script>
<div contenteditable="true" bind:innerHTML={text}></div>
<div>{text}</div>

```
![](https://i.imgur.com/L04z5Un.png)

#### 08 - Content editable text content binding
```javascript=
<script>
  let text = "<p>I fell in love</p>";
</script>

<style>
  [contenteditable] {
    padding: 1em;
    border: 1px solid #eee;
    border-radius: 4px;
    margin-bottom: 1em;
  }
</style>

<div contenteditable="true" bind:textContent={text} />
<div>{text}</div>

```
![](https://i.imgur.com/NB5FH4b.png)

#### 09 - Media element current time binding
```javascript=
<script>
	let currentTime = 0;
</script>
<div>
    <audio controls 
     src="https://file-examples.com/wp-content/uploads/2017/11/file_example_MP3_700KB.mp3" 
     bind:currentTime={currentTime}>
</audio>
</div>
<button on:click={()=>currentTime=50}>set currentTime to 50 sec</button>

```
![](https://i.imgur.com/suPlqdh.png)

#### 10 - Media element puase binding
```javascript=
<script>
	let volume =  0.2
	let paused =true
</script>
<div>
	<audio controls src="https://file-examples.com/wp-content/uploads/2017/11/file_example_MP3_700KB.mp3" bind:volume={volume} bind:paused ={paused} >
</audio>
</div>
<label>
	volume  <input type="range" name="volumne" min="0" max="1" step="0.1" bind:value={volume}>
	{volume*100}%
</label>
<button on:click={()=>paused=!paused}>{paused ? 'Play':'Pause' }</button>

```
![](https://i.imgur.com/NABzfC3.png)

#### 11 - Element dimension binding
```javascript=
<script>
let clientWidth
let clientHeight
let offsetWidth
let offsetHeight
</script>
<style>
div {
  height: 150px;width: 200px;padding: 10px; margin: 15px; border: 5px solid red; background:lightyellow;
}
</style>
<div bind:clientWidth={clientWidth} bind:clientHeight={clientHeight} bind:offsetWidth={offsetWidth} bind:offsetHeight={offsetHeight} >
 <b>Box Information:</b><br>
  Height: 150px<br> Width: 200px<br> padding: 10px<br>
  margin: 15px<br> border: 5px<br>
</div>
<p><b>clientWidth = {clientWidth}px</b></p> 
<p><b>clientHeight = {clientHeight}px</b></p>
<p><b>offsetWidth = {offsetWidth}px</b></p>
<p><b>offsetHeight ={offsetHeight}px</b></p> 
```
#### 12 - Component binding
```javascript=
// App.svelte
<script>
  import Child from "./Child.svelte";
  let textEntered;
</script>

<Child bind:value={textEntered} />
{#if textEntered}
  <p>
    Text enter by child is
    <b>{textEntered}</b>
  </p>
{/if}

// Child.svelte
<script>
  export let value = "";
</script>

<input type="text" bind:value placeholder="Please enter your text" />

```
![](https://i.imgur.com/oyLlyuH.png)


#### 13 - Form validation and submission
```javascript=
<script>
  let email = "";
  let password = "";
  let isSuccess = false;
  let errors = {};
  let validEmailRegex = RegExp(
    /^(([^<>()\[\]\.,;:\s@\"]+(\.[^<>()\[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i
  );
  const handleSubmit = () => {
    errors = {};
    if (email.length === 0) {
      errors.email = "Please enter your email.";
    } else if (!validEmailRegex.test(email)) {
      errors.email = "Please enter valid email.";
    }
    if (password.length === 0) {
      errors.password = "Please enter your password.";
    } else if (password.length > 6 || password.length < 6) {
      errors.password = "Password must be of 6 characters.";
    }
    if (Object.keys(errors).length === 0) {
      isSuccess = true;
      console.log(email);
      console.log(password);
    }
  };
</script>

<style>
  form {
    background: #fff;
    padding: 50px;
    width: 250px;
    height: 300px;
    display: flex;
    flex-direction: column;
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.58);
  }

  input {
    border: none;
    border-bottom: 1px solid #ccc;
    transition: all 300ms ease-in-out;
    width: 100%;
  }
  input:focus {
    outline: 0;
    border-bottom: 1px solid #666;
  }
  button {
    margin-top: 20px;
    background: #ff3e00;
    color: white;
    padding: 10px 0;
    width: 200px;
    border-radius: 25px;
    font-weight: bold;
    cursor: pointer;
  }
  button:hover {
    transform: translateY(-2.5px);
    box-shadow: 0px 1px 10px 0px rgba(0, 0, 0, 0.58);
  }
  .field-control {
    margin-bottom: 20px;
  }
  .error {
    color: red;
  }
  .success {
    font-size: 24px;
    text-align: center;
  }
  h3 {
    text-align: center;
  }
</style>

<form on:submit|preventDefault={handleSubmit}>
  {#if isSuccess}
    <div class="success">
      <h4>Welcome {email}</h4>
      You've been successfully logged in.
    </div>
  {:else}
    <h3>Login Form</h3>
    <div class="field-control">
      <input
        type="email"
        name="email"
        placeholder="Enter your email"
        bind:value={email} />
      {#if errors && errors.email}
        <div class="error">{errors.email}</div>
      {/if}
    </div>
    <div class="field-control">
      <input
        type="password"
        name="password"
        placeholder="Enter your password"
        bind:value={password} />
      {#if errors && errors.password}
        <div class="error">{errors.password}</div>
      {/if}
    </div>
    <center>
      <button type="submit">LOGIN</button>
    </center>
  {/if}
</form>

```
![](https://i.imgur.com/SJcZWwG.png)


### :memo: Fetch API, Onmount, onDestroy, 
#### 01 - Fetch API
```javascript=

function serviceHandler(){
    fetch('https://api.github.com/repos/PacktPublishing/Learn-Svelte.js-3').then(res => res.json())
    .then(response => {
    console.log(response)
    })
    .catch(err => {
        console.log(err)
    });
    }
    
serviceHandler()
```
#### 02 - onMount Demo
```javascript=

<script>
 import { onMount } from "svelte";
	let repo;
  onMount(()=>{
     fetch('https://api.github.com/repos/PacktPublishing/Learn-Svelte.js-3').then(response => response.json())
        .then(jsonData => {
             repo  = jsonData 
             console.log(repo)
        })
        .catch(err => {
            console.log(err)
        });
    });
</script>
<h2>Your Repository details are </h2>
<div class="card">
  {#if repo}
    <img src={repo.owner.avatar_url} alt="repo image"/>
    <div><strong>Name - </strong>{repo.name}</div>
    <div><strong>Owner - </strong>{repo.owner.login}</div>
    <div><strong>Description - </strong>{repo.description}</div>
  {:else}
    <p>Fetching data.....</p>
  {/if}
</div>
<style>
img{
        height: 100px;
        border-radius: 50%;
    }
    .card{
        box-shadow: 2px 2px 6px;
        padding: 1rem;
        width: 50%;
    }
</style>
```
```javascript=
// App.sevlet
<script>
  let githubRepoInfoPromise;
  let repoName = 'mikenikles/ghost-v3-google-cloud-storage';

  const loadRepoInfo = async () => {
    const response = await fetch(`https://api.github.com/repos/${repoName}`);
    if (response.status === 200) {
      return await response.json();
    } else {
      throw new Error(response.statusText);
    }
  }
	
  const handleClick = () => {
    githubRepoInfoPromise = loadRepoInfo();
  }
</script>

<input type="text" placeholder="user/repo" bind:value={repoName} />
<button on:click={handleClick}>
  load Github repo info
</button>

{#await githubRepoInfoPromise}
  <p>...loading</p>
{:then apiResponse}
  <p>{apiResponse ? `${apiResponse.full_name} is written in ${apiResponse.language}` : ''}</p>
{:catch error}
  <p style="color: red">{error.message}</p>
{/await}
```

#### 03 - onDestroy Demo
```javascript=
// App.svelte
<script>
import Timer from './Timer.svelte'
let show= false	
</script>
     <button on:click={()=>show=!show}>{show? 'Stop Timer': 'Start    Timer'} </button>
{#if show}
<Timer/>
{/if}

// Timer.svelte
<script>
  import { onDestroy } from 'svelte'
	let time = new Date().toLocaleTimeString();
	let timer = setInterval(()=>{
		time = new Date().toLocaleTimeString();
	}, 1000);
	onDestroy(()=>{
		console.log('onDestroy called')
		clearInterval(timer);
		console.log(`Timer stopped at ${time}`)
	})
</script>
<h2>{time}</h2>

```
![](https://i.imgur.com/ZQj0cCU.png)

#### 04 - Before and After update
```javascript=
<script>
	import { beforeUpdate , afterUpdate  } from 'svelte'
	let policyAccepted = false
	let name 
	let scroll
	beforeUpdate(() => {
		scroll = policyAccepted
		console.log('the component is about to update');
	});
	afterUpdate(() => {
		if(scroll){
			const elem = document.querySelector(".container")
			elem.scrollTo(0,elem.scrollHeight)
		}
		console.log('the component is updated');
	});

</script>
<div class="container">
	<div><input type="checkbox" bind:checked={policyAccepted}> i have read and accept the investments policy</div>
	<p>
		Mutual Fund investments are subject to market risk. Please read the offer document carefully before investing’ says the disclaimer in the every advertisement of the mutual fund. The objective of this disclaimer is to meet a statutory requirement which is basically intended to communicate the risks that mutual fund schemes have as an investment option		
</p>. 
<input type="text" bind:value={name} placeholder="Enter your name"/> 
</div>
{#if name & policyAccepted}
<h3>Thanks {name} for accepting the investment policy</h3>{/if}
<style>
	div.container{
		height:100px;
		width:500px;
		overflow:auto;
		padding:1rem;
		border:1px solid #cdcdcd;
	}
</style>


```
#### 05 - Trick Demo
```javascript=
<script>
	import {onMount, tick} from 'svelte'
	let size= 100;
	let boxHeight
	onMount(()=>{
		boxHeight = document.querySelector('#box').clientHeight
	})
	async function sizeHandler(){
		size+= 10
		await tick()
		boxHeight = document.querySelector('#box').clientHeight
	}
</script>
<button on:click={ sizeHandler }>Increase height by 10</button>
<div class='container'>
  <div id="box" style="height:{size}px"></div>
</div>
<h3>size is {size} pixel</h3>
<h3>boxHeight is {boxHeight} pixel</h3><style>
	.container{
		display:flex;
		justify-content:center;
		height:50vh;
	  align-items: center;
		color:white;
	}
	#box{
		width:100px;
		background:red;
	}
</style>

```

Happy Learning !!!!

