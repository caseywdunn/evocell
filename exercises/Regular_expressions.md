# Regular expressions

## Reading
>Chapters 2 and 3 of Haddock, SHD and CW Dunn (2011)[Practical Computing for Biologists](http://practicalcomputing.org/)

## Getting started
We will be using regular expressions or **regex** to manipulate text files.

- Download [Atom](https://atom.io) if you haven't already.

- Download the `pcfb` folder from [Practical Computing for Biologists](http://practicalcomputing.org/files/pcfb_examples.zip) or the EvoCell github

## Introduction

For regex find and replace, we will be using wildcards in Atom to manipulate text data. Use cmd f to search. Make sure that the Regex option is selected `option cmd /` or click the regex button `.*` that can be found just above 'Find All'.

In an atom window, type:
```
+40 46'N +014 15'E
+21 17'N -157 52'W
```
Use the wildcard `\w` to identify any letter (A-z) or digit (0-9) and remove the direction from the end of each coordinate (e.g N, E, W)

You can also use `()` to capture text.

Type into a fresh atom window:

```
5th
1st
2nd
3rd
```
You can search for each separate letter with `\w\w\w`. If you click replace, you will remove everything.

To keep just the first number in this list, you can use `()` to capture it by searching for `(\w)\w\w` and using the replacement term `$1`. You could keep the first two using `(\w)(\w)\w` and replacing with `$1$2`, or even rearrange these by replacing with `$2$1`.



## Exercise

## Tips

Some documents or pasted data may have non-ASCII unicode characters. This can cause problems when trying to run scripts or manipulate the data using python or R. You can search for any non-ASCII unicode character using `[^\x00-\x7F]`.

## Resources

How to use regex in Atom http://2017.compciv.org/guide/topics/end-user-software/atom/how-to-use-regex-atom.html
