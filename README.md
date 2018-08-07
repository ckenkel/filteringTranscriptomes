# assemblingTranscriptomes
Scripts and walkthrough necessary to assemble and filter a holobiont transcriptome. Please see the TranscriptomeWalkthru.txt file for the full set of steps.

It's a good idea to start with enough read data, but not too much - assemblers choke on an overabundance of transcripts, which makes the resulting assemblies worse. 70-90K reads is a decent starting point. If you are trying to assemble a reference from a full-blown RNA-seq study, take the subset of your best individual samples - for example, one genotype exhibiting the best coverage in all your treatments. This should increase representation of transcripts, while not overloading the assembler. 

This pipeline uses Trinity for assembly, and reads are pre-filtered to aid in the assembly process. Low quality reads and PCR duplicates are removed. The in-silico-norm from the Trinity assembler is also used to reduce redundant transcripts. Remaining steps parse the holobiont assembly into host, symbiont and 'other' components based on blast matches to a series of reference databases. Finally, transcriptomes are annotated with gene names, GO and KOG terms.

Scripts provided here were modified from ones written by M. Matz https://github.com/z0on and E. Meyer https://github.com/Eli-Meyer
