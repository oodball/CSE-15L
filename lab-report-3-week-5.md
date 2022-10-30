# Lab Report 3

## 1. Using `-i` to search for a word within a file or files disregarding casing.

<span style="color:maroon">Example 1.</span>

The command here searches through everything in `technical/plos/journal*` to see how many times "may 1997" or "May 1997" shows up, regardless of casing. It prints out the fileand the context around it. It would be useful for finding files that mention a specific date that you want.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -i "may 1997"  technical/plos/journal*
technical/plos/journal.pbio.0020001.txt:        output between the developing and already developed countries (Gibbs 1995; May 1997;
technical/plos/journal.pbio.0020001.txt:        the world (Gibbs 1995; May 1997; Alonso and Fernández-Juricic 2001; Vohora and Vohora
technical/plos/journal.pbio.0020001.txt:        assessing scientific productivity or technical advances (May 1997). More relevant
technical/plos/journal.pbio.0020001.txt:        and development (May 1997). The proportional change in the number of publications, using
```

<span style="color:maroon">Example 2.</span>

The same command works for searching within a specific file. It will return all the times when "olfaction" or "Olfaction" show up in the file or within a word as well as some context around them. This is useful if you only want to know about olfaction, as it would point you towards the area where it is specifically mentioned.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -i "olfaction"  technical/plos/journal.pbio.0030137.txt
       hearing, and olfaction, there are strong differences between species. For example, bees,
```

<span style="color:maroon">Example 3.</span>

This is the same command as Example 2 run on the `technical/911report/chapter-9.txt` file. Again, it searches everywhere where the string "There" or "there" show up in the file. It would be useful with another, more specific word to narrow down areas to read within the file that might be better suited for what you want to find.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -i "There"  technical/911report/chapter-9.txt
          Doors leading to the roof were locked. There was no rooftop evacuation plan. The
              by a superintendent. There was a separate PAPD command for each of the Port
              utilized at a major incident at the WTC. In particular, there were no standard
              dispatcher assigned to each. In addition, there were several radio channels for
              senior staff, would respond there. In addition, an OEM field responder would be sent
              access should elevators become inoperable). There was no backup site.
          Hundreds of civilians trapped on or above the 92nd floor gathered in large and small
              below the smoke or fire-and to wait there for further instructions. The deputy fire
              or the magnitude of the impact zone and were therefore unable to provide information
              answer when callers asked whether to go up or down. In most instances, therefore,
              debilitating volumes and isolated fires were reported, although there were some
              received by the deputy fire safety director making announcements there. However, at
              appeared to be out, and there were no assurances that sprinklers or standpipes were
              We realized that, because of the impact of the plane, that there was some
                  We knew that at the height of the day there were as many as 50,000 people in
              to level 4, thereby sending to the WTC approximately 22 lieutenants, 100 sergeants,
              officers in the WTC Command to meet at the police desk in 5 WTC. Soon thereafter, he
              interoperable radio frequencies. As a result, there was no comprehensive
              likely unable to descend because of intensifying smoke in the stairwell. There were
              affected until shortly before the building collapsed. There were several areas
              given any information about the inability to conduct rooftop rescues and therefore
              zone possibly could be rescued, or whether there should be even limited firefighting
              third plane was debunked, other chiefs continued operations, and there is no
              from there proceeded to climb stairwell B. Another ladder company arrived soon
              thereafter, and began to rescue civilians trapped in an elevator between the first
              confusion over how to get to there, he instead ended up in the Marriott at about
              lobby there directed some units to proceed to what he thought was the SouthTower. In
              lobby, and there is no evidence that it was conveyed to chiefs in the South Tower
              team began to climb the stairs. Shortly thereafter, a second NYPD ESU team entered
              there appeared to be no more civilians still descending. This ESU team encountered a
              lowered in order to rescue people, but there was no one on the roof. This pilot's
          The ESU team on the 31st floor conferred with the FDNY personnel there to ensure that
              (though they did not know the cause). Immediately thereafter, they were joined by
          At the time of the collapse of the South Tower, there were numerous NYPD officers in
              the concourse, some of whom are believed to have died there. Those who survived
              West and Vesey, compelling PAPD officers to move north. There is no evidence that
              the far more difficult task in New York. There was a single incident, and it was not
              contain, and there were no other buildings in the immediate area. There was no
              York. As the "Arlington County: After-Action Report" notes, there were significant
              local, federal, bistate, and state agencies acted in a supporting role. There was a
              approximately 9:20. There were other instances of coordination at operational
              themselves. Although there were ESU teams and a few individual police officers
              there were so few of them (in comparison to the number of FDNY companies) and all
              was shared among agencies on 9/11, even prior to its evacuation. There was a lack of
              would have been in the Twin Towers if there had been an integrated response, or what
              catastrophic effect has been the subject of controversy. We believe that there are
```

## 2. Using `-c` to count the number of times a word shows up within a file or files.

<span style="color:maroon">Example 1.</span>

This command is useful as it allows the user to look at what files in `technical/plos/*` had the word "Introduction" in them and how many times it shows up. In this one, the `-i` command from earlier was used so casing wouldn't matter. It is useful for knowing where to look if you have to read the introduction to an academic paper, since not all the files have a specifically named "Introduction" Section, so it would narrow down your choices significantly.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -c -i "Introduction" technical/plos/*
technical/plos/journal.pbio.0020001.txt:0
technical/plos/journal.pbio.0020010.txt:0
technical/plos/journal.pbio.0020012.txt:0
technical/plos/journal.pbio.0020013.txt:0
technical/plos/journal.pbio.0020019.txt:0
technical/plos/journal.pbio.0020028.txt:1
technical/plos/journal.pbio.0020035.txt:0
technical/plos/journal.pbio.0020040.txt:1
technical/plos/journal.pbio.0020042.txt:0
technical/plos/journal.pbio.0020043.txt:0
technical/plos/journal.pbio.0020046.txt:0
technical/plos/journal.pbio.0020047.txt:0
technical/plos/journal.pbio.0020052.txt:1
technical/plos/journal.pbio.0020053.txt:0
technical/plos/journal.pbio.0020054.txt:0
technical/plos/journal.pbio.0020063.txt:0
technical/plos/journal.pbio.0020064.txt:0
technical/plos/journal.pbio.0020067.txt:0
technical/plos/journal.pbio.0020068.txt:0
technical/plos/journal.pbio.0020071.txt:5
technical/plos/journal.pbio.0020073.txt:0
technical/plos/journal.pbio.0020100.txt:0
technical/plos/journal.pbio.0020101.txt:0
technical/plos/journal.pbio.0020105.txt:0
technical/plos/journal.pbio.0020112.txt:0
technical/plos/journal.pbio.0020113.txt:0
technical/plos/journal.pbio.0020116.txt:0
technical/plos/journal.pbio.0020121.txt:0
technical/plos/journal.pbio.0020125.txt:0
technical/plos/journal.pbio.0020127.txt:0
technical/plos/journal.pbio.0020133.txt:0
technical/plos/journal.pbio.0020140.txt:0
technical/plos/journal.pbio.0020145.txt:0
technical/plos/journal.pbio.0020146.txt:0
technical/plos/journal.pbio.0020147.txt:0
technical/plos/journal.pbio.0020148.txt:0
technical/plos/journal.pbio.0020150.txt:0
technical/plos/journal.pbio.0020156.txt:0
technical/plos/journal.pbio.0020161.txt:0
technical/plos/journal.pbio.0020164.txt:0
technical/plos/journal.pbio.0020169.txt:0
technical/plos/journal.pbio.0020172.txt:0
technical/plos/journal.pbio.0020183.txt:0
technical/plos/journal.pbio.0020187.txt:0
technical/plos/journal.pbio.0020190.txt:0
technical/plos/journal.pbio.0020206.txt:1
technical/plos/journal.pbio.0020213.txt:0
technical/plos/journal.pbio.0020214.txt:0
technical/plos/journal.pbio.0020215.txt:0
technical/plos/journal.pbio.0020216.txt:0
technical/plos/journal.pbio.0020223.txt:0
technical/plos/journal.pbio.0020224.txt:0
technical/plos/journal.pbio.0020228.txt:0
technical/plos/journal.pbio.0020232.txt:0
technical/plos/journal.pbio.0020241.txt:0
technical/plos/journal.pbio.0020262.txt:0
technical/plos/journal.pbio.0020263.txt:0
technical/plos/journal.pbio.0020267.txt:0
technical/plos/journal.pbio.0020272.txt:0
technical/plos/journal.pbio.0020276.txt:0
technical/plos/journal.pbio.0020297.txt:0
technical/plos/journal.pbio.0020302.txt:0
technical/plos/journal.pbio.0020306.txt:0
technical/plos/journal.pbio.0020307.txt:0
technical/plos/journal.pbio.0020310.txt:0
technical/plos/journal.pbio.0020311.txt:0
technical/plos/journal.pbio.0020337.txt:0
technical/plos/journal.pbio.0020346.txt:0
technical/plos/journal.pbio.0020347.txt:0
technical/plos/journal.pbio.0020348.txt:0
technical/plos/journal.pbio.0020350.txt:0
technical/plos/journal.pbio.0020353.txt:0
technical/plos/journal.pbio.0020354.txt:0
technical/plos/journal.pbio.0020394.txt:0
technical/plos/journal.pbio.0020400.txt:0
technical/plos/journal.pbio.0020401.txt:0
technical/plos/journal.pbio.0020404.txt:0
technical/plos/journal.pbio.0020406.txt:0
technical/plos/journal.pbio.0020419.txt:0
technical/plos/journal.pbio.0020420.txt:0
technical/plos/journal.pbio.0020430.txt:0
technical/plos/journal.pbio.0020431.txt:1
technical/plos/journal.pbio.0020439.txt:0
technical/plos/journal.pbio.0020440.txt:0
technical/plos/journal.pbio.0030021.txt:0
technical/plos/journal.pbio.0030024.txt:0
technical/plos/journal.pbio.0030032.txt:0
technical/plos/journal.pbio.0030050.txt:0
technical/plos/journal.pbio.0030051.txt:0
technical/plos/journal.pbio.0030056.txt:0
technical/plos/journal.pbio.0030062.txt:0
technical/plos/journal.pbio.0030065.txt:0
technical/plos/journal.pbio.0030076.txt:1
technical/plos/journal.pbio.0030094.txt:0
technical/plos/journal.pbio.0030097.txt:0
technical/plos/journal.pbio.0030102.txt:0
technical/plos/journal.pbio.0030105.txt:0
technical/plos/journal.pbio.0030127.txt:0
technical/plos/journal.pbio.0030129.txt:1
technical/plos/journal.pbio.0030131.txt:0
technical/plos/journal.pbio.0030136.txt:0
technical/plos/journal.pbio.0030137.txt:0
technical/plos/pmed.0010008.txt:1
technical/plos/pmed.0010010.txt:0
technical/plos/pmed.0010013.txt:0
technical/plos/pmed.0010021.txt:0
technical/plos/pmed.0010022.txt:1
technical/plos/pmed.0010023.txt:0
technical/plos/pmed.0010024.txt:0
technical/plos/pmed.0010025.txt:0
technical/plos/pmed.0010026.txt:0
technical/plos/pmed.0010028.txt:1
technical/plos/pmed.0010029.txt:0
technical/plos/pmed.0010030.txt:0
technical/plos/pmed.0010034.txt:0
technical/plos/pmed.0010036.txt:1
technical/plos/pmed.0010039.txt:1
technical/plos/pmed.0010041.txt:0
technical/plos/pmed.0010042.txt:0
technical/plos/pmed.0010045.txt:1
technical/plos/pmed.0010046.txt:0
technical/plos/pmed.0010047.txt:0
technical/plos/pmed.0010048.txt:0
technical/plos/pmed.0010049.txt:0
technical/plos/pmed.0010050.txt:0
technical/plos/pmed.0010051.txt:0
technical/plos/pmed.0010052.txt:0
technical/plos/pmed.0010056.txt:0
technical/plos/pmed.0010058.txt:0
technical/plos/pmed.0010060.txt:0
technical/plos/pmed.0010061.txt:0
technical/plos/pmed.0010062.txt:1
technical/plos/pmed.0010064.txt:1
technical/plos/pmed.0010066.txt:2
technical/plos/pmed.0010067.txt:0
technical/plos/pmed.0010068.txt:0
technical/plos/pmed.0010069.txt:0
technical/plos/pmed.0010070.txt:0
technical/plos/pmed.0010071.txt:0
technical/plos/pmed.0020002.txt:0
technical/plos/pmed.0020005.txt:0
technical/plos/pmed.0020007.txt:0
technical/plos/pmed.0020009.txt:0
technical/plos/pmed.0020015.txt:2
technical/plos/pmed.0020016.txt:3
technical/plos/pmed.0020017.txt:1
technical/plos/pmed.0020018.txt:1
technical/plos/pmed.0020019.txt:0
technical/plos/pmed.0020020.txt:0
technical/plos/pmed.0020021.txt:0
technical/plos/pmed.0020022.txt:0
technical/plos/pmed.0020023.txt:0
technical/plos/pmed.0020024.txt:0
technical/plos/pmed.0020027.txt:0
technical/plos/pmed.0020028.txt:0
technical/plos/pmed.0020033.txt:0
technical/plos/pmed.0020034.txt:1
technical/plos/pmed.0020035.txt:0
technical/plos/pmed.0020036.txt:0
technical/plos/pmed.0020039.txt:0
technical/plos/pmed.0020040.txt:0
technical/plos/pmed.0020045.txt:1
technical/plos/pmed.0020047.txt:0
technical/plos/pmed.0020048.txt:0
technical/plos/pmed.0020050.txt:1
technical/plos/pmed.0020055.txt:0
technical/plos/pmed.0020059.txt:1
technical/plos/pmed.0020060.txt:0
technical/plos/pmed.0020061.txt:0
technical/plos/pmed.0020062.txt:0
technical/plos/pmed.0020065.txt:0
technical/plos/pmed.0020067.txt:1
technical/plos/pmed.0020068.txt:0
technical/plos/pmed.0020071.txt:0
technical/plos/pmed.0020073.txt:1
technical/plos/pmed.0020074.txt:0
technical/plos/pmed.0020075.txt:0
technical/plos/pmed.0020082.txt:0
technical/plos/pmed.0020085.txt:0
technical/plos/pmed.0020086.txt:0
technical/plos/pmed.0020088.txt:0
technical/plos/pmed.0020090.txt:0
technical/plos/pmed.0020091.txt:0
technical/plos/pmed.0020094.txt:0
technical/plos/pmed.0020098.txt:0
technical/plos/pmed.0020099.txt:0
technical/plos/pmed.0020102.txt:0
technical/plos/pmed.0020103.txt:1
technical/plos/pmed.0020104.txt:0
technical/plos/pmed.0020113.txt:0
technical/plos/pmed.0020114.txt:0
technical/plos/pmed.0020115.txt:0
technical/plos/pmed.0020116.txt:0
technical/plos/pmed.0020117.txt:0
technical/plos/pmed.0020118.txt:0
technical/plos/pmed.0020120.txt:0
technical/plos/pmed.0020123.txt:1
technical/plos/pmed.0020140.txt:0
technical/plos/pmed.0020144.txt:0
technical/plos/pmed.0020145.txt:0
technical/plos/pmed.0020146.txt:0
technical/plos/pmed.0020148.txt:0
technical/plos/pmed.0020149.txt:0
technical/plos/pmed.0020150.txt:0
technical/plos/pmed.0020155.txt:0
technical/plos/pmed.0020157.txt:0
technical/plos/pmed.0020158.txt:0
technical/plos/pmed.0020160.txt:1
technical/plos/pmed.0020161.txt:1
technical/plos/pmed.0020162.txt:1
technical/plos/pmed.0020180.txt:0
technical/plos/pmed.0020181.txt:0
technical/plos/pmed.0020182.txt:1
technical/plos/pmed.0020187.txt:0
technical/plos/pmed.0020189.txt:0
technical/plos/pmed.0020191.txt:0
technical/plos/pmed.0020192.txt:0
technical/plos/pmed.0020194.txt:0
technical/plos/pmed.0020195.txt:0
technical/plos/pmed.0020196.txt:0
technical/plos/pmed.0020197.txt:0
technical/plos/pmed.0020198.txt:0
technical/plos/pmed.0020200.txt:0
technical/plos/pmed.0020201.txt:0
technical/plos/pmed.0020203.txt:0
technical/plos/pmed.0020206.txt:0
technical/plos/pmed.0020208.txt:0
technical/plos/pmed.0020209.txt:0
technical/plos/pmed.0020210.txt:0
technical/plos/pmed.0020212.txt:0
technical/plos/pmed.0020216.txt:0
technical/plos/pmed.0020226.txt:0
technical/plos/pmed.0020231.txt:0
technical/plos/pmed.0020232.txt:0
technical/plos/pmed.0020235.txt:0
technical/plos/pmed.0020236.txt:0
technical/plos/pmed.0020237.txt:0
technical/plos/pmed.0020238.txt:1
technical/plos/pmed.0020239.txt:0
technical/plos/pmed.0020242.txt:0
technical/plos/pmed.0020246.txt:1
technical/plos/pmed.0020247.txt:0
technical/plos/pmed.0020249.txt:1
technical/plos/pmed.0020257.txt:1
technical/plos/pmed.0020258.txt:0
technical/plos/pmed.0020268.txt:0
technical/plos/pmed.0020272.txt:0
technical/plos/pmed.0020273.txt:0
technical/plos/pmed.0020274.txt:0
technical/plos/pmed.0020275.txt:0
technical/plos/pmed.0020278.txt:0
technical/plos/pmed.0020281.txt:0
```

<span style="color:maroon">Example 2.</span>

The same command can operate on a single file. In this case, I chose `technical/plos/pmed.0020238.txt` to see how many times the word "the" shows up in the file. The command counts up how many times it does and returns an integer. This is useful for only having to count up how many times a word or phrase shows up in a single file.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -c -i "the" technical/plos/pmed.0020238.txt
31
```

<span style="color:maroon">Example 3.</span>

Using the same command as in Example 1, the command searched for how many times "level" showed up in each file of the `technical/911report` directory. The total number for each file is printed next to the file name. It is useful for counting how many times a word shows up without having to go through and `-c` for each file.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -c "level"  technical/911report/*
technical/911report/chapter-1.txt:21
technical/911report/chapter-10.txt:2
technical/911report/chapter-11.txt:7
technical/911report/chapter-12.txt:13
technical/911report/chapter-13.1.txt:6
technical/911report/chapter-13.2.txt:7
technical/911report/chapter-13.3.txt:5
technical/911report/chapter-13.4.txt:5
technical/911report/chapter-13.5.txt:10
technical/911report/chapter-2.txt:0
technical/911report/chapter-3.txt:23
technical/911report/chapter-5.txt:0
technical/911report/chapter-6.txt:14
technical/911report/chapter-7.txt:0
technical/911report/chapter-8.txt:13
technical/911report/chapter-9.txt:19
technical/911report/preface.txt:0
```

## 3. Using `-m #` to search through only a certain number of files:

<span style="color:maroon">Example 1.</span>

This line only searches for the word "there" at most twice through each file, as specified by the 2 after `-m`. With a more specific word, this command is useful for searching through large directories like this one to filter out which ones have the word there, and some context about what the file contents are without having to read each one.

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$  grep -m 2 "there" technical/plos/journal*
technical/plos/journal.pbio.0020001.txt:        and therefore account for the largest number of publications. It is also likely that there
technical/plos/journal.pbio.0020001.txt:        focusing on the Americas as a case study. Not surprisingly, there was a huge disparity in
technical/plos/journal.pbio.0020010.txt:        access and therefore securing longer-term financial stability (as the major publishers have
technical/plos/journal.pbio.0020010.txt:        to be imaginative. For all vendors, there has to be an understanding of the political,
technical/plos/journal.pbio.0020012.txt:        Sir-2, and thereby extended the organism's lifespan by 70% (Box 1). Sir-2 belongs to a
technical/plos/journal.pbio.0020012.txt:        Sinclair puts it, has anything to do with longevity, there is a good chance that it does,
technical/plos/journal.pbio.0020013.txt:        Inside eukaryotic cells there is a massive protein complex called the proteasome whose
technical/plos/journal.pbio.0020013.txt:        disassembly, thereby allowing ample time for unfolding and proteolysis of the substrate
technical/plos/journal.pbio.0020019.txt:        changed from on to off or vice versa (i.e., there was a shift in the environmental
technical/plos/journal.pbio.0020019.txt:        phenotypic optimum by releasing hidden genetic variation, thereby providing a new substrate
technical/plos/journal.pbio.0020028.txt:        is we just don't know. The more aggressive answer is there's no reason to think so.” Rossi
technical/plos/journal.pbio.0020028.txt:        you can get it there, and if it's in one piece, there no doubt in our minds that it will
technical/plos/journal.pbio.0020035.txt:        which the growing carbon chain is tethered; see Figure 1A), that would come together to
technical/plos/journal.pbio.0020040.txt:        time on. There were oncogenes and there were tumour suppressor genes. Oncogenes were
technical/plos/journal.pbio.0020040.txt:        therefore, they were dominant. Tumour suppressor genes were genes that would normally
technical/plos/journal.pbio.0020042.txt:        are ones for which a function has been assigned, but for which there is a good reason to
technical/plos/journal.pbio.0020043.txt:        across approximately half of their genomes), there might be conflict between the two
technical/plos/journal.pbio.0020043.txt:        nonidentical cell lineages, as there is between the tissues of a mother mammal and her
technical/plos/journal.pbio.0020046.txt:        severely impairs communication, with devastating socioeconomic consequences. However, there
technical/plos/journal.pbio.0020046.txt:        to what extent this recovery is spontaneous or induced by early speech therapy. Also, there
technical/plos/journal.pbio.0020052.txt:        unsurprising that there is pressure on pharmaceutical companies to set drug prices to
technical/plos/journal.pbio.0020052.txt:        innovation and extend marketing monopolies. And there are growing fears that the huge
technical/plos/journal.pbio.0020053.txt:        there, but it will keep living as sort of an infected zombie for as long as the phage wants
technical/plos/journal.pbio.0020053.txt:        In the meantime, there is a rising clamor to slow down the rate at which bacteria
technical/plos/journal.pbio.0020054.txt:        largely a luxury for developed countries. Managers there can choose to let a fire burn
technical/plos/journal.pbio.0020054.txt:        that there's been too much concern about removing trees, when what counts most is the
technical/plos/journal.pbio.0020064.txt:        explains Zuker, who previously worked on other sensory systems in flies, ‘there was a
technical/plos/journal.pbio.0020064.txt:        not alone, however, in thinking there may be more than one umami receptor (and additional
technical/plos/journal.pbio.0020067.txt:        decades. The work there contributed to Randall's scheme for making radar practical in air
technical/plos/journal.pbio.0020067.txt:        structure must be antiparallel and that there were probably two chains entwined. Watson
technical/plos/journal.pbio.0020068.txt:        pathways may therefore have general utility for bacteria associated with host cells and may
technical/plos/journal.pbio.0020068.txt:        mutualisms, there may be little room for negotiation. For example, the highly conserved,
technical/plos/journal.pbio.0020071.txt:        but progress always depends on the consideration of new ideas, and there might be important
technical/plos/journal.pbio.0020071.txt:        evolutionary biology with the hope that there are still some theoretical battles to be
technical/plos/journal.pbio.0020073.txt:        al. first tethered a covalently linked biotin moiety to the central region of each DNA
technical/plos/journal.pbio.0020073.txt:        such “hinge” structures may enable the coordinated linear movement of hundreds of tethered
technical/plos/journal.pbio.0020101.txt:        ability, too, there exist animal parallels, such as the habit of chimpanzees to reconcile
technical/plos/journal.pbio.0020105.txt:        representative of more widespread reactions to the debate, there appear to be a number of
technical/plos/journal.pbio.0020112.txt:        As Pennington clearly explains, there is still much uncertainty in the science of BSE,
technical/plos/journal.pbio.0020112.txt:        sequence of events that led the UK government in the early 1990s to conclude that there was
technical/plos/journal.pbio.0020113.txt:        production, even in areas where there is only subsistence fishing (Box 1). As scientists
technical/plos/journal.pbio.0020113.txt:        Marine Resource Services, Jorge Csirke, states that “from a stock point of view, there is
technical/plos/journal.pbio.0020116.txt:        therefore of deep concern to us. We discuss them in turn below.
technical/plos/journal.pbio.0020116.txt:        title is not consistent with the knowledge, stated in that chapter, that there is no
technical/plos/journal.pbio.0020125.txt:        and therefore become silent when termination of translation by Sup35 is partially
technical/plos/journal.pbio.0020125.txt:        necessarily self-propagating aggregates, i.e., prions. In fact, there are additional
technical/plos/journal.pbio.0020127.txt:        from the host, whose cells were induced to form an axis by the graft, therefore named the
technical/plos/journal.pbio.0020127.txt:        but there is now no doubt that the FGF signaling pathway plays a major role in the
technical/plos/journal.pbio.0020133.txt:        Although the word ‘revolution’ should not be used lightly in science, there is no other
technical/plos/journal.pbio.0020133.txt:        thereafter, dsRNA was shown to provoke gene silencing in other organisms, including plants
technical/plos/journal.pbio.0020145.txt:        open-access journals, and there are a few new open-access education journals such as
technical/plos/journal.pbio.0020145.txt:        it would be helpful if there were a way to identify all the genes within a certain
technical/plos/journal.pbio.0020146.txt:        From rodents through the primate series to humans there is a progressive reduction in
technical/plos/journal.pbio.0020146.txt:        among the early hunter-gatherer human cultures and continued through the last ice age. With
technical/plos/journal.pbio.0020147.txt:        construction, thereby justifying some of the bold claims for their new theory. We think
technical/plos/journal.pbio.0020148.txt:        course, there are developmental differences between people and fish, and no one pretends
technical/plos/journal.pbio.0020148.txt:        the human heart’, says Stainier. ‘Obviously, there are additional processes involved in
technical/plos/journal.pbio.0020150.txt:        boardroom? Are there neuroethical nightmares just around the corner? Or are all these vivid
technical/plos/journal.pbio.0020150.txt:        largely about group averages, not about the functionings of individual brains, and therein
technical/plos/journal.pbio.0020156.txt:        their journals' access policies, there is by now a broad consensus that widespread open
technical/plos/journal.pbio.0020156.txt:        because there are lots of other reasons why people are members” (Anonymous 2003).
technical/plos/journal.pbio.0020161.txt:        science”, scientists as civil servants, and there is obviously much greater possibility of
technical/plos/journal.pbio.0020161.txt:        ‘I'm not saying that there aren't countries that have this standard—like the UK, parts of
technical/plos/journal.pbio.0020164.txt:        a lens?” most often calls for the answer that the lens is there to focus light rays, and
technical/plos/journal.pbio.0020164.txt:        only rarely for the answer that the lens is there because lens cells are induced by the
technical/plos/journal.pbio.0020169.txt:        other (Haas and Plow 1996). Since these original observations, there has been an intensive
technical/plos/journal.pbio.0020169.txt:        et al. 2001). Shortly thereafter, the model gained direct and strong experimental support
technical/plos/journal.pbio.0020172.txt:        be had. Nonetheless, the texton elements served useful duty in the demonstration that there
technical/plos/journal.pbio.0020183.txt:        around—there are females, and there are males. But our perspective seems biased and narrow
technical/plos/journal.pbio.0020183.txt:        As things stand, there are three main aspects to the definition of a sex: who you are,
technical/plos/journal.pbio.0020187.txt:        Coping with Methuselah (p. 143). Once AEV is achieved, there will be no
technical/plos/journal.pbio.0020187.txt:        going back: rejuvenation research will be intense forever thereafter and will anticipate
technical/plos/journal.pbio.0020190.txt:        With the advent of larger human haplotype data sets, it has become clear that there are
technical/plos/journal.pbio.0020190.txt:        what genes have been under selection and what patterns of linkage disequilibria there may
technical/plos/journal.pbio.0020206.txt:        subsequent piecemeal loss and gain of gene family members. Consequently, there is heated
technical/plos/journal.pbio.0020206.txt:        likelihood of such a mutation being introduced increases. Recent studies suggest that there
technical/plos/journal.pbio.0020213.txt:        that there are things about its species we didn't even know we didn't know. ‘What I find
technical/plos/journal.pbio.0020213.txt:        P. ramorum . ‘If it reaches areas where there are a lot of
technical/plos/journal.pbio.0020214.txt:        “Is it still possible to work there?” The best response to the first question is, “Why
technical/plos/journal.pbio.0020214.txt:        Union. However, some laboratories are conducting outsourced research, and there are now
technical/plos/journal.pbio.0020215.txt:        followed by endocytosis by the recipient cell. Alternatively, membranetethered ligands
technical/plos/journal.pbio.0020215.txt:        and the cells they were connected to, suggesting that indeed there was continuity between
technical/plos/journal.pbio.0020216.txt:        But there must be something else beside visual cues. Navigation over water, in the near
technical/plos/journal.pbio.0020216.txt:        60% does. Interestingly, the perceived change in quality is stronger when there is a
technical/plos/journal.pbio.0020223.txt:        DNA routing was therefore used to achieve the splitting step of “split-and-pool”
technical/plos/journal.pbio.0020223.txt:        thereof. This result demonstrates that the DNA display method is capable of facilitating
technical/plos/journal.pbio.0020224.txt:        scion and induced gene silencing there. The establishment of systemic silencing took 4 wk
technical/plos/journal.pbio.0020224.txt:        the grafting puzzle. Researchers there introduced additional chitinase genes using
technical/plos/journal.pbio.0020228.txt:        restricted and for which there is an immediate demand. All articles published by PLoS can
technical/plos/journal.pbio.0020228.txt:        the same legal terms as well, thereby facilitating their permanent accessibility and
technical/plos/journal.pbio.0020232.txt:        Soon thereafter, several other prominent scientists of the eighteenth century, including
technical/plos/journal.pbio.0020232.txt:        benefits of either embryonic or adult stem cells, there are several investigators who are
technical/plos/journal.pbio.0020241.txt:        from the combination of the 129 and B6 genomes may might therefore provide a primed
technical/plos/journal.pbio.0020241.txt:        Apcs was therefore an interesting candidate gene to evaluate.
technical/plos/journal.pbio.0020262.txt:        loudly and clearly: there is much more genetic variation within any village on earth than
technical/plos/journal.pbio.0020262.txt:        there is between different human populations. We are extraordinarily unified, from a
technical/plos/journal.pbio.0020263.txt:        variation. Despite the mantra that humans share 99.9% of our genetic makeup, there is
technical/plos/journal.pbio.0020267.txt:        there is little consensus among researchers on how the disorder develops in children and
technical/plos/journal.pbio.0020267.txt:        “Since there is no major hypothesis as to cause [of autism], there are many plausible
technical/plos/journal.pbio.0020272.txt:        planet, there has never been anything as productive of life as a wheat field in Kansas. It
technical/plos/journal.pbio.0020272.txt:        diversity while increasing actual biomass. Now, there is no question that if current trends
technical/plos/journal.pbio.0020276.txt:        processes. Not only is there extensive similarity in the sequences of fly and human genes,
technical/plos/journal.pbio.0020276.txt:        are present, there is a clear interdependence between the two systems. For a fully
technical/plos/journal.pbio.0020297.txt:              abstract. In the overly replete world of Funes there were nothing but details, almost
technical/plos/journal.pbio.0020297.txt:        terms of the theory and thereby cemented the revolution. Copernicus's statements, showed
technical/plos/journal.pbio.0020302.txt:        productivity known is chemical energy, and there are only two ecosystems known, both
technical/plos/journal.pbio.0020302.txt:        orbit of Pluto (Ravens et al. 2000); therefore, energy is not the limitation for life.
technical/plos/journal.pbio.0020306.txt:        one is sure how many living species there are—probably about 100,000—or why there are so
technical/plos/journal.pbio.0020306.txt:        from there. Both the finished shells, with their precise and reproducible nanometre-scale
technical/plos/journal.pbio.0020307.txt:        continually being tried out by natural selection. It is therefore little wonder that the
technical/plos/journal.pbio.0020307.txt:        (therein christening the family), while another family member, the activation-induced
technical/plos/journal.pbio.0020310.txt:        non-governmental organisations, national governments, and international bodies, and there
technical/plos/journal.pbio.0020310.txt:        funding shortfall, argues Balmford. What's more, there need to be smarter ways to spend the
technical/plos/journal.pbio.0020311.txt:        degradation by the 26S proteasome thereby de-repressing the response pathway (Gray et al.
technical/plos/journal.pbio.0020337.txt:        In a nutshell, are there tiny, independently tuned elements in the cochlea, like the
technical/plos/journal.pbio.0020337.txt:        a detector—right at the front end of the sensitivity of the system’. He therefore proposed
technical/plos/journal.pbio.0020346.txt:        the literature—and indeed towards such constructions in general—but there is no review and
technical/plos/journal.pbio.0020346.txt:        background. Although there is mention of the so-called FOX genes—some mutations of which
technical/plos/journal.pbio.0020347.txt:        success of the cultivar development scheme described by Zamir and Gur (2004), there is
technical/plos/journal.pbio.0020347.txt:        systems are better understood, there will be many opportunities for creative synthesis of
technical/plos/journal.pbio.0020348.txt:        Reggiani 1996). However, there exists a large variation in the magnitude of adaptability
technical/plos/journal.pbio.0020348.txt:        accommodate substantial aerobic and anaerobic metabolism (Saltin et al. 1977). While there
technical/plos/journal.pbio.0020350.txt:        parasites (such as nectar robbers and seed predators). Consequently, there is often strong
technical/plos/journal.pbio.0020350.txt:        ultraviolet light, and there is no evidence that, for example, hummingbirds have greater
technical/plos/journal.pbio.0020354.txt:        and mtDNA) for these purposes (Avise 2004), there is nothing fundamentally new in the DNA
technical/plos/journal.pbio.0020354.txt:        although there are exceptions. Furthermore, within many species there is sufficient
technical/plos/journal.pbio.0020394.txt:        With respect to the philosophy of mind, there seems to be something of an enthusiast's
technical/plos/journal.pbio.0020394.txt:        played by structures in the brain. However, although formally agreeing that ‘there's
technical/plos/journal.pbio.0020400.txt:        phosphorylation/dephosphorylation (Sitia and Molteni 2004). In support of this model, there
technical/plos/journal.pbio.0020400.txt:        predict there will be many more examples of regulation by thiol modification.
technical/plos/journal.pbio.0020401.txt:        Whether the Lewy body is damaging or neuroprotective, there are clearly several possible
technical/plos/journal.pbio.0020401.txt:        expression of parkin is neuroprotective in a number of contexts, and there is even evidence
technical/plos/journal.pbio.0020404.txt:        composed of five polypeptide subunits (Figure 1), but there are many nAChR subtypes made of
technical/plos/journal.pbio.0020404.txt:        background but letting the bursts through well,” he says. “I'll be surprised if there's not
technical/plos/journal.pbio.0020406.txt:        therein (Qian and Ricklefs 2004; Ricklefs 2004). Explanations involving ecological
technical/plos/journal.pbio.0020406.txt:        that, to the extent that there is symmetry in the continuity of land (or water) about the
technical/plos/journal.pbio.0020419.txt:        starting point; from the elucidation of the structure of DNA, there was an explosion, a
technical/plos/journal.pbio.0020419.txt:        that we could see exactly how many there are, how big each one is and exactly how it is
technical/plos/journal.pbio.0020420.txt:        But there is another possibility, one that can cause the speciation between the two
technical/plos/journal.pbio.0020420.txt:        Individuals who mate with members of the opposing population will therefore produce
technical/plos/journal.pbio.0020439.txt:        heterogeneous than non-living nature. For example, it is estimated that there are
technical/plos/journal.pbio.0020439.txt:        minerals in Earth's crust). By contrast, there are probably between 3 million and 100
technical/plos/journal.pbio.0020440.txt:        Wouldn't it be good if there were a simple theory that used life's shared fundamentals
technical/plos/journal.pbio.0020440.txt:        “I don't believe there's anything to explain—there's no universal scaling exponent,”
technical/plos/journal.pbio.0030024.txt:        valuable research time, especially when there are so many potentially interesting genes. In
technical/plos/journal.pbio.0030024.txt:        “In an atlas, there will be considerable variability from one individual to the
technical/plos/journal.pbio.0030032.txt:        federal funds for tuition and other expenses, there is little money for master's students,
technical/plos/journal.pbio.0030050.txt:        Throughout mammalian and primate evolution, there has been a gradual increase in brain
technical/plos/journal.pbio.0030050.txt:        chimpanzees. Already, Zilles has discovered that there is much more interindividual
technical/plos/journal.pbio.0030051.txt:        which there were also two possible responses in order to obtain the time required for
technical/plos/journal.pbio.0030051.txt:        orchestrated to carry out a cognitive task. Although, as in all sciences, there are
technical/plos/journal.pbio.0030056.txt:        assumptions about how evolution really unfolded. However, there is still concern that many
technical/plos/journal.pbio.0030056.txt:        how evolution unfolded. “It just shows you there's a bear and then there's not a bear,” he
technical/plos/journal.pbio.0030062.txt:        prezygotic isolation (i.e., lack of mating or zygote formation) between species and thereby
technical/plos/journal.pbio.0030062.txt:        selection, but there is hardly enough evidence, in my opinion, to support Coyne and Orr's
technical/plos/journal.pbio.0030065.txt:        concepts and phenomena? Fortunately, there are many groups that are now seeking to answer
technical/plos/journal.pbio.0030065.txt:        sequences without known function in genetic databases), and there are inconsistencies
technical/plos/journal.pbio.0030076.txt:        Saccharomyces cerevisiae , there are two candidates for PTEFb,
technical/plos/journal.pbio.0030094.txt:        chromosomes are gathered together at each pole of the cell, which can then divide. Cohesion
technical/plos/journal.pbio.0030094.txt:        therefore plays a critical part in this process.
technical/plos/journal.pbio.0030097.txt:        And there's the rub: this actually happened to the Director of the Wellcome Trust. Prior
technical/plos/journal.pbio.0030097.txt:        to see if there was anything research-funding organisations could be doing to stimulate
technical/plos/journal.pbio.0030102.txt:        The study of tubeworms is now in its fourth decade, and there are still many fascinating
technical/plos/journal.pbio.0030102.txt:        source fluids and gases do not contain much sulfide, because there are no high-temperature
technical/plos/journal.pbio.0030127.txt:        might find there are other things declining as well as sea ice, such as their food, or
technical/plos/journal.pbio.0030127.txt:        there might be a change in the fertilization of the waters.”
technical/plos/journal.pbio.0030129.txt:        In the world of scientific publishing, there is nothing quite like launching a journal,
technical/plos/journal.pbio.0030131.txt:        not simply related to cardiac repair. To date, there have been no continuous differentiated
technical/plos/journal.pbio.0030137.txt:        hearing, and olfaction, there are strong differences between species. For example, bees,
technical/plos/journal.pbio.0030137.txt:        Even though perceptual sensations may strike us as ethereal, they must be based on
```

<span style="color:maroon">Example 2.</span>

This command limited the number of loops to stop at 5 (still including 0). It searched through the `technical/911report/chapter-9.txt` file and produced this output. This is useful for figuring out where a certain word is in the file if it's at the beginning without reading through the whole file or opening it.

```
$ grep -i -m 4 "level"  technical/911report/chapter-9.txt
            Stairwells A and C ran from the 110th floor to the raised mezzanine level of the
                lobby. Stairwell B ran from the 107th floor to level B6, six floors below ground,
                and was accessible from the West Street lobby level, which was one floor below the
                West Street lobby level; and the B4 level, four stories below ground. The burning
```

<span style="color:maroon">Example 3.</span>

The command searches through the entire `911report` directory to find the first two times that each file contains the string "level" and returns them. This is useful if you need to find certain information within the directory about "levels".

```
audre@AUDREYPC MINGW64 ~/OneDrive/Documents/docsearch (main)
$ grep -m 2 "level"  technical/911report/*
technical/911report/chapter-1.txt:    United 175 was hijacked between 8:42 and 8:46, and awareness of that hijacking began to spread after 8:51. American 77 was hijacked between 8:51 and 8:54. By 9:00, FAA and airline officials began to comprehend that attackers were going after multiple aircraft. American Airlines' nationwide ground stop between 9:05 and 9:10 was followed by a United Airlines ground stop. FAA controllers at Boston Center, which had tracked the first two hijackings, requested at 9:07 that Herndon Command Center "get messages to airborne aircraft to increase security for the cockpit." There is no evidence that Herndon took such action. Boston Center immediately began speculating about other aircraft that might be in danger, leading them to worry about a transcontinental flight-Delta 1989-that in fact was not hijacked. At 9:19, the FAA's New England regional office called Herndon and asked that Cleveland Center advise Delta 1989 to use extra cockpit security.
technical/911report/chapter-1.txt:    The hijackers attacked at 9:28. While traveling 35,000 feet above eastern Ohio, United 93 suddenly dropped 700 feet. Eleven seconds into the descent, the FAA's air traffic control center in Cleveland received the first of two radio transmissions from the aircraft. During the first broadcast, the captain or first officer could be heard declaring "Mayday" amid the sounds of a physical struggle in the cockpit. The second radio transmission, 35 seconds later, indicated that the fight was continuing. The captain or first officer could be heard shouting:" Hey get out of here-get out of here-get out of here."
technical/911report/chapter-10.txt:                anyone at the White House above the level of Richard Clarke participated in a
technical/911report/chapter-10.txt:                discussion at his level. Clarke told us, "I asked the FBI, Dale Watson . . . to
technical/911report/chapter-11.txt:                soon it might do it. At some level that is hard to define, we believe the threat had
technical/911report/chapter-11.txt:            By 2001 the government still needed a decision at the highest level as to whether al
technical/911report/chapter-12.txt:                little higher-level organization, and capable of anything. The American people are
technical/911report/chapter-12.txt:                    rule at the national level, although that turbulent process does continue to
technical/911report/chapter-13.1.txt:                obstacles up to the level where they could be resolved. Responsibility and
technical/911report/chapter-13.1.txt:                    human source collection and signals collection at the operational level; and (f)
technical/911report/chapter-13.2.txt:                title when referring to working-level employees in those agencies. At the request of
technical/911report/chapter-13.2.txt:            78. FAA audio file, Cleveland Center, position Lorain Radar; Flight 93 CVR data; FBI
technical/911report/chapter-13.3.txt:                the low level of removals, see Daniel Cadman interview (Oct. 9, 2003); Rocky
technical/911report/chapter-13.3.txt:                calling for increased high-level pressure on the Taliban and the three countries
technical/911report/chapter-13.4.txt:                Oct.18,2000. For the high-level interventions, see Samuel Berger interview (Jan. 14,
technical/911report/chapter-13.4.txt:                three high-level briefing items discussed responsibility for the attack. The next
technical/911report/chapter-13.5.txt:                29, 2001. For threat level, see White House document, "Selected Summer 2001 Threat
technical/911report/chapter-13.5.txt:                exactly a year earlier, despite the fact that by 2001 the threat level was higher
technical/911report/chapter-3.txt:            The Justice Department and the FBI At the federal level, much law enforcement
technical/911report/chapter-3.txt:                driven at the local level by the field offices, whose concerns centered on
technical/911report/chapter-6.txt:                appears that the heightened sense of alert at the national level played no role in
technical/911report/chapter-6.txt:                United States began a high-level effort to persuade Pakistan to use its influence
technical/911report/chapter-8.txt:                distributed to only a handful of high-level officials.
technical/911report/chapter-8.txt:                (NSA), CIA, or FBI. The Drumbeat Begins In the spring of 2001, the level of
technical/911report/chapter-9.txt:            Stairwells A and C ran from the 110th floor to the raised mezzanine level of the
technical/911report/chapter-9.txt:                lobby. Stairwell B ran from the 107th floor to level B6, six floors below ground,
```
