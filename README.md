# ECE2112: Programming Assignment 1
**Ryan Joseph C. Dungca, 2ECE-D**

This repository contains code for Programming Assignment 1 of the course ECE2112, covering three problems related to _Module 1 - Base Computing with Python_. The creation of this code demonstrates the ability to:

- use basic Python functions, operators, and string operations;
- manipulate strings using indexing, slicing, and built-in string methods;
- apply sequence unpacking to manipulate the elements of a list; and
- construct simple Python functions that return a specified result.

To view the code itself, access the [related Python notebook file](ECE2112-PA1.ipynb).

# A. Word Rotation Problem
>_Objective_: Create a function named `rotate_word()` that accepts a non-empty string. Move the first character of the string to the end while keeping all remaining characters in their original order. Preserve the capitalization of every character.

The constructed function utilizes basic string slicing and indexing to achieve the desired objective for the input string `word`:
- `word[0]` identifies the first character of `word`, which has an index of 0, and
- `word[1:]` method slices beginning from the second character of `word`, and returns the rest of the string.

It is noted that, if the slice method is not given arguments for the start index, end index, or step, it will default to starting with the first character, ending with the last character, and keeping all characters or having a step of 1, respectively.     

Thus, by providing no ending index or step, the method `word[1:]` can be interpreted as `word[1:len(word):1]`: it will start at the _second_ character, and return the rest of the string. This result is then joined to the first character of the word by concatenation.

The constructed function is:
```py
def rotate_word(word):
    return word[1:] + word[0]
```

# B. Username Builder Problem
>_Objective_: Create a function named `make_username()` that accepts two strings: `first_name` and `last_name`. The function must:
> 1. convert all letters to lowercase;
> 2. remove all spaces from the first name;
> 3. remove all spaces from the last name; and
> 4. join the processed first and last names using one period (.).

The constructed function uses two methods to process both `first_name` and `last_name` to make them appropriate for use in a username:
- `lower()` method is used to convert the entire string to lowercase, and
- `replace(" ", "")` method, in function, erases all instances of the space character ` `.

These methods are stacked and applied to both inputs. These are then joined using the prescribed format `first_name.last_name`.

The constructed function is:
```py
def make_username(first_name, last_name):
    return first_name.lower().replace(" ", "") + "." + last_name.lower().replace(" ", "")
```

# C. Bookend Swap Problem
>_Objective_: Create a function named `swap_bookends()` that accepts a list containing at least two elements. Unpack the list into three variables:
> - `first` – the first element;
> - `middle` – a list containing everything between the first and last elements; and
> - `last` – the last element.
> 
>Using these variables, return a new list in which the first and last elements have exchanged positions. The elements in `middle` must remain in their original order. Do not modify the input list.

The constructed function uses extended sequence unpacking for `middle` to dynamically adapt to the length of the input list. The elements of the input list `items` is assigned to the variables `first, *middle, last` as prescribed by the objective: the first element is `first`, the last element is `last`, and all remaining elements in between them are assigned to the list `middle`.

When returning the list, extended sequence unpacking is also used on `middle` to properly interpret each element of the list, instead of treating the list as a singular element.

The constructed function is:
```py
def swap_bookends(items):
    first, *middle, last = items
    return last, *middle, first
```

## History
- 2026, August 20: File created.
- 2026, August 21: Reworded explanation for problem A; naming convention changes; notebook uploaded and linked.
- 2026, August 27: Added overall assignment objectives.
- 2026, August 30: Uploaded revised notebook.
- 2026, September 4: Updated code block format.
