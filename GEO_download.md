To download supplementary files of an experiment, e.g., GSE217494,

```bash
wget -r -np -nH --cut-dirs=3 -A "*.gz,*.h5,*.tar,*.zip" ftp://ftp.ncbi.nlm.nih.gov/geo/series/GSE217nnn/GSE217494/suppl/
```
where

-A "*.gz,*.h5,*.tar,*.zip" → one string, comma-separated

-nH --cut-dirs=3 → removes the long FTP directory structure

ftp:// works better than https:// for recursive downloads

-r -np → recursively downloads all files without going up directories
