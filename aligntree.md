# BIOL33221 Sequence Retrieval and Alignment

This *formative* exercise includes production of a short report.

## Choose a Gene
Pick one of the genes from this list:
* A4GALT
* FBXO31
* KIF1A
* AAA1
* FBXO44
* LPPR2
* AHI1
* FTO
* NMNAT2
* ARHGEF6
* GAS7
* NRL
* AVPR2
* GDAP2
* NRSN2
* C1orf36
* GJB3
* PSEN2
* CACNA1G
* GUCA1B
* TCF2
* CACNA2D4
* HNF4A
* TDP1
* FBXO18
* HYAL1

Start a new document in your preferred word processing package and note down the gene you have chosen. This is your report for this workshop.


## Sequence Retrieval
The aim of this first task is to determine what information you can find about your gene, starting from the gene page. Use [Entrez Pubmed](http://www.ncbi.nlm.nih.gov/) to query Gene db.

Select the link for the gene from any mammal (human and mouse will be found most frequently). From the gene page see what information you can determine, either directly or by following links. (You may also wish to record the URL for this page).

This information can include accession numbers for mRNA and protein sequences, transcript length, protein length, number of exons, length of genomic region occupied by the gene, function of the protein and disease association.

Compile this information as a set of bullet points, add to your document and post to the discussion board under the "Sequence Retrieval" thread. If others have posted information about your gene, have a look at what they have posted and compare with your own data.


## Download Related Sequences
Find the accession ID for a protein sequence corresponding to your chosen gene from the human or another well-annotated species. Using this annotation, go to [NCBI's BLAST server](https://blast.ncbi.nlm.nih.gov/) and use BLASTP to search the refseq_protein db for closely matching sequences.

Pick sequences from ~15 species. Using the checkboxes choose some sequences from species closely related to the query species (e.g., if query is human protein, choose some primate sequences), but also some that are more distant (e.g., a rodent, an invertebrate). Taxonomy resources can be found [at NCBI](https://www.ncbi.nlm.nih.gov/taxonomy) or at the [Tree of Life Project](http://tolweb.org/tree/).

With your sequence selected, use the "Download" link in the "Descriptions" section of your BLAST output to download the following:
* a hit table of your chosen sequences,
* their complete sequences.

Format the hit table for your results document. Examine the FASTA file using a your text editor (e.g., Notepad++).

Read about the FASTA format [at the Wikipedia page](https://en.wikipedia.org/wiki/FASTA_format).

Edit the description lines in your FASTA file to give just the names of the species (in English or the Latin binomial). Avoid space characters (you can use _ instead). Give the FASTA file itself a sensible name, e.g., "Genename_annotated.fasta". (Note that you are deleting important information here, but you have the accession numbers stored in the hit table so you are good).


## Alignment
Now it's time to use your FASTA file to carry out a multiple sequence (and species) alignment (MSA). Many MSA tools exist, but a great selection is maintained at [EMBL-EBI's MSA page](http://www.ebi.ac.uk/Tools/msa/).

Launch MUSCLE and load in your FASTA file. Set it running to generate an alignment. You may wish to refresh your memory about how alignments can be calculated by looking at my lectures (key concepts: local vs. global, progressive).

When you get your results keep open this page tab also, download the alignment file using the button. You may be taken to a text only page or an instant download depending on your browser's behaviour. In any case, get the output into a file. This is still a FASTA file but it contains pads/spaces in the sequences. Name this something like "Genename_msa.fasta".


## Curating Your Alignment
The aim here is to trim poorly aligned regions. This usually takes place at the ends of an alignment where typical algorithms struggle. This task can be carried out by hand or using a program called Gblocks. Let's try Gblocks. There are several online versions, but let's try [the version linked here](http://phylogeny.lirmm.fr/phylo_cgi/one_task.cgi?task_type=gblocks) (note that this server can provide an entire workflow similar to ours – feel free to explore – but I find it too clunky overall).

Submit your MUSCLE-aligned FASTA file. When the run is complete download the "cured" alignment in FASTA format from the Outputs section. Name this something like "Genename_cured_msa.fasta".


## Presenting Your Alignment
Going back to the EMBL-EBI tools page above, launch MView and submit your cured alignment. This display colours for conservation. Go ahead and download this file and add it to your report document. You may need to choose a fixed width font such as ```Courier New``` to maintain the spacing in the alignment view. In the worst case, you can take a screenshot, but try to avoid that.


## Creating a Phylogeny
Go back to the MUSCLE results page which you kept open above and click the "Send to ClustalW2_Phylogeny" button. If you've lost that page, launch [ClustalW2Phylogeny](https://www.ebi.ac.uk/Tools/phylogeny/) again and submit your alignment.

While this is working you can take a chance to learn a bit about phylogenetic methods. A [basic introduction can be found here](http://www.scq.ubc.ca/introduction-to-phylogenetics/) (start at "Tree construction methods"). For a maths-heavy overview see [this course page](https://www.stat.wisc.edu/courses/st992-newton/smmb/files/phylogeny/phylogeny-4.pdf). An especially detailed page may be found by looking at the lecture [on this course](http://homes.cs.washington.edu/~ruzzo/courses/gs559/09wi/) dealing with and titled "Phylogeny".


When the phylogeny program has completed take a look at the cladogram and the "real" phylogeny. Next, download the tree file which is in Newick format and give it a sensible name, e.g., "Genename_tree.nwk". Take a look at the Newick format [page on Wikipedia](https://en.wikipedia.org/wiki/Newick_format). More detail about the specification can also be found [at this page](http://evolution.genetics.washington.edu/phylip/newicktree.html).


## Visualizing Your Tree
Let's use another program to get a flexible visualization of your tree. Go to the [interactive Tree of Life's upload site](http://itol.embl.de/upload.cgi) and upload your Newick-formatted file. When it's finished processing explore the display options. When you are happy with your image choose the "Export" tab and select an appropriate format (PNG is pretty easy across platforms, unless you want to change resolution/play with vector graphics).

Add this image to your report.


## Questions to Consider
You will probably want to add some notes to your report to connect all the information. In that context you can consider some questions.

The difference between a cladogram and a phylogenetic tree relates to branch lengths.
* What determines branch length?
* What is the difference between a rooted and an unrooted tree?
* Which do you think is more appropriate?
