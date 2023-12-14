Introduction and Context:
Medulloblastoma (MB) is the most common childhood cancer with a higher occurrence in boys. This extremely aggressive brain tumor is categorized into four distinct subtypes based on their molecular and genetic characteristics, including SHH (Group 1), WNT (Group 2), Group 3, and Group 4. Investigating these subtypes can lead to early detection and intervention, hopefully to improve outcomes. 
Among molecular groupings of MB, Group (MBG) 1, 3, and 4 originate from cells in the rhombic lip of the cerebellum. Rhombic lip (RL) is the progenitor zone of the glutamatergic cells of the cerebellum. Group 3 medulloblastoma (MBG3) is particularly aggressive and lethal. This subtype is characterized by low survival rate, low prognosis, and high risk of recurrence and metastasis. Despite of recent studies on MBG3, the molecular drivers of this subgroup is not fully understood (1,2). Further research into the molecular drivers of MBG3 is essential to develop targeted therapies.
Research Question: What are the molecules and pathways involved in human MBG3?
I aim to generate a profile of molecules and pathways involved in human MBG3. Using scRNA-seq and bioinformatic comparisons on human G3 tumors with controls, I will identify potential drivers of MBG3.

Methods and Materials & Results:
I analyzed a wildtype single-cell RNA sequencing (scRNAseq) sample obtained from the mouse cerebellum in the GSE129730 dataset. Additionally, I examined a tumor sample of scRNAseq from the human Medulloblastoma Group 3, sourced from the GSE155446 dataset. All data is publicly available, so CC0 1.0 Universal license is attributed to the project. R programming was used to analyze data using Seurat, dplyr, tidyverse, enrichR packages. 
R version: 4.3.1
https://cran.r-project.org/bin/windows/base/
Seurat Package version: 4.4.0
https://cran.r-project.org/web/packages/Seurat/index.html
tidyverse Package version: 2.0.0
https://cran.r-project.org/web/packages/tidyverse/index.html
dplyr Package version: 1.1.4
https://cran.r-project.org/web/packages/dplyr/index.html
enrichR Package version: 3.2
https://cran.r-project.org/web/packages/enrichR/index.html
Initially, the wildtype sample underwent data importation and processing in the R environment. Following the generation of a Seurat Object, a comprehensive quality control process was undertaken, selectively retaining cells with an expression of features ranging from 200 to 2500 and a mitochondrial gene percentage below 16%. In the preprocessing phase, data normalization and scaling were performed. Subsequently, genes demonstrating significant biological variation across cells were identified. Principal Component Analysis (PCA) was employed to diminish the high-dimensional gene expression space
Utilizing the first 30 principal components, UMAP was applied as a dimensionality reduction technique. The data underwent clustering, and a Dimplot was constructed based on the established parameters. Marker genes for each identified cell type within the Seurat object were then determined. Additional investigation involved the search for gene markers for each cluster in external databases (https://panglaodb.se/index.html and http://xteam.xbio.top/CellMarker/) to elucidate cell types, and subsequent annotations were made for each cluster.
Similar procedures including quality control, preprocessing, and clustering were applied to the tumor sample. Integration of both datasets preceded a reanalysis of the combined data. A Dimplot was generated based on tissue and cell types. Broad gene expression changes in the tumor sample, in comparison to the healthy sample, were identified, revealing the top 10 upregulated and downregulated genes. Conclusively, the enrichR package was employed for conducting biological and molecular enrichment analysis on the integrated dataset. 
