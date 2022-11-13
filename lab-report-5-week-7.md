# Lab report 5 Week 7

## Part 1

Here specific vim commands to change the DocSearchServer.java file to accept a path, rather than hardcoding the "./technical" path.

Access the file and append `+74` to jump to the line of interest.

![Image](/lab5_images/labreport5-1.png)

![Image](/lab5_images/labreport5-2.png)

`f<Shift>'` this command "finds" the `"` char.

![Image](/lab5_images/labreport5-3.png)

`ci<Shift>9` this "changes inside ()" deleting the contents within the parenthesis that the cursor is within. Then enters INSERT mode.

![Image](/lab5_images/labreport5-4.png)

`args[1]<Esc>` types the variable in and leaves INSERT mode.

![Image](/lab5_images/labreport5-5.png)

`<Shift>Z<Shift>Z` Saves file and exits

![Image](/lab5_images/labreport5-6.png)

## Part 2

The first option, starting in VSCode and scp-ing the new file over took about 36 seconds. Using vim from inside the ssh only took about 14 seconds. I misspelled the scp the first try which slowed down the speed of makind this update.

I would much prefer the second method. I am pretty well practiced at vim, and switching between servers, using scp, and sending files adds unnecessary steps to the process.

Something that may affect my choice in process is if I'm updating and pushing a git file I do prefer to use VSCode for that because the IDE is optimized for using github, and I find the preview extremely helpful particularly while editing mark-down files.