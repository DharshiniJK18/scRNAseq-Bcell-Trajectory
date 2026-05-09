## &#x20;           **Single-cell RNA-seq Trajectory Analysis of B-cell Development**



### **Overview :**



This project performs single-cell RNA sequencing (scRNA-seq) analysis and trajectory inference of human B-cell populations using Seurat and Monocle3 in R. The workflow integrates preprocessing, dimensionality reduction, clustering, trajectory reconstruction, pseudotime analysis, and dynamic gene identification to characterize transcriptional transitions across B-cell developmental states.



The analysis reconstructs continuous cellular progression trajectories and identifies genes associated with differentiation dynamics using pseudotemporal ordering.





### **Project Objectives :**



The primary goals of this project were:



* Perform quality control and preprocessing of single-cell RNA-seq data
* Identify biologically distinct B-cell populations
* Visualize transcriptional heterogeneity using UMAP
* Reconstruct developmental trajectories using Monocle3
* Infer pseudotime progression across B-cell states
* Identify genes dynamically regulated during trajectory progression
* Generate reproducible and publication-style computational biology outputs





### **Dataset Description :**



The project uses single-cell RNA-seq expression profiles consisting of:



* Gene expression count matrix
* Cell-level metadata
* Gene annotation and marker information



The dataset contains transcriptomic profiles from multiple B-cell populations and developmental states.





### **Computational Workflow :** 



#### **1. Data Import and Seurat Object Construction**



The raw expression matrix and metadata were imported into R and converted into a Seurat object.



Main steps:



* Transpose expression matrix
* Create Seurat object
* Integrate metadata
* Calculate mitochondrial transcript percentage



#### **2. Quality Control and Filtering**



Quality control filtering was performed to remove low-quality cells and potential technical artifacts.



Filtering criteria:



* nCount\_RNA > 800
* nFeature\_RNA > 500
* mitopercent < 10



This step improves downstream clustering and trajectory inference by removing noisy cells.



#### **3. Identification of B-cell Populations**



The filtered dataset was subsetted to retain only B-cell populations for focused lineage analysis.



Cell identities were assigned using metadata annotations.



#### **4. Dimensionality Reduction and Clustering**



Standard Seurat preprocessing workflow was performed:



* Log normalization
* Variable feature selection
* Data scaling
* Principal Component Analysis (PCA)
* Graph-based clustering
* UMAP visualization
* UMAP Clustering



The UMAP embedding revealed transcriptionally distinct B-cell populations and developmental heterogeneity.



#### **5. Conversion to Monocle3 Cell Data Set**



The processed Seurat object was converted into a Monocle3 cell\_data\_set object for trajectory analysis.



Gene metadata and UMAP embeddings were transferred to enable pseudotime reconstruction.



#### **6. Trajectory Graph Learning**



Monocle3 was used to reconstruct developmental trajectories between B-cell populations.



Trajectory inference was performed using:



* Cell clustering
* Graph learning
* Principal graph embedding



**Trajectory Visualization**



The learned trajectory graph captures potential developmental transitions across B-cell states.



#### **7. Pseudotime Analysis**



Cells were ordered along a pseudotemporal axis to model continuous differentiation progression.



Pseudotime values were assigned using Monocle3 trajectory ordering.



**Pseudotime UMAP**



Cells are colored according to inferred pseudotime progression.



#### **8. Dynamic Gene Expression Analysis**



Genes significantly associated with trajectory progression were identified using Monocle3 graph\_test().



These genes represent transcriptional programs dynamically regulated during B-cell developmental progression.



**Example Dynamic Marker Genes**



Feature plots for representative genes:



* E2F2
* STMN1
* CD52

##### 

### **Major Findings :** 



* Successfully reconstructed B-cell developmental trajectories using Monocle3
* Identified transcriptionally distinct B-cell populations using Seurat clustering
* Inferred pseudotemporal progression across B-cell states
* Detected genes dynamically regulated along differentiation trajectories
* Integrated Seurat and Monocle3 workflows for comprehensive single-cell analysis





### **Reproducibility :** 



The repository includes:



* Processed Seurat objects (.rds)
* Processed Monocle3 objects (.rds)
* Exported pseudotime values
* Dynamic gene tables



These files ensure reproducibility and facilitate downstream reuse.





### **Biological Interpretation :** 



Trajectory analysis suggests continuous transcriptional transitions across B-cell developmental states. The pseudotime framework captures dynamic progression and reveals genes associated with lineage progression and cellular state transitions.



Dynamic genes identified across pseudotime may represent regulatory programs involved in B-cell maturation and differentiation.





### **Conclusion :**



This project demonstrates a complete end-to-end single-cell RNA-seq trajectory analysis workflow using Seurat and Monocle3. The pipeline integrates preprocessing, clustering, dimensionality reduction, pseudotime inference, and dynamic gene analysis to characterize cellular heterogeneity and developmental progression in B-cell populations.



The workflow highlights how trajectory inference can uncover continuous biological transitions beyond static clustering approaches and provides a reproducible framework for downstream single-cell transcriptomic studies.

