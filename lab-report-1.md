*Lab Report 1*

*Monday, 9 October 2023*

---

## Task

For each of the commands cd, ls, and cat, and using the workspace you created in this lab, share an example of:
1. Using the command with no arguments.
2. Using the command with a path to a directory as an argument.
3. Using the command with a path to a file as an argument.

For each, include:
1. A screenshot or Markdown code block showing the command and its output.
2. What the working directory was before the command was run.
3. A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
4. Indicate whether the output is an error or not, and if it’s an error, explain why it’s an error.

---

## cd
*Change Directory: used to switch the current working directory to the given path*

> cd

![Image](cd1.png)

* Working directory before the command was run: /home

* Output explanation: Using the command 'cd' with no argument does not change anything. The initial working directory, as displayed by the command 'pwd,' does not get switched; it remains the same before and after running 'cd' with no arguments.

* The output is not an error. The 'cd' command produces no output when it works. In this case, it was not an error and no changes were made.

> cd lecture1

![Image](cd2.png)

* Working directory before the command was run: /home

* Output explanation: Running the command 'cd lecture1' switched the current working directory, /home, to /home/lecture1, which can be seen after running 'pwd' the second time.

* The output is not an error. After running 'cd lecture1,' no output was produced which means it worked. Further, the working directory printed after running the command was /home/lecture1, which is consistent with the expected results.

> cd Hello.java

![Image](cd3.png)

* Working directory before the command was run: /home/lecture1

* Output explanation: The initial working directory before running 'cd Hello.java' was /home/lecture1. After running 'cd Hello.java' the current working directory displayed by 'pwd' remains the same. Since Hello.java is a file and not a directory, the command was unable to switch the current working directory.

* The output is an error because the 'cd' command is used to switch the current working directory to the given path, which must be a directory. It cannot switch the current working directory to a file.

---

## ls
*List: used to list the files and folders in the given path*

> ls

![Image](ls1.png)

* Working directory before the command was run: /home

* Output explanation: The 'ls' command with no arguments simply lists the files and folders in the current working directory since no specific path was given as an argument. In this case, the current working directory was /home therefore 'ls' printed out the folder lecture1 and the java file lab1.java, which can be seen in the image below are the only two files and folders in the /home working directory.

![Image](ls11.png)

* The output is not an error.

> ls lecture1

![Image](ls2.png)

* Working directory before the command was run: /home

* Output explanation: The command 'ls lecture1' lists the files and folders in the /home/lecture1 path. As shown in the image below, there are four files and folders under lecture1, namely 'Hello.class', 'Hello.java', 'messages', and 'README', which are consistent with the output shown in the first image above.

* Another thing to note is that the argument given to the command in 'ls lecture1' is not an absolute path. 'lecture1' is simply a relative path. The terminal automatically adds the relative path to the end of the current working directory to combine it and produce an absolute path. In this case, the absolute path becomes '/home/lecture1'.

![Image](ls11.png)

* The output is not an error.

> ls Hello.java / ls lab1.java

![Image](ls3.png)

* Working directory before the command was run: /home/lecture1

* Output 1 explanation: When 'ls Hello.java' was run, the output was 'Hello.java' since 'Hello.java' does not contain any other files or folders besides itself. Moreover, the 'Hello.java' file is within the current working directory (/home/lecture1). The output is not an error.

* Output 2 explanation: When 'ls lab1.java' was run, the output was an error as the command is unable to access the file 'lab1.java'. That file is not within the current working directory of /home/lecture1. That file is in the working directory /home, as shown in the image below. The output is an error.

![Image](ls31.png)

---

## cat
*Concatenate: used to print the contents of one or more files given by the paths*

> cat

![Image](cat1.png)

* Working directory before the command was run: /home

* Output explanation: When 'cat' was run without any arguments, it reads from standard input (stdin) and writes to standard output (stdout). Whatever is typed and entered into the keyboard will be displayed on the screen, as shown in the image above. The current working directory does not change.

* Note: This was an unexpected output as it is not something we have discussed in lecture. I did some research to try and understand the output on a surface level, however, I still do not fully understand what happened.

* I do not believe the output is an error.

> cat lecture1 / cat lecture1/messages

![Image](cat2.png)

* Working directory before the command was run: /home

* Output explanation: For both of the commands 'cat lecture1' and 'cat lecture1/messages', these paths refer to a directory and not a file. The 'cat' command is used to print the contents of one or more files, so when given a path that refers to a directory, the output simply states that the path is a directory. Nothing gets printed out and the current working directory stays the same, too.

* The output is not an error.

> cat en-us.txt / cat es-mx.txt id.txt zh-cn.txt

![Image](cat3.png)

* Working directory before the command was run: /home/lecture1/messages

* Output explanation: The first command printed out the contents of the 'en-us.txt' file. The second command printed out the contents of the three files in order of 'es-mx.txt', 'id.txt', and 'zh-cn.txt'. All the contents printed out were in plain text form, and no errors were produced since all the .txt files were within the current working directory of /home/lecture1/messages. The current working directory did not change.

* Both the outputs are not errors.
