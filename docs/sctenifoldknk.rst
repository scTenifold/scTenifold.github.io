scTenifoldKnk
=============
The characterization of the perturbation profiles caused by a gene knockout allows identifying genes under its direct regulation. Due to the economical and biological limitations to perform the experimental systematic knockout of all genes in a cell-type-specific manner, the development of computational tools to predict the effect of gene knockouts is needed. Following that purpose, we introduced scTenifoldKnk, a machine learning workflow performing virtual knockout experiments on single-cell gene regulatory networks. scTenifoldKnk only requires wild-type single-cell RNA-seq data as input, and returns a weighted list of genes, that ranked by the regulatory effect predicted for the knockout gene over all the other genes expressed in the cell. 

Identifying biological processes regulators based on genome-wide perturbation profiles
--------------------------------------------------------------------------------------



Shear Stress Response in Human Dermal Lymphatic Endothelial Cells
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Using this weighted list together with the gene sets provided by the gene ontology (GO), it is also possible to predict unknown regulators of the already characterized biological processes. As an example, we performed the systematic knockout of 7,548 genes expressed in 885 Mice Dermal Lymphatic Endothelial Cells (MDLEC). We collected by the integration of 23 public datasets  containing PECAM1+, PROX1+, and PDPN+ endothelial cells from the PanglaoDB database (SRS2749416, SRS2532206, SRS4004491, SRS3348010, SRS3044263, SRS3044258, SRS3044262, SRS2874285, SRS2874279, SRS2874276, SRS2874271, SRS3600293, SRS3600294, SRS3600295, SRS3600296, SRS3600297, SRS3600298, SRS3600299, SRS3600300, SRS3600301, SRS3020563, SRS4388158, and SRS4388159)--that is, we harmonized all publicly available scRNA-seq datasets for endothelial cells.

We used the predicted perturbation profile of each gene to identify novel regulators associated with the response to shear stress using the gene sets reported by the gene ontology for this process (`GO:0034616 <http://amigo.geneontology.org/amigo/term/GO:0034616>`_, `GO:0071498 <http://amigo.geneontology.org/amigo/term/GO:0071498>`_, `GO:0071499 <http://amigo.geneontology.org/amigo/term/GO:0071499>`_). We did this applying single-sample gene set enrichment analysis (ssGSEA included in the GSVA R package) on the predicted perturbation profiles for all genes and then ranked them based on the decreasing average enrichment score for the selected three gene sets. Using this approach, we found *Nfe2l2* (PMID: 25563726, 28877882), *Map2k5* (PMID: 26416763, 21166929), *Ddrgk1*/*Ufbp1* (PMID: 29461087), *Grina*, *H1f0* (PMID: 23802622), *Oaz1*, *Clasp2*, *Pdia6*, *Plpp3* (30429326, 26034042), *Tmod3* as the top 10 predicted candidate genes regulating the response to shear stress in MDLEC cells. 

https://version-11-0b.string-db.org/cgi/network?networkId=boc6qhFWt8zW
https://maayanlab.cloud/Enrichr/enrich?dataset=65bc740f7cdc9c1679934b699ddacbdf

.. image:: https://github.com/sctenifold/sctenifold.github.io/raw/main/docs/knk1.png
    :width: 500px
    :align: center
    :alt: alternate text

