# Problem 1:
The first problem is the reverseInPlace() method.

This test produced a failure in the method:
![Image](/lab3_images/Lab3-p1-test.png)

Here is the output of the test (symptoms)
![Image](/lab3_images/Lab3-p1-symptoms.png)

And here is the bug, and an example of a solution:
![Image](/lab3_images/Lab3-p1-bug.png)
![Image](/lab3_images/Lab3-p1-sln.png)

This problem would be replicated for an array of any size greater than one, and contained different elements at the beginning and end. The issue was that the first element of the array was being overwritten and so the last index was being refilled with its original value. Also, to prevent the array from performing this on every other index in the first half, the array should stop at `.length/2`.

# Problem 2:
For the second problem we will be looking at the `merge` method from ListExamples.


This test produced a failure in the method:
![Image](/lab3_images/Lab3-p2-test.png)

Here is the output of the test (symptoms)
![Image](/lab3_images/Lab3-p2-symptoms.png)

And here is the bug, and an example of a solution:
![Image](/lab3_images/Lab3-p2-bug.png)
![Image](/lab3_images/Lab3-p2-sln.png)

An OutOfMemoryError was triggered as a symptom. This was caused by the program entering an infinite loop. Any input outside of empty lists would have caused this, as the index2 was not being incremented as expected. This filled the computers memory until the program eventually crashed.