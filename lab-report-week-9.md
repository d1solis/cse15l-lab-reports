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

## Second command: `find [path] -size [filesize]`
The `find [path] -size [filesize]` command is used to search for files based on their size.
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
This command is searching the directory `written_2` and its subdirectories that are **greater** than `100 kilobytes` in size. This command is useful if you need to look
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
This command is searching the directory `written_2` and its subdirectories that are **less** than `1500 bytes` in size. This command is useful if you need to look
for files with a specific size and manage them accordingly (moving, archiving, deleting).

## Third command: `find [path] -name [filename] -exec grep [name] {} \;`
The `find [path] -name [filename] -exec grep [name] {} \;` command is used to search for a specific text string in a file with a particular filename, within a given directory path and its subdirectories.
1. Example `find written_2 -name "*.txt" -exec grep "coconuts" {} \;` outputs this:
```
crops including bananas, coconuts, and citrus fruit. It has a beautiful
Hainan Island. This tropical island off the southernmost tip of China, nearly four times the size of Corsica, provides China with coffee, coconuts, sugar, and rubber. It’s also destined for promotion as one of those paradise islands Western tourists dream about. The original inhabitants, members of the Li and Miao minorities, live in the rainforests of the interior, preserving a rich folklore; Han Chinese make up most of the coastal population. The island’s biggest city, Haikou (on the north shore), has a bustling street life. The beautiful, palm-shaded beaches are on the southern shore — big enough, the Chinese reckon, for 100,000 sunbathers.
Cayo Coco is named not for coconuts but for a bird: the ibis, as revealed in Hemingway’s Islands in the Stream. The author patrolled these shores in World War II on the lookout for Nazis. Ibises and other wading birds, often pink flamingoes, can be seen balancing in the brackish waters around the principal causeway and a smaller causeway connecting the cay to Cayo Guillermo.
```
This command is searching for all files ending with the `.txt` extension in the directory `written_2` and its subdirectories, and then searching for the string `coconuts` inside those files. This command is useful as it can save time and effort by automating the search for specific files and text patterns within a directory and its subdirectories.

1. Example `find written_2 -name "*.txt" -exec grep "iguana" {} \;` outputs this:
```
pigs and ate iguana, both native to the island. They were highly
        find the last few Jamaican iguanas and yellow snakes. The string of
        with monkeys, mouse-deer, iguanas, and peacocks.
At the end of Leidsestraat is Leidseplein, probably the busiest in the city and a major focus for “R&R” in the city. The bars and cafés spill out onto the square which strangely has no real point of focus, unlike Rembrandtsplein. Look out for a small grassy area, with sculptures of life-size iguanas and other large lizards. The narrow streets leading off the square are filled with cinemas, concert halls, and intimate live venues. There is also a busy VVV Amsterdam Tourist Office.
Traveling north from George Town you’ll pass Three Sisters Rock, a formation that lies just offshore from a sandy beach; the three rocks are said to represent three sisters who drowned in the waters here. Gradually the island narrows, and past Rolleville, Great Exuma gives way to the Exuma Cays, a ribbon of small islands of which only four are inhabited. Stanial Cay offers accommodation as well as yachting supplies. It also has an airfield with regular service from Fort Lauderdale on the Florida coast. These cays are home to the endangered iguana along with numerous rare plant species. A 22-mile (35-km) stretch north of Conch Cut has been protected for future generations by the creation of the Exuma Cays Land and Sea Park, 175 sq miles (453 sq km) of land and sea that includes some of the best yet most remote beaches in the Bahamas. The park is only accessible by boat — except for the occasional powerboats bringing passengers over from Nassau for a day of snorkeling and picnics on the beach, the only sounds you’ll hear will be the wind whipping through the sails of yachts anchored offshore.
These two islands lie 225 miles (360 km) south of Nassau and are totally off the beaten path for most tourists today, though they were often visited during the age of steam ships. Columbus described them as “the fragrant islands” after the smell of cascarilla, an indigenous tree; the bark is a major ingredient in perfumes, medicines, and in the Italian aperitif Campari. The Ocean Den marine cave system in the Bight of Acklins is one of the most impressive in the Bahamas. The totally unspoiled long sandy beaches provide a rich environment for birds and animal life. The area to the west of the two islands is a shallow sheltered lagoon where many small cays offer protection to a rare species of iguana.
Fifty miles (80 km) off the coast is Mona Island, called “the Galapagos of Puerto Rico.” This isolated place, characterized by a coastline of high cliffs, is home to turtles, iguanas, and endangered pelicans. There is no human settlement today, but there is evidence that Taíno Indians once lived here. Columbus is also said to have landed, as did Ponce de León. Camping trips of the “commune-with nature” variety can be arranged from Mayagüez.
Just beyond the plaza is the Cuale River, and in its center, a shady retreat — an island, found between the two traffic bridges. Birds twitter, men read the papers over a cup of coffee, and a little girl plays with an iguana outside a shop that sells the same reptiles stuffed. At the western end of the island, the small Museo Río Cuale features archeological artifacts found in the region. Adjoining the upper bridge, the municipal mercado (market) has a range of handicrafts for sale, with traditional foods sold on the second floor.
Another neighboring venue for birdwatching is Ventanilla Estuary, where iguanas and crocodiles can be viewed in their natural habitat. Iguanas can also be seen at the nearby El Potrero iguana ranch.
```
This command is searching for all files ending with the `.txt` extension in the directory `written_2` and its subdirectories, and then searching for the string `iguana` inside those files. This command is useful if you have a large number of text files and you want to search for a specific string within all of them.

## Fourth command: `find [path] -atime [time]`
The `find [path] -name [time]` command is used to find files based on date or time accessed.
1. Example `find written_2 -atime -2` outputs this:
```
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chB.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chL.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chO.txt
written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Castro/chQ.txt
written_2/non-fiction/OUP/Castro/chR.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/non-fiction/OUP/Castro/chZ.txt
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/non-fiction/OUP/Rybczynski/ch3.txt
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```
This command is searching for files and directories inside the `written_2` directory that were accessed **less than or equal** to 2 days ago. This command is useful
if you want to find files that haven't been accessed in a certain amount of time, and consider whether they are still needed or can be deleted to free up disk space.

2. Example `find written_2 -atime +10` outputs this:
```
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMadrid.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/HistoryDublin.txt
written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
written_2/travel_guides/berlitz1/HistoryEgypt.txt
written_2/travel_guides/berlitz1/HistoryFWI.txt
written_2/travel_guides/berlitz1/HistoryFrance.txt
written_2/travel_guides/berlitz1/HistoryGreek.txt
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/HistoryIbiza.txt
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/HistoryIsrael.txt
written_2/travel_guides/berlitz1/HistoryIstanbul.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt
written_2/travel_guides/berlitz1/HistoryJamaica.txt
written_2/travel_guides/berlitz1/HistoryJapan.txt
written_2/travel_guides/berlitz1/HistoryJerusalem.txt
written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt
written_2/travel_guides/berlitz1/HistoryLasVegas.txt
written_2/travel_guides/berlitz1/HistoryMadeira.txt
written_2/travel_guides/berlitz1/HistoryMadrid.txt
written_2/travel_guides/berlitz1/HistoryMalaysia.txt
written_2/travel_guides/berlitz1/HistoryMallorca.txt
written_2/travel_guides/berlitz1/IntroDublin.txt
written_2/travel_guides/berlitz1/IntroEdinburgh.txt
written_2/travel_guides/berlitz1/IntroEgypt.txt
written_2/travel_guides/berlitz1/IntroFWI.txt
written_2/travel_guides/berlitz1/IntroFrance.txt
written_2/travel_guides/berlitz1/IntroGreek.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/IntroIbiza.txt
written_2/travel_guides/berlitz1/IntroIndia.txt
written_2/travel_guides/berlitz1/IntroIsrael.txt
written_2/travel_guides/berlitz1/IntroIstanbul.txt
written_2/travel_guides/berlitz1/IntroItaly.txt
written_2/travel_guides/berlitz1/IntroJamaica.txt
written_2/travel_guides/berlitz1/IntroJapan.txt
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
written_2/travel_guides/berlitz1/IntroLasVegas.txt
written_2/travel_guides/berlitz1/IntroLosAngeles.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt
written_2/travel_guides/berlitz1/IntroMadrid.txt
written_2/travel_guides/berlitz1/IntroMalaysia.txt
written_2/travel_guides/berlitz1/IntroMallorca.txt
written_2/travel_guides/berlitz1/JungleMalaysia.txt
written_2/travel_guides/berlitz1/WhatToDublin.txt
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
written_2/travel_guides/berlitz1/WhatToEgypt.txt
written_2/travel_guides/berlitz1/WhatToFWI.txt
written_2/travel_guides/berlitz1/WhatToFrance.txt
written_2/travel_guides/berlitz1/WhatToGreek.txt
written_2/travel_guides/berlitz1/WhatToHawaii.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhatToIndia.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhatToIstanbul.txt
written_2/travel_guides/berlitz1/WhatToItaly.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt
written_2/travel_guides/berlitz1/WhatToJapan.txt
written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhatToLasVegas.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToMadeira.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhatToMallorca.txt
written_2/travel_guides/berlitz1/WhereToDublin.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
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
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-History.txt
written_2/travel_guides/berlitz2/Athens-Intro.txt
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Bali-History.txt
written_2/travel_guides/berlitz2/Bali-WhatToDo.txt
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt
written_2/travel_guides/berlitz2/Barcelona-History.txt
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Beijing-History.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt
written_2/travel_guides/berlitz2/Berlin-History.txt
written_2/travel_guides/berlitz2/Berlin-WhatToDo.txt
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-history.txt
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
written_2/travel_guides/berlitz2/Budapest-History.txt
written_2/travel_guides/berlitz2/Budapest-WhatToDo.txt
written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt
written_2/travel_guides/berlitz2/California-History.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-History.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/CanaryIslands-History.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2/travel_guides/berlitz2/Cancun-History.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/China-WhatToDo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-History.txt
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/CostaBlanca-History.txt
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-History.txt
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-History.txt
written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/Nepal-History.txt
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt
written_2/travel_guides/berlitz2/NewOrleans-History.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
written_2/travel_guides/berlitz2/Poland-History.txt
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-History.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/PuertoRico-History.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
This command is searching for files and directories inside the `written_2` directory that were accessed **more than** 10 days ago. This command is useful
if you want to audit file access, and identify files that may have been accessed without authorization or you can use it to investigate issues related to file access, such as identifying files that have been recently accessed or modified.


## Sources Cited:
1. [find(1) — Linux manual page](https://man7.org/linux/man-pages/man1/find.1.html)
2. [find command in Linux with examples](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)
3. [How to Use the find Command in Linux](https://www.howtogeek.com/771399/how-to-use-the-find-command-in-linux/)
4. [10 ways to use the Linux find command](https://www.redhat.com/sysadmin/linux-find-command)
5. [40 Best Examples of Find command in Linux](https://geekflare.com/linux-find-commands/)
6. [ChatGPT](https://openai.com/blog/chatgpt/)
