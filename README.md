# csci2275-project-minigit-a-mini-version-control-system-solved
**TO GET THIS SOLUTION VISIT:** [CSCI2275 Project-MiniGit (A mini version control system) Solved](https://www.ankitcodinghub.com/product/csci-2275-data-structures-project-specifications-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;119716&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSCI2275 Project-MiniGit (A mini version control system) Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
MiniGit (A mini version control system)

1 Version Control System

A version control system, also known as revision control system, is a class of systems responsible for managing changes to a set of documents typically containing computer programs, documents, web sites, or other collections of information. Version control systems track the changes users make to files, so users have a historical record of all of the changes, and they can revert to specific versions should they ever need to. Version control systems also make collaboration easier, allowing changes by multiple people to all be merged into one source. In this project, you are required to implement a toy version-control system that we call minigit. This document provides minimum capability your tool should have, but you are encouraged to add more functionality to bring it closer in capability to well-known version control systems such as git, mercurial or cvs (Concurrent Versions System).

2 Phase I: Core Features

2.1 Overview

For the first phase of the project, you will need to create a miniGit program with the following core functionality:

1. Initialising a new repo

2. Adding files to the current commit

3. Removing files from the current commit

4. Committing changes

5. Searching commits based on a keyword

6. Checking out a specific version based on a unique commit number

1

This project is intended to be more open-ended than the preceding course assignments. With that, you are given minimal starter code. You will have to create your own test cases, for which you will need to generate a set of test files. Your miniGit repository needs to be able to accept files of .cpp, .hpp, and .txt type (i.e. you do not need to worry about PDF or executable files, etc.)

2.2 Implementation Requirements

2.2.1 User interface

The user shall interact with the program via a list of choices presented in a textual menu. The program should continue running indefinitely until the user chooses to quit. The menu is to be implemented using a switch statement and a while loop (as has been done for the assignments in the class thus far.)

2.2.2 Initializing a new repository

Executing the program will prompt the user with an option to initialize an empty repository in the current directory.

#include &lt;filesystem&gt; namespace fs = std::filesystem; ….

fs::remove_all(“.minigit”); // removes a directory and its contents fs::create_directory(“.minigit”); // create a new directory

Note that you are not allowed to use the copy function from the filesystem library. You must implement your own file-copy procedure.

If the user chooses to initialize, a doubly linked list will be created with a single head node. Going forward, each doubly linked list (DLL) node will correspond to a single commit. Each DLL node will contain a member with a unique commit number as well as a head pointer to a singly linked list (SLL). The first node in the DLL should have a commit number of 0. Each DLL node will also store a commit message.

It is suggested that you define the DLL and SLL structs as follows:

struct BranchNode { int commitID;

string commitMessage; // at least one word length

BranchNode* next; //DLL next node

BranchNode* previous; //DLL previous node

FileNode* fileHead; //SLL head

};

struct FileNode { string name; //name of the local file int version; //version of the file in .minigit FileNode* next; //sll next node

};

The SLL will then be used to store a list of files in the current commit. The initialization step will also create a new sub-directory within the current directory called .minigit. The user will then be given the following choices: (1). Add file, (2). Remove file, (3). Commit, and (4). Checkout.

2.2.3 Adding A File

If the user chooses to add a file to the repository, the following sequence should occur:

1. Prompt user to enter a file name.

2. Check whether the file with the given name exists in the current directory. If not, keep prompting the user to enter a valid file name.

3. The SLL is checked to see whether the file has already been added. A file by the same name cannot be added twice.

2.2.4 Removing a file

If the user chooses to remove a file from the repository, the following steps should take place:

1. Prompt user to enter a file name.

2. Check the SLL for whether the file exists in the current version of the repository.

3. If found, delete the SLL node.

2.2.5 Committing Changes

Once the user chooses to commit their changes, the following steps need to be taken:

1. Ask user for a commit message. The message cannot be an empty string. If the user enters an invalid commit message, prompt user until the system gets a valid commit message. Populate the commit message field of the current DLL node.

2. The current SLL should be traversed in its entirety, and for every node. Check whether the corresponding fileVersion file exists in .minigit directory. Then, do one of two things:

(a) If the fileVersion file does not exist, copy the file from the current directory into the .minigit directory. The newly copied file should get its name from the file name combined with the node’s fileVersion member. (Note: this will only be the case when a file is added to the repository for the first time.)

(b) If the fileVersion file does exist in .minigit, check whether the current directory file has been changed (i.e. has it been changed by the user?) with respect to the fileVersion file. (To do the comparison, you can read in the file from the current directory into one string and read in the file from the .minigit directory into another string, and check for equality.) Based on the comparison result, do the following:

i. File is unchanged: do nothing.

ii. File is changed: copy the file from the current directory to the .minigit directory, and give it a name with the incremented version number. Also, update the SLL node member fileVersion to the incremented name.

3. The commit function should ask the user to provide a short message (string) with every commit. The commit message is to be parsed and the sub-strings stored in a Hash Table that uses linked-list based chaining for collision resolution.

(a) Use a single white space as the delimiter.

(b) For each word (sub-string) in the commit message:

i. Calculate the hash function for the key.

ii. Retrieve the chain and scan the chain for the key.

iii. If the a node with the key is found, then add the current commit number to the commitNumber vector.

iv. Otherwise, create a new node with the key. Add the current commit number to the commitNumber. Add the node to the chain.

The Hash Table data structure should be implemented as its own C++ class with the following definitions:

struct hashNode{ std:: string key; std:: vector&lt;int&gt; commitNumber; struct hashNode* next;

}

class HashTable{ int tableSize; // No. of buckets (linked lists) hashNode* *table; // Pointer to an array

// containing lists of hashNodes

int hashFunction(string key); … }

int HashTable::hashFunction(string s)

{ int sum=0,index=0; for(string::size_type i=0; i &lt; s.length(); i++){ sum += s[i];

} index = sum % tableSize; return index;

}

4. Once all the files have been scanned, the final step of the commit will create a new Doubly Linked List node. An exact (deep) copy of the SLL from the previous node shall be copied into the new DLL node. The commit number of the new DLL node will be the previous node’s commit number incremented by one. Make the commit message of this newly created DLL empty.

2.2.6 Checkout

This step will require a search through the DLL for a node with a matching commit number. Also, note that you must disallow add, remove, and commit operations when the current version is different from the most recent commit (the last DLL node).

2.2.7 Searching with a Hash Table

Implement a minigit search function that takes a search key and prints all commit IDs whose messages contain the given search key. The search key should be a single word (no white spaces.) Implement this search function efficiently using the hash-table populated by the commit messages.

2.3 Example Flow

Once the user starts the minigit program, they are prompted to initialize a new repository. If they choose to do so, a new DLL is created, with a single node. Also, a new .minigit sub-directory is created in the current directory. Figure 1 shows a diagram of what the data structure should look like after the initialization.

.minigit

Empty

(a) (b) (c)

Figure 1: Repository data structure after initialization. a) The initial DLL state b) The state of minigit folder c) the hash table is also empty at this point

The user then gets the option to add files to the repository. For example, they choose to add files f1.txt and f2.txt. These actions result in two new SLL nodes being created. The diagram in Figure 2 illustrates the state of the data structure after the two adds. The figure also shows that there are currently no files in the .minigit directory.

Next, the user decides to commit their changes. The user is prompted for a valid commit message. For example, the commit message is “computer science”.

After the commit a new DLL node is created, with the SLL copied from the previous DLL node. The state of the data structure right after the commit is visualized in the Figure 3 diagram a. The sub-figure b also shows the files that are now present in the .minigit subdirectory. Assume that the word “science” got a hash value of 1 and “computer” got 3.

Figure 3 (c) shows the hash-table.

Let us say that the user then decides to do the following:

• Make some changes to f1.txt

• Do nothing to f2.txt

Figure 2: Repository data structure after adding f1.txt and f2.txt. a) The current state of DLL b) The state of minigit folder. It will contain copies of files with version number appended to their names

(b) (c)

Figure 3: Repository data structure after the first commit. a) The current state of DLL b)

The state of minigit folder.c) the hash table

Figure 4: Repository data structure after user actions. Note: string member of the SLL node corresponding to f1 00.txt remains unchanged until commit.

• Add a new file (f3.txt).

The SLL that is pointed to by the second DLL node should be used to keep track of these changes. Note that a new node will be created as soon as the user issues an add with f3.txt. However, the change to f1.txt will not be recorded until the user makes a new commit. The diagram in Figure 4 shows the state of the data structure after the aforementioned user actions.

The user issues a second commit with commit message “science fun”. Recall that the commit will traverse the entire corresponding SLL, checking each file against the most recent repository version. Because a change is detected in f1.txt, a copy of the file gets saved to the .minigit directory. The name of the fileVersion member also gets changed to f1 01.txt, to reflect the incremented file version. f2.txt is unchanged, so the node stays unaltered. f3.txt has been newly added, so the initial version of the file gets copied to the .minigit directory. Figure 5 shows the post-commit resulting diagram. Assume the hash function for key fun is 3. Figure 5 (c) shows the hash-table after this commit.

Figure 5: Repository data structure after the second commit

3 Phase II: Additional Features for Extra Credits

1. Branching: Implement a version of git branch where users can manage separate branches of their files in your minigit repository. You are not required to implement merge for those branches. So far you have implemented only a single branch in your minigit implementation, often called the main branch. You can implement the branch feature by simply keeping a list of various branches (instead of implementing a tree-like structure). Each branch should be uniquely identified by a name. The commit IDs should be unique within a branch. Hence your checkout should specify both the branch name and the commit ID.

2. Friendly Checkouts. Implement a special checkout git checkout HEAD to help users to move back to the most recent commit version. Moreover, allow your users to revert back to the previous version of the code (more like an undo feature) by implementing checkout with special commit id, e.g. git checkout – (checkout followed by a dash). Finally, allow your users to go to the commit i-steps back in the past (git checkout HEAD~3).

3. Diff and Status. Implement the minigit diff feature that takes a file and prints the first difference (print the whole line) with respect to the most recent commit. Also, implement minigit status feature that lists all of the files that have been changed since the last commit.

4. Serialization and Deserialization. Your current minigit implementation is not state-ful, i.e. it is not required to keep information between different invocations from within a same directory. In this feature you are required to make your implementation state-ful by serializing and de-serializing your data-structure.

Serialization is the process of translating a data structure or object state into a format that can be stored (e.g., in a file) and reconstructed later. The process of storing a data-strucutre to a file is called serialization, and the process of re-constructing the data-structure from a file is called deserialization. For this feature, you are required to implemented both serialization and deserialization of your minigit repository so that you can use the minigit using the commandline.

One way to serialize the repository shown in figure 5 is the following xml-like encoding.

&lt;branch dir=”.minigit”&gt; &lt;commit id = 0&gt;

&lt;files&gt;

&lt;file src=”f1.txt”&gt; f1.txt_00 &lt;/file&gt;

&lt;file src=”f2.txt”&gt; f2.txt_00 &lt;/file&gt; &lt;/files&gt;

&lt;/commit&gt;

&lt;commit id = 1&gt;

&lt;files&gt;

&lt;file src=”f1.txt”&gt; f1.txt_01 &lt;/file&gt;

&lt;file src=”f2.txt”&gt; f2.txt_00 &lt;/file&gt;

&lt;file src=”f3.txt”&gt; f3.txt_00 &lt;/file&gt; &lt;/files&gt;

&lt;/commit&gt;

&lt;commit id = 2&gt;

&lt;files&gt;

&lt;file src=”f1.txt”&gt; f1.txt_01 &lt;/file&gt;

&lt;file src=”f2.txt”&gt; f2.txt_00 &lt;/file&gt;

&lt;file src=”f3.txt”&gt; f3.txt_00 &lt;/file&gt; &lt;/files&gt;

&lt;/commit&gt;

&lt;ranch&gt;

This can be accomplished by a traversal to the Doubly-linked list (of commit nodes) and for every commit node another traversal to the singly-linked lists or the files. This xml file can be stored in the .minigit folder with the name (minigit.xml) when program exits. Similarly, such a file can be read the minigit data-structure can be recreated when the program initializes again. Be careful not to delete the contents of the minigit folder between different invocations.

4 Project Submission and Grading

4.1 Deliverables

• miniGit.hpp – header file

• miniGit.cpp – implementation file

• hash.hpp – header file for hash implementation

• hash.cpp – hash table implementation file

• main 1.cpp – driver file containing the user interface

• readme.md – description of program functionality and special features implemented in the project; names of team members
