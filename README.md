
# Comparison Operators

## Introduction
In this lesson, we will be looking at operators in Python. Operators are, generally, used to compare two elements. They can be used to check equality, inequality, truthiness and falsiness, and value. They are a hugely important tool in programming that can be used to filter lists of elements, validate data, and assign and reassign values appropriately. Operators have a return value that can be a boolean, `True` or `False`, as well as an element being used for comparison. We will use operators frequently in our code, so, it is important to have a solid understanding of them. Let's get started!

## Objectives
* What are comparison operators
* How are comparison operators used
* What other kinds of operators are there

## What Are Comparison Operators?

Comparison operators (or Relational operators) take two elements and compare their values and then return a value that is either True or False. In Python, comparison operators are:

```python
== # tests equality between two elements
!= # tests inequality between two elements
<, >, <=, >= # each tests the value between two elements
```
Perhaps the last line's operators are a little more familiar because we've seen these operators in math classes. But the first two might be bit more confusing, so, let's dive into those first.

The double equals operator (`==`) is testing whether the value of the first element is equal to that of the second element (e.g. `element1 == element2`).
```python 
False == True # returns False
False == False # returns True
10 == 20 # returns False
10 == 10 # returns True
"hi" == "HI" # returns False
"heLLo" == "heLLo" # returns True
```

The bang (exclamation point) equals operator (`!=`) is testing whether the value of first element is **NOT** equal to that of the second element (e.g. `element1 != element2`).

```python 
True != True # returns False
True != False # returns True
10 != 20 # returns True
10 != 10 # returns False
"hi" != "HI" # returns True
"heLLo" != "heLLo" # returns False
```



Now onto the third grouping of comaparison operators. The greater than (`>`), less than (`<`), greater than or equal to (`>=`) and less than or equal (`<=`) to operators also only return True or False from an operation. Essentially they are doing the same thing as the operators we see above, but the comparison is slightly different.

```python
True > True # False
True >= True # True
10 <= 10 # True
7 < 7 # False
10 < 100 # True
100 > 101 # False
```
We can even compare strings to see which is alphabetically greater or less than. A string is greater than if it comes after another string alphabetically (or if its ascii value is greater). An important note is that capital letters have lower ascii values, which means that they come earlier in the alphabet than lowercase letters. For example the ascii Alphalbet would look something like: `Aa Bb Cc Dd Ee Ff ... Xx Yy Zz` with `A` having the lowest ascii value and `z` having the highest ascii value.

```python
"APPLE" < "apple" # True
"aaron" > "alexa" # False
"Terrance" > "Teresa" # True
"SAME" == "SAME" # True
```
So, when comparing strings to other strings, it is important to be cognizant of whether the comparison should be case sensitive or not.

## How Are Comparison Operators Used?
We've already seen some examples of this above. Essentially, we use comparison operators to *compare* two things. So, the most basic structure is two elements with an operator in between. The return value will be `True` or `False`. The best way to get comfortable with comparison operators is through practice, so, let's take a look at some examples:


```python
print('1.', True != True) # False
print('2.', False == True) # False
print('3.', 10 == "10") # False
print('4.', "hi" != "HI") # True
print('5.', type(0) == int) # True
print('6.', ["hi"] == ["hi"]) # True
print('7.', "Thomas" != "Samantha") # True
```

Above we can see examples using both the `!=` and `==` operators to compare elements of several datatypes and values. Remember that these operators are testing for the value of each element.

Next, we will look at examples using the greater than (>), less than (<), greater than or equal to (>=) and less than or equal (<=) to operators.


```python
print('1.', True > True) # False
print('2.', True >= True) # True
print('3.', 10 <= 10) # True
print('4.', 7 < 7) # False
print('5.', 10 < 100) # True
print('6.', 100 > 101) # False
print('7.', "APPLE" < "apple") # True 
print('8.', "aaron" > "alexa") # False
print('9.', "Terrance" > "Teresa") # True
```

## Other Types of Operators
### Logical Operators

The next group of operators are logical operators. They compare truthy/falsy values. The operators are:
```python
and 
# Compares two elements. If both elements are truthy, the second element is returned
# If there is a falsy value, the first falsy value is returned

or 
# Compares two elements. The first truthy element is returned. 
# If both elements are falsy, the second element is returned

not 
# returns a boolean value that is the opposite of the truthy/falsy value of the element
```
Let's see these in action:

*try to reason what the values will be before running the code - **write** your answers in a comment next to the print statement*


```python
print("1.", 2 and 0) #
print("2.", False and 2) #
print("3.", True and 2) #
print("4.", 2 and 3) #
print("5.", 2 or []) #
print("6.", 0 or []) #
print("7.", not False) #
print("8.", not True) #
print("9.", not []) #
print("10.", not 0) #
print("11.", not 100) #
```

### Identity Operators

The next type of operators are identity operators, `is` and `is not`. They check to see if one element **is** or **is not** the other element. This is similar to `!=` and `==`. However there is one key difference. The `!=` and `==` check to see if the value of each element is the same, however, the `is` and `is not` operators check to see if the elements are the same element. 

Let's check it out:

*again, try to find the correct return value for each example and write the answer in a comment next to the print statement*


```python
x = {'name': "example"}
b = x
c = {'name': "example"}
print("1.", {} is {}) #
print("1A.", {} == {}) #
print("2.", [] is []) #
print("3.", "Hi" is "Hi") #
print("4.", ["same"] is ["same"]) #
print("4A.", ["same"] == ["same"]) #
print("5.", 9 is not 10) #
print("6.", x is b) #
print("7.", b is c) #
print("7A.", b == c) #
print("8.", x is not c) #
```

As we can see, the `is` and `is not` operators are checking to see if the objects are exactly the same object in memory. However, the `==` and `!=` operators are simply checking to see if the value of each element is the same. This will become clearer as we learn more about how python stores data. 

All objects are stored in a specific place in memory, we can think of this as an address on the computer, so, all objects will have their own unique address. A **variable**, like `x`, is a **reference** to that object and not the object itself. So, when we use the `is` or `is not` operator, we are checking to see if the address of the object is the same as another object. When we use the `==` or `!=` operators, we are checking to see if they are basically equal in value, irrespective of whether they are the same or two different objects.

### BONUS: Ternary Operator 

The next operator is the Ternary. It is a bit more of a complicated operator, but it can be very useful when you would like to decide which value to assign to a variable. Ternaries are good for one-line conditions, but anything more complex makes ternary operators quite difficult to read. Let's check it out:


```python
my_condition = True
value = 10 if my_condition else 1000
print(value)
```


```python
# let's say we are receiving two variables with different 
# values and we want to assign the higher value to a new variable
x = 12
y = 20
new_variable = x if x > y else y
# here we are saying, take the value of x if it is greater than the value of y. else take the value of y
# since x > y evaluates to false, the ternary returns the value of the variable after the else statement or y
print(new_variable)
```

# Summary
In this lesson, we looked at operators in Python. Operators are fundamental tools in many languages that provide a succicnt way to compare multiple elements. Comparison operators return boolean values and compare the value between two elements. Logical operators compare the truthiness and falsiness of two elements and either return one of the elements or a boolean value. Logical operators compare two elements for their equality, that is whether they are the same object or not, and they return a boolean value. Lastly, ternary operators are used to assign a value to a variable. They use an if statement and another operator to compare two values and return one of two values, which is used to assign the value of a variable.
