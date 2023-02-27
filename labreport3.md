# Week 5 Lab Report

## Alternate ways to use the less command

Each option was found from this source: [phoenixnap.com](https://phoenixnap.com/kb/less-command-in-linux#:~:text=The%20less%20command%20is%20a,resulting%20in%20fast%20loading%20speeds.)

**-f option**

```
less -f ./written_2
```

```
drwxr-sr-x   2 cs15lwi23apa ieng6_cs15lwi23  4096 Jan 11 15:36 perl5/
drwxr-s---   4 cs15lwi23apa ieng6_cs15lwi23  4096 Feb  8 13:30 skill-demo1-data/
drwxr-s---   5 cs15lwi23apa ieng6_cs15lwi23  4096 Feb  8 13:29 skill-demo1-server/
drwxr-s---   4 cs15lwi23apa ieng6_cs15lwi23  4096 Jan 18 16:22 wavelet/
```

Using this command shows the written_2 directory and its contents in the less format. Whereas less usually shows the contents of a text file, the -f option allows you to see the contents of a directory instead.

```
less -f ./written_2/travel_guides/berlitz1
```

```
-rwxr-x--- 1 cs15lwi23apa ieng6_cs15lwi23  65176 Feb  8 13:30 WhereToMadeira.txt*
-rwxr-x--- 1 cs15lwi23apa ieng6_cs15lwi23  78028 Feb  8 13:30 WhereToMadrid.txt*
-rwxr-x--- 1 cs15lwi23apa ieng6_cs15lwi23 180940 Feb  8 13:30 WhereToMalaysia.txt*
-rwxr-x--- 1 cs15lwi23apa ieng6_cs15lwi23  74270 Feb  8 13:30 WhereToMallorca.txt*
```

Using this command on a directory like berlitz1 that contains text files shows all the text files in the directory, as well as some other useful information like date created.

**-m option**

```
less -m ./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
```

```
        Walter had a keen interest in the old West and, in order
        to create a diversion for the ravenous patrons, began building a ghost
        town. It was a slow process; many of its buildings were brought piece
        by piece from abandoned desert towns. Eventually, a theme park was
87%
```

Using this -m option shows the percentage on the bottom line, which represents how far into the text file has been read, similar to a progress bar.

```
less -m ./written_2/travel_guides/berlitz1/WhatToGreek.txt
```

```
        With its centuries-old seafaring tradition, the Aegean has
        long been a lure to sports sailors. Many of the elite of Athens have
        sailed the short distance from the capital for a weekend at a deserted
        inlet. Until recently, there was little for ordinary mortals who lacked
        a yacht, but now there are sailing fleets waiting to be hired either
30%
```

For smaller text files, like the WhatToGreek.txt file, this option can show the relative size while being scrolled through and reveal how big the file is.

**-p(string) option**

```
less -pthe ./written_2/travel_guides/berlitz1/WhatToGreek.txt

  Although ==the== warm, clear waters of ==the== Aegean constitute a
  near-perfect diving environment, until recently ==the== Greek government
  was rightly concerned about ==the== possible damage divers might do to
  submerged ancient sites, and diving was prohibited. However, attitudes
```


Using the -p(string) option lets you highlight a specified string in the text file using the less interface (imagine the highlighted words are between ==).

```
less -pCalifornia ./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt

        The adjacent George C. Page Museum of La Brea Discoveries
        (5801 Wilshire Boulevard) provides fascinating insight into Ice Age
        life in southern ==California==. The 15-minute La Brea Story is an
        introductory film illustrating how the animals became trapped in the
```


The -p(string) option is helpful for identifying certain key words in the text file that aren't common.

**-X option**

```
less -X ./written_2/travel_guides/berlitz1/WhereToMadrid.

        the proportions of Madrid's most elegant architectural ensemble from a
        seat at one of the outdoor cafes.
        Leading out of each of the arched doorways of the Plaza is a
[cs15lwi23apa@ieng6-203]:skill-demo1-data:527$ 
```

The -X option shows the text file and keeps the view of the text file even after exiting for the less interface.

```
less -X ./written_2/travel_guides/berlitz1/HistoryIsrael.txt

        azed, the Temple destroyed, and its people forced into exile and
        slavery.
        By the fourth century b.c. the Babylonians had been
        overthrown, and the Israelites returned to their land, which was now
[cs15lwi23apa@ieng6-203]:skill-demo1-data:528$ 
```

This option is particularly useful if there's information, like an error message, and can be used simultaneously while using the terminal.
