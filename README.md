# Romanized Telugu NLP Robustness

Major project: Evaluating and improving the semantic robustness of NLP models to Romanization variations in Telugu.

## Project Status
- Phase 1: Dataset setup and verification completed.
- Next: Dataset structure and exploration.

## CMTET Dataset Exploration — Summary

### Dataset structure
- Total records: 19,868
- Sentiment classes: POS, NEG, NTL
- No missing values in the parsed DataFrame.
- All sentence token counts match their corresponding language-tag counts.

### Sentiment distribution
- POS: 7,929
- NEG: 7,717
- NTL: 4,222

### Duplicate and annotation observations
- 144 duplicate sentence texts were identified by the initial duplicate check.
- 73 distinct sentence texts occur more than once.
- 51 repeated sentence groups contain conflicting sentiment labels.
- 172 records belong to those conflicting groups (0.87% of the dataset).
- Original labels are preserved; no records have been removed.

### Sentence length
- Mean: 18.95 whitespace-separated tokens.
- Median: 14 tokens.
- Minimum: 5 tokens.
- Maximum: 603 tokens.
- Sentence lengths are right-skewed, with a small number of very long examples.
- NEG sentences have the highest mean and median lengths among the three sentiment classes.

### Language composition
- TE: 160,286 tokens (42.56%).
- EN: 130,620 tokens (34.69%).
- UNIV: 70,971 tokens (18.85%).
- NE: 14,709 tokens (3.91%).

The dataset contains substantial English–Telugu code-mixing. Language-tag definitions should be interpreted according to the dataset documentation.

### Decisions for later stages
- Preserve the original dataset and annotations.
- Prevent identical sentence texts from leaking across training and test splits.
- Investigate conflicting labels during data-quality analysis.
- Check model-specific token lengths before choosing input truncation strategies.
