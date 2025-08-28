# prep

Template litrals `${}`

DIfference between let, var, const

Var: can be accessable from anywhere within a function

example: 

function fun(){

if(true){

    var a = 14;

}

console.log(a)

}

Var: it can be redeclared with same name

var a = 14;

var a = 15;

let: it can only be accessable within a block of code

it can't be redeclared with same name in a block

const: it can also only accessable within a block of code

can't be redeclared with same name

also can't reassign a value to it

Difference between map and foreach

Map: It not modify the original array it return new array

in this we need to return something

it can be writen in single line

Foreach: it modify the original array

no need to return anything

Event bubbling: it happens bottom to top

Event Capturing: it happens top to bottom



Higher Order Function (HOC)

A Higher-Order Function (HOF) is a function that does at least one of the following:

Takes one or more functions as arguments. () => {}

Returns a function as its result.

map(), filter(), reduce(): These are HOFs because they take a callback function as an argument.

const numbers = [1, 2, 3]; const doubled = numbers.map(num => num * 2); // map takes a function

setTimeout(() => console.log("Hello"), 1000); // setTimeout takes a function

Immediately Called Function

(function(){

console.log("hello")

}

)()

Closures

It remembers it's lexical environment even if the parent function got finish executing

function outerFunction() {

  const outerVariable = "I am from the outer function!";

  function innerFunction() {

    // innerFunction "closes over" outerVariable

    console.log(outerVariable);

  }

  return innerFunction;

}

// When we call outerFunction, it returns innerFunction.

// The outerFunction has already finished executing.

const myClosure = outerFunction();

// Now, we execute innerFunction (via myClosure)

// even though outerFunction's execution context is long gone.

myClosure(); // Output: I am from the outer function!```

Promises

Helps to handle asynchronous tasks

they return three states Pending, Fulfilled and rejected

Asyn Await

it's a simpler way of doing asynchronious tasks as comparison to the promises so async tell that a functions is a asynchronous and await will wait until the promise got resolved

Reduce Function

it's used to calculate the array of numbers

const nums = [1, 2, 3, 4]

console.log(nums.reduce((a,b) => a + b));

Weak Map

it helps to store temporary data in object type

Weak Set

it helps to store temporary data but it does not allow duplicate values to be stored

Shallow Copy

when you change the actual object data

Deep copy

when you firstly create a copy of a data array or object and then you make changes to that copy data

Array Methods

toString()

slice()

splice()

find()

filter()

reduce()

map()

foreach()

split()

join()

includes()

splice(0,1) will delete those items withing that range in actual array

slice(0,1) will slice the item from an actual array and create new array 

Typescript

object oriented 

typesafe

Disadvantages

Takes to much time to compile

it's bit complex

Extend

allow to extend existing type and add new type into it

Interface

allow to extend the data types but not let you override existing type

Type 

allow to extend the data types also allow to override 

Generics

<T> allow to dynamically pass data types

Pattrens

const pattren = (n) => {

  let count = 0;

  for(let i = 0; i < n; i++){

    let star = "";

    for(let j = 0; j < n; j++){

      star+= " *"

    }

    console.log(star);

  }

}

pattren(5);

*****

*****

*****

*****

*****

const pattren = (n) => {

  let count = 0;

  for(let i = 0; i < n; i++){

    let star = "";

    for(let j = 0; j <= i; j++){

      star+= " *"

    }

    console.log(star);

  }

}

pattren(5);

*

**

***

****

*****

const pattren = (n) => {

  let count = 0;

  for(let i = 0; i < n; i++){

    let star = "";

    for(let j = 0; j < n-i; j++){

      star+= " *"

    }

    console.log(star);

  }

}

pattren(5);

*****

****

***

**

*

const pattren = (n) => {

  let count = 0;

  for(let i = 1; i < n; i++){

    let star = "";

    for(let j = 0; j < i; j++){

      count++;

      star+= " " + count;

    }

    console.log(star);

  }

}

pattren(5);

1 

2 3 

4 5 6 

7 8 9 10

const patterns = (n) => {

  for(let i = n; i > 0; i--){

    let res = "";

    for(let j = i; j > 0; j--){

      res+= j;

    }

    

    console.log(res);

  }

};

patterns(5);

54321 

4321 

321 

21 

1

const patterns = (n) => {

    

  for(let i = 0; i < n; i++){

    let res = "";

    for(let j = 0; j <= i; j++){

      

      if((i + j) % 2 === 0){

        res+= " 1";

      }else{

        res+= " 0"

      }

    }

    console.log(res);

  }

};

patterns(5);

1 
0 1 

1 0 1 
0 1 0 1 
1 0 1 0 1

Spread Operator

it's used to spread out the content usually user for shallow copy array

const originalArray = [1, 2, 3]; 

const copiedArray = [...originalArray];

Rest Operator

it helps to get the rest remaining data items

function sumAll(1, 2, ...numbers) { console.log(numbers); // numbers will be an array return

mainly used as function argument, destructuring array or object

Debouncing

Debouncing ensures that a function is not called until a certain amount of time has passed without any further activity. It effectively delays the execution of a function until the user "stops doing something." If the event fires again before the delay has elapsed, the timer is reset, and the function call is delayed again.

  const inputRef = useRef();

  const searchDebounce = useCallback((value) => {

    if(inputRef.current){

      clearTimeout(inputRef.current);

    }

    inputRef.current = setTimeout(() => {

        setDebounceValue(value)

    },2000)

  },[]);

Throttling

in this it ensures that a functionality happens after certain interval ensure minimum time between executions

useCallback

useCallback is a hook that helps to memoize a function. it only re render the function if the dependancy array has changed

useMemo

it's is used to memoize a value only if some change happens to it's dependancy array item only that it recalculates the value it's manly used for calculating large values

Logical Questions

Find even or odd number

Find largest num in array

Reverse a string

const reverseString = (str) => {

  const res = str.split("").reverse().join("");

  return res;

}

console.log(reverseString("hello"))

const reverseString = (str) => {

  const s = str.split("");

  let res = "";

  for(let i = s.length - 1; i >= 0; i--){

    res+= s[i];

  }

  return res;

}

console.log(reverseString("hello"))

Check if a string is a palindrome

// "madam" -> true

// "hello" -> false

const checkPalindrome = (str) => {

  let reverse = str.split("").reverse().join("");

  return reverse === str;

}

console.log(checkPalindrome("mom"))

Find factorial of a number

// 5! = 5*4*3*2*1 = 120

const checkFactorial = (num) => {

  let res = 1;

  for(let i = num; i > 0; i--){

    res*= i;

  }

  return res;

}

console.log(checkFactorial(5))

Find the Fibonacci sequence up to n terms

// n=5 -> [0, 1, 1, 2, 3]

const generateFibonacci = (n) => {

  const fibSequence = [0, 1]; 

  if (n === 0) {

    return []; 

  }

  if (n === 1) {

    return [0];

  }

  if (n === 2) {

    return [0, 1];

  }

  

  for(let i = 2; i < n; i++){

    const nextNum = fibSequence[i - 1] + fibSequence[i - 2];

    fibSequence.push(nextNum);

  }

  return fibSequence;

}

console.log(generateFibonacci(10))

Remove duplicates from an array

// [1,2,2,3,4,4,5] -> [1,2,3,4,5]

const removeDuplicates = (nums) => {

  const newNums = [...new Set(nums)];

  return newNums;

}

console.log(removeDuplicates([1,2,2,3,4,4,5]))

const removeDuplicates = (nums) => {

  const newNums = [];

  for(let i = 0; i < nums.length; i++){

    const item = nums[i];

    if(!newNums.includes(item)){

      newNums.push(item);

    }

  }

  return newNums;

}

console.log(removeDuplicates([1,2,2,3,4,4,5, 6]))

Find the second largest number in an array

// [10, 20, 4, 45, 99] -> 45

const findSecondLargeNum = (nums) => {

  let largest = 0;

  let secondLargest = 0;

  for(let i = 0; i < nums.length; i++){

    const item = nums[i];

    

    if(item > largest){

      secondLargest = largest;

      largest = item;

    }else if(item > secondLargest && item !== largest){

      secondLargest = item;

    }

  }

  return secondLargest;

}

console.log(findSecondLargeNum([10, 20, 4, 45, 99]))

const findSecondLargeNum = (nums) => {

  let secondLargest = 0;

  const sorted = nums.sort();

  secondLargest = sorted[sorted.length - 2];

  return secondLargest;

}

console.log(findSecondLargeNum([10, 20, 4, 45, 99, 46]))

Check if two strings are anagrams

// "listen" & "silent" -> true

// "hello" & "world" -> false

const checkAnagrams = (str1, str2) => {

  

  let str1Reverse = str1.split("").sort().join("");

  let str2Reverse = str2.split("").sort().join("");

  

  return str1Reverse === str2Reverse;

}

console.log(checkAnagrams("listen", "silent"))

Count vowels in a string

// "javascript" -> 3

const countVowelsIterative = (str) => {

  const vowels = "aeiou";

  let count = 0;

  

  for (let i = 0; i < str.length; i++) {

    let char = str[i].toLowerCase();

    

    if(vowels.includes(char)){

      count++;

    }

  }

  return count;

}

console.log(countVowelsIterative("javascript"))

Flatten a nested array

// [1, [2, [3, 4]], 5] -> [1, 2, 3, 4, 5]

const flatArray = (str) => {

  const nestedArray = [1, [2, [3, 4]], 5];

  const flat = nestedArray.flat(Infinity);

  

  return flat;

}

console.log(flatArray())

// Problem:

// You are given an array of transactions. Each transaction has a userId, amount, and type (either "credit" or "debit").

// Example input:

// const transactions = [

//   { userId: 1, amount: 50, type: "credit" },

//   { userId: 2, amount: 30, type: "debit" },

//   { userId: 1, amount: 70, type: "debit" },

//   { userId: 2, amount: 100, type: "credit" },

//   { userId: 1, amount: 40, type: "credit" },

// ];

// Task:

//  produce an array of objects where each object contains:

// userId

// totalCredits (sum of amounts where type is "credit")

// totalDebits (sum of amounts where type is "debit")

// balance (credits minus debits)

// Expected Output:

// [

//   { userId: 1, totalCredits: 90, totalDebits: 70, balance: 20 },

//   { userId: 2, totalCredits: 100, totalDebits: 30, balance: 70 }

// ]


const transactions = [

  { userId: 1, amount: 50, type: "credit" },

  { userId: 2, amount: 30, type: "debit" },

  { userId: 1, amount: 70, type: "debit" },

  { userId: 2, amount: 100, type: "credit" },

  { userId: 1, amount: 40, type: "credit" },

];

const result = [];

let userTotalCredits = 0;

let userTotalDebits = 0;

let user2TotalCredits = 0;

let user2TotalDebits = 0;

transactions.forEach(user => {

    if(user.userId === 1){

        if(user.type === "credit"){

            userTotalCredits+= user.amount

        }else{

            userTotalDebits+= user.amount

        }

    }else{

         if(user.type === "credit"){

            user2TotalCredits+= user.amount

        }else{

            user2TotalDebits+= user.amount

        }

    }

});

        const user1Obj = {

            userId: 1,

            totalCredits: userTotalCredits,

            totalDebits: userTotalDebits,

            balance: userTotalCredits - userTotalDebits

        }

         const user2Obj = {

            userId: 2,

            totalCredits: user2TotalCredits,

            totalDebits: user2TotalDebits,

            balance: user2TotalCredits - user2TotalDebits

        }

        result.push([user1Obj, user2Obj]);

console.log(result);

const res = {};

const tranData = transactions.reduce((acc, transaction) => {

  const { userId, type, amount } = transaction;

  if(!res[userId]){

    res[userId] = {

      userId: userId,

      totalCredits: 0,

      totalDebits: 0

    }

  }

  

  

  if(type === "credit"){

    res[userId].totalCredits += amount;

  }else{

    res[userId].totalDebits += amount;

  }

  

  

},{});

const finalRes = Object.values(res).map((item) => {

  return {

    ...item,

    balance: item.totalCredits - item.totalDebits

  }

});

console.log(finalRes);

Find first non repeating char

const checkFirstNonRepeatingChar = (str) => {

  

  let charCount = {};

  

  for(let i = 0; i < str.length; i++){

    const char = str[i];

    

    if(charCount[char] === undefined){

      charCount[char] = 1;

    }else{

      charCount[char]++;

    }

  }

  

  

  for(let j = 0; j < str.length; j++){

    const char = str[j];

    

    if(charCount[char] === 1){

      console.log(charCount)

      return char;

    }

  }

  

  

  return null;

  

}

console.log(checkFirst("sawiss"));

Cookie

cookie get send back by the server to the web browser then in every https requrest the cookie automaticallly got sent by the browser to server it has expiration date 4kb




Local storage

 aslo used to store info but it get stored only via the client side in broswers size 5 to 10 mb and no expiration

Session Storage



is similar to the local storage but user to store temoparry data only as when user closes the tab or window session storage got clear

Mongo Db Replication

means duplicating same data across multiple different mongodb servers

MongoDb Shadering

distributing data across mulitple databases mongodb supports

for example 2 millions data 1 million store to one database another 1 million stoer to another

Vertical Scaling 

is like adding more ram, cpus to the database server

Horizontal Scaling

refers to adding more virtual machines or server for the database it's also called shadering

Map Reduce

"map reduce helps to count out something we want to count via across different documents": Exactly! Its primary purpose is to process data across many documents to derive aggregated results or counts.

"map first find out all the things we are looking for and seperate them in key value pairs": Correct. The "map" stage iterates through each document, identifies the piece of information you're interested in (the "key"), and associates a specific "value" with it. It prepares the data for the next step.

"reduce will combine those and give us the actual count": Spot on! The "reduce" stage then takes all the values that share the same key and aggregates them (sums them, counts them, averages them, etc.) to produce the final, summarized result for that key.

GridFs

grid file system in mongodb helps to store and reterive large files like images, videos, documents

Instead of storing a large file as a single document, GridFS divides the file into smaller parts, called chunks, and stores each chunk as a separate document. By default, the chunk size is 255 kB, though this can be configured

Primary key and Secondary Key

primary key is uniques identyfire _id

secondary key is used for indexing and query a data

Streams

in nodejs refers to reading large amount of data in chunks rather then reading whole data once

Cluster

cluster in nodejs about creating multiple node servers and distuributing the requests across those server?

Server-Side Rendering (SSR) - "Pre-built Webpages"

What happens: When you ask for a webpage, the server (the "restaurant kitchen") builds the entire page with all the text, pictures, and buttons right there.

What you get: It then sends that complete, ready-to-look-at page directly to your web browser (your "plate").

Result: You see the page very quickly because it's already finished.

Client-Side Rendering (CSR) - "Build-It-Yourself Webpages"

What happens: When you ask for a webpage, the server (the "delivery service") sends you a tiny, almost empty page along with a bunch of instructions (called JavaScript).

What you get: Your web browser (your "kitchen") then takes those instructions and builds the page itself right there on your computer, fetching ingredients (data) as needed.

Result: It takes a moment for your browser to build everything, but once it's done, it's very interactive.

Data assets 

the valuable information that an organization stores and manages within its databases.

trpc full form

TypeScript Remote Procedure Call

Hashing

Hashing is a one way process once done it can't be reverse backed generally used for password hashing

Encryption

Encryption is a two way process it created via a secret key and any plain text you want to encrypt it can decrypt using the same secret key

Authentication

it's about checking whether you are valid user or not it checks via the username email password you enter for login if everthing is correct then you are authenticated

Authorization

is a process where we check after authentication what things you are allowed to access for example if you are  a simple user and trying to access admin features then you should not be able to access those via proper authorization

Primitive Data Types

they are simple data types

number

string

char

Boolean

float

undefined/null

Non-Primitive Data Types

they are more complex and advanced data types

array

object

functions

Pass by value

Premitive Data types

let a = 5;

let b = a;

b = a + 5;

both will work independently in pass by value if we change something it only applies for that variable no other value get changed

Pass by reference

Non premitive data types

in this suppose we create two objs and second one is referencing the first one so if we change something inside the obj2  it will reflect in obj1 as well

Mongodb query optimization

use the indexing

single field indexing

compound indexing (multiple fields indexing)

we can also use the sort(), limit(), aggregations methods as well

Cleanup Function

it's basically used inside the useeffect when we want to stop the process that's going inside the useeffect we just return at the end of the useeffect logic

Composition in React

is basically means to creating separate components for the sections to increase readability and reusability

Virtual Dom

is a lightweight copy of the real dom whenever any state or data got changed inside the reactjs it firstly got changed insid the virtual dom then react uses diffing algorithm to check the difference between the vdom and real dom and then it only changes the that section that differs not the entire dom

State

it contains any data for a component that in future can get changed

Component Lifecycles

ComponentDidMount();

componentDidUpdate();

componentWillUnmount():

shouldComponentUpdate() is way to manually define whether a component should update or not

side effects in React

are the operations that interacts outside of the react for like api requests, timers, dom, console.log()

synthetic event" in React?

stopPropagation() and preventDefault()

reconciliation" in React?

is used in react to check the difference in the virtual dom and real dom if any changes found it updated the real dom only that part of the tree

Portals in React?

in react is used for the modals, tooltips, dialouges, so it's a way to create dom element outside the dom hierarchy

What is a bundler (e.g., Webpack, Vite) and why is it used in React projects?

A bundler (like Webpack or Vite) is a tool that processes and optimizes the assets of a web application (JavaScript, CSS, HTML, images, etc.) by packaging them into deployable bundles

Babel in Reactjs

Babel is a js compiler that's used in react to convert the jsx into the javascript code so it can be undertood by the browsers

