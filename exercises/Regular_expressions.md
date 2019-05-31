# Regular expressions

## Reading
>Chapters 2 and 3 of Haddock, SHD and CW Dunn (2011) [Practical Computing for Biologists](http://practicalcomputing.org/)

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
The wildcard `\w` identifies any letter (A-z) or digit (0-9).

You can type `'\w` to  and remove the direction from the end of each coordinate (e.g N, E, W)

### Capture

You can also use `()` to capture text.

Type into a fresh atom window:

```
5th
1st
2nd
3rd
```
You can search for each separate letter with `\w\w\w`. If you click replace, you will remove everything.

To keep just the first number in this list, you can use `()` to capture it by searching for `(\w)\w\w` and using the replacement term `$1`. You could keep the first two characters using `(\w)(\w)\w` and replacing with `$1$2`, or even rearrange these by replacing with `$2$1`.

You can also add text with your replacement term, e.g. `Position $1`

### Quantifiers

You can adjust how many characters you select by adding a quantifier. Plus (+) enables you to change different types of characters at once, for example `\w+` would match a term one or more times in succession.

Type into a fresh Atom window:
```
Agalma elegans
Frillagalma vityazi
Cordagalma tottoni
Mus musculus
```
`\w+` will select all of the characters in the document.

To keep only the first letter of the genus and the species name, you can put `(\w)\w+ (\w+)` in the search term and `$1. $2`in the replacement term

### Escaping

If you want to search for `\` , `+`, or `()` specifically, you have to modify how it is interpreted in the search. As you use punctuation, `+`, and `()` as special characters, you have to use `\` to remove the special meaning of this character when you search for it.

Take for example:
```
Physalia physalis (Linnaeus)
```
You can use `\` in front of the character `(` to remove the special meaning of this character. This is called 'Escaping'.

You can search for: `\w+ \w+ \(\w+\)` to select all of the text. Capture it with `(\w+) (\w+) \((\w+)\)` and replace with, for example, `$1_$2_$3`

### Other special search terms

- `\t` searches for tabs, which is especially useful for text files that are tab separated (tsv)
- `\s` searches for white space
- `\n` (or `\r` depending on the program) searches for the end of the line
- `\d` A digit from 0-9
- `.*` (or just `.`) Any letter, number or symbol. Not end of line characters.

Special searches `\t`,`\s`,`\d` can be combined with `+`

## Exercise 1

Go to [GenBank](https://www.ncbi.nlm.nih.gov/genbank/) and download a series of protein sequences for your favourite species and proteins (approx 4 or 5). Or use the file `FPexamples.fta` in the `pcfb`>`examples` folder.

Modify the header so that the name begins with `>` followed by the Genbank id and the genus name, all separated by a `_`.

For example:
```
>AER00326.1 GFP, partial [Aequorea victoria]
NGIKVNFKIRHNIEDGSVQLADHYQQNTPIGDGPVLLPDNHYLS
```

Would become:
```
>AER00326.1_Aequorea
NGIKVNFKIRHNIEDGSVQLADHYQQNTPIGDGPVLLPDNHYLS
```

## Make your own wildcards

Sometimes you need to make your own wildcards. You can do this using `[]`.

For example, you only want to select the nucleotides A G C T, you could search for `[AGCT]`.

- Uppercase letters can be selected using `[A-Z]`, or lowercase `[a-z]` (you need to select the option 'Case sensitive - Aa' in Atom). `[A-Za-z]` gives any letter
- [0-9\.] matches any digit or decimal point

If we open up the example file `LatLon.txt` in `pcfb`>`examples`, you will find latitude and longitude data. There are five locations, but the latitude and longitude for each location are found on separate lines.

To put them on the same line, separated by a tab, you would use the wildcard `(\"[NS])` to select only lines that end with N or S. You also want to remove the end of line character `\n` (`\r` in some text editors). So if you search for `(\"[NS])\n` and replace it with `$1\t` where `\t` is a tab, you are able to put the latitudes and longitudes on the same line.

Let's say we want to add `-` to WS lines and remove the compass point from NE lines.

Search for `([0-9]+ [0-9 \'\.\"]+)[WS]` and replace with `-$1` . Exchange `WS` for `NE` and replace with `$1`.

## Exercise 2



## Tips

Some documents or pasted data may have non-ASCII unicode characters. This can cause problems when trying to run scripts or manipulate the data using python or R. You can search for any non-ASCII unicode character using `[^\x00-\x7F]`.

## Resources

How to use regex in Atom http://2017.compciv.org/guide/topics/end-user-software/atom/how-to-use-regex-atom.html
