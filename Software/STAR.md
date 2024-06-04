*record: 2024.06.04*
## 前言  
最近在编写nextflow分析流程的时候，用到了star中starsolo的部分参数，在查看star manual的时候，未发现starsolo输出的具体描述，只在star的Issues里面找到，在此做些整理。
### Barcode Reads Stats:  
- Reads not used for quantification because:
  - noNoAdapter: Reads without an Adapter
  - noNoUMI: Reads not Associated to a Valid UMI
  - noNoCB: Reads not Associated to a Valid Cell Barcode
  - noNinCB: Reads with N's in Cell Barcodes
  - noNinUMI: Reads with N's in UMIs
  - noUMIhomopolymer: Reads associated with a Homopolymeric UMI
  - noNoWLmatch: Reads Without Match to the Whitelist
  - noTooManyMM: Reads With Too Many Mismatches to the Whitelist
  - noTooManyWLmatches: Reads With Too Many matches to the Whitelist
- Reads used for the quantification:
  - yesWLmatchExact: Reads with Exact Match to Whitelist
  - yesOneWLmatchWithMM: Reads with One Match to the Whitelist with Mismatches
  - yesMultWLmatchWithMM: Reads with Multiple Matches to the Whitelist with Mismatches
### Feature ReadsStats:
- Reads not used for quantification because:
  - noUnmapped: Unmapped Reads
  - noNoFeature: Reads not Mapped to a Feature
  - MultiFeature: Reads Aligned to Multiple Features
  - subMultiFeatureMultiGenomic: reads mapping to multiple genomic loci and multiple features (a subset of MultiFeature)
  - noTooManyWLmatches: Reads Not Counted Because their Barcoded pair has Too Many Matches to the Whitelist
  - noMMtoWLwithoutExact: Reads Not Counted Because their Barcoded pair has Mismatches to the Whitelist and there's no more reads supporting that barcode
- Reads used for the quantification:
  - yesWLmatch: Reads whose Barcoded Pair has a Match to the Whitelist
  - yessubWLmatchExact: reads with cell barcode exactly matched to the whitelist (a subset of yesWLmatch)
  - yessubWLmatch_UniqueFeature: reads with matched to the WL and unique feature (a subset of yesWLmatch)
  - yesCellBarcodes: Reads Assossiated to a Valid Cell Barcode
  - yesUMIs: Reads Assossiated to a Valid UMI

### Cell Readstats:  
  - cbMatch: the number of read that matched the cell barcode
  - cbPerfect: the number of perfect match on cell barcode
  - exonic: the number of read mapping on exonic
  - intronic: the number of read mapping on intronic
  - mito: the number of read mapping on mitochondrial genome
  - nUMIunique: the total number of counted UMI
  - nGenesUnique: the number of genes having non 0 counts
  - genomeU: number of reads mapping to one locus in the genome
  - genomeM: number of reads mapping to multiple loci in the genome
  - featureU: number of reads mapping to one feature (Gene, GeneFull, etc)
  - featureM: number of reads mapping to multiple features
  - cbMMunique: number of reads with cell barcodes that map with mismatches to one barcode in the passlist
  - cbMMmultiple: number of reads with cell barcodes that map with mismatches to multiple barcodes in the passlist
  - exonicAS: number of reads mapping antisense to annotated exons
  - intronicAS: number of reads mapping antisense to annotated introns
  - countedU: number of unique-gene reads that were used in counting UMIs (!= number of UMIs), i.e. reads with valid CB/UMI/gene
  - countedM: same for multi-gene reads
  - nUMImulti: number of UMI for multi-gene reads, if requested
  - nGenesMulti: number of genes supported by just multi-gene reads, if requested

### Ref
[**Barcoded/Feature ReadsStats**](https://github.com/alexdobin/STAR/issues/1887 "Barcoded Reads Stats and Feature ReadsStats")  
[**Cell Readstats**](https://github.com/alexdobin/STAR/issues/1501)

