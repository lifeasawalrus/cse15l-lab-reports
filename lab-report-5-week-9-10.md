# Lab Report 5 Week 9/10
grade.sh:
```
  0 # Create your grading script here
  1 
  2 #set -e
  3 
  4 CP="./lib/junit-4.13.2.jar:./lib/hamcrest-core-1.3.jar:."
  5 
  6 rm -rf student-submission
  7 git clone $1 student-submission 2> trash.txt
  8 
  9 if ! test -f ./student-submission/ListExamples.java; then
 10     echo "ListExamples.java file not found!"
 11     exit 1
 12 fi
 13 
 14 cp TestListExamples.java ./student-submission/
 15 cp -r lib/ ./student-submission/
 16 cd ./student-submission/
 17 
 18 if ! javac -cp $CP *.java; then
 19     echo "compile failure"
 20     exit 2
 21 else echo "compilation successful"
 22 fi
 23 
 24 java -cp $CP org.junit.runner.JUnitCore TestListExamples > test-results.txt
 25 
 26 grep Failures test-results.txt

```

Result:

Example1:

![Image](/lab5-9_images/Lab_5_evidence_of_GradeServer1.png)

Example2:

![Image](/lab5-9_images/Lab_5_evidence_of_GradeServer2.png)

Example3:

![Image](/lab5-9_images/Lab_5_evidence_of_GradeServer3.png)

## Code Trace:
Let's walk through what happened on example 2.

Line 4 sets a string parameter CP to the classpath that will be 
used for this assignment.

Line 6 recursively removes all files and data stored from the previous 
grading instance (if available).

Line 7 produces standard error output that simply gives feedback
on the git clone process. All of this output is redirected 
to a file called `trash.txt` in order to clean up the output
printed to the screen. Return code zero.

Next we have the first `if` statement at line 9. This line checks 
to see if student's ListExamples.java file was submitted 
properly. In this case, it did not, so we enter line 10.

The command at line 10 sends an error message through standard 
output to be printed to the screen and let the student know 
that their file was not submitted properly (In this case, 
their file was improperly placed in a directory). Return code zero.

Line 11 exits the script, storing error code `1`.
Thus, the rest of the code from lines 12-26 are not able to run.
Return code nonzero.