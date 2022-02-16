# Analysis of T cell clonotype expansion and underlying molecular features

**Hypothesis:** E2F4 activity is increased in tumor-reactive (expanding) T cells

## Datasets

TBA.

## Covariates

* `patient_id` patient ID as in the original dataset; **beware of BRCA ID remapping!**
* `timepoint` time of T cell collection, either *pre* or *post*;
* `response` patient's response according to the original publication;
* `cell_type` fine-grained classification of cell types as in the original publication;
* `expansion` either *yes* or *no* according to the orginal publication;
* `expansion_on`either according to ouw own classification scheme: *yes* if `p_post > p_pre`, *no* otherwise; Where:
  * `Patient_clonotype`: Combination of the patient and the clonotype ID
  * `n_pre`: Number of *pre* cells corresponding to this `Patient_clonotype`
  * `n_post`: Number of *post* cells corresponding to this `Patient_clonotype`
  * `n_patient: The number of total cells belonging to this patient, it is the sum of all *pre* and *post* assigned to the clonotypes of a patient
  * `p_pre = n_pre * 100 / n_patient`
  * `p_post = n_post * 100 / n_patient`
* `VDJdb' clonotype classification based on VDJdb TCR-antigen annotations (originally called `antigen.species`)
* `IEDB` clonotype classification based on IEDB TCR-antigen annotations (originally `Organism`)
* `E2F4_score` estimated regulon activity of the E2F4 TF
* `E2F4_activity` binarization of the `E2F4_score` according to the median: *E2F4_high* if `E2F4_score > median`, *E2F4_low* otherwise. 
