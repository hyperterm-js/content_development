<!-- Confidential + Proprietary Google&#174;-->
<!-- Exercise #1 - findNeedles (required)-->
<!-- This exercise has two required parts:-->
<!--
1. Write an API reference document that explains
how to call this method. Your audience for this
document is an experienced Java programmer.
 
2. Assume you have a chance to send comments or
questions to the person who wrote the code.
Suggest ways to improve the code, for example,
to reduce memory usage or enhance features -->

# findNeedles() API

[Overview](#Overview)
- [findNeedles() example](#Example)
- [findNeedles() error messages](#Errors)

[Use case example](#Uses)

[Code reference](#Code)

## Overview <a name="Overview"/>


**findNeedles()** is a Java-based API that takes two strings, *needles*, an array of **up to 5 strings**,
and *haystack*, a string of unrestricted length, as parameters. It then searches for *needles* in *haystack* and returns each *needle* with the number of times it occured in *haystack*.  

### findNeedles() example:<a name="Example"/>
	
	String haystack = "Heavy rain expected tommorrow.";
	String[] needles = {"Heavy", "rain", "expected", "Friday"};
	findNeedles(haystack, needles);
	
Will return:
	
	Heavy: 1
	rain: 1
	expected: 1
	Friday: 0

### findNeedles() error messages:<a name="Errors"/>

	String haystack = "Heavy rain expected tommorrow.";
	String[] needles = {"Heavy", "rain", "snow", wind", "expected", "Friday"};
	findNeedles(haystack, needles);
	
Will return:
	
	Too many words!

> :memo: **Note:** The array within *String[ ] needles* can only take up to 5 strings. 

## Use case example<a name="Uses"/>

The following is an example of a **findNeedles()** use case:

- SEO keyword indexing:
	- Given a keyword list as *needles* and your target files, each as a "haystack", 
	you can iterate over files and compare your list of *needles* using each 
	file (converted to a string) as a *haystack*. Each *needle* is counted and 
	you can see if your targets are using the list of keywords.
	

## Code reference <a name="Code"/>


```java
    public static void findNeedles(String haystack, String[] needles) {
       if (needles.length > 5) {
           System.err.println("Too many words!");
       } else {
           int[] countArray = new int[needles.length];
           for (int i = 0; i < needles.length; i++) {
               String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
               for (int j = 0; j < words.length; j++) {
                   if (words[j].compareTo(needles[i]) == 0) {
                       countArray[i]++;
                   }
               }
           }
           for (int j = 0; j < needles.length; j++) {
               System.out.println(needles[j] + ": " + countArray[j]);
           }
       }
   }
```
