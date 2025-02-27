# Introduction to Mongo DB(NO SQL data Base)
1. MongoDB is an open source, document-oriented database designed with both scalability and developer agility in mind. 
2. Instead of storing your data in tables and rows as you would with a relational database, in MongoDB you store JSON-like documents with dynamic schemas (schema-free, schemaless)

##  Mongo DB architecture
![image](https://user-images.githubusercontent.com/49730521/116961766-d0ff7400-acc1-11eb-9ecb-a446ff678194.png)
 
 ##  What is NoSQL
1. Class of non-relational data storage systems
2. Usually do not require a fixed table schema nor do they use the concept of joins : Distributed data storage systems
3. All NoSQL offerings relax one or more of the ACID properties 

## CAP Theorem
Three properties of a system
1. Consistency (all copies have same value)
2. Availability (system can run even if parts have failed) :All nodes can still accept reads and writes 
3. Partition Tolerance (Even if part is down, others can take over)

CAP “Theorem”: 
You can have at most two of these three properties for any system
![image](https://user-images.githubusercontent.com/49730521/116962121-cd202180-acc2-11eb-81ee-01dfb01124d6.png)

## What does NoSQL Not Provide!
1. No built-in join
2. No ACID transactions
3. No SQL

## Data Model used by Mongo DB
1. BSON format (binary JSON)
2. Developers can easily map to modern object-oriented languages without a complicated ORM layer. 
3. lightweight,  traversable,  efficient

## CRUD Operation in Mongo DB
1. Create
   1. db.collection.insert( <document> ) 
   2. db.collection.save( <document> ) 
   3. db.collection.update( <query>, <update>, { upsert: true } ) 
2. Read
   1. db.collection.find( <query>, <projection> )
   2. db.collection.findOne( <query>, <projection> ) 
3. Update
   1. db.collection.update( <query>, <update>, <options> ) 
4. Delete
   1. db.collection.remove( <query>, <justOne> ) 


# Installation MongoDB on a Mac M1

### Step 1st -  Install Brew 
> /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

###### Problem I faced 
According to the Homebrew site, to install it, I need to type: 
> brew install wget

I get an error message: -bash: brew: command not found Found this answer. The problem, however, is I don't see brew in /usr/local/bin.
I added the below line to my .bashrc file 
> export PATH=/usr/local/bin:$PATH

Still getting the command not found error.

###### Solution
1. cd /opt/homebrew/bin/
2. PATH=$PATH:/opt/homebrew/bin
3. cd
4. touch .zshrc
5. echo export PATH=$PATH:/opt/homebrew/bin >> .zshrc

Explanation
Run the commands in that order in terminal, you'll be editing the path and creating the missing .zshrc file, exporting the path to this new file.
Now you should be able to use:
> brew doctor

It should say: "Your system is ready to brew."

### Step 2nd - Install Xcode Command-Line Tools
> xcode-select --install


### Step 3rd Installing MongoDB 5.0 Community Edition

1. brew tap mongodb/brew
2. brew update
3. brew install mongodb-community@5.0

Note: Apple's documentation for the current list of Apple hardware using the M1 processor. You can also run the following command to check where brew has installed these files and directories:
> brew --prefix

### Step 4th : Start/Stop MongoDB Community Edition
1. brew services start mongodb-community@5.0
2. brew services stop mongodb-community@5.0



