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

# findNeedles

[Overview](#Overview)

[Uses](#Uses)

[Code reference](#Code)

## Overview
<a name="Overview"/>

**findNeedles** is a simple function that takes two strings, one string *needles* 
and another string *haystack*, and searches for *needles* in *haystack*. 

## Uses
<a name="Uses"/>
Although quite simple, depending on what you do with them once you find them, **findNeedles** has several practical uses. For instance:

1) SEO keyword indexing:
	- Given a keyword list, we will call your *needles*, and your target files, the larger "haystack", 
	you can iterate over files and compare your list of *needles* using each 
	file (converted to a string) as a *haystack*. For each *needle*, count them and return 
	the result by file to see if your targets are using the list of preferred keywords.
2) Terminology cleansing:
	- Given a list of terms you want need to change in your texts, 
	we will call your *needles*, and your target files, the larger "haystack", you can 
	iterate over files and find and replace your *needles* using each 
	file (converted to a string) as a *haystack*. For each *needle*, provide an alternate term and replace it 
	in your files. 


## Code reference
<a name="Code"/>
```java
public static void findNeedles(String haystack, String[] needles) {
if (needles.length > 5) {
System.err.println("Too many words!");
} else {
int[] countArray = new int[needles.length];
for (int i = 0; i< needles.length; i++) { String[] words=haystack.split("[ \" \'\t\n\b\f\r]", 0);\
for (int j=0; j
< words.length; j++) { if (words[j].compareTo(needles[i])==0) { countArray[i]++;\
} } } for (int j=0; j
< needles.length; j++) { System.out.println(needles[j] +":" + countArray[j]); } } }
```
