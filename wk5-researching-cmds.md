# Week 5 (2023-01-12) - Remote Access

---


This week heralded the beginning of the end: the first Skill Demo in 15L. Even after practicing a bunch and making sure I got everything down on my notes, I'm still not confident in my performance. Because of that, here's some advice for the me of the future: get some sleep in before you do anything big.

In any case, for Week 5, we'll be going over researching command line interface (CLI) options, specifically for the `grep` command. All examples are done from the parent directory of a folder called written_2 with multiple folders and text files contained within it.

# grep -r \<string to be searched\> \<file path\>

```
// INPUT:
$ grep -r Honolulu

// OUTPUT:
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Oahu (Including Honolulu)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Halekulani $$$$ 2199 Kalia Road, Honolulu, HI 96815; Tel.
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Hilton Hawaiian Village $$$–$$$$ 2005 Kalia Road, Honolulu,
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96815; Tel. (808) 923-1234 or (800) 233-1234; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        half-hour drive of Honolulu. 387 rooms.
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96816; Tel. (808) 739-8888 or (800) 367-2525; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Outrigger Reef $$$ 2169 Kalia Road, Honolulu, HI 96815; Tel.
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Pacific Beach Hotel $$$ 2490 Kalakaua Avenue,, Honolulu, HI
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Royal Hawaiian $$$$ 2259 Kalakaua Avenue, Honolulu, HI
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96815; Tel. (808) 922-3111 or (800) 325-3535; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96815; Tel. (808) 922-5811 or (800) 325-3535; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Sheraton Waikiki $$$–$$$$ 2255 Kalakaua Avenue, Honolulu,
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        church and the mission schools (which you can still visit in Honolulu)
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        Honolulu. The Calvinistic reforms were soon reversed when Kaahumanu
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        still be toured in Honolulu. He also legalized the hula, Hawaii’s
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        governor was Dole. Queen Liliuokalani lived out her life near Honolulu,
written_2/travel_guides/berlitz1/WhatToHawaii.txt:        Midway. Lying some 1,100 miles northwest of Honolulu, Midway
```

`grep` with the `-r` flag searches recursively through a directory, particularly through every subfolder and file in that directory. Without the `filepath` argument, it searches the entire current working directory for text files containing the specified string. This is useful if you're looking through a bunch of files in various subfolders for a string and don't know the exact path.

```
// INPUT:
$ grep -r Mermaid ./written_2/non-fiction/OUP/

// OUTPUT:
written_2/non-fiction/OUP/Castro/chM.txt:Mermaid 
```

`grep -r` can also look through specific directories when provided one as an argument, which can be useful if you know where the file is located.

# grep -n \<string to be searched\> \<file path\>

```
// INPUT: 
$ grep -r -n Amstelredamme

// OUTPUT:
written_2/travel_guides/berlitz2/Amsterdam-History.txt:13:In 1275 the settlement of Amstelredamme, as it was known, received permission from Count Floris of Holland to transport goods along the river Amstel without incurring tolls, giving the city a monopoly on trade along the river. In 1323 Amstelredamme became a toll-free port for beer, and once a method of preserving herring had been perfected in the late 14th century, the town also had a product with a high profit margin and began exporting fish around Europe.
written_2/travel_guides/berlitz2/Amsterdam-History.txt:14:However, something happened in 1345 which caused Amstelredamme to change from being a mere trading port to a settlement of spiritual importance. A dying man was given a piece of communion bread which he could not swallow. When attendants threw the piece in the fire it would not burn. The event was declared a miracle and within a few years Amstelredamme became a place of pilgrimage, further increasing the wealth flowing into the city.
written_2/travel_guides/berlitz2/Amsterdam-History.txt:48:Perhaps the only specter in the air is the one which worried the inhabitants of old Amstelredamme centuries before; water levels. Global warming over the next few decades threatens to raise water levels around the world, and the Netherlands — “nether” means “low-lying” or “below” — will have to work hard at solving the problem for its future inhabitants.
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:12:Central Amsterdam — what was once the Medieval city — is very small indeed. The port was the lifeblood of the city at that time and ships would sail right into the heart of Amstelredamme, as it was then known. Today, only a few architectural gems are left to remind us of this era, but the tangle of narrow alleyways gives a feel of the hustle and bustle which must have accompanied the traders.
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:19:As its name suggests, Oude Kerk is the earliest Parish church in Amsterdam; work began on it at the start of the 13th century when Amstelredamme was only just starting as a trading town. Over the following three centuries, the church saw several extensions as the population of the city grew, until it took on the interesting and rather over-busy shape it is today — with several chapels adding gables to the original structure. In its early life it was more than a church, acting as a marketplace and hostel for the poor and needy.
```

`grep -n` prints the line number of the specified string, which can be useful for locating certain strings in certain texts; when paired with `-r`, it can be used to search multiple files within subfolders in a directory, as shown above.

```
// INPUT:
$ grep -n Amstelredamme ./written_2/travel_guides/berlitz2/*.txt

// OUTPUT:
./written_2/travel_guides/berlitz2/Amsterdam-History.txt:13:In 1275 the settlement of Amstelredamme, as it was known, received permission from Count Floris of Holland to transport goods along the river Amstel without incurring tolls, giving the city a monopoly on trade along the river. In 1323 Amstelredamme became a toll-free port for beer, and once a method of preserving herring had been perfected in the late 14th century, the town also had a product with a high profit margin and began exporting fish around Europe.
./written_2/travel_guides/berlitz2/Amsterdam-History.txt:14:However, something happened in 1345 which caused Amstelredamme to change from being a mere trading port to a settlement of spiritual importance. A dying man was given a piece of communion bread which he could not swallow. When attendants threw the piece in the fire it would not burn. The event was declared a miracle and within a few years Amstelredamme became a place of pilgrimage, further increasing the wealth flowing into the city.
./written_2/travel_guides/berlitz2/Amsterdam-History.txt:48:Perhaps the only specter in the air is the one which worried the inhabitants of old Amstelredamme centuries before; water levels. Global warming over the next few decades threatens to raise water levels around the world, and the Netherlands — “nether” means “low-lying” or “below” — will have to work hard at solving the problem for its future inhabitants.
./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:12:Central Amsterdam — what was once the Medieval city — is very small indeed. The port was the lifeblood of the city at that time and ships would sail right into the heart of Amstelredamme, as it was then known. Today, only a few architectural gems are left to remind us of this era, but the tangle of narrow alleyways gives a feel of the hustle and bustle which must have accompanied the traders.
./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:19:As its name suggests, Oude Kerk is the earliest Parish church in Amsterdam; work began on it at the start of the 13th century when Amstelredamme was only just starting as a trading town. Over the following three centuries, the church saw several extensions as the population of the city grew, until it took on the interesting and rather over-busy shape it is today — with several chapels adding gables to the original structure. In its early life it was more than a church, acting as a marketplace and hostel for the poor and needy.
```

With a given path, `grep -n` can be used on the identified files; it can even be used on specific named files.

# grep -c \<string to be searched\> \<file path\>

```
// INPUT: 
$ grep -r -c Amsterdam ./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt

// OUTPUT: 
47
```

The `-c` returns the amount of times the identified term appears in a given file; in the above example, we look for the amount of times "Amsterdam" appears in "Amsterdam-WhereToGo.txt". This has plenty of uses, especially if the file specified has important data where its appearances matter.



> Warning: the following example is very, very long as it searches through every file in written_2.

```
// INPUT: 
$ grep -r -c João

// OUTPUT: 
.git/config:0
.git/description:0
.git/FETCH_HEAD:0
.git/HEAD:0
.git/hooks/applypatch-msg.sample:0
.git/hooks/commit-msg.sample:0
.git/hooks/fsmonitor-watchman.sample:0
.git/hooks/post-update.sample:0
.git/hooks/pre-applypatch.sample:0
.git/hooks/pre-commit.sample:0
.git/hooks/pre-merge-commit.sample:0
.git/hooks/pre-push.sample:0
.git/hooks/pre-rebase.sample:0
.git/hooks/pre-receive.sample:0
.git/hooks/prepare-commit-msg.sample:0
.git/hooks/push-to-checkout.sample:0
.git/hooks/update.sample:0
.git/index:0
.git/info/exclude:0
.git/logs/HEAD:0
.git/logs/refs/heads/main:0
.git/logs/refs/remotes/origin/HEAD:0
.git/logs/refs/remotes/upstream/HEAD:0
.git/logs/refs/remotes/upstream/main:0
.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.idx:0
.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.pack:0
.git/packed-refs:0
.git/refs/heads/main:0
.git/refs/remotes/origin/HEAD:0
.git/refs/remotes/upstream/HEAD:0
.git/refs/remotes/upstream/main:0
written_2/non-fiction/OUP/Abernathy/ch1.txt:0
written_2/non-fiction/OUP/Abernathy/ch14.txt:0
written_2/non-fiction/OUP/Abernathy/ch15.txt:0
written_2/non-fiction/OUP/Abernathy/ch2.txt:0
written_2/non-fiction/OUP/Abernathy/ch3.txt:0
written_2/non-fiction/OUP/Abernathy/ch6.txt:0
written_2/non-fiction/OUP/Abernathy/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch8.txt:0
written_2/non-fiction/OUP/Abernathy/ch9.txt:0
written_2/non-fiction/OUP/Berk/ch1.txt:0
written_2/non-fiction/OUP/Berk/ch2.txt:0
written_2/non-fiction/OUP/Berk/CH4.txt:0
written_2/non-fiction/OUP/Berk/ch7.txt:0
written_2/non-fiction/OUP/Castro/chA.txt:0
written_2/non-fiction/OUP/Castro/chB.txt:0
written_2/non-fiction/OUP/Castro/chC.txt:0
written_2/non-fiction/OUP/Castro/chL.txt:0
written_2/non-fiction/OUP/Castro/chM.txt:0
written_2/non-fiction/OUP/Castro/chN.txt:0
written_2/non-fiction/OUP/Castro/chO.txt:0
written_2/non-fiction/OUP/Castro/chP.txt:0
written_2/non-fiction/OUP/Castro/chQ.txt:0
written_2/non-fiction/OUP/Castro/chR.txt:0
written_2/non-fiction/OUP/Castro/chV.txt:0
written_2/non-fiction/OUP/Castro/chW.txt:0
written_2/non-fiction/OUP/Castro/chY.txt:0
written_2/non-fiction/OUP/Castro/chZ.txt:0
written_2/non-fiction/OUP/Fletcher/ch1.txt:0
written_2/non-fiction/OUP/Fletcher/ch10.txt:0
written_2/non-fiction/OUP/Fletcher/ch2.txt:0
written_2/non-fiction/OUP/Fletcher/ch5.txt:0
written_2/non-fiction/OUP/Fletcher/ch6.txt:0
written_2/non-fiction/OUP/Fletcher/ch9.txt:0
written_2/non-fiction/OUP/Kauffman/ch1.txt:0
written_2/non-fiction/OUP/Kauffman/ch10.txt:0
written_2/non-fiction/OUP/Kauffman/ch3.txt:0
written_2/non-fiction/OUP/Kauffman/ch4.txt:0
written_2/non-fiction/OUP/Kauffman/ch5.txt:0
written_2/non-fiction/OUP/Kauffman/ch6.txt:0
written_2/non-fiction/OUP/Kauffman/ch7.txt:0
written_2/non-fiction/OUP/Kauffman/ch8.txt:0
written_2/non-fiction/OUP/Kauffman/ch9.txt:0
written_2/non-fiction/OUP/Rybczynski/ch1.txt:0
written_2/non-fiction/OUP/Rybczynski/ch2.txt:0
written_2/non-fiction/OUP/Rybczynski/ch3.txt:0
written_2/travel_guides/berlitz1/HandRHawaii.txt:0
written_2/travel_guides/berlitz1/HandRHongKong.txt:0
written_2/travel_guides/berlitz1/HandRIbiza.txt:0
written_2/travel_guides/berlitz1/HandRIsrael.txt:0
written_2/travel_guides/berlitz1/HandRIstanbul.txt:0
written_2/travel_guides/berlitz1/HandRJamaica.txt:0
written_2/travel_guides/berlitz1/HandRJerusalem.txt:0
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt:0
written_2/travel_guides/berlitz1/HandRLasVegas.txt:0
written_2/travel_guides/berlitz1/HandRLisbon.txt:0
written_2/travel_guides/berlitz1/HandRLosAngeles.txt:0
written_2/travel_guides/berlitz1/HandRMadeira.txt:0
written_2/travel_guides/berlitz1/HandRMadrid.txt:0
written_2/travel_guides/berlitz1/HandRMallorca.txt:0
written_2/travel_guides/berlitz1/HistoryDublin.txt:0
written_2/travel_guides/berlitz1/HistoryEdinburgh.txt:0
written_2/travel_guides/berlitz1/HistoryEgypt.txt:0
written_2/travel_guides/berlitz1/HistoryFrance.txt:0
written_2/travel_guides/berlitz1/HistoryFWI.txt:0
written_2/travel_guides/berlitz1/HistoryGreek.txt:0
written_2/travel_guides/berlitz1/HistoryHawaii.txt:0
written_2/travel_guides/berlitz1/HistoryHongKong.txt:0
written_2/travel_guides/berlitz1/HistoryIbiza.txt:0
written_2/travel_guides/berlitz1/HistoryIndia.txt:0
written_2/travel_guides/berlitz1/HistoryIsrael.txt:0
written_2/travel_guides/berlitz1/HistoryIstanbul.txt:0
written_2/travel_guides/berlitz1/HistoryItaly.txt:0
written_2/travel_guides/berlitz1/HistoryJamaica.txt:0
written_2/travel_guides/berlitz1/HistoryJapan.txt:0
written_2/travel_guides/berlitz1/HistoryJerusalem.txt:0
written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt:0
written_2/travel_guides/berlitz1/HistoryLasVegas.txt:0
written_2/travel_guides/berlitz1/HistoryMadeira.txt:1
written_2/travel_guides/berlitz1/HistoryMadrid.txt:0
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:0
written_2/travel_guides/berlitz1/HistoryMallorca.txt:0
written_2/travel_guides/berlitz1/IntroDublin.txt:0
written_2/travel_guides/berlitz1/IntroEdinburgh.txt:0
written_2/travel_guides/berlitz1/IntroEgypt.txt:0
written_2/travel_guides/berlitz1/IntroFrance.txt:0
written_2/travel_guides/berlitz1/IntroFWI.txt:0
written_2/travel_guides/berlitz1/IntroGreek.txt:0
written_2/travel_guides/berlitz1/IntroHongKong.txt:0
written_2/travel_guides/berlitz1/IntroIbiza.txt:0
written_2/travel_guides/berlitz1/IntroIndia.txt:0
written_2/travel_guides/berlitz1/IntroIsrael.txt:0
written_2/travel_guides/berlitz1/IntroIstanbul.txt:0
written_2/travel_guides/berlitz1/IntroItaly.txt:0
written_2/travel_guides/berlitz1/IntroJamaica.txt:0
written_2/travel_guides/berlitz1/IntroJapan.txt:0
written_2/travel_guides/berlitz1/IntroJerusalem.txt:0
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt:0
written_2/travel_guides/berlitz1/IntroLasVegas.txt:0
written_2/travel_guides/berlitz1/IntroLosAngeles.txt:0
written_2/travel_guides/berlitz1/IntroMadeira.txt:1
written_2/travel_guides/berlitz1/IntroMadrid.txt:0
written_2/travel_guides/berlitz1/IntroMalaysia.txt:0
written_2/travel_guides/berlitz1/IntroMallorca.txt:0
written_2/travel_guides/berlitz1/JungleMalaysia.txt:0
written_2/travel_guides/berlitz1/WhatToDublin.txt:0
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt:0
written_2/travel_guides/berlitz1/WhatToEgypt.txt:0
written_2/travel_guides/berlitz1/WhatToFrance.txt:0
written_2/travel_guides/berlitz1/WhatToFWI.txt:0
written_2/travel_guides/berlitz1/WhatToGreek.txt:0
written_2/travel_guides/berlitz1/WhatToHawaii.txt:0
written_2/travel_guides/berlitz1/WhatToHongKong.txt:0
written_2/travel_guides/berlitz1/WhatToIbiza.txt:0
written_2/travel_guides/berlitz1/WhatToIndia.txt:0
written_2/travel_guides/berlitz1/WhatToIsrael.txt:0
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:0
written_2/travel_guides/berlitz1/WhatToItaly.txt:0
written_2/travel_guides/berlitz1/WhatToJamaica.txt:0
written_2/travel_guides/berlitz1/WhatToJapan.txt:0
written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt:0
written_2/travel_guides/berlitz1/WhatToLasVegas.txt:0
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt:0
written_2/travel_guides/berlitz1/WhatToMadeira.txt:0
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:0
written_2/travel_guides/berlitz1/WhatToMallorca.txt:0
written_2/travel_guides/berlitz1/WhereToDublin.txt:0
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt:0
written_2/travel_guides/berlitz1/WhereToEgypt.txt:0
written_2/travel_guides/berlitz1/WhereToFrance.txt:0
written_2/travel_guides/berlitz1/WhereToFWI.txt:0
written_2/travel_guides/berlitz1/WhereToGreek.txt:0
written_2/travel_guides/berlitz1/WhereToHawaii.txt:0
written_2/travel_guides/berlitz1/WhereToHongKong.txt:0
written_2/travel_guides/berlitz1/WhereToIbiza.txt:0
written_2/travel_guides/berlitz1/WhereToIndia.txt:0
written_2/travel_guides/berlitz1/WhereToIsrael.txt:0
written_2/travel_guides/berlitz1/WhereToIstanbul.txt:0
written_2/travel_guides/berlitz1/WhereToItaly.txt:0
written_2/travel_guides/berlitz1/WhereToJapan.txt:0
written_2/travel_guides/berlitz1/WhereToJerusalem.txt:0
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt:0
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:0
written_2/travel_guides/berlitz1/WhereToMadeira.txt:5
written_2/travel_guides/berlitz1/WhereToMadrid.txt:0
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:0
written_2/travel_guides/berlitz1/WhereToMallorca.txt:0
written_2/travel_guides/berlitz2/Algarve-History.txt:1
written_2/travel_guides/berlitz2/Algarve-Intro.txt:0
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt:3
written_2/travel_guides/berlitz2/Amsterdam-History.txt:0
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt:0
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Athens-History.txt:0
written_2/travel_guides/berlitz2/Athens-Intro.txt:0
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Bahamas-History.txt:0
written_2/travel_guides/berlitz2/Bahamas-Intro.txt:0
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Bali-History.txt:0
written_2/travel_guides/berlitz2/Bali-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Barcelona-History.txt:0
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Beijing-History.txt:0
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Berlin-History.txt:0
written_2/travel_guides/berlitz2/Berlin-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Bermuda-history.txt:0
written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Budapest-History.txt:0
written_2/travel_guides/berlitz2/Budapest-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt:0
written_2/travel_guides/berlitz2/California-History.txt:0
written_2/travel_guides/berlitz2/California-WhatToDo.txt:0
written_2/travel_guides/berlitz2/California-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Canada-History.txt:0
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:0
written_2/travel_guides/berlitz2/CanaryIslands-History.txt:0
written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:0
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Cancun-History.txt:0
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt:0
written_2/travel_guides/berlitz2/China-History.txt:0
written_2/travel_guides/berlitz2/China-WhatToDo.txt:0
written_2/travel_guides/berlitz2/China-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Costa-History.txt:0
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt:0
written_2/travel_guides/berlitz2/CostaBlanca-History.txt:0
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Crete-History.txt:0
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt:0
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Cuba-History.txt:0
written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Nepal-History.txt:0
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt:0
written_2/travel_guides/berlitz2/NewOrleans-History.txt:0
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Poland-History.txt:0
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Portugal-History.txt:4
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt:1
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt:14
written_2/travel_guides/berlitz2/PuertoRico-History.txt:0
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt:0
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Vallarta-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:0
```

Just like the other flags, `-c` can be used without a filepath argument. However, in the case where you have many, many `.txt` files to sort through, this may not be so helpful.

# grep -n \<string to be searched\> \<file path\>

```
// INPUT: 
$ grep -r -l Amsterdam

// OUTPUT: 
.git/index
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
```

Adding `-l` to the `grep` command lists all files in the designated directory that contain the given string. Adding on `-l` to the `-r` flag can help with information overload by removing the lines to the right of the files which list the content within the file that contains the given string.

```
// INPUT: 
$ grep -r -l propagating

// OUTPUT:
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
```

Listing files that contain the given string can be very useful, but as seen above, the output is usually not numerically sorted in ways that we might consider to be correct. To remedy this, files can be named with the maximum amount of digits included in the numbers. For example, instead of 1, 2, 3, 10, 20, it would be 01, 02, 03, 10, 20.

# Closing Remarks

It's fascinating to see just how much information can be gleaned from bash commands, as well as how flags modify what information is displayed and how. Having all these different options, as well as having similar flags mean different things across different commands really impresses the fact that there's still a lot to learn about bash and terminals in general that I haven't encountered yet. It was also really nice to finally (kind of) understand how terminal commands worked, as someone who's had to install Optifine and modded Minecraft Launchers through cmd for the past 3 years. 

All CLI options were found from Lars Vogel's article [here](https://www.vogella.com/tutorials/UnixGrep/article.html).