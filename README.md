# How to use this to learn

## Before Starting:

Before starting, review the files in this repository and understand what they are all doing.

## bisect-01

This is the setup for the first bisect tutorial. What you'll want to do here is to

0. Learn the words to the song, "Row, Row, Row your boat"

1. Run the ./bisect-01 script

2. git log

3. Find the SHA value for the commit labeled "Commit 1"

4. git bisect start HEAD <SHA Value from Step 3>

5. Then, you can manually look at the contents of test.txt, using 'git bisect good' and 'git bisect bad' as necessary to indicate which commits are good or bad.

6. git bisect reset

7. Once you have done all the previous steps, you can revert the commit identified to be bad: git revert <bad commit>

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
