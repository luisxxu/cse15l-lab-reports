# Week 5 Lab Report

## Alternate ways to use the less command

Each option was found from this source: [phoenixnap.com](https://phoenixnap.com/kb/less-command-in-linux#:~:text=The%20less%20command%20is%20a,resulting%20in%20fast%20loading%20speeds.)

**-f option**

```
less -f ./written_2
```
<img width="539" alt="Screen Shot 2023-02-13 at 9 33 24 PM" src="https://user-images.githubusercontent.com/114445896/218649232-02ae7ff0-268e-4fb9-b94e-6a369afcbc7b.png">

Using this command shows the written_2 directory and its contents in the less format. Whereas less usually shows the contents of a text file, the -f option allows you to see the contents of a directory instead.

```
less -f ./written_2/travel_guides/berlitz1
```
<img width="628" alt="Screen Shot 2023-02-13 at 9 43 04 PM" src="https://user-images.githubusercontent.com/114445896/218649767-01475139-bc35-423d-a109-f1a63dadfe8c.png">

Using this command on a directory like berlitz1 that contains text files shows all the text files in the directory, as well as some other useful information like date created.

**-m option**

```
less -m ./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
```
<img width="627" alt="Screen Shot 2023-02-13 at 9 51 52 PM" src="https://user-images.githubusercontent.com/114445896/218651405-edf2c0fb-f36a-499a-8b0c-4557762ef507.png">

Using this -m option shows the percentage on the bottom line, which represents how far into the text file has been read, similar to a progress bar.

```
less -m ./written_2/travel_guides/berlitz1/WhatToGreek.txt
```
<img width="611" alt="Screen Shot 2023-02-13 at 9 52 28 PM" src="https://user-images.githubusercontent.com/114445896/218652263-2211b874-fdd6-4a16-bb09-3f3a0223c0f8.png">

For smaller text files, like the WhatToGreek.txt file, this option can show the relative size while being scrolled through and reveal how big the file is.

**-p(string) option**

```
less -pthe ./written_2/travel_guides/berlitz1/WhatToGreek.txt
```
<img width="630" alt="Screen Shot 2023-02-13 at 9 56 11 PM" src="https://user-images.githubusercontent.com/114445896/218652597-cb47908d-a97e-4f50-a781-7373b157fe24.png">

Using the -p(string) option lets you highlight a specified string in the text file using the less interface.

```
less -pCalifornia ./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
```
<img width="654" alt="Screen Shot 2023-02-13 at 9 56 48 PM" src="https://user-images.githubusercontent.com/114445896/218652672-e5c2a242-e5f2-43aa-849d-58c594f478b8.png">

The -p(string) option is helpful for identifying certain key words in the text file that aren't common.

**-X option**

```
less -X ./written_2/travel_guides/berlitz1/WhereToMadrid.txt
```
<img width="632" alt="Screen Shot 2023-02-13 at 9 57 57 PM" src="https://user-images.githubusercontent.com/114445896/218654662-161c622b-4053-47af-aa38-0b345786865e.png">

The -X option shows the text file and keeps the view of the text file even after exiting for the less interface.

```
less -X ./written_2/travel_guides/berlitz1/HistoryIsrael.txt
```
<img width="612" alt="Screen Shot 2023-02-13 at 9 58 30 PM" src="https://user-images.githubusercontent.com/114445896/218654698-a72cabf1-c200-4516-8066-82c7ccc9d664.png">

This option is particularly useful if there's information, like an error message, and can be used simultaneously while using the terminal.
