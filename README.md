(Assuming that the number reading function code is saved in a separate file called tech_number_reading_functions; you can, of course, call the file anything you want, just change it appropriately in gosub_scene.)

NUMBER = number you want to have spelled out
NUMBER_SPELLED = temp for the result (spelled out number). Can also be a normal var of course

*set number_count_1 length(NUMBER)
*set number_count_1b NUMBER
*gosub_scene tech_number_reading_functions number_reading_function_1
*temp NUMBER_SPELLED number_count_1_result_total

After that, if NUMBER is 123, the sentence

"Numeric value ${NUMBER} spelled out is ${NUMBER_SPELLED}."

would give this result:

"Numeric value 123 spelled out is one hundred and twenty-three."

There are three different settings for this code.
ON (*set number_reading_function_mode 1) means that, when called, the number reading function will spell out all numbers smaller than or equal to a billion.
Numbers above one billion will be given as "more than a billion".
OFF (*set number_reading_function_mode 0) turns the function completely off (duh), numbers will stay numeric.
HYBRID (*set number_reading_function_mode 2) is the same as ON, but numbers above one billion will stay numeric.

To use this function, you also need to declare the following vars in your startup.txt:
*create number_reading_function_mode 1
*create number_count_1 0
*create number_count_1b 0
*create number_count_1_1 0
*create number_count_1_2 0
*create number_count_1_3 0
*create number_count_1_4 0
*create number_count_1_5 0
*create number_count_1_6 0
*create number_count_1_7 0
*create number_count_1_8 0
*create number_count_1_9 0
*create number_count_1_result_total ""
*create number_count_1_result_0 ""
*create number_count_1_result_1 ""
*create number_count_1_result_2 ""
*create number_count_1_result_3 ""
*create number_count_1_result_4 ""
*create number_count_1_result_5 ""
*create number_count_1_result_6 ""
*create number_count_1_result_7 ""
*create number_count_1_result_8 ""
*create number_count_composite_ones_tens_done false
*create number_count_composite_ten_thousands_thousands_done false
*create number_count_composite_ten_millions_millions_done false
*create number_0 "zero"
*create number_1 "one"
*create number_2 "two"
*create number_3 "three"
*create number_4 "four"
*create number_5 "five"
*create number_6 "six"
*create number_7 "seven"
*create number_8 "eight"
*create number_9 "nine"
*create number_10 "ten"
*create number_11 "eleven"
*create number_12 "twelve"
*create number_13 "thirteen"
*create number_14 "fourteen"
*create number_15 "fifteen"
*create number_16 "sixteen"
*create number_17 "seventeen"
*create number_18 "eighteen"
*create number_19 "nineteen"
*create number_20 "twenty"
*create number_30 "thirty"
*create number_40 "fourty"
*create number_50 "fifty"
*create number_60 "sixty"
*create number_70 "seventy"
*create number_80 "eighty"
*create number_90 "ninety"

(number_reading_function_mode can be set to 0, 1 or 2 here depending on what you want as default.)
