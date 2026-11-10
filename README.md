# CZBenchmarks

# To-Do List
- Look for brain related DNA methylation array (HM450/EPIC/mouse array) data and convert them into .cz format.
- Run and test deconvolution to calculate the cell type composition of DNA methylation array data and bulk WGBS dataset.
- Test cell type prediction model on mouse brain dataset using pseudobulk cz (convert allc to cz) as reference, validate the model on downsampled deep seqencing single-cell cz and MiSeq cz files.
- Cytozip genome browser website (host on neomorph).
- merge_cz: merge cz files from the same cell type (sum up mc and cov)

# Behck merge_cz
## cytozip merge cz
```shell
create environment: conda env create -f m3c.yaml
reference cz: /anvil/projects/x-mcb130189/Wubin/Ref/mm10/mm10_with_chrL.allc.cz
chrom size path: /anvil/projects/x-mcb130189/Wubin/Ref/mm10/mm10_ucsc.nochrM.sizes
metadata path: /anvil/projects/x-mcb130189/Wubin/mouse_dev/clustering/5kb/annotations.tsv
cz files: /anvil/scratch/x-wding2/mouse_dev/mapped/*/cz/*.cz
merge into Subclass (from metadata), record time memory usage, and compare it with ALLCools.
```

## ALLCools merge allc
```shell
ALLCools: https://github.com/DingWB/ALLCools
documentation: https://github.com/lhqing/ALLCools
allcools merge-allc --allc_paths your.allc.path --cpu ${n_jobs} --output_path '${outdir}/${bname}.allc.tsv.gz' --chrom_size_path '${chrom_size_path}'
```