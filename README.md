# BLCA_ICI_Response_Predictor

This repository contains the executable for the trained machine learning model presented in " "Tumor subtype-resolution of the response to immunotherapy in advanced bladder cancer by the meta-analysis of six independent cohorts" by Boll & Vázquez Montes de Oca et al. (unpublished).

## Usage

Trained models are available in this repository in .joblib format. They can be utilized to predict ICI Response for BLCA patients. These models were trained using multiple cohorts totaling 205 patients for the Complete model and 348 for the TMB + RNA model. To apply the model with new data, whether for validation or predicting a patient's response to treatment, a pandas dataframe containing all the features used during model training must be provided as input.

Complete model:
-TMB_zsore
-APOBECenrichment.total
-nonstop
-CCND1
-PD1.zscore
-PDL1.zscore
-HLA-I.GSVA
-IFNg_Ayers.GSVA
-Stroma_EMT.GSVA
-T_cell_inflamed.GSVA
-TGF_beta.GSVA
-Macrophages M1
-T cells CD4 memory activated
-T cells CD8
-T cells regulatory (Tregs)
-ECOG_under0
-Liver.Metastasis
-APM_8.GSVA
-t.spec.lncRNA.GSVA

TMB + RNA model:
-TMB_zsore
-CCND1
-PD1.zscore
-PDL1.zscore
-HLA-I.GSVA
-IFNg_Ayers.GSVA
-Stroma_EMT.GSVA
-T_cell_inflamed.GSVA
-TGF_beta.GSVA
-Macrophages M1
-T cells CD4 memory activated
-T cells CD8
-T cells regulatory (Tregs)
-APM_8.GSVA
-t.spec.lncRNA.GSVA

Please note that if any variable is missing, the model will not function properly. Therefore, various imputation techniques can be employed. However, anticipate decreased performance compared to when all the original variables are present.

## Contact:
- Sergio Vázquez Montes de Oca (svazquez1@researchmar.net)
- Lilian Marie Boll (lboll@researchmar.net)
