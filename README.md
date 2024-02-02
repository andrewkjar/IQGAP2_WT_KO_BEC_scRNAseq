# IQGAP2_WT_KO_BEC_scRNAseq
Analysis pipeline for scRNAseq datasets published by Katdare et al. (2023)

[Final paper citation] \ https://www.biorxiv.org/content/10.1101/2023.02.07.527394v1.full

[Raw data location] \ ArrayExpress under accession number E-MTAB-12687

Session info
---
R version 4.1.2 (2021-11-01)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows >= 8 x64 (build 9200)

Matrix products: default

locale:
[1] LC_COLLATE=English_United States.1252 
[2] LC_CTYPE=English_United States.1252   
[3] LC_MONETARY=English_United States.1252
[4] LC_NUMERIC=C                          
[5] LC_TIME=English_United States.1252    

attached base packages:
[1] grid      stats     graphics 
[4] grDevices utils     datasets 
[7] methods   base     

other attached packages:
 [1] DoubletFinder_2.0.3    
 [2] CellChat_1.5.0         
 [3] Biobase_2.54.0         
 [4] BiocGenerics_0.40.0    
 [5] assertive.numbers_0.0-2 \
 [6] RColorBrewer_1.1-3     
 [7] igraph_1.3.4           
 [8] stringr_1.4.0          
 [9] pracma_2.3.8           
[10] ggvenn_0.1.9           
[11] dplyr_1.0.9            
[12] EnhancedVolcano_1.12.0 
[13] ggrepel_0.9.1          
[14] sp_1.5-0               
[15] SeuratObject_4.1.0     
[16] Seurat_4.1.1           
[17] DescTools_0.99.47      
[18] FRACTION_1.0           
[19] ggprovenance_0.1.0     
[20] scales_1.2.0           
[21] gdata_2.18.0.1         
[22] reshape2_1.4.4         
[23] provenance_4.0         
[24] ggplot2_3.3.6          
[25] drc_3.0-1              
[26] MASS_7.3-58            

loaded via a namespace (and not attached):
  [1] utf8_1.2.2           
  [2] reticulate_1.25      
  [3] tidyselect_1.1.2     
  [4] htmlwidgets_1.5.4    
  [5] Rtsne_0.16           
  [6] munsell_0.5.0        
  [7] codetools_0.2-18     
  [8] ica_1.0-3            
  [9] future_1.27.0        
 [10] miniUI_0.1.1.1       
 [11] withr_2.5.0          
 [12] spatstat.random_2.2-0
 [13] colorspace_2.0-3     
 [14] progressr_0.10.1     
 [15] ggalluvial_0.12.3    
 [16] ggalt_0.4.0          
 [17] knitr_1.39           
 [18] rstudioapi_0.13      
 [19] stats4_4.1.2         
 [20] ROCR_1.0-11          
 [21] assertive.base_0.0-9 
 [22] ggsignif_0.6.3       
 [23] tensor_1.5           
 [24] Rttf2pt1_1.3.10      
 [25] listenv_0.8.0        
 [26] NMF_0.24.0           
 [27] labeling_0.4.2       
 [28] polyclip_1.10-0      
 [29] farver_2.1.1         
 [30] coda_0.19-4          
 [31] parallelly_1.32.1    
 [32] vctrs_0.4.1          
 [33] generics_0.1.3       
 [34] TH.data_1.1-1        
 [35] xfun_0.31            
 [36] R6_2.5.1             
 [37] doParallel_1.0.17    
 [38] clue_0.3-61          
 [39] ggbeeswarm_0.6.0     
 [40] spatstat.utils_2.3-1 
 [41] assertthat_0.2.1     
 [42] promises_1.2.0.1     
 [43] multcomp_1.4-19      
 [44] rgeos_0.5-9          
 [45] beeswarm_0.4.0       
 [46] rootSolve_1.8.2.3    
 [47] gtable_0.3.0         
 [48] ash_1.0-15           
 [49] globals_0.15.1       
 [50] goftest_1.2-3        
 [51] lmom_2.9             
 [52] sandwich_3.0-2       
 [53] rlang_1.0.4          
 [54] systemfonts_1.0.4    
 [55] GlobalOptions_0.1.2  
 [56] splines_4.1.2        
 [57] rstatix_0.7.0        
 [58] extrafontdb_1.0      
 [59] lazyeval_0.2.2       
 [60] broom_1.0.0          
 [61] spatstat.geom_2.4-0  
 [62] yaml_2.3.5           
 [63] abind_1.4-5          
 [64] backports_1.4.1      
 [65] httpuv_1.6.5         
 [66] extrafont_0.18       
 [67] tools_4.1.2          
 [68] gridBase_0.4-7       
 [69] statnet.common_4.6.0 
 [70] ellipsis_0.3.2       
 [71] spatstat.core_2.4-4  
 [72] proxy_0.4-27         
 [73] ggridges_0.5.3       
 [74] Rcpp_1.0.9           
 [75] plyr_1.8.7           
 [76] purrr_0.3.4          
 [77] ggpubr_0.4.0         
 [78] rpart_4.1.16         
 [79] deldir_1.0-6         
 [80] GetoptLong_1.0.5     
 [81] pbapply_1.5-0        
 [82] cowplot_1.1.1        
 [83] S4Vectors_0.32.4     
 [84] zoo_1.8-10           
 [85] cluster_2.1.3        
 [86] magrittr_2.0.3       
 [87] sna_2.7              
 [88] RSpectra_0.16-1      
 [89] data.table_1.14.2    
 [90] scattermore_0.8      
 [91] circlize_0.4.16      
 [92] lmtest_0.9-40        
 [93] RANN_2.6.1           
 [94] mvtnorm_1.1-3        
 [95] fitdistrplus_1.1-8   
 [96] matrixStats_0.62.0   
 [97] patchwork_1.1.1      
 [98] mime_0.12            
 [99] xtable_1.8-4         
[100] readxl_1.4.0         
[101] shape_1.4.6          
[102] IRanges_2.28.0       
[103] gridExtra_2.3        
[104] compiler_4.1.2       
[105] tibble_3.1.8         
[106] maps_3.4.0           
[107] crayon_1.5.1         
[108] KernSmooth_2.23-20   
[109] htmltools_0.5.3      
[110] mgcv_1.8-40          
[111] later_1.3.0          
[112] tidyr_1.2.0          
[113] expm_0.999-6         
[114] Exact_3.2            
[115] DBI_1.1.3            
[116] ComplexHeatmap_2.13.1
[117] proj4_1.0-11         
[118] boot_1.3-28          
[119] Matrix_1.4-1         
[120] car_3.1-0            
[121] cli_3.3.0            
[122] parallel_4.1.2       
[123] pkgconfig_2.0.3      
[124] registry_0.5-1       
[125] plotly_4.10.0        
[126] spatstat.sparse_2.1-1
[127] foreach_1.5.2        
[128] svglite_2.1.0        
[129] vipor_0.4.5          
[130] rngtools_1.5.2       
[131] pkgmaker_0.32.2      
[132] digest_0.6.29        
[133] sctransform_0.3.3    
[134] RcppAnnoy_0.0.19     
[135] spatstat.data_2.2-0  
[136] cellranger_1.1.0     
[137] leiden_0.4.2         
[138] gld_2.6.6            
[139] uwot_0.1.11          
[140] shiny_1.7.2          
[141] gtools_3.9.3         
[142] rjson_0.2.21         
[143] lifecycle_1.0.1      
[144] nlme_3.1-158         
[145] jsonlite_1.8.0       
[146] network_1.17.2       
[147] carData_3.0-5        
[148] viridisLite_0.4.0    
[149] fansi_1.0.3          
[150] pillar_1.8.0         
[151] lattice_0.20-45      
[152] ggrastr_1.0.1        
[153] fastmap_1.1.0        
[154] httr_1.4.3           
[155] plotrix_3.8-2        
[156] survival_3.3-1       
[157] glue_1.6.2           
[158] FNN_1.1.3.1          
[159] png_0.1-7            
[160] iterators_1.0.14     
[161] class_7.3-20         
[162] stringi_1.7.6        
[163] irlba_2.3.5          
[164] e1071_1.7-11         
[165] future.apply_1.9.0   

