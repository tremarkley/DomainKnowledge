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

