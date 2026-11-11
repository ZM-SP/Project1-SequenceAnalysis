# Project 1 - Sequence Analysis
<ins>Title and Purpose</ins>  
This Python programme analyses next-generation sequencing datasets containing control and genotoxic treatment groups. It identifies nucleotide mismatches against a known reference DNA sequence to characterise potential mutations.

<ins>How to Run the Programme</ins>  
Open the notebook in Google Colab and run all setup and function-definition cells, excluding the final analysis section. Load a new dataset using the provided setup code before applying the analysis functions to it.

<ins>Inputs and Outputs</ins>  
The programme requires a known reference DNA sequence string and sequencing reads stored as a list of dictionaries containing the keys read_id, sample, group and sequence. Outputs include a summary table of mismatch events, a table showing substitution mutation counts per group, and a dictionary containing an exploratory comparison of the three most frequent mismatch positions, including results from a two-sided Welch's t-test.

<ins>Code Design</ins>  
I chose not to import additional packages for ordering function results, although this could have reduced the amount of code required. Instead, I implemented the ordering logic myself to make the code easier to follow and understand. In step 4, I used for loops rather than list comprehensions, as I felt this made the more complex operations easier to interpret and debug, despite potentially increasing runtime. In step 5, I added a fallback section to handle cases where Welch's test did not produce results. This ensures the programme can still return some general informative descriptive results rather than failing when statistical significance cannot be determined.

<ins>Testing</ins>  
I tested the programme using three types of input, with assertions to check the expected outputs. A valid input checks that calculations and structure are correct, e.g. for mismatch counts. An empty input tests whether the programme can handle missing information e.g. no sequencing reads. An invalid input checks its robustness when given incorrectly formatted data.
