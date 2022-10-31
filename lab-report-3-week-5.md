# Lab Report 3

## `Grep`: `-i`, `-c`, `-m`.

<span style="color:maroon">Example 1: Using -i to find a word regarless of casing</span>

The command here searches through everything in `technical/plos/journal*` to see how many times "may 1997" or "May 1997" shows up, regardless of casing. It prints out the fileand the context around it. It would be useful for finding files that mention a specific date that you want.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -i "may 1997"  technical/plos/journal*
technical/plos/journal.pbio.0020001.txt:        output between the developing and already developed countries (Gibbs 1995; May 1997;
technical/plos/journal.pbio.0020001.txt:        the world (Gibbs 1995; May 1997; Alonso and Fernández-Juricic 2001; Vohora and Vohora
technical/plos/journal.pbio.0020001.txt:        assessing scientific productivity or technical advances (May 1997). More relevant
technical/plos/journal.pbio.0020001.txt:        and development (May 1997). The proportional change in the number of publications, using
```

<span style="color:maroon">Example 2: Using `-c` to count the number of times a word shows up within a file or files.</span>

The `-c`  can operate on a single file or a file. In this case, I chose `technical/plos/pmed.0020238.txt` to see how many times the word "the" shows up in the file. The command counts up how many times it does and returns an integer. This is useful for only having to count up how many times a word or phrase shows up in a single file.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -c -i "the" technical/plos/pmed.0020238.txt
31
```

<span style="color:maroon">Example 3: Using `-m #` to search through only a certain number of files:.</span>

This command limited the number of loops to stop at 5 (still including 0). It searched through the `technical/911report/chapter-9.txt` file and produced this output. This is useful for figuring out where a certain word is in the file if it's at the beginning without reading through the whole file or opening it.

```
$ grep -i -m 4 "level"  technical/911report/chapter-9.txt
            Stairwells A and C ran from the 110th floor to the raised mezzanine level of the
                lobby. Stairwell B ran from the 107th floor to level B6, six floors below ground,
                and was accessible from the West Street lobby level, which was one floor below the
                West Street lobby level; and the B4 level, four stories below ground. The burning
```

## find: `-type`, `-empty`, `-atime`

<span style="color:maroon"> Example 1: Using `-type` to specify what file we're looking for:.</span>

This command determines that the user is looking for a file with the name `chapter*.txt`. This is useful for if there are several files of the same name, but they are different file types. 

```
$ find -type f -name chapter*.txt 
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-8.txt
./technical/911report/chapter-9.txt
```


<span style="color:maroon"> Example 2: Using `-empty` to find which files are empty:.</span>

This command finds all the files that are empty. It is useful if you want to find all files to be removed later. 

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ find /tmp -type f -empty
/tmp/03aac8fa-e968-4443-a9fd-8cc289eac60b.tmp
/tmp/3aef4007-11a7-43fa-9b69-ac5ebfb917c4.tmp
/tmp/409b6ecc-b955-41d5-8aaa-d6b334b16dde.tmp
/tmp/759c72a1-c5aa-4ca0-8032-f5fa64593ba6.tmp
/tmp/jna-93166819/jna14615899170306579324.dll.x
/tmp/jna-93166819/jna2319828102910322187.dll.x
/tmp/mat-debug-10768.log
/tmp/mat-debug-10996.log
/tmp/mat-debug-12396.log
/tmp/mat-debug-12672.log
/tmp/mat-debug-1348.log
/tmp/mat-debug-14376.log
/tmp/mat-debug-14472.log
/tmp/mat-debug-14728.log
/tmp/mat-debug-14832.log
/tmp/mat-debug-14900.log
/tmp/mat-debug-15004.log
/tmp/mat-debug-15024.log
/tmp/mat-debug-16284.log
/tmp/mat-debug-16512.log
/tmp/mat-debug-1684.log
/tmp/mat-debug-17340.log
/tmp/mat-debug-17712.log
/tmp/mat-debug-18664.log
/tmp/mat-debug-19356.log
/tmp/mat-debug-19840.log
/tmp/mat-debug-20300.log
/tmp/mat-debug-21024.log
/tmp/mat-debug-21584.log
/tmp/mat-debug-22376.log
/tmp/mat-debug-2296.log
/tmp/mat-debug-23704.log
/tmp/mat-debug-23940.log
/tmp/mat-debug-24212.log
/tmp/mat-debug-24464.log
/tmp/mat-debug-24500.log
/tmp/mat-debug-24544.log
/tmp/mat-debug-24584.log
/tmp/mat-debug-24712.log
/tmp/mat-debug-25796.log
/tmp/mat-debug-26300.log
/tmp/mat-debug-26440.log
/tmp/mat-debug-26608.log
/tmp/mat-debug-27804.log
/tmp/mat-debug-27876.log
/tmp/mat-debug-28104.log
/tmp/mat-debug-28364.log
/tmp/mat-debug-28712.log
/tmp/mat-debug-28956.log
/tmp/mat-debug-2896.log
/tmp/mat-debug-29144.log
/tmp/mat-debug-29156.log
/tmp/mat-debug-29516.log
/tmp/mat-debug-29688.log
/tmp/mat-debug-30048.log
/tmp/mat-debug-30636.log
/tmp/mat-debug-30748.log
/tmp/mat-debug-3088.log
/tmp/mat-debug-31192.log
/tmp/mat-debug-31568.log
/tmp/mat-debug-31644.log
/tmp/mat-debug-31648.log
/tmp/mat-debug-31868.log
/tmp/mat-debug-32256.log
/tmp/mat-debug-32332.log
/tmp/mat-debug-32440.log
/tmp/mat-debug-32484.log
/tmp/mat-debug-32648.log
/tmp/mat-debug-33108.log
/tmp/mat-debug-33116.log
/tmp/mat-debug-33396.log
/tmp/mat-debug-33532.log
/tmp/mat-debug-34120.log
/tmp/mat-debug-34160.log
/tmp/mat-debug-35196.log
/tmp/mat-debug-35220.log
/tmp/mat-debug-35304.log
/tmp/mat-debug-36140.log
/tmp/mat-debug-36544.log
/tmp/mat-debug-36616.log
/tmp/mat-debug-36948.log
/tmp/mat-debug-37100.log
/tmp/mat-debug-37196.log
/tmp/mat-debug-37536.log
/tmp/mat-debug-38044.log
/tmp/mat-debug-38172.log
/tmp/mat-debug-38332.log
/tmp/mat-debug-38724.log
/tmp/mat-debug-39112.log
/tmp/mat-debug-39400.log
/tmp/mat-debug-39888.log
/tmp/mat-debug-4680.log
/tmp/mat-debug-5580.log
/tmp/mat-debug-5588.log
/tmp/mat-debug-5804.log
/tmp/mat-debug-6088.log
/tmp/mat-debug-6268.log
/tmp/mat-debug-6404.log
/tmp/mat-debug-6932.log
/tmp/mat-debug-8060.log
/tmp/mat-debug-8132.log
/tmp/mat-debug-8232.log
/tmp/wct3E92.tmp
/tmp/wct7B86.tmp
```


<span style="color:maroon"> Example 3: Using `-size` to find files at a certain size:.</span>

This command finds the files that are a certain size. It is useful for finding files within a certain size range. 

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ find / -size 10M
/mingw64/bin/git-lfs.exe
```


## `Less`: `-N`, `/pattern`, `m` .

<span style="color:maroon"> Example 1: Using `-N` to show the line numbers of a file</span>

Using the `-N` command in less allows the user to check line numbers while they read the file. It is especially useful for if you want to refer back to a line, or if you're telling someone else what line to look at. 

```
      1
      2
      3
      4             PREFACE
      5             We present the narrative of this report and the recommendations that flow from it to
      6                 the President of the United States, the United States Congress, and the American
      7                 people for their consideration. Ten Commissioners-five Republicans and five
      8                 Democrats chosen by elected leaders from our nation's capital at a time of great
      9                 partisan division-have come together to present this report without dissent.
     10             We have come together with a unity of purpose because our nation demands it.
     11                 September 11, 2001, was a day of unprecedented shock and suffering in the history of     
     12                 the United States. The nation was unprepared. How did this happen, and how can we        
     13                 avoid such tragedy again?
     14             To answer these questions, the Congress and the President created the National
     15                 Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November     
     16                 27, 2002).
     17             Our mandate was sweeping. The law directed us to investigate "facts and circumstances        
     18                 relating to the terrorist attacks of September 11, 2001," including those relating       
     19                 to intelligence agencies, law enforcement agencies, diplomacy, immigration issues        
     20                 and border control, the flow of assets to terrorist organizations, commercial
Use line numbers  (press RETURN)
```

<span style="color:maroon"> Example 2: Using `/(string)` to highlight how many times a word shows up:.</span>

This is a command in less that allows the user to visually see where certain words are in the file. It is useful for skimming through files looking for certain words. 

This commands wasn't able to be copied properly, so it is in image form below:

[pattern image](https://media.discordapp.net/attachments/1023749314587140137/1036531816355606608/unknown.png)

<span style="color:maroon"> Example 3: Using `m` to mark a line</span>

The m command, followed by a letter, marks a line that you can refer back to. It is useful for quickly going back to a mark for further usage. 

```
set mark: ...skipping...
     23                 reviewed more than 2.5 million pages of documents and interviewed more than 1,200
     24                 individuals in ten countries. This included nearly every senior official from the        
     25                 current and previous administrations who had responsibility for topics covered in        
     26                 our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.     
     27                 From the outset, we have been committed to share as much of our investigation as we      
     28                 can with the American people. To that end, we held 19 days of hearings and took
     29                 public testimony from 160 witnesses.
     30             Our aim has not been to assign individual blame. Our aim has been to provide the
     31                 fullest possible account of the events surrounding 9/11 and to identify lessons
     32                 learned.
     33             We learned about an enemy who is sophisticated, patient, disciplined, and lethal. The        
     34                 enemy rallies broad support in the Arab and Muslim world by demanding redress of
     35                 political grievances, but its hostility toward us and our values is limitless. Its       
     36                 purpose is to rid the world of religious and political pluralism, the plebiscite,        
     37                 and equal rights for women. It makes no distinction between military and civilian        
     38                 targets. Collateral damage is not in its lexicon.
     39             We learned that the institutions charged with protecting our borders, civil aviation,        
     40                 and national security did not understand how grave this threat could be, and did not     
     41                 adjust their policies, plans, and practices to deter or defeat it. We learned of
     42                 fault lines within our government-between foreign and domestic intelligence, and
     43                 between and within agencies. We learned of the pervasive problems of managing and
     44                 sharing informa
     ```