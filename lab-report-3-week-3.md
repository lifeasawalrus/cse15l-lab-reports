# Problem 1:
The first problem is the reverseInPlace() method.

This test produced a failure in the method:
![Image](/lab3_images/Lab3-p1-test.png)

Here is the output of the test (symptoms)
![Image](/lab3_images/Lab3-p1-symptoms.png)

And here is the bug, and a example of a solution:
![Image](/lab3_images/Lab3-p1-bug.png)
![Image](/lab3_images/Lab3-p1-sln.png)

This problem would be replicated for an array of any size greater than one, and contained different elements at the beginning and end. The issue was that the first element of the array was being overwritten and so the last index was being refilled with its original value. Also, to prevent the array from performing this on every other index in the first half, the array should stop at `.length/2`.

# Problem 2:











