# PhecodeXVocabulary
This repo includes support files for phecodes, including:

- Mapping files which specify the ICD codes that define a phecode
- Information files which include descriptions of phecodes (e.g. phecode strings and phecode categories)

Here is a description of each file:

### phecodeX information file

The [phecodeX_info.csv](https://github.com/PheWAS/PhecodeXVocabulary/blob/main/PhecodeX%20(version%201.0)/phecodeX_info.csv) file includes information related to each phecode, including the phecode string, category, and columns indicating sex-specificity and ICD-10 only status. The columns are as follows:

- <b>phecode</b>  The phecode label (two letters, “_”, and numeric phecode)
- <b>phecode_string</b> A descriptive label for phecode
- <b>category_num</b>   A numeric value corresponding to the phecode category
- <b>category</b>              A string indicating the phecode category
- <b>sex</b>                         A string with values “Both”,”Female” or “Male.” Sex-specific phecodes (e.g. Prostate cancer) are labeled by accordingly.
- <b>icd10_only</b>          A Boolean value: 1 if the phecode is defined only by ICD-10 codes; 0 if the phecode is defined by both ICD-9 and -10 codes
- <b>phecode_num</b>   The unique numeric component of the phecode label. Can be useful for sorting


### phecodeX to ICD unrolled map
 
This file includes the ICD-9 and -10 codes that define each phecodes. All codes are “unrolled” meaning that phecode ID_002.1 implies ID_002.
This file is particularly useful for generating phecodes from ICD tables using join my mysql or merge in R. The columns are as follows:
 
- <b>phecode</b>               The phecode label
- <b>ICD</b>                         The ICD code included in the phecode grouping
- <b>vocabulary_id</b>        A string indicating the type of ICD code (ICD9CM or ICD10CM)

Use [phecodeX_unrolled_ICD_CM.csv](https://github.com/PheWAS/PhecodeXVocabulary/blob/main/PhecodeX%20(version%201.0)/phecodeX_unrolled_ICD_CM.csv) for the clinical modification of ICD used in the United States. Use [phecodeX_unrolled_ICD_WHO.csv](https://github.com/PheWAS/PhecodeXVocabulary/blob/main/PhecodeX%20(version%201.0)/phecodeX_unrolled_ICD_WHO.csv) WHO ICD-10 codes.

### phecodeX to ICD descriptive map
A highly descriptive file that includes both phecode strings and ICD descriptions. This file is “flat” (i.e. not “unrolled”) such that child codes are not mapped to parents. This file is useful for examining which ICDs inform a particular phecode. The columns are as follows:
 
- <b>phecode</b>               The phecode label
- <b>phecode_string</b> A descriptive label for phecode
- <b>category_num</b>   A numeric value corresponding to the phecode category
- <b>category</b>              A string indicating the phecode category
- <b>ICD</b>                         The ICD-9 or ICD-10 code
- <b>vocabulary_id</b>          A string indicating the type of ICD code (ICD9CM, ICD10CM, or ICD10)
- <b>ICD_string</b>           The string description of the ICD code
- <b>ICD_chapter</b>       The chapter of the ICD code

Use [phecodeX_ICD_CM_map_flat.csv](https://github.com/PheWAS/PhecodeXVocabulary/blob/main/PhecodeX%20(version%201.0)/phecodeX_ICD_CM_map_flat.csv) for the clinical modification of ICD used in the United States. Use [phecodeX_ICD_WHO_map_flat.csv](https://github.com/PheWAS/PhecodeXVocabulary/blob/main/PhecodeX%20(version%201.0)/phecodeX_ICD_WHO_map_flat.csv) WHO ICD-10 codes.

For files that are compatible with the R PheWAS package, along with example code, use this [link](https://github.com/PheWAS/PhecodeX).
