# Cross-Validation Analysis: Moran's I vs Differential Gene Expression

## Overview
This analysis compares the results from two different methods for identifying significant genes in pseudotime analysis across three modalities (K4, K27, RNAPII) and two lineages (CM, EM).

## Methods Compared
1. **Moran's I Test**: Tests for spatial autocorrelation in gene expression patterns
2. **Differential Gene Expression (DE)**: Tests for significant changes in gene expression along pseudotime

## Key Findings

### Overall Statistics
- **Total Moran's I significant genes**: 144,408
- **Total DE significant genes**: 115,079
- **Total overlapping genes**: 113,550
- **Overall Jaccard index**: 0.7780

### Modality-Specific Results

#### K4 Modality
- **CM Lineage**:
  - Moran's I genes: 23,028
  - DE genes: 18,568
  - Overlapping: 17,987 (96.9% of DE genes)
  - Jaccard index: 0.7618
  - Moran's precision: 0.7810
  - DE precision: 0.9687

- **EM Lineage**:
  - Moran's I genes: 23,445
  - DE genes: 19,773
  - Overlapping: 19,240 (97.3% of DE genes)
  - Jaccard index: 0.8024
  - Moran's precision: 0.8206
  - DE precision: 0.9730

#### K27 Modality
- **CM Lineage**:
  - Moran's I genes: 24,768
  - DE genes: 18,384
  - Overlapping: 18,384 (100% of DE genes)
  - Jaccard index: 0.7422
  - Moran's precision: 0.7422
  - DE precision: 1.0000

- **EM Lineage**:
  - Moran's I genes: 24,630
  - DE genes: 20,147
  - Overlapping: 20,083 (99.7% of DE genes)
  - Jaccard index: 0.8132
  - Moran's precision: 0.8153
  - DE precision: 0.9968

#### RNAPII Modality
- **CM Lineage**:
  - Moran's I genes: 24,460
  - DE genes: 18,877
  - Overlapping: 18,816 (99.7% of DE genes)
  - Jaccard index: 0.7673
  - Moran's precision: 0.7692
  - DE precision: 0.9967

- **EM Lineage**:
  - Moran's I genes: 24,077
  - DE genes: 19,330
  - Overlapping: 19,040 (98.5% of DE genes)
  - Jaccard index: 0.7813
  - Moran's precision: 0.7907
  - DE precision: 0.9849

## Cross-Validation Results

### High Concordance
- **DE precision**: 96.9% - 100% across all conditions
- This indicates that nearly all genes identified as significant by DE are also identified by Moran's I

### Method-Specific Findings
- **Moran's I identifies more genes**: Consistently identifies 20,000+ genes per condition
- **DE is more selective**: Identifies 18,000-20,000 genes per condition
- **High overlap**: 96.9% - 100% of DE genes are also identified by Moran's I

### Lineage-Specific Patterns
- **EM lineage shows higher concordance**: Generally higher Jaccard indices (0.78-0.81)
- **CM lineage shows good concordance**: Jaccard indices range from 0.74-0.77

### Modality-Specific Patterns
- **K27 shows highest DE precision**: 100% in CM lineage, 99.7% in EM lineage
- **K4 shows most balanced results**: Moderate Jaccard indices but good precision
- **RNAPII shows consistent performance**: Good overlap across both lineages

## Genes Consistently Significant

### Cross-Method, Cross-Lineage Genes
Several genes appear significant in both methods and both lineages across modalities:

**K4 Modality** (14,533 genes):
- A1BG-AS1, A2M, A2ML1, A3GALT2, A4GALT, A4GNT, AA06, AAAS, AACS, AADAC, AADACL2, AADACL3, AADAT, AAGAB, AAK1, AAMDC, AANAT, AASDH, AATBC, AATF

**K27 Modality** (15,090 genes):
- A1BG, A1BG-AS1, A1CF, A2M, A2M-AS1, A2ML1, AA06, AAAS, AACS, AADAC, AADACL2-AS1, AADACL3, AAGAB, AAK1, AAMDC, AAR2, AARD, AARS2, AARSD1, AASDH

**RNAPII Modality** (14,691 genes):
- A1BG, A2ML1, A4GALT, AA06, AAAS, AADAC, AADACL2, AADACL2-AS1, AADACL4, AADAT, AAGAB, AAK1, AAMDC, AANAT, AAR2, AARS, AARS2, AASDHPPT, AASS, AATBC

## Method-Specific Genes

### Genes Unique to Moran's I
- Typically 4,000-6,000 genes per condition
- Examples: A2M-AS1, AADACL4, AAMP, AAR2, AARS, AARS2, AARSD1, AASS, ABAT, ABCA12

### Genes Unique to DE
- Typically 0-600 genes per condition
- Examples: ABI3BP, ACMSD, ACTR5, ADAM12, ADAMTS15, ADAMTS18, ADAMTS8, ADAMTSL1, ADCK5, ADCY2

## Conclusions

1. **High Cross-Validation Success**: The two methods show excellent concordance with 96.9% - 100% of DE genes also identified by Moran's I

2. **Complementary Approaches**: 
   - Moran's I identifies more genes overall (spatial autocorrelation)
   - DE is more selective but highly precise (temporal changes)

3. **Method Reliability**: The high overlap suggests both methods are identifying biologically relevant genes

4. **Lineage Consistency**: Both CM and EM lineages show similar patterns of concordance

5. **Modality Robustness**: Results are consistent across all three modalities (K4, K27, RNAPII)

## Recommendations

1. **Use both methods**: They provide complementary information
2. **Focus on overlapping genes**: These represent the most robust findings
3. **Investigate method-specific genes**: May represent different biological processes
4. **Consider lineage-specific patterns**: EM lineage shows slightly higher concordance

## Files Generated
- `cross_validation_summary.csv`: Detailed statistics
- `simple_cross_validation.sh`: Analysis script
- `detailed_analysis.sh`: Detailed analysis script
- `cross_validation_summary.md`: This summary report
