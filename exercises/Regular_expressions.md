# Regular expressions

## Reading
>Chapters 2 and 3 of Haddock, SHD and CW Dunn (2011)[Practical Computing for Biologists](http://practicalcomputing.org/)

## Getting started
We will be using regular expressions or **regex** to manipulate text files.

- Download [Atom](https://atom.io) if you haven't already.

- Download the `pcfb` folder from [Practical Computing for Biologists](http://practicalcomputing.org/files/pcfb_examples.zip) or the EvoCell github

## Exercise

For regex find and replace, we will be using wildcards in Atom to manipulate text data. Use cmd f to search. Make sure that the Regex option is selected `option cmd /` or click the regex button `.*`.

In an atom window, type:
```
+40 46'N +014 15'E
+21 17'N -157 52'W

```
Use the wildcard `\w` to identify any letter (A-z) or digit (0-9) and remove the direction from the end of each coordinate (e.g N, E, W)



## Resources

How to use regex in Atom http://2017.compciv.org/guide/topics/end-user-software/atom/how-to-use-regex-atom.html
