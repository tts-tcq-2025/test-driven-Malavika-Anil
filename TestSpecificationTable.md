| Test ID | Test Name                             | Input                  | Expected Output                         | Notes                                    |
| ------- | ------------------------------------- | ---------------------- | --------------------------------------- | ---------------------------------------- |
| TC01    | Empty String Returns Zero             | `""`                   | `0`                                     | Validates base case                      |
| TC02    | Single Number Input                   | `"1"`                  | `1`                                     | Validates single number parsing          |
| TC03    | Multiple Comma-Separated Numbers      | `"1,2,3"`              | `6`                                     | Validates summing multiple numbers       |
| TC04    | Newline as Valid Delimiter            | `"1\n2,3"`             | `6`                                     | Supports newline delimiter               |
| TC05    | Custom Single-Character Delimiter     | `"//;\n1;2"`           | `3`                                     | Validates custom delimiter usage         |
| TC06    | Custom Multi-Character Delimiter      | `"//[***]\n1***2***3"` | `6`                                     | Validates multi-character delimiter      |
| TC07    | Multiple Negatives in Input           | `"1,-2,-3"`            | Exception: negatives not allowed: -2,-3 | Must report all negatives                |
| TC08    | Numbers Greater Than 1000 Are Ignored | `"2,1001"`             | `2`                                     | Validates exclusion of large numbers     |
| TC09    | Only Large Numbers Present            | `"1001,1002"`          | `0`                                     | Validates when all numbers are too large |
| TC10    | Invalid Input with Trailing Delimiter | `"1,\n"`               | Exception: invalid input format         | Validates rejection of malformed numbers |
