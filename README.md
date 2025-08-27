# 4-to-2 Priority Encoder with Valid Output

This project is a simple digital design of a 4-to-2 priority encoder with a valid output signal. I built and tested it in Logisim Evolution to understand how encoders behave when multiple inputs are active at the same time. The encoder ensures that the highest-priority input always takes precedence, which is an important concept in interrupt controllers and other digital systems.

## Project Overview
The encoder has four inputs (D3, D2, D1, D0) and produces two outputs (A1, A0) along with a valid output signal. The priority order is defined as:

D3 > D2 > D1 > D0

If more than one input is active, the encoder outputs the binary code corresponding to the highest-priority input. The valid output goes high whenever any input is active.

## Circuit Details
- Inputs: D3, D2, D1, D0  
- Outputs: A1 (MSB), A0 (LSB), Valid  
- Logic gates used: OR, AND, and NOT  

The circuit is entirely constructed using basic gates in Logisim Evolution.

## Truth Table
Below is the simplified truth table showing how the encoder behaves:

| D3 | D2 | D1 | D0 | A1 | A0 | Valid |
|----|----|----|----|----|----|-------|
| 0  | 0  | 0  | 1  | 0  | 0  | 1     |
| 0  | 0  | 1  | 0  | 0  | 1  | 1     |
| 0  | 1  | 0  | 0  | 1  | 0  | 1     |
| 1  | 0  | 0  | 0  | 1  | 1  | 1     |

The encoder always resolves to the highest-priority input if multiple lines are active.

## Testing
I manually toggled the inputs in Logisim Evolution and confirmed the output values matched the expected behavior. Some examples:

- D0 = 1 → Output = 00, Valid = 1  
- D1 = 1 → Output = 01, Valid = 1  
- D2 = 1 → Output = 10, Valid = 1  
- D3 = 1 → Output = 11, Valid = 1  
- D0 = 1 and D2 = 1 → Priority goes to D2 → Output = 10, Valid = 1  
- D1 = 1 and D3 = 1 → Priority goes to D3 → Output = 11, Valid = 1  

In all cases, the results were consistent with the priority scheme.

## Repository Contents
- Circuit Files: contains the Logisim Evolution circuit files  
- All Inputs and Outputs.pdf: contains all input and output test screenshots  

## Conclusion
This project helped me practice digital logic design using Logisim Evolution while also reinforcing the idea of priority handling in encoders. It’s a small but useful building block for larger designs like interrupt controllers and multiplexing systems.
