# Python Week 6 Assessed Workshop

---

#### Note on workshop attendance...

Please make sure you sign the workshop attendance sheet. 

Work that has been submitted via remote working for core workshops will only be accepted if:

 - students have arranged this with module lead (Phil)
 - students agree that inclusion of remote work in assessed portfolio may require a viva discussion to check understanding

---

Work in CodeSpaces. 

You may use the following cheat sheets if you need to look up any Python commands.

https://github.com/phil-lewis-exe/PythonCheatSheets

**This week you may not use any other websites to help you code.**

**You must ask if you need to use a website to translate the task questions**

**Mobile phones may not be used in class**

---

## TASKS


### Part 1: Rolling Dice

Work in code file `6b_part1.py`

This contains starter code that:

 - defines a function to simulate the rolls of a number of dice. 
 - demonstrates how to call this function to roll two dice, storing the dice roll as variable `demo1` and displays the result.

```python
import random

def roll_dice(n_dice):
    n_sides = 6
    # you do not need to change the code below
    rolls = []
    for i in range(n_dice):
        rolls.append(random.randint(1,n_sides))
    return rolls

demo1 = roll_dice(2)
print(demo1)
```

Restructure and change the function so that:

 - it takes the two arguments `n_dice` and `n_sides` (e.g. an 8 sided dice can return values 1-8)
 - if not provided `n_dice` will take a default value of 1 
 - if not provided `n_sides` will take a default value of 6

Below the function definition add additional demonstrations storing the results as `demo2` `demo3` and `demo4`, displaying the results in each case:

`demo2` : shows how to calls the function to roll three 10 sided dice

`demo3` : shows how to call the function to roll four dice with 8 sides, specifying the arguments in reverse order 

(i.e. the values must passed in the order `n_sides` then `n_dice` as keyword arguments).

`demo4` : shows how to call the function without specifying arguments (so that the default values are used).


---

### Part 2: Finding the length of the longest word

Work in code file `6b_part2.py`

This contains the following starter code that defines a function `max_length` that takes three arguments (`word1`, `word2` and `word3`) that contain strings.

The function makes a list of all the provided words then returns the length of the longest word in the list. 

It then demonstrates how to call this function to using three example words, stores the value returned in variable `demo1`, and displays the result.

```python
def max_length(word1, word2, word3):
    word_list = [ word1, word2, word3 ]   
    # you do not need to change the code below
    longest_word = word_list[0]
    for item in word_list:
        if len(item) > len(longest_word):
            longest_word = item
    return len(longest_word)


demo1 = max_length("cat","beetles","dogs")
print(demo1)
```

Edit the function code so that the function will work with any set of words passed as individual input arguments. 

To demonstrate add the following additional code examples to show your function works correctly in each case: 

```python
demo2 = max_length("cat")
print(demo2)

demo3 = max_length("cat","dogs")
print(demo3)

demo4 = max_length("mouse","cat","apple","banana","enormous")
print(demo4)
```

---


### Part 3: Processing a string to make replacements

Work in code file `6b_part3.py`

This contains the following starter code that defines a function `process_text`.

This is set up to take two arguments:

 - `mystr` that contains a text string to process
 - an additional argument that contains a dictionary that defines a set of word replacements pairs, e.g.

`mod_dict = {"cat": "dog", "red": "blue"}`  

It then demonstrates how to call this function, stores the value returned in variable `demo1` and displays the result.

```python
def process_str(mystr, mod_dict):
    for key, value in mod_dict.items():
        # you do not need to change the code below
        target = key
        replacement = value
        print(f" ( replacing {target} with {replacement} ) ")
        mystr = mystr.replace(target, replacement)
    return mystr

mod_dict = {"cat": "dog", "red": "blue"}
demo1 = process_str("The cat sat on the red mat.",mod_dict)
print(demo1)
```

Edit the function code so that the function will work with any set of target and replacement pairs passed as an arbitrary number of keyword arguments `kwargs`. 

You should update the demonstration code so that it makes the replacements `cat -> dog` and `red -> blue` using your modified function, i.e.

```python
demo1 = process_str("The cat sat on the red mat.", cat="dog", red="blue")
print(demo1)
```

Then add the additional demonstrations to show that your code works correctly in each case.

```python
demo2 = process_str("The cat sat on the red mat.", cat="mouse")
print(demo2)
demo3 = process_str("The cat sat on the red mat.", cat="flea", sat="hopped", mat="dog")
print(demo3)
```

---

### Part 4: Creating a greetings module

The following python code defines some functions to display greetings. 

**Note there is a typo in the code template - please correct it as below**

```python
def say_hello(name):
    print(f"Hello {name}!")

def say_hi(name=None):
    # TYPO PLEASE EDIT TO REMOVE THE not
    if name is None:
        print("Hi, whoever you are!")
    else:
        print(f"Hi, its good to see you {name}!")

```

We want to store these functions so that we can call them as python module `greetings`.

Create an appropriately named python module file to do this. (e.g. click on the new file icon in the file panel toolbar).

Then work in code file `6b_part4.py`

Show how to import the `greetings` module and call the functions it contains using appropriate code so that the file will produce the following output:

```
Hi, its good to see you Sarah!
Hello Fred!
Hi, whoever you are!
```

---

### Submitting your work

Run the following lines in the terminal to stage, commit and push your code back to your GitHub repository:

```
git add .
git commit -m "completed 6b"
git push
```

To check your work has been saved you can run the line of code below in the terminal to get the web address of the repository in GitHub. Goto the repository and check the completed code files are stored.

```
git config --get remote.origin.url
```
