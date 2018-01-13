# Mystery Sequence & Genome Browsers

## Mystery Sequence
Download and save the mystery sequence [linked here](mystery.fa).


## Search a Genome Database
Recall (and perhaps look again) at my lecture on databases. In a moment, we are going to search a genome-scale database using the mystery sequence. The take home point here is that these types of database integrate and display large quantities of information, derived manually and using algorithms, that is used to *annotate* sequences at the level of the genome.

My lecture introduced the [Ensembl Genome Browser](http://www.ensembl.org/), but let's look first at one of its rivals, the UCSC (University of California at Santa Cruz) Genome Browser, the European mirror site for which can be found [at this page](http://genome-euro.ucsc.edu).

From the UCSC Genome Browser homepage launch a BLAT search. Read the BLAT landing page to learn a little bit about what this algorithm does and how it differs from BLAST. When you're reading paste in your nucleotide sequence and search the human genome (hg38). (If you are wondering what the _hg38_ means, scroll down [this page](http://genome-euro.ucsc.edu/cgi-bin/hgGateway) and read about genome releases).

Browse the top scoring alignment (if you weren't feeling lucky). *Can you identify the gene?*

I also *strongly* recommend keeping this tab open.


## (Optional) Try the Ensembl Genome Browser
Try the same BLAT search using the the [Ensembl Genome Browser](http://www.ensembl.org/). Do you get the same answer?

## Exploring Genome "Tracks"
Go back to UCSC page. Let's take a closer look at the graphics. Each _row_ in the figure is a *track* showing some information about the sequence (from gene locations to comparisons with other sequences). See if you can find the following tracks and expand them to the "full" view:

* [GENCODE](http://www.gencodegenes.org) (gene annotation from the [ENCODE](https://www.encodeproject.org) project)
* RefSeq genes (recall from the previous workshops)
* Conservation (derived from multiple alignment)
* [OMIM](http://omim.org) (Online Mendelian Inheritance in Man)
* SNPs
* RepeatMasker

_Hint: you can use the options below the graphic + refresh buttons or right click on the tabs to the left._

Let's look in detail at the last two tracks indicated above, which may be less familiar, and see what kind of data they are displaying. You may also find [this site](https://www.genome.ucsc.edu/goldenPath/help/hgTracksHelp.html) helpful.


## SNPs: Single-Nucleotide Polymorphisms
If you don't know what a SNP is, [look at the Wikipedia page](https://en.wikipedia.org/wiki/Single-nucleotide_polymorphism) and remind yourself of the [different functional categories of point mutation](https://en.wikipedia.org/wiki/Point_mutation#Functional_categorization). The reference database for SNPs is called dbSNP and can be found via this [NCBI portal](https://www.ncbi.nlm.nih.gov/SNP/). This can give you information about the frequencies of a SNP in different populations. Although not as comprehensive right now, there is also a site called [SNPedia](http://www.snpedia.com/) for crowd-sourcing information about SNPs.

Let's see if we can identify a functionally significant SNP in our gene. First, make sure you have the "full" view of SNPs displayed. Next scroll down to the Variation section below the graphical display and click on the "Common SNPs" link. Learn about the "Coloring Options" (yes, it's a perfect mirror of an American website).

Armed with this information let's pick out an interesting SNP. Go back to the main display and select the only red SNP that you can see (rs61740803). Take a look at the information on this page and also click through to dbSNP. What kind of SNP is this? Write down what effect this SNP has on the sequence of the (mystery) gene's protein product.


## Repeats and RepeatMasker
As described at [its homepage](http://repeatmasker.org), RepeatMasker is a program that identifies repeat sequences (commonly derived from transposons) using a database called Repbase (or Dfam, a Repbase-derived database enhanced using a [Hidden Markov Model](http://users-cs.au.dk/cstorm/courses/PRiB_f12/slides/hidden-markov-models-1.pdf)). It can be used to "mask" these sequences in order to exclude them from certain kinds of analysis, but it can also be used to identify their positions and identities.

Although RepeatMasker makes use of an algorithm called [Tandem Repeats Finder](http://tandem.bu.edu/trf/trf.html) to identify simple repeats, it is dependent on the database. (This is one good reason why you should record the version of programs you use in analysis or at least the access data, if using online tools). Alternative methods exist that rely only on search algorithms, e.g., [PClouds](https://github.com/PollockLaboratory/pclouds) which decomposes the genome into short oligonucleotides, groups them (into "clouds") and looks for those that are probably over-represented. This yields an estimate of [>2/3 of the human genome as consisting of repetitive elements](http://dx.doi.org/10.1371/journal.pgen.1002384). Methods that rely solely on algorithms, and not on prior information in databases, are called _de novo_ methods.

Look again at the main UCSC display for the region identified by your BLAT search. Making sure that the RepeatMasker track is not squished (it is in "full" mode), identify the only repeat element that is *not* a simple repeat. Answer these questions:

* What is it? Is it a microsatellite? Or is it a transposon?
* Give a little more detail about this family of elements.

You may find these references helpful if you want to know more about:
* [Retrotransposons](https://www.ncbi.nlm.nih.gov/pubmed/26912865)
* [DNA transposons](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2167627/)
* [Evolution of Repeat Elements](http://dx.doi.org/10.1073/pnas.1102343108)

Repeats and conservation data can be intersected. Repeats shared by a group of lineages are called ancestral repeats; those limited to a particular taxon are called lineage-specific repeats. A famous example of the latter are the _Alu_ elements [shared by primates](http://dx.doi.org/10.1186/gb-2011-12-12-236).


## Further Exploration of the Mystery Gene
OK, so you know what the gene is. Look it up on NCBI's [Gene db](https://www.ncbi.nlm.nih.gov/gene/) and choose the human version of the gene. Navigating down to the graphic, hover over the gene until a context menu appears. This gives you the option of downloading the protein sequence (beginning NP) or the RNA sequence (beginning NM), but instead look down and select "FASTA View" which gives you the genomic interval including the gene. In case you want to check, [this is what you should see](https://www.ncbi.nlm.nih.gov/nuccore/NC_000017.11?report=fasta&from=72121020&to=72126420).

Look up to where it says "Send" with the down arrow. Click on this, select "Complete Record", "File" and then choose FASTA as the format. Hit the "Create File" button and your sequence will be downloaded. Rename it if you wish (I called mine "interval.fa"). It should open in your preferred text editor and you will see a standard FASTA file with the header line indicating the chromosome coordinates. From now on, I will refer to this as your interval sequence file.

Go to the [RepeatMasker homepage](http://repeatmasker.org) and choose RepeatMasking under Services. Input your interval sequence file and run with default parameters. *What kinds of repeat can you see? Click through and save the Annotation file.*

Yes, you are not wrong, you cannot find that repeat. What's going on? Do you recall above I mentioned about versions of programs? Look at the version of RMLib used by the web-based tool (on the [submission page](http://repeatmasker.org/cgi-bin/WEBRepeatMasker)). Compare that to the [statement here](https://genome.ucsc.edu/FAQ/FAQdownloads.html#download16). Best practice in bioinformatic work is to download a local copy of RepeatMasker and the relevant database and use offline. Consider yourself warned!


## Gene Structure Prediction
Let's see if we can have more luck predicting gene structure using your interval sequence file. Obviously we could just refer to the annotation tracks on the UCSC or Ensembl Genome Browsers to see the current best information on the genes present in this interval, but what if we had completely new sequence? Then we need to use a _ab initio_ gene prediction method (see [this page](http://bioinformatica.upf.edu/P19/) for a description of types of gene prediction).

Again some of the good software for gene prediction is best run stand-alone on your own (unix-based) box (see the [list of software here](https://en.wikipedia.org/wiki/List_of_gene_prediction_software). Let's have a go with GENSCAN. Go the [GENSCAN website](http://genes.mit.edu/GENSCAN.html) and run it with your interval file and default parameters.

You can see it has made some predictions. Scroll down and you will see it has predicted a polypeptide sequence. Copy this into a text file (yes, it's finicky -> old site) and create a correctly formatted protein FASTA file. Give it a sensible name (I called mine "predicted.fa").

Go to [NCBI BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi) and run a BLASTP search with the predicted sequence. Some questions for you:

* What did the BLASTP search recover?
* Do you think GENSCAN made an accurate prediction?
* Can you explain any deviations?


## Domain Search
For completeness, you might also be interested in searching for domains in your protein of interest. Go to the [Pfam homepage](http://pfam.xfam.org) and carry out a sequence search using your predicted protein sequence. *What do you see?*

## Coda: Other Resources
OK, that's it for these workshops. Of course we've only scratched the surface.

There are so many more programs and databases out there. For example, in alignments you can use [this program](https://www.ncbi.nlm.nih.gov/sutils/splign/splign.cgi) to align mRNA to genomic DNA (a challenging thing to do) and many new methods exist for handling next-generation sequencing data.

Many excellent stand-alone programs exist for phylogeny reconstruction (e.g., [BEAST](http://beast.bio.ed.ac.uk), [MrBayes](http://mrbayes.sourceforge.net), [HyPhy](http://hyphy.org/w/index.php/Main_Page) and [MEGA](http://megasoftware.net)) and again such approaches are recommended for obtaining the best results. However, as I hope you can see, there is a lot you can do with widely available, and free, web tools provided by the scientific community.
