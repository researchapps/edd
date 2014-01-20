# EDD (Enriched Domain Detector)

## What
EDD is a ChIP-seq peak caller for detection of megabase domains of enrichment. 

## Usage

## Additional

### Getting chromosome sizes
This can be extracted in various ways. For hg19, it is as simple as this (example borrowed from bedtools):
```bash
mysql --user=genome --host=genome-mysql.cse.ucsc.edu -A -e "select chrom, size from hg19.chromInfo" > hg19.genome
```

### Getting a Gap file
The gap file is a bed file that identifies regions that should be excluded from the analysis. Typical candidates for exclusion are broad spanning repeat regions such as centromeres and telomeres. Failure to include a proper gap file for an experiment will increase the number of false positives among the detected peaks. An example gap file for hg19 can be found at https://github.com/eivindgl/edd/blob/master/data/gap_hg19.bed

This has been downloaded from the UCSC table browser using [these options](http://genome.ucsc.edu/cgi-bin/hgTables?hgsid=359889977&clade=mammal&org=Human&db=hg19&hgta_group=map&hgta_track=gap&hgta_table=0&hgta_regionType=genome&position=chr21%3A33031597-33041570&hgta_outputType=primaryTable&hgta_outFileName=).
