### What's a "tuple"? What's a "triple"? What's the difference between a tuple and a set?
A tuple is a data structure used for organizing data. It is used to group any number of items into a single compound value. Useful for representing related data that belongs together.
A triple is a tuple of three items. The difference between a tuple and a set is that a set is a collection of objects that is unordered and does not allow for duplicates.

### What is the average and worst-case time complexity of access, search, and insertion for common data structures? For each answer, briefly explain why.
| Data Structure | Access | Search | Insertion
|---|---|---|---|
Array | O(1) | O(n) | O(n)
Queue | O(n) | O(n) | O(1)
Stack | O(n) | O(n) | O(1)
Singly-linked list | O(n) | O(n) | O(1)
Hash table | O(1) | O(1) | O(1)
BST | O(log(n)) | O(log(n)) | O(log(n))

### When using git, what exactly do people mean when they talk about "the SHA-1"? How is that related to how git works?
SHA-1 is a cryptographic hash algorithm which takes an input and produces a 160 bit (20-byte) hash value known as a message digest typically rendered as a hexadecimal 40 digits long. Git uses this algorithm when you make commits. It is used as a method of verification and identification. Git creates the checksum by using metadata of the commit as well as the commit itself (author, parent commit's checksum, and the checksum of the changes made in the commit). Then when you pull from a git repo git will check the checksums of the files you received against the ones on the server to make sure you didnt receive corrupt files.

### Practically speaking, how does git rebase function compared to git merge?
So a typical scenario where you would rebase would be if you make some changes then submit a pull request. While waiting for that pull request to go through you make some more changes that get pushed to the master branch which conflict with the pull request. Therefore, you rebase the branch of the pull request to reset the base commit so that when your pull request is merged into the master branch your changes are clean and just include the changes you made. [helpful link](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

### Present a quick overview of TDD. What are the proposed benefits? How popular is it, really? What are the arguments against it?

TDD stands for test driven development. The idea is that you will write all of the tests for a specific feature before you implement it. This forces you to really think out the inputs and outputs to the function. Additionally, by having tests in place you can check to make sure new features you implement dont break existing code. Downsides are that it can be time consuming, you dont always know your design up front and things change therefore you spend a lot of time tweaking or re-writing tests.

### Is JavaScript a functional language? What does it mean for a language to be "functional"?
Javascript is a multi-paradigm language. Although it is not widely known as a functional language it does have some functional elements. It can be written in imperative, prototype based object oriented, or functional. It's up to you to pick which one is best for your use case. Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids state and mutable data. It emphasizes the application of functions, in contrast to the imperative programming style, which emphasizes changes in state.

### Practically speaking, what's a "declarative" language?

**An imperative approach (HOW):** I see that table located under the Gone Fishin’ sign is empty. My husband and I are going to walk over there and sit down.

**A declarative approach (WHAT):** Table for two, please.

The imperative approach is concerned with HOW you’re actually going to get a seat. You need to list out the steps to be able to show HOW you’re going to get a table.The declarative approach is more concerned with WHAT you want, a table for two. It is important to realize that many declarative approaches have some sort of imperative abstraction layer. Look at the above example: The declarative response to the Red Lobster employee is assuming that the Red Lobster employee knows all the imperative steps to get us to the table.

Popular declarative languages are SQL and HTML. Many (if not all) declarative approaches have some sort of underlying imperative abstraction.

Example of difference between imperative and declarative languages:
Imperative:

* Start
* Turn on your shoes size 9 1/2.
* Make room in your pocket to keep an array[7] of keys.
* Put the keys in the room for the keys in the pocket.
* Enter garage.
* Open garage.
* Enter Car.
... and so on and on ...

* Put the milk in the refrigerator.
* Stop.

Declarative, whereof functional is a subcategory:

* Milk is a healthy drink, unless you have problems digesting lactose.
* Usually, one stores milk in a refrigerator.
* A refrigerator is a box that keeps the things in it cool.
* A store is a place where items are sold.
* By "selling" we mean the exchange of things for money.
* Also, the exchange of money for things is called "buying".
... and so on and on ...

* Make sure we have milk in the refrigerator (when we need it - for lazy functional languages).

[Reference](https://tylermcginnis.com/imperative-vs-declarative-programming/)

### Is JavaScript statically or dynamically typed? Is JavaScript strongly typed or loosely typed? What do those terms mean?
Javascript is dynamically typed. This means that types are determined at run time rather than at compile time. Loosely typed means that the language does not bother too much with types and does the conversions automatically i.e. you can add a string and an integer together. With a strongly typed language once a variable has a certain typed assigned to it, then it cannot be changed. 

### Give a brief analogy explaining how computer memory works to a beginning programmer.
Computer memory has very fast access time. Which means that your program knows exactly where each value is in memory. When a program is running variables are mapped to addresses in memory where their values can be retrieved. This allows a program to run very quickly. For values which are stored in sequence like arrays. You can quickly find any value in the array because all the values lineup side by side in memory. Memory is also limited and you can run out of space. 

A good analogy can be viewing memory as a post office. Each deposit box has the same size and is labelled 1 - 1000. You then have a directory of what is in each box number and you can quickly look things up. For a string you might have string = "AB". Let's then say that the character A is mapped to box 1 and the char B is mapped to box 2. This string may be stored in box 100. If you go to box 100 you would find a slip in it that specifies the length of the string, 2. From here you would know that you can only traverse two boxes for this string. So then you go to box 101 and it contains a slip that points to box 1 ("A"). Then you would go to box 102 and it would contain a slip that points to box 2. 

Another analogy is that you can think of a computer as a kitchen. The chef is the processor and the counter space is the memory. The more ingredients and tools a chef can fit on his counter the faster his access is and the faster he can cook. Then if he needs to get things from cupboards or the fridge (disk) it takes time for him to go retrieve them.

### Using official terminology, summarize how Promises work in JS.
Some terms to use: pending, fulfilled, rejected, resolve, reject, then, catch, all. Cover how chaining/sequencing promises works.

When creating a promise you have a resolve and a reject function. The resolve and reject functions are used in order to determine when the promise is either fuflfilled or rejected. Since promises involve asynchronous actions you do not have a way of knowing when the asyn action will return. Therefore, you will provide a callback to the asynchonous function and when it returns, you will check to see if it returned in error or success. If it was a successful call then you can call the resolve function and pass in any data you would like sent back. If an error occurred in the async function then you would call the rejectfunction and pass in the error. In order to access the data returned byt the promise you use a .then block. In order to handle an error you would use the .catch block. If you have several promises that you need to wait on before progressing in the code then you would pass them into Promise.all() then after they return you can access there values in a .then block.


### What's an IIFE in JS? When would you use it?
An IIFE stands for an Immediately Invoke Function Expression. An IIFE protects a modules scope from the environment in which it was placed. For example you have a for loop in which you pass the i into an IIFE then you use the i in an asynchronous function. Even though the i is changing on the outside in the for loop, the i does not change within the IIFE.

### From memory, write the one-liner that determines if a given string is a palindrome.
```javascript
const isPalindrome = (inputString) => inputString === inputString.split('').reverse().join('');
```

### From memory, write the one-liner that generates a random number between two given integers.
```javascript
\\  last number not included 
const randomNumber = (int1, int2) => Math.floor(Math.random()*(int2 - int1)) + int1;

\\  last number included
const randomNumber = (int1, int2) => Math.floor(Math.random()*(int2 - int1 + 1)) + int1;
```
