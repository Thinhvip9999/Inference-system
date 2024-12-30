An inference system is a framework for deriving logical conclusions from a set of premises or facts. In computer science, especially in artificial intelligence, inference systems are used to implement reasoning processes. They are used in various applications like expert systems, natural language processing, and automated theorem proving.

Here's a more detailed explanation of each key component and file in this repository:

### Files Overview

- **backwardChaining.py**:
  - Implements the Backward Chaining algorithm for inference.
  - This algorithm works backward from the goal (query) to determine if it can be inferred from the known facts and rules.
  - It parses a knowledge base and query from a file and determines if the query can be inferred.
  - It involves recursively proving that the premises of rules leading to the query are true.

- **converter.py**:
  - Provides functions to convert logical sentences to Conjunctive Normal Form (CNF).
  - This involves eliminating biconditional (`<=>`) and implication (`=>`) operators and applying De Morgan's laws to move negations inward.
  - CNF is a standard form of a logical formula that is required for certain algorithms like the DPLL algorithm used in SAT solvers.

- **dpll.py**:
  - Implements the DPLL (Davis-Putnam-Logemann-Loveland) algorithm for SAT (satisfiability) solving.
  - It includes techniques like unit propagation, pure literal elimination, and recursive splitting (branching).
  - This algorithm is used to determine if a given logical formula can be satisfied, i.e., if there exists an assignment of truth values to variables that makes the formula true.

- **forwardChaining.py**:
  - Implements the Forward Chaining algorithm for inference.
  - This algorithm works forward from known facts to derive new facts using rules.
  - It parses a knowledge base and query from a file and derives conclusions based on known facts and rules.
  - It involves adding new facts to a set of known facts until the query is derived or no more facts can be added.

- **iengine.py**:
  - The main entry point for the inference system.
  - It supports multiple inference methods (Truth Table, Forward Chaining, Backward Chaining, Resolution, and DPLL) based on the provided arguments.
  - This script reads command-line arguments to determine which inference method to use and which file to parse.

- **parser.py**:
  - Contains utility functions for parsing logical expressions, handling parentheses, and extracting literals and clauses.
  - It includes methods to find and process tokens in logical expressions, which are essential for converting and manipulating these expressions in various algorithms.

### Setup and Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Thinhvip9999/Inference-system.git
   cd Inference-system
   ```

2. **Run the inference engine**:
   ```bash
   python iengine.py <filename> <method>
   ```
   - `<filename>`: The file containing the knowledge base and query.
   - `<method>`: The inference method to use (`TT`, `FC`, `BC`, `RES`, or `DPLL`).

Example:
   ```bash
   python iengine.py example.txt FC
   ```
   This will run the Forward Chaining algorithm on the `example.txt` file.

### Contributions

Contributions are welcome. Please fork the repository and submit a pull request for any improvements or additional features.

### Inference System Explanation

An inference system can be broadly categorized into the following components:

1. **Knowledge Base (KB)**:
   - A collection of facts and rules that represent the information about a certain domain.
   - Facts are statements that are known to be true.
   - Rules are conditional statements that describe how new facts can be derived from existing facts.

2. **Inference Engine**:
   - The core component that applies logical rules to the knowledge base to derive new information.
   - It can operate in different modes like Forward Chaining, Backward Chaining, and others.

3. **Inference Methods**:
   - **Forward Chaining**:
     - Starts with known facts and applies rules to infer new facts until the query is derived or no more facts can be inferred.
     - It is data-driven and suitable for situations where all data is available upfront.
   - **Backward Chaining**:
     - Starts with the goal (query) and works backward to see if it can be derived from known facts and rules.
     - It is goal-driven and suitable for situations where we need to determine if a specific conclusion can be reached.
   - **DPLL (Davis-Putnam-Logemann-Loveland)**:
     - A complete, backtracking-based search algorithm for deciding the satisfiability of propositional logic formulas in CNF.
   - **Resolution**:
     - A rule of inference used for automated theorem proving.
     - It involves refuting the negation of the query and deriving a contradiction.

By understanding these concepts and how they are implemented in the provided code, you can effectively utilize the inference system to solve various logical inference problems.
