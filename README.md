# NanoPlot
Plotting scripts for Oxford Nanopore sequencing data

![Example plot](https://github.com/wdecoster/NanoPlot/blob/master/examples/scaled_Log_Downsampled_LengthvsQualityScatterPlot_kde.png)

The example plot above shows a bivariate plot comparing log transformed read length with average basecall Phred quality score. More examples can be found in the [gallery on my blog 'Gigabase Or Gigabyte'.](https://gigabaseorgigabyte.wordpress.com/2017/06/01/example-gallery-of-nanoplot/)

This script performs data extraction from Oxford Nanopore sequencing data in the following formats:
- fastq files (can be bgzip, bzip2 or gzip compressed)  
- fastq files generated by albacore containing additional information (can be bgzip, bzip2 or gzip compressed)  
- bam files  

### Installation

`pip install NanoPlot`  
The script is written for python3 but might also work for python2.7 (untested).

### USAGE:
```
usage: NanoPlot [-h] [--threads THREADS] [--time] [--maxlength MAXLENGTH]
                   [--drop_outliers] [--downsample DOWNSAMPLE] [--loglength]
                   [--alength] [--outdir OUTDIR] [--version] [--prefix PREFIX]
                   (--fastq FASTQ | --fastq_albacore FASTQ_ALBACORE | --bam BAM)


Required argument is one of these:
    --fastq FASTQ         Data presented is in fastq format exported from fast5
                          files by e.g. poretools.
    --fastq_albacore FASTQ_ALBACORE
                          Data presented is in fastq format generated by
                          albacore with additional information concerning
                          channel and time.
    --bam BAM             Data presented as a sorted bam file.


Optional arguments:
  -h, --help            show this help message and exit
  -v, --version         Print version and exit.
  -t, --threads THREADS Set the allowed number of threads to be used by the script
  --maxlength MAXLENGTH
                        Drop reads longer than length specified.
  --drop_outliers       Drop outlier reads with extreme long length.
  --downsample DOWNSAMPLE
                        Reduce dataset to N reads by random sampling.
  --loglength           Logarithmic scaling of lengths in plots.
  --alength             Use aligned read lengths rather than sequenced length
                        (bam mode)
  --outdir OUTDIR       Specify directory in which output has to be created.
  --prefix PREFIX       Specify an optional prefix to be used for the output
                        files.
```

## Companion scripts
- [NanoFilt](https://github.com/wdecoster/nanofilt): filtering and trimming of reads
