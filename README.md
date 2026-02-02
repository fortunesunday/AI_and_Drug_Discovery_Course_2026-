# **QSAR DATA CURATION**

- **Target:** Caspase 8 (CASP 8)
- **Number of biactivity records:** 455

---

## **QSAR Data Curation Workflow - CASP8**
### Step 1: Setup
- Relevant libraries were insatlled and imported including:
  - `chembl_webresource_client` for acessing ChEMBL.
  - `pandas` for data handling

### Step 2: Target search:
- ChEMBL was search for the target CASP8
- The relevant target with ChEMBL ID `CHEMBL3776` was used.

### Step 3: Bioactivity Data Retrieval
- Bioactivity data for the target was retrieved with their **IC50 values** (nanomolar)
- The results were converted to a dataframe containing **459 records across 46 columns**
- The `standard_type` column was inspected for missing values and none was found.

### Step 4: Filtering and Cleaning
- Rows with valid bioctivity values were filtered
- Bioactivity classes were assigned: IC50 <= 1000 nM - **active**, IC50 > 1000 nM and <10000 nM - **intermediate**, IC50 >= 10000nM - **inactive**

### Step 5: Extraction of Relevant Columns
- Only essential columns for QSAR modeling were kept, including: `molecule_chembl_id`, `canonical_smiles`, `standard_value`, `bioactivity_class`.
- They were assigned to a new DataFrame for preprocessed data.

### Step 6: SMILES Preprocessing
- Compounds with invalid SMILES were removed
- SMILES strings were standardized to lowercase and stripped of spaces.

### Step 7: Save Data
- Bioactivity data was saved as `bioactivity_raw_data.csv`
- The preprocessed dataset was also saved as `bioactivity_preprocessed_data.csv`
- Both datasers were copied to Google Drive for storage.

