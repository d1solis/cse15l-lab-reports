# Lab Report 3 - Researching Commands (Week 5)
**`grep` command:**

The `grep` command takes a string and a file, and print out all the lines in that file that match the string. (The command to search for a pattern in text files).

## First command: `grep -l`
The `grep -l` command is used to print only the names of the files that contain the specified search pattern, instead of printing the matching lines.
1. Example `grep -l "explore" written_2/*/*/*.txt` outputs this:
```
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HistoryEgypt.txt
written_2/travel_guides/berlitz1/HistoryFWI.txt
written_2/travel_guides/berlitz1/HistoryGreek.txt
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/HistoryJapan.txt
written_2/travel_guides/berlitz1/HistoryLasVegas.txt
written_2/travel_guides/berlitz1/IntroEgypt.txt
written_2/travel_guides/berlitz1/IntroJamaica.txt
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
written_2/travel_guides/berlitz1/WhatToGreek.txt
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt
written_2/travel_guides/berlitz1/WhatToLasVegas.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToMadeira.txt
written_2/travel_guides/berlitz1/WhereToDublin.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToIstanbul.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
written_2/travel_guides/berlitz1/WhereToMadrid.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToMallorca.txt
written_2/travel_guides/berlitz2/Algarve-History.txt
written_2/travel_guides/berlitz2/Algarve-Intro.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt
written_2/travel_guides/berlitz2/California-History.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-History.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/CanaryIslands-History.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
written_2/travel_guides/berlitz2/Portugal-History.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/PuertoRico-History.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
This command is searching for the word "explore" in all .txt files in any immediate subdirectories of the `written_2/` directory, and 
printing the names of the files that contain the word "explore". This command is useful if you want to find all files that contain 
a particular word or phrase in a large project with many text files.
 
2. Example `grep -l "Lucayans" written_2/*/*/*.txt` outputs this:
```
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
This command is searching for the word "Lucayans" in all .txt files in any immediate subdirectories of the `written_2/` directory, and 
printing the names of the files that contain the word "Lucayans". This command is useful if you want to find all files that contain 
a particular word or phrase in a large project with many text files.

## Second command: `grep -i`
The `grep -i` command is used to perform a case-insensitive search when searching for a pattern in text files.
1. Example `grep -i "pineapples" written_2/*/*/*.txt` outputs this:
```
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        Pineapples and War
written_2/travel_guides/berlitz1/WhereToFWI.txt:        emporium you’ll have your pick of fresh Martinique pineapples, coconut
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:        of rambutans, pineapples, and bananas, as well as locally made nougat
written_2/travel_guides/berlitz2/China-History.txt:Conservatism and hostility to foreign ideas, however, couldn’t be absolutely maintained. During the Ming era, China imported tobacco, pineapples, peanuts, and syphilis. Thanks to the emancipated Confucian tradition, Christian missionaries were usually welcomed, although they hardly achieved mass conversions. From the Jesuits the Chinese learned mathematics and astronomy; the old observatory still stands in downtown Beijing.
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:Ice cream, fruit, cheese, or flan (crème caramel) are the most popular desserts. In the summer and early autumn you will be spoiled with an enormous array of fruit. The weekly markets — the best place to buy — are full of strawberries, nísperos (a cousin of the lychee), grapes, figs, melons, peaches, apricots, raspberries, pomegranates, grapefruit, lemons, oranges, tangerines, apples, pears, and even locally grown bananas, pineapples, and dates.
```
This command is searching for the word "pineapples" in all .txt files in any immediate subdirectories of the `written_2/` directory, and printing all the lines that contain the word "pineapples", regardless if it is upper case or lower case. This command is useful if you want to perform a search that's not case-sensitive, and you do not want to have to search for all possible variations of the word.

2. Example `grep -i -l "pineapples" written_2/*/*/*.txt` outputs this:
```
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt
```
This command is searching for the word "pineapples" in all .txt files in any immediate subdirectories of the `written_2/` directory, and printing only the names of the files that contain the word "pineapples", regardless if it is upper case or lower case. This command is useful if you want to perform a search that's not case-sensitive and simply looking for the files containing the word or phrase without having to read the text along with it.
