# How to use this to learn

## Before Starting:

Before we begin section one, take a look at the file bisect-01. This is a shell script. [LINK TO SHELL SCRIPT VIDEO] You can run it and it will do things for you. Read it line by line. Here's the gist of what each line is doing:

echo word > file
The echo command prints something. The inequality sign there assigns the output of echo to a file. So if we write "echo xyz > file.txt" then "xyz" will be written to file.txt. If you go and open file.txt, you'll see xyz written there because of the echo command. You should try this in the terminal.

git add file
This is a git [LINK TO GIT VIDEO] command that adds a file to the staging area.

&&
The double ampersand here allows us to execute multiple commands. Try this in your terminal: echo "What's " && echo "up?" 

git commit -m "Some message"
This creates a commit based on our staged changes. The -m indicates that a message will be attached to this commit, and that message will be whatever is in between the following quotation marks.

sed -i -e 's/boat/car/g' test.txt
sed stands for "Stream EDit." This line uses regular expressions [LINK TO REGEX VIDEO] to replace every instance of 'boat' with 'car' in test.txt. The s/ means that a replacement is going on, boat is the word being targeted, car is what replaces the target word (more properly, pattern). The /g flag at the end stands for "global" so that every occurence of 'boat' will be replaced with 'car' and not just the first one. 

## bisect-01

0. To understand this example, you will need to know the words to the song, "Row, row, row your boat." If you don't know the words already, it goes like this:

"Row, row, row your boat
Gently down the stream
Merrily, merrily, merrily, merrily
Life is but a dream."

Now you know.

1. Run the ./bisect-01 script. You can accomplish this by cd-ing into the project folder from terminal and typing ./bisect-01. 

2. Type "git log" in your terminal and scroll up. You'll notice a series of messages that read like this: "Commit 1", "Commit 2", "Commit 3", etc. Those are the messages that were added since we used git commit -m "message" to add messages to each commit. You'll also see an author (usually your username) and a date on which the commit was made.

3.  Most importantly, you'll see a SHA value. SHA stands for Secure Hash Algorithm, and that's all you need to know about it right now. Each commit has a unique SHA value. Find the SHA value for the commit labeled "Commit 1".

4. Run this command in your terminal, without quotes: "git bisect start HEAD <SHA Value from Step 3>"

5. Then, you can manually look at the contents of test.txt, using 'git bisect good' and 'git bisect bad' as necessary to indicate which commits are good or bad.

6. git bisect reset

7. Once you have done all the previous steps, you can revert the commit identified to be bad: git revert <commit identified as bad>

8. Continue to Part II where the tests are automated.

## bisect-02

This is the setup for the second bisect tutorial. What you'll want to do here is to

0. Run the ./bisect-setup-02 script if you didn't already do part 01

1. Run the ./bisect-02 script

2. git log

3. Find the SHA value for the commit labeled "Commit 11"

4. git bisect start HEAD <SHA Value from Step 3>

5. git bisect run ./test_nightmare

6. Step 5 automated the same general idea that you did manually in Part 1.

7. git bisect reset

8. git revert <bad commit>
