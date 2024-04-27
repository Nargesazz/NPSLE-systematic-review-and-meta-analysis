# NPSLE-systematic-review-and-meta-analysis
Code snippets for a systematic review and meta-analysis on cerebral perfusion patterns in Neuropsychiatric Systemic Lupus Erythematosus (NPSLE). This repository includes scripts for statistical analysis.
import numpy as np

def calculate_se_rom(mu1, sigma1, mu2, sigma2):
    """
    Calculate the Standard Error (SE) of the Ratio of Means (RoM) for two groups.

    Parameters:
    - mu1 (float): mean of NPSLE
    - sigma1 (float): standard deviation of NPSLE
    - mu2 (float): mean of non-NPSLE
    - sigma2 (float): standard deviation of non-NPSLE

    Returns:
    - float: SE of the RoM
    """
    se_rom = np.sqrt(((sigma1 / mu1) ** 2) + ((sigma2 / mu2) ** 2)) * (mu2 / mu1)
    return se_rom

#For example Zhuo 2019:
mu1 = 33.65   # mean for NPSLE
sigma1 = 14.69  # standard deviation for NPSLE
mu2 = 36.02   # mean for non-NPSLE
sigma2 = 13.63  # standard deviation for non-NPSLE

se_rom = calculate_se_rom(mu1, sigma1, mu2, sigma2)
print("Standard Error of the Ratio of Means (RoM):", se_rom)
