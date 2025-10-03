# TDD Driven StringCalculator

Build a StringCalculator functionality that can take up to two numbers, separated by commas, and will return their sum. 
for example “” or “1” or “1,2” as inputs.

> DO NOT jump into implementation! Read the example and the starting task below.

- For an empty string it will return 0
- Allow the Add method to handle an unknown amount of numbers
- Allow the Add method to handle new lines between numbers (instead of commas).
  - the following input is ok: “1\n2,3” (will equal 6)
  - the following input is NOT ok: “1,\n” (not need to prove it - just clarifying)
- Support different delimiters : to change a delimiter, the beginning of the string will contain a separate line that looks like this: “//[delimiter]\n[numbers…]” for example “//;\n1;2” should return three where the default delimiter is ‘;’ .
the first line is optional. all existing scenarios should still be supported
- Calling Method with a negative number will throw an exception “negatives not allowed” - and the negative that was passed. if there are multiple negatives, show all of them in the exception message.
- Numbers bigger than 1000 should be ignored, so adding 2 + 1001 = 2
- Delimiters can be of any length with the following format: “//[delimiter]\n” for example: “//[***]\n1***2***3” should return 6

## Tasks



Establish quality parameters:

- Ensure  maximum complexity (CCN) per function == 3

- Ensure 100% line and branch coverage at every step

  

Start Test-driven approach

1. Write the smallest possible failing test: give input `"" assert output to be 0 ` .
2. Write the minimum amount of code that'll make it pass.
3. Refactor any assumptions, continue to pass this test. Do not add any code without a corresponding test.


StringCalculator Test Specifications
Test ID	Test Name	Input	Expected Output	Notes
TC01	Empty string returns 0	""	0	Base case: empty input.
TC02	Single number returns itself	"1"	1	Simplest valid number.
TC03	Two numbers separated by comma	"1,2"	3	Basic addition with default delimiter.
TC04	Multiple numbers separated by commas	"1,2,3,4"	10	Supports unknown count of numbers.
TC05	Newline as delimiter along with comma	"1\n2,3"	6	Mixed delimiters (, and \n).
TC06	Custom single-character delimiter	"//;\n1;2;3"	6	Explicit custom delimiter overrides defaults.
TC07	Custom multi-character delimiter	"//[***]\n1***2***3"	6	Delimiter of arbitrary length.
TC08	Multiple negatives throw exception	"1,-2,-3"	Exception: negatives not allowed: -2, -3	Must report all negatives.
TC09	Numbers larger than 1000 ignored	"2,1001,3"	5	1001 is ignored.
TC10	Custom delimiter with number > 1000	"//;\n1002;2;3"	5	Large numbers skipped even with custom delimiter.
TC11	Custom delimiter with newline inside numbers	"//;\n1;2\n3"	6	Should combine both custom delimiter and \n.
