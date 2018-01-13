# BIOL33221 Guidance with Repeats

## Extracting Repeats from UCSC RepeatMasker Track
A number of folk have encountered a problem in which the RepeatMasker track in the UCSC Genome Browser shows a very large number of transposable elements. This page will suggest a workaround for this problem.

## Access UCSC Graphical Genome Browser
Start by accessing your gene (paralog) using the [UCSC Genome Browser](http://genome-euro.ucsc.edu/cgi-bin/hgTracks). You may not be aware whether you are using the main [US-based site](https://genome.ucsc.edu/cgi-bin/hgTracks) or the [European Mirror site](http://genome-euro.ucsc.edu/cgi-bin/hgTracks). You can check on this and move between these using the "Mirror" menu and it generally makes sense to use the closest site for efficiency.

Note that in the top panel the view position is written in genome coordinates. It should look something like this:
```
chr11:31,788,910-31,817,961
```
depending on where your gene is located.

The difficulty people are experiencing is the large number of SINEs, LINEs and so on in some regions making it difficult to prepare a table.

## Access UCSC Table Browser
Open a new tab in your browser and visit the [UCSC *Table* Browser](http://genome-euro.ucsc.edu/cgi-bin/hgTables). I have linked the European Mirror version there. Here is the [US Table link](https://genome.ucsc.edu/cgi-bin/hgTables).

(If you take a look at the URL in your browser you will see that the Graphical Browser URL ends with ```hgTracks``` while the Table Browser URL ends with ```hgTables```).

## Examine the Table Interface
Looking now at the Table Browser page you should see that it has picked up the same location that you are viewing in the graphical version. (It might fail to do so if you are using different mirror sites or different browsers, etc. In that case manually enter the correct location via copy and paste).

The Table Browser is essentially an alternative interface to the tracks displayed in the graphical version. For RepeatMasker data:

* under "group:"" choose "Repeats", then
* under "track:" choose "RepeatMasker".

At this point you can just hit the "get output" button and it should yield a list of repeats in the region indicated in position. This data can be copied into Microsoft Excel or other software for counting/manipulation.

## Going a Step further (Gingerly)
It is also possible to look for intersections between tracks. For this:

* under "intersection:" hit the "create" button,
* under "group:" choose "Genes and Gene Predictions",
* under "track:" choose "RefSeq Genes",
* hit the "submit" button, then "get output" then "get BED".

You can explore these options further, *but*, if you are unlucky enough to have a very large number of repeats and overlaps, I am happy with you providing an overall summary (of numbers) and indicating whether overlap is present in answer to question 9.

## Question 9: Clarification
I am just looking for some summary of the information available regarding repeats at your paralogous loci. Since repeat numbers will vary quite widely between gene sets I will not be expecting a comprehensive accounting of the coordinates of every repeat.
