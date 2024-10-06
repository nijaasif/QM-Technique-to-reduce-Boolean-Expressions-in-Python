# QM-Technique-to-reduce-Boolean-Expressions-in-Python
# Project Overview
This project implements the Quine-McCluskey algorithm in Python, which is used for minimizing Boolean functions. The Quine-McCluskey algorithm provides a systematic method to simplify Boolean expressions, similar to Karnaugh Maps, but can handle larger numbers of variables more efficiently.

The project takes minterms (in decimal form) as input, converts them to binary representations, and then applies the Quine-McCluskey procedure to find prime implicants. It further identifies essential prime implicants and generates a minimized Boolean expression.

# Files in the Project
QM_Technique.ipynb: This is the primary script file that contains the full implementation of the Quine-McCluskey algorithm.
# How It Works
1. Input
The program expects the user to input minterms (as a comma-separated list of integers). These minterms represent the "1" values in the truth table of the Boolean function to be minimized.

2. Binary Representation
Each minterm is converted into its binary equivalent. The program considers a fixed number of variables (5 in this case), so the binary representation is padded with leading zeros as necessary.

3. Prime Implicants
The algorithm groups the binary minterms based on the number of '1's they contain. It then tries to combine adjacent terms that differ by only one bit, creating prime implicants by substituting the differing bit with a dash (-), which represents "don't care."

4. Prime Implicants Chart
A chart is created that maps each prime implicant to the minterms it covers. This helps in determining which prime implicants are essential, meaning they must be included in the final minimized expression to cover all the minterms.

5. Essential Prime Implicants
The algorithm identifies the essential prime implicants that cover minterms not covered by any other implicant. These are then used to form the minimized Boolean expression.

6. Boolean Expression
The final Boolean expression is output in a human-readable form, where each variable is denoted by a letter (A, B, C, D, E). Variables with a value of 1 are included as is, while those with a value of 0 are complemented (denoted by a prime, e.g., A').

# Key Functions
get_minterms(): Prompts the user to enter a list of minterms.
binary_representation(): Converts decimal numbers to binary strings with leading zeros.
count_ones(): Counts the number of '1's in a binary string.
find_prime_implicants(): Groups minterms by their number of '1's and generates prime implicants.
get_prime_implicants_chart(): Creates a chart that shows which minterms are covered by each prime implicant.
select_essential_prime_implicants(): Identifies the essential prime implicants.
implicant_to_expression(): Converts a binary implicant into a Boolean expression.
quine_mccluskey(): Runs the Quine-McCluskey algorithm and outputs the minimized Boolean expression.
# Dependencies
Python 3.x
itertools library (standard Python module)
# Usage Instructions
Run the Script:

You can run the script by executing it in any Python environment. For example, using Jupyter Notebook or Google Colab.
When prompted, enter the minterms in decimal form, separated by commas (e.g., 0, 1, 5, 7, 8).
# Output:

The script will output the essential prime implicants and the minimized Boolean expression based on the given minterms.
# Future Improvements
Support for don't-care terms could be added to further simplify the Boolean expression when some combinations of inputs don't affect the output.
Extend the algorithm to handle more than 5 variables dynamically.
# License
This project is licensed under the MIT License. Feel free to use and modify it as per your needs.
