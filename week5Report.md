# Week 5 Lab Report: Researching Commands

The command I chose to research is `grep`.

## `-l` and `-c`

The first command-line options I found for `grep` (on [Wikibooks](https://en.wikibooks.org/wiki/Grep)) are `-l` and `-c`. The `-l` option is described to "output matching files only", whire the `-c` option is described to "output count of matching lines only". In other words, rather than printing the matching contents of the file, `-l` and `-c` allow for only compacted results to be displayed.

```bash
written_2 % grep -Rl "Batu Renggong"
./travel_guides/berlitz2/Bali-History.txt
./travel_guides/berlitz2/Bali-WhereToGo.txt
```

This command recursively searches the entire directory for files containing "Batu Renggong", then outputs only the names of the matching files due to the `-l` option, rather than the entire matching lines. This is useful for compacting the amount of data shown to the user and making it more readable.

```bash
written_2 % grep -Rl "San Diego"
./non-fiction/OUP/Castro/chC.txt
./non-fiction/OUP/Castro/chA.txt
./travel_guides/berlitz1/WhereToLosAngeles.txt
./travel_guides/berlitz1/WhatToLasVegas.txt
./travel_guides/berlitz2/California-WhereToGo.txt
./travel_guides/berlitz2/California-History.txt
./travel_guides/berlitz2/Vallarta-History.txt
./travel_guides/berlitz2/California-WhatToDo.txt
./travel_guides/berlitz2/Vallarta-WhereToGo.txt
...etc
```

This is the same usage of the command, this time for the string "San Diego". In cases where there are large numbers of files found like this one, compacting the data makes it much easier to read the command output.

```bash
written_2 % grep -Rc "the"
./non-fiction/.DS_Store:0
./non-fiction/OUP/Berk/CH4-s.xml:0
./non-fiction/OUP/Berk/ch2-np.xml:0
./non-fiction/OUP/Berk/ch2-s.xml:0
./non-fiction/OUP/Berk/ch2-vp.xml:0
./non-fiction/OUP/Berk/ch2.txt:183
./non-fiction/OUP/Berk/ch7-s.xml:0
./non-fiction/OUP/Berk/CH4-np.xml:0
./non-fiction/OUP/Berk/ch1.txt:153
./non-fiction/OUP/Berk/CH4.txt:189
...etc
```

This command recursively searches the directory for files containing "the", and counts the number of matching lines in each file. This could be useful for analyzing large sets of text files for given words and their frequencies, such as in statistical analysis.

## `-i`

Another command-line option I found for `grep` (on [Wikibooks](https://en.wikibooks.org/wiki/Grep)) is `-i`. This option ignores case when looking for matching lines.

```bash
written_2 % grep -Rl "hawaii"
./travel_guides/berlitz1/HistoryHawaii-hepple.xml
./travel_guides/berlitz1/HandRHawaii-hepple.xml
./travel_guides/berlitz1/WhatToHawaii-hepple.xml
./travel_guides/berlitz1/WhereToHawaii-hepple.xml
./travel_guides/berlitz1/HandRHawaii.txt
./travel_guides/berlitz2/Bahamas-Intro-hepple.xml
./technical/biomed/1471-2407-3-5-hepple.xml
./technical/biomed/1471-2148-1-6-hepple.xml
./technical/biomed/1471-2407-2-3-hepple.xml
./technical/biomed/1472-6874-2-13-hepple.xml
./technical/biomed/1471-2407-3-5.anc
./technical/biomed/bcr285-hepple.xml
```

This command recursively searches the directory for files containing "hawaii" (case-sensitive).

```bash
written_2 % grep -Rli "hawaii"
./travel_guides/berlitz1/WhatToHawaii.txt
./travel_guides/berlitz1/HandRHawaii.anc
./travel_guides/berlitz1/HistoryHawaii-hepple.xml
./travel_guides/berlitz1/HandRHawaii-hepple.xml
./travel_guides/berlitz1/WhereToHawaii.anc
./travel_guides/berlitz1/WhatToHawaii-hepple.xml
./travel_guides/berlitz1/HistoryHawaii.txt
./travel_guides/berlitz1/WhatToHawaii.anc
./travel_guides/berlitz1/WhereToHawaii.txt
./travel_guides/berlitz1/WhereToHawaii-hepple.xml
...etc
```

On the other hand, this command recursively searches the directory for files containing "hawaii" (not case-sensitive). In this case, since the query matches "Hawaii" or "HAWAII" as well, much more matching files are found. This option is useful for when case is not important to the user.

```bash
written_2 % grep -Rli "HTML"
./travel_guides/berlitz1/HandRMadrid-hepple.xml
./travel_guides/berlitz1/HandRMadrid.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/tech_adden-hepple.xml
./technical/government/Env_Prot_Agen/jeffordslieberm.txt
./technical/government/Env_Prot_Agen/tech_sectiong-hepple.xml
./technical/government/Env_Prot_Agen/tech_sectiong.txt
...etc
```

This command recursively searches for "HTML" (not case-sensitive), finding both references to "html" in .xml file data as well as some references to "HTML" within the actual text file contents.


## RegEx
A useful behavior I found for `grep` (on [Wikibooks](https://en.wikibooks.org/wiki/Grep)) is RegEx pattern matching, which allows for RegEx patterns to be used for matching file contents instead of just strings.

```bash
written_2 % ls ./travel_guides/berlitz1 | grep '.*\(anc\|txt\)'
HandRHawaii.anc
HandRHawaii.txt
HandRHongKong.anc
HandRHongKong.txt
HandRIbiza.anc
HandRIbiza.txt
HandRIsrael.anc
HandRIsrael.txt
...etc
```

This command lists all the files in `berlitz1/`, then pipes the output into a command that searches for lines matching the ".\*(anc|txt)" pattern. Essentially, the command finds all .txt or .anc files. 

```bash
written_2 % grep -R '<link targets="[a-z]*-[a-z][0-9]*"/>'
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r0"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r1"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r2"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r3"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r4"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r5"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r6"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r7"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r8"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r9"/>
./non-fiction/OUP/Berk/CH4-s.xml:        <link targets="s-r10"/>
...etc
```

This command searches for all lines matching the RegEx `<link targets="[a-z]*-[a-z][0-9]*"/>`, which is essentially any string of the form `<link targets="[letters]-[letter][digits]"\>`. In general, the command is useful for looking for patterns when you already know generally what form the desired data is of.

## `-o`

The last command-line option I found for `grep` (on [Wikibooks](https://en.wikibooks.org/wiki/Grep)) is `-o`. This option outputs the matched parts of the file, rather than the entire lines containing the matches.

```bash
written_2 % grep -Ro "[a-zA-Z]\{15,\}"
./non-fiction/OUP/Berk/ch2.txt:individualistic
./non-fiction/OUP/Berk/ch2.txt:individualistic
./non-fiction/OUP/Berk/ch2.txt:interdependence
./non-fiction/OUP/Berk/ch2.txt:psychologically
./non-fiction/OUP/Berk/ch2.txt:interdependency
./non-fiction/OUP/Berk/ch2.txt:interdependency
./non-fiction/OUP/Berk/ch2.txt:interconnection
./non-fiction/OUP/Berk/ch2.txt:counterproductive
./non-fiction/OUP/Berk/ch2.txt:inappropriately
./non-fiction/OUP/Berk/ch2.txt:intersubjectivity
...etc
```

This command searches for all lines matching the RegEx `[a-zA-Z]{15, }`, which is any string that is 15 letters or longer. The `-o` option prints only the matched part of the line rather than the entire line, so the command as a whole prints every string that is 15 letters or longer. This makes it much easier to find the desired output, rather than having to search through the long printed lines for 15 letter strings.

```bash
written_2 % grep -Ro '[a-zA-Z]*="[a-zA-Z]*"'
./non-fiction/OUP/Berk/CH4-s.xml:gi="s"
./non-fiction/OUP/Berk/CH4-s.xml:name="xces"
./non-fiction/OUP/Berk/CH4-s.xml:label="s"
./non-fiction/OUP/Berk/CH4-s.xml:as="xces"
./non-fiction/OUP/Berk/CH4-s.xml:name="id"
./non-fiction/OUP/Berk/CH4-s.xml:label="s"
./non-fiction/OUP/Berk/CH4-s.xml:as="xces"
./non-fiction/OUP/Berk/CH4-s.xml:name="id"
./non-fiction/OUP/Berk/CH4-s.xml:label="s"
...etc
```

This command searches for all lines matching the RegEx `[a-zA-Z]*="[a-zA-Z]*"`, which is any string of the form `[letters]="[letters]"`. Again, the `-o` option prints only the matched part of the line.
