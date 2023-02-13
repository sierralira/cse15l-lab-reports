## Lab Report 3: Researching Commands 

For my research, I chose to find alternative ways to use the `grep` command. The information used in this lab report was collected from the following online resources: [https://linuxhint.com/use-grep-recursively/#:~:text=Grep%20command%20is%20used%20to,from%20the%20top%2Dlevel%20directory](https://linuxhint.com/use-grep-recursively/#:~:text=Grep%20command%20is%20used%20to,from%20the%20top%2Dlevel%20directory), [https://www.softwaretestinghelp.com/grep-command-in-unix/](https://www.softwaretestinghelp.com/grep-command-in-unix/), and [https://wizardzines.com/comics/grep/](https://wizardzines.com/comics/grep/).

### Alternative Way to Use `grep` #1
An alternate way to use `grep` is to use the flag `-r`, making the complete command `grep -r` followed by the string that is desired to be found. 
#### Example 1
In this example, we can see that we never actually gave any files in the command to be searched. From this command, we get the same output that we would if we used the command `grep "Lucayans" written_2/travel_guides/*/*` because the `-r` flag makes the grep command search files from the current directory and all subdirectories. The file that contains the string, Lucayans", is returned as well as the portion of text where the string appears. 

Input: 
```
grep -r "Lucayans"
```
Output: 
```
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themsel
ves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by
 cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared t
hem for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the
East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Baha
mas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towar
ds Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attes
t that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On
 Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water o
n their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 year
s all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fish
eries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
#### Example 2
In this example, once again, we can see that we never actually gave any files in the command to be searched. However, as previously discussed, the `-r` flag makes the grep command search files from the current directory and all subdirectories. All files that contain the string within the directory and its subdirectories as returned as well as the portion of text where the string appears. 

Input: 
 ```
 grep -r "Pharaohs"
 ```
 Output:
 ```
 written_2/travel_guides/berlitz1/HistoryEgypt.txt:        during the New Kingdom and many of the most renowned Pharaohs reigned
written_2/travel_guides/berlitz1/HistoryEgypt.txt:        burial ground for the Pharaohs when Tuthmoses I (1504–1492 b.c. ) was
written_2/travel_guides/berlitz1/IntroEgypt.txt:        wealth of the Pharaohs, and when the backer of the dig, Lord Carnarvon,
written_2/travel_guides/berlitz1/IntroEgypt.txt:        curse of the Pharaohs mummy — and Hollywood was quick to feed our
written_2/travel_guides/berlitz1/IntroEgypt.txt:        coming years. The kingdom of the Pharaohs has many more eras of history
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt:        related to the Pharaohs of Egypt — fashionable imagery of the time
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        important deities — Osiris, Hathor, Isis and others — and the Pharaohs
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        burial places of the great Pharaohs of Ancient Egypt, hidden in a
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        Whilerulingfrompalaces ontheeastbankoftheNile, Pharaohs
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        major funerary site of the ancient Egyptian Pharaohs (c.3100–2755 b.c.
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        southwest wing, you will find 76 cartouches listing Pharaohs throughout
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        Ptolemaic Pharaohs worshipping Horus, and the interior carvings of
written_2/travel_guides/berlitz1/WhereToItaly.txt:        the staggering variety of statues of the Pharaohs of the period around
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt:Rooms 36–39 have a collection of bronzes including votive offerings found at the Idaean
Cave in Crete — mythical birthplace of the god Zeus. Rooms 40 and 41 display artifacts from Egypt covering every era of history in the land of
 the Pharaohs, including the Ptolemaic period when Ptolemy (a general under Alexander the Great, and therefore of Greek descent) took control
of Egypt. One of his descendants was Cleopatra, perhaps this most famous ancient queen.
```

In conclusion, the `grep -r` command allows a whole directory and its subdirectories to be searched for a string rather without having to use a directory pattern or explicitly state files that are desired to be searched. This command is useful when you are not sure of the file pattern to use and if you are not sure exactly where within a directory that a string you are searching for may appear. 


### Alternative Way to Use `grep` #2
An alternate way to use `grep` is to use the flag `-i`, making the complete command `grep -i` followed by the string that is desired to be found and the file/files that will be searched. 
#### Example 1
In this example we can see that even though the string we used in the command was in all capital letters, the string is still located with only the first letter capital in the string in the file. 

Input:
```
grep -i "LUCAYANS" written_2/travel_guides/*/*
```
Output:
```
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themsel
ves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by
 cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared t
hem for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the
East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Baha
mas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towar
ds Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attes
t that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On
 Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water o
n their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 year
s all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fish
eries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
#### Example 2
In this example we can see that even though the string we used in the command was in all lowercase letters, the string is still located with the first letters in each word uppercase in the string in the file. 

Input:
```
grep -i "amsterdam casino" written_2/travel_guides/*/*
```
Output:
```
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt:The Amsterdam Casino at Max Euweplein off Leidseplein offers the opportunity for adults
to gamble (Tel. 620 1006). Open every day from 1:30pm.
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt:The Amsterdam Casino at Max Euweplein off Leidseplein offers the opportunity for adult
s to gamble (Tel. 620 1006). Open every day from 1:30pm.
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:Turn left once through Leidseplein and across the Singelgracht canal, and you will fi
nd the Amsterdam Casino and Lido on your left. On your right, across Stadhouderskade, is a narrow gate leading to Vondelpark. This park, found
ed in 1865, has been called “the lungs of Amsterdam” and was founded after a number of philanthropic city fathers decided that there was a nee
d for a genteel recreation area for the city’s population, many of whom lived in overcrowded slums. The park was named after the Netherlands’
premier poet Joost van den Vondel and designed in the English fashion of the times. Today its 46 hectares (120 acres) have grazing farm animal
s, flocks of parakeets, jogging tracks, and cycle paths. It is the perfect place for a picnic on a summer’s day. The large pavilion, which ope
ned in 1881, was restored and refurbished in 1991 and reopened as the Nederlands Filmmuseum. It now shows more than 1000 films each year inclu
ding many outdoor screenings and other artistic performances in the summer.
```

In conclusion, the `grep -i` makes the search for the string insensitive to case, meaning that the string is found within the file no matter if the letters of the string are uppercase or lowercase. This command is useful when you are not sure of the casing of the string you are searching for. 

### Alternative Way to Use `grep` #3
An alternate way to use `grep` is to use the flag `-c`, making the complete command `grep -c` followed by the string that is desired to be found and the file/files that will be searched. The number after each file is the number of times that a string appears in the file.
#### Example 1
In this example, we can see that the output lists all the files that were searched followed by a number. 

Input:
```
grep -c "Lucayans" written_2/travel_guides/berlitz2/Bahamas*.txt
```
Output:
```
written_2/travel_guides/berlitz2/Bahamas-History.txt:2
written_2/travel_guides/berlitz2/Bahamas-Intro.txt:0
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt:0
```
#### Example 2
In this example, we can see that the output lists all the files that were searched followed by a number. The number after each file is the number of times that a string appears in the file.

Input:
```
grep -c "Algarve" written_2/travel_guides/*/Algarve*.txt
```
Output:
```
written_2/travel_guides/berlitz2/Algarve-History.txt:12
written_2/travel_guides/berlitz2/Algarve-Intro.txt:12
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt:46
```
In conclusion, the `grep -c` returns the files that were searched as well as the number of times that the string appears within the file. One situation that this command could be useful is if, for example, you have a text file containing a list of all the grades received on a test and you want to determine how many A's were received. 

### Alternative Way to Use `grep` #4
An alternate way to use `grep` is to use the flag `-l`, making the complete command `grep -l` followed by the string that is desired to be found and the file/files that will be searched. 
#### Example 1
In this example, we can see that the output shows the file that the string was found in but does not show any of the actual text of where the string was found within the file. This is different from the usual output of `grep` as the command usually would display the text where the string was found. 

Input:
```
grep -l "Lucayans"  written_2/travel_guides/*/*
```
Output:
```
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
#### Example 2
In this example, we can see that the output lists all the files that the string was found in but does not show any of the actual text of where the string was found within the files.  This is different from the usual output of `grep` as the command usually would display the text where the string was found. 

Input:
```
grep -l "Hong Kong" written_2/travel_guides/*/*
```
Output:
```
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
```
In conclusion, the `grep -l` returns the paths of the files that the string was found in without returning any of the actual text in the file where the string  was found, unlike the usual 'grep' command. This could be useful, for example, if you have multiple files, each with names of students in a section, and you want to determine how many students have a specific name, like Ben. 

