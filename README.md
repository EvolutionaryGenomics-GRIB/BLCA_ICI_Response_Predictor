# BLCA_ICI_Response_Predictor

This repository contains the executable for the trained machine learning model presented in " "Tumor subtype-resolution of the response to immunotherapy in advanced bladder cancer by the meta-analysis of six independent cohorts" by Boll & Vázquez Montes de Oca et al. (unpublished).

## Usage

Trained model is available in this repository in .joblib format. It can be utilized to predict ICI Response for BLCA patients. This model was trained using multiple cohorts totaling 348 patients. To apply the model with new data, whether for validation or predicting a patient's response to treatment, a pandas dataframe containing all the features used during model training must be provided as input.

**TMB + RNA model**:
- TMB_zsore
- CCND1
- PD1.zscore
- PDL1.zscore
- HLA-I.GSVA
- IFNg_Ayers.GSVA
- Stroma_EMT.GSVA
- T_cell_inflamed.GSVA
- TGF_beta.GSVA
- Macrophages M1
- T cells CD4 memory activated
- T cells CD8
- T cells regulatory (Tregs)
- APM_8.GSVA
- t.spec.lncRNA.GSVA

Please note that if any variable is missing, the model will not function properly. Therefore, various imputation techniques can be employed. However, anticipate decreased performance compared to when all the original variables are present.

## Training results

After training the aforementioned model, we evaluated it using different strategies. The first one was the classical train/test approach, where 30% of the data was reserved for testing purposes. However, due to the limited amount of data, we repeated this process 1000 times to ensure that the results were not influenced by chance. Furthermore, we employed bootstrap .632+ as an internal validation technique. To ensure the robustness of the model, we also conducted train/test procedures while systematically removing each cohort from the merged dataframe, thereby verifying that the results were not influenced by any particular cohort among the five. Additionally, undersampling was performed to ensure that the model predicts both classes equally well.

| Evaluation Type | AUC Score |
| --------------- | --------- |
| Train/test      | 0.75      |

## Contact:
- Sergio Vázquez Montes de Oca (svazquez1@researchmar.net)
- Lilian Marie Boll (lboll@researchmar.net)
