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

## `-v`

Another command-line option I found for `grep` (on [Wikibooks](https://en.wikibooks.org/wiki/Grep)) is `-v`. This option inverts the match, essentially outputting the files that do not match the desired string.

```bash
```

## `-e`

## `-o`
