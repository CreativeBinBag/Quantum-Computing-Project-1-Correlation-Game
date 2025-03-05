# CorrelationGame

A Python project simulating the process of adding classical bits, introducing correlations between them using CNOT gates (Controlled-NOT), and reducing the system by removing uncorrelated bits. It's a simplified model to explore how state space can be reduced through correlations.

## Purpose and Motivation

The goal is to visualize and understand how correlations between bits can reduce the complexity of a system. By applying CNOT gates, we create dependencies between bits, and then we can simplify the system by removing bits that are not correlated with others. This has connections to quantum computing concepts like entanglement and state preparation.

## How It Works (Conceptual Overview)

The simulation works as follows:

1.  **Bit Addition:** Classical bits (0 or 1) are added to the system. Initially, each bit is considered uncorrelated.
2.  **CNOT Application:** CNOT gates are randomly applied to pairs of bits. This introduces correlations: the state of the target bit becomes dependent on the state of the control bit.
3.  **Uncorrelated Bit Removal:** Bits that are not correlated with any other bits are removed, simplifying the system.

## Dependencies

*   `random` (built-in Python module)
*   `numpy` (for numerical operations)

## Installation

1.  Make sure you have Python 3.x installed.
2.  Install the `numpy` package:

    ```bash
    pip install numpy
    ```

## Usage

Save the code in a file called `correlation_game.py`. Then, you can use it like this:

```python
from correlation_game import CorrelationGame

game = CorrelationGame()
for _ in range(9):
    game.add_a_new_bit()

for _ in range(10):
    game.randomCNOT()

game.remove_uncorrelated_bits()

print("Final State:", game.state)
print("Correlated Bits:", game.get_correlated_bits())
