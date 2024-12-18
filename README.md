# Inference-system
#Inference-system
My inference system repository focuses on implementing various inference engines using Python. It serves as a resource for understanding and utilizing these essential algorithms and techniques in various applications.

## Files Overview

- **backwardChaining.py**: Implements the Backward Chaining algorithm for inference. It parses a knowledge base and query from a file and determines if the query can be inferred.
- **converter.py**: Provides functions to convert logical sentences to Conjunctive Normal Form (CNF). This includes elimination of biconditional and implication operators, application of De Morgan's laws, and distribution of OR over AND.
- **dpll.py**: Implements the DPLL (Davis-Putnam-Logemann-Loveland) algorithm for SAT solving. It includes unit propagation, pure literal elimination, and branching.
- **forwardChaining.py**: Implements the Forward Chaining algorithm for inference. It parses a knowledge base and query from a file and derives conclusions based on known facts and rules.
- **iengine.py**: Main entry point for the inference system. It supports multiple inference methods (Truth Table, Forward Chaining, Backward Chaining, Resolution, and DPLL) based on the provided arguments.
- **parser.py**: Contains utility functions for parsing logical expressions, handling parentheses, and extracting literals and clauses.

## Setup and Usage

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

## Contributions

Contributions are welcome. Please fork the repository and submit a pull request for any improvements or additional features.
