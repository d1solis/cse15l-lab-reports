# Lab Report 5 - Researching Commands (Week 9)
**`find` command:**

The `find` command recursively traverses the given path and lists all the files in that directory and subdirectories. 
(The command to search for files in a directory hiearchy).

## First command: `find [path] -name [filename]`
The `find [path] -name [filename]` command is used to search for a file with a specific name.
1. Example `find written_2 -name "*-History.txt"` outputs this:
```
written_2/travel_guides/berlitz2/Algarve-History.txt
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Athens-History.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bali-History.txt
written_2/travel_guides/berlitz2/Barcelona-History.txt
written_2/travel_guides/berlitz2/Beijing-History.txt
written_2/travel_guides/berlitz2/Berlin-History.txt
written_2/travel_guides/berlitz2/Budapest-History.txt
written_2/travel_guides/berlitz2/California-History.txt
written_2/travel_guides/berlitz2/Canada-History.txt
written_2/travel_guides/berlitz2/CanaryIslands-History.txt
written_2/travel_guides/berlitz2/Cancun-History.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/Costa-History.txt
written_2/travel_guides/berlitz2/CostaBlanca-History.txt
written_2/travel_guides/berlitz2/Crete-History.txt
written_2/travel_guides/berlitz2/Cuba-History.txt
written_2/travel_guides/berlitz2/Nepal-History.txt
written_2/travel_guides/berlitz2/NewOrleans-History.txt
written_2/travel_guides/berlitz2/Poland-History.txt
written_2/travel_guides/berlitz2/Portugal-History.txt
written_2/travel_guides/berlitz2/PuertoRico-History.txt
written_2/travel_guides/berlitz2/Vallarta-History.txt
```
This command is searching the directory `written_2` and its subdirectories for any file with a name that ends with `-History.txt` and will display the path 
to each matching file it finds. This command is useful if you are locating specific file names ending in `.txt` in a directory with a large amount of files.

2. Example `find written_2 -name "*Cancun*"` outputs this:
```
written_2/travel_guides/berlitz2/Cancun-History.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
```
This command is searching the directory `written_2` and its subdirectories for any file with a name that starts with `Cancun` and will display the path 
to each matching file it finds. This command is useful if you are locating specific files name starting with particular word in a directory with a large 
amount of files.

## Second command: `find [path] -size [filename]`
The `find [path] -size [filename]` command is used to search for files based on their size.
1. Example `find written_2 -size +100k` outputs this:
```
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
```
This command is searching the directory `written_2` and its subdirectories that are **greater** than 100 kilobytes in size. This command is useful if you need to look
for files with a specific size and manage them accordingly (moving, archiving, deleting). 


1. Example `find written_2 -size -1500c` outputs this:
```
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
```
This command is searching the directory `written_2` and its subdirectories that are **less** than 1500 bytes in size. This command is useful if you need to look
for files with a specific size and manage them accordingly (moving, archiving, deleting).
