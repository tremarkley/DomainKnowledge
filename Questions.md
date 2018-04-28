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
