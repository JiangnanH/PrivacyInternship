# Privacy in Synthetic generated data

## WGAN-GP
Based on the original implementation (available on this [repository](https://github.com/igul222/improved_wgan_training)) of WGAN with gradient penalty proposed by Gulrajani et al. in [Improved Training of Wasserstein GANs](https://arxiv.org/abs/1704.00028).

We have updated the code to work in python 3, refactorized it and added support to train with the original NIST dataset after applying some preprocessing.

Example of execution:
```
cd wgan-gp
python gan_nist.py --datapath /path/to/nist/data/folder
```
The NIST data folder expected is the one produced by the script `linkNist.py` in the root directory.

## NIST Data

Source: https://www.nist.gov/srd/nist-special-database-19

Summary table

| partition | writers | forms | digits | uppers | lowers | const | writer origin |
| --- | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |---|
| hsf_0 | 0000-0499 | SD1 | SD3 | SD3 | SD3 | SD19 | Census Field |
| hsf_1 | 0500-0999 | SD1 | SD3 | SD3 | SD3 | SD19 | Census Field |
| hsf_2 | 1000-1499 | SD1 | SD3 | SD3 | SD3 | SD19 | Census Field |
| hsf_3 | 1500-2099 | SD1 | SD3 | SD3 | SD3 | † | Census Field |
| hsf 4 | 2100-2599 | SD19 | SD7 | SD7 | SD7 | ø | High School |
| hsf 5 | 2600-3099 | - | - | - | - | ø | High School |
| hsf 6 | 3100-3599 | SD19 | SD19 | SD19 | SD19 | ø | Census MD |
| hsf 7 | 3600-4099 | SD19 | SD19 | SD19 | SD19 | ø | Census MD |
| hsf 8 | 4100-4169 | SD19 | † | † | † | † | Census MD |

SD3, SD7 are Special Databases 3 and 7 released as as the training and testing materials for the First Census OCR Systems Conference. A † indicates that those fields were completed but not processed at the time of the CD release. A ø indicates that the field was never filled out.