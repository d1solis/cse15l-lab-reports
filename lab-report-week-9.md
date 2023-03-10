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
to each matching file it finds. This command is useful if you are locating specific a file name ending in `.txt` in a directory with a large amount of files.

2. Example `find written_2 -name "*Cancun*"` outputs this:
```
written_2/travel_guides/berlitz2/Cancun-History.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
```
This command is searching the directory `written_2` and its subdirectories for any file with a name that starts with `Cancun` and will display the path 
to each matching file it finds. This command is useful if you are locating specific a file name starting with particular word in a directory with a large 
amount of files.
