# Drug Standsards
 This package provides tools for standardizing drug names into a single format.  For example; Benadryl and diphenhydramine refer to the same chemical entity. In certain tasks, such as mining the FDA Adverse Event Reporting System database, it is useful to standardize all drug names (i.e. convert all instances of Benadryl to diphenhydramine) in order to compute various statistics. This package uses a database of drug synonyms and brand names to return the generic name for a drug. To handle misspellings the `standardize` function will return the generic name for the most similar match based on Jario-Winkler similarity. A threshold can be set in order to specify the minimal similarity required to be considered a match.

## Installation

#### 1. Install drugstandards pacakge
`sudo pip install git+git https://github.com/user/mlbernauer/drugstandards`

## Usage
```import drugstandards as drugs

# This function takes a list of drug names and converts it into a list
# of generic names of equal length.
drugs.standardize(["metoprolol", "Benadryl", "prinvil"])

# Return generic names for matches greather than or equal to Jario-Winkler
# similarity of 0.95.  This will be conservative, returning None for elements
# that do not meet the cuttoff.
drugs.standardze(["metoprolal"], thresh=0.95)
```
