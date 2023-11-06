*Lab Report 3 - Bugs and Commands*

*Sunday, 5 November 2023*

---

## Part 1 - Bugs

1. Choose one of the bugs from week 4’s lab:

The bug in the ```reversed``` array method.

2. A failure-inducing input for the buggy program, as a JUnit test and any associated code:

```
@Test
public void testReversed() {
  int[] input = {1, 2, 3, 4, 5};
  assertArrayEquals(new int[]{5, 4, 3, 2, 1}, ArrayExamples.reversed(input));
}
```

4. An input that doesn’t induce a failure, as a JUnit test and any associated code:

```
@Test
public void testReversed() {
  int[] input = {0};
  assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input));
}
```

5. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above):

> The output when the test failed (the symptom)

![Image](labreport3fail.png)

> The output when the test was a success

![Image](labreport3success.png)

6. The bug, as the before-and-after code change required to fix it:

> Before: the buggy code
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
```

> After: the fixed code
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```

7. Briefly describe why the fix addresses the issue:

The ```reversed``` method should return a new array with all the elements of the input array in reversed order. The problem with the initial code is that it is copying elements from ```newArray``` into the input ```arr``` in reversed order, then returning the input ```arr``` and not a new array. Moreover, the elements copied from ```newArray``` into ```arr``` are all ```0```. When we initialize the ```newArray``` in ```int[] newArray = new int[arr.length];```, the initial values will be 0 for each element in the array since in Java, integer arrays are initialized to 0 by default. This is why the input in #4 which was an array with a single element 0 (```int[] input = {0};```) did not induce a failure.

The change I made to fix the code made sure that it copies the elements from the input ```arr``` into the new array ```newArray``` (instead of the other way around) and then returns ```newArray``` instead of ```arr```.

---

## Part 2 - Researching Commands

The ```find``` command

> -size

> This option specifies the size of the file you want to find.

*[Source](https://www.example.com)*

1. This command finds all files that are greater than 10MB, which can be useful when...

```
$ find /home/docsearch/technical/biomed -size +10M

```

2. This command finds all files that are smaller than 100MB, which can be useful when...
 
```
$ find /home/docsearch/technical/911report -size -100M
/home/docsearch/technical/911report
/home/docsearch/technical/911report/chapter-13.1.txt
/home/docsearch/technical/911report/chapter-6.txt
/home/docsearch/technical/911report/chapter-13.2.txt
/home/docsearch/technical/911report/chapter-5.txt
/home/docsearch/technical/911report/chapter-1.txt
/home/docsearch/technical/911report/chapter-13.3.txt
/home/docsearch/technical/911report/chapter-12.txt
/home/docsearch/technical/911report/chapter-11.txt
/home/docsearch/technical/911report/chapter-13.5.txt
/home/docsearch/technical/911report/chapter-13.4.txt
/home/docsearch/technical/911report/chapter-8.txt
/home/docsearch/technical/911report/chapter-10.txt
/home/docsearch/technical/911report/chapter-7.txt
/home/docsearch/technical/911report/chapter-2.txt
/home/docsearch/technical/911report/preface.txt
/home/docsearch/technical/911report/chapter-9.txt
/home/docsearch/technical/911report/chapter-3.txt
```

> -iname

> This option is like -name, but the match is case insensitive. For example, the pattern `Fo*` matches the file names `Foo`, `foo`, `FO0`, `FOO`, `fOO`, etc.

*[Source](https://www.example.com)*

1. This command finds all files that ..., which can be useful when...
 
```
$ find /home/docsearch/technical/911report -iname *CHAPTER*
/home/docsearch/technical/911report/chapter-13.1.txt
/home/docsearch/technical/911report/chapter-6.txt
/home/docsearch/technical/911report/chapter-13.2.txt
/home/docsearch/technical/911report/chapter-5.txt
/home/docsearch/technical/911report/chapter-1.txt
/home/docsearch/technical/911report/chapter-13.3.txt
/home/docsearch/technical/911report/chapter-12.txt
/home/docsearch/technical/911report/chapter-11.txt
/home/docsearch/technical/911report/chapter-13.5.txt
/home/docsearch/technical/911report/chapter-13.4.txt
/home/docsearch/technical/911report/chapter-8.txt
/home/docsearch/technical/911report/chapter-10.txt
/home/docsearch/technical/911report/chapter-7.txt
/home/docsearch/technical/911report/chapter-2.txt
/home/docsearch/technical/911report/chapter-9.txt
/home/docsearch/technical/911report/chapter-3.txt
```

2. This command finds all files that ..., which can be useful when...
 
```
$ find /home/docsearch/technical/911report -iname *chAPTer-13
/home/docsearch/technical/911report/chapter-13.1.txt
/home/docsearch/technical/911report/chapter-13.2.txt
/home/docsearch/technical/911report/chapter-13.3.txt
/home/docsearch/technical/911report/chapter-13.5.txt
/home/docsearch/technical/911report/chapter-13.4.txt
```

> -maxdepth

> This option limits the depth of searches by the number of directories you want to go into after the starting point.

*[Source](https://www.example.com)*

1. This command will only find files that are only 1 directory deep, ... This is useful because...
 
```
$ find /home/docsearch/technical -maxdepth 1
/home/docsearch/technical
/home/docsearch/technical/biomed
/home/docsearch/technical/911report
```

2. This command will only find files that are 2 directories deep, ... This can be useful when...
 
```
$ find /home/docsearch/technical -maxdepth 2 -name *1471-2180-2*
/home/docsearch/technical/biomed/1471-2180-2-16.txt
/home/docsearch/technical/biomed/1471-2180-2-1.txt
/home/docsearch/technical/biomed/1471-2180-2-2.txt
/home/docsearch/technical/biomed/1471-2180-2-13.txt
/home/docsearch/technical/biomed/1471-2180-2-7.txt
/home/docsearch/technical/biomed/1471-2180-2-32.txt
/home/docsearch/technical/biomed/1471-2180-2-22.txt
/home/docsearch/technical/biomed/1471-2180-2-38.txt
/home/docsearch/technical/biomed/1471-2180-2-35.txt
/home/docsearch/technical/biomed/1471-2180-2-26.txt
/home/docsearch/technical/biomed/1471-2180-2-20.txt
/home/docsearch/technical/biomed/1471-2180-2-29.txt
```

> -type

> This option specifies the type of file you want to find.

*[Source](https://www.example.com)*

1. ```-type f``` specifies that you want to look for regular files (all the file paths; the actual files and not the ones that are just directories). Regular files include common types of files, such as text files and script files. This can be useful when you just want to look for file paths and don't want to include all the directory names.
 
```
$ find /home/docsearch/technical/911report -type f
/home/docsearch/technical/911report/chapter-13.1.txt
/home/docsearch/technical/911report/chapter-6.txt
/home/docsearch/technical/911report/chapter-13.2.txt
/home/docsearch/technical/911report/chapter-5.txt
/home/docsearch/technical/911report/chapter-1.txt
/home/docsearch/technical/911report/chapter-13.3.txt
/home/docsearch/technical/911report/chapter-12.txt
/home/docsearch/technical/911report/chapter-11.txt
/home/docsearch/technical/911report/chapter-13.5.txt
/home/docsearch/technical/911report/chapter-13.4.txt
/home/docsearch/technical/911report/chapter-8.txt
/home/docsearch/technical/911report/chapter-10.txt
/home/docsearch/technical/911report/chapter-7.txt
/home/docsearch/technical/911report/chapter-2.txt
/home/docsearch/technical/911report/preface.txt
/home/docsearch/technical/911report/chapter-9.txt
/home/docsearch/technical/911report/chapter-3.txt
```

2. ```-type d``` specifies that you want to look for directories only. This is useful when ...
 
```
$ find /home/docsearch/technical -type d
/home/docsearch/technical
/home/docsearch/technical/biomed
/home/docsearch/technical/911report
```
