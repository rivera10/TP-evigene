### Edit from original evigene19may14.tar
To use with docker and singularity

### Author
EvidentialGene Gene Set Reconstruction Software
Don Gilbert, gilbertd At indiana edu, 2018
http://eugenes.org/EvidentialGene/  

### About evigene/scripts/prot/tr2aacds.pl
  See also http://eugenes.org/EvidentialGene/about/EvidentialGene_trassembly_pipe.html

  Too many transcript assemblies are much better than too few. It allows one
  then to apply biological criteria to pick out the best ones. Don't be
  misled by the "right number" of transcripts that one or other transcript
  assembler may produce. It is the "right sequence" you want, and now the
  only way to get it is to produce too many assemblies (an "over-assembly")
  from RNA data, with several methods and several parameter settings.

  EvidentialGene tr2aacds.pl is a pipeline script for
  processing large piles of transcript assemblies, from several methods
  such as Velvet/Oases, Trinity, Soap, etc, into the most biologically useful
  "best" set of mRNA, classified into primary and alternate transcripts.

  It takes as input the transcript fasta produced by any/all of the
  transcript assemblers.  These are classified (not clustered) into valid,
  non-redundant coding sequence transcripts ("okay"), and and redundant,
  fragment or non-coding transcripts ("drop"). The okay set is close to a
  biologically real set regardless of how many millions of input assemblies
  you start with.

  It solves major problems in gene set reconstruction found in other methods:

  1. Others do not not classify alternate transcripts of same locus properly,
  Alternates may differ in protein quite a bit, but share identical exon parts.

  2. Others remove paralogs with high identity in protein sequence, which
  is a problem for some very interesting gene families.

  3. Others may select artifacts with insertion errors by selecting longest transcripts.
  Evigene works first with coding sequences.

  Quality assessment of this Transcript Assembly Software is
  described in http://eugenes.org/EvidentialGene/about/EvidentialGene_quality.html

### Required additional software
  You need these additional software for tr2aacds, installed in Unix PATH or via
  run scripts.

  * fastanrdb of exonerate package, quickly reduces perfect duplicate sequences
    https://www.ebi.ac.uk/~guy/exonerate/  OR
    https://www.ebi.ac.uk/about/vertebrate-genomics/software/exonerate
  * cd-hit, cd-hit-est, clusters protein or nucleotide sequences.
    http://cd-hit.org/ OR https://github.com/weizhongli/cdhit/
  * blastn and makeblastdb of NCBI BLAST, https://blast.ncbi.nlm.nih.gov/
    Basic Local Alignment Search Tool, finds regions of local similarity between sequences.
