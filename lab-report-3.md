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

> -name

*[title](https://www.example.com)*

1. 

```
$
x
```

2. 
 
```
$
x
```

> -iname

*[title](https://www.example.com)*

1. 
 
```
$ find ~ -empty
x
```

2. 
 
```
$
x
```

> -maxdepth

*[title](https://www.example.com)*

1. 
 
```
$ find ~ -maxdepth 1
x
```

2. 
 
```
$ find ~ -maxdepth 2
x
```

> -type

*[title](https://www.example.com)*

1. 
 
```
$ find ~ -type f
x
```

2. 
 
```
$ find ~ -type d
x
```
