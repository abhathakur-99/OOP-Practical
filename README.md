# Python-Practicals
## 1. Write a program to find the nature of the roots of a quadratic equation
```
# Quadratic Equation: ax^2 + bx + c = 0

a = float(input("Enter coefficient a: "))
b = float(input("Enter coefficient b: "))
c = float(input("Enter coefficient c: "))

# Calculate discriminant
D = b**2 - 4*a*c

print("Discriminant (D) =", D)

# Nature of roots
if D > 0:
    print("The equation has real and distinct roots.")
elif D == 0:
    print("The equation has real and equal roots.")
else:
    print("The equation has imaginary (complex) roots.")
```
## 2. Write a program to accept a number ‘n’ and 
1. Check if ’n’ is prime 
2. Generate all prime numbers till ‘n’ 
3. Generate first ‘n’ prime numbers This program may be done using functions

```
# Function to check if a number is prime
def is_prime(num):
    if num <= 1:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True

# Function to generate all prime numbers till n
def primes_till_n(n):
    primes = []
    for i in range(2, n + 1):
        if is_prime(i):
            primes.append(i)
    return primes

# Function to generate first n prime numbers
def first_n_primes(n):
    primes = []
    num = 2
    while len(primes) < n:
        if is_prime(num):
            primes.append(num)
        num += 1
    return primes


# Main program
n = int(input("Enter a number n: "))

# a. Check if n is prime
if is_prime(n):
    print(f"{n} is a prime number.")
else:
    print(f"{n} is not a prime number.")

# b. Generate all prime numbers till n
print(f"Prime numbers till {n}:", primes_till_n(n))
```


# 3. Write a program to create a pyramid of the character ‘*’ and a reverse pyramid 

```
# Function to print pyramid
def pyramid(n):
    for i in range(1, n + 1):
        print(" " * (n - i) + "*" * (2 * i - 1))

# Function to print reverse pyramid
def reverse_pyramid(n):
    for i in range(n, 0, -1):
        print(" " * (n - i) + "*" * (2 * i - 1))


# Main program
rows = int(input("Enter number of rows: "))

print("\nPyramid:")
pyramid(rows)

print("\nReverse Pyramid:")
reverse_pyramid(rows)
```

## 4. Write a program that accepts a character and performs the following:
1. print whether the character is a letter or numeric digit or a special character.
2. if the character is a letter, print whether the letter is uppercase or lowercase
3. if the character is a numeric digit, prints its name in text (e.g., if input is 9, output is
NINE)
```
# Program to check type of character and give details

ch = input("Enter a single character: ")

# Ensure only one character is entered
if len(ch) != 1:
    print("Please enter only one character.")
else:
    # a. Check type of character
    if ch.isalpha():
        print("It is a letter.")

        # b. Check case
        if ch.isupper():
            print("The letter is uppercase.")
        else:
            print("The letter is lowercase.")

    elif ch.isdigit():
        print("It is a numeric digit.")

        # c. Print digit name
        digit_names = {
            "0": "ZERO",
            "1": "ONE",
            "2": "TWO",
            "3": "THREE",
            "4": "FOUR",
            "5": "FIVE",
            "6": "SIX",
            "7": "SEVEN",
            "8": "EIGHT",
            "9": "NINE"
        }
        print("Digit in words:", digit_names[ch])

    else:
        print("It is a special character.")
```
## 5. Write a program to perform the following operations on a string
1. Find the frequency of a character in a string.
2. Replace a character by another character in a string.
3. Remove the first occurrence of a character from a string.
4. Remove all occurrences of a character from a string.

```
# Input string
text = input("Enter a string: ")

# a. Frequency of a character
char = input("Enter a character to find its frequency: ")
freq = text.count(char)
print(f"Frequency of '{char}' in the string: {freq}")

# b. Replace a character by another character
old_char = input("Enter the character to replace: ")
new_char = input("Enter the new character: ")
replaced_text = text.replace(old_char, new_char)
print("String after replacement:", replaced_text)

# c. Remove the first occurrence of a character
remove_char = input("Enter the character to remove its first occurrence: ")
first_removed = text.replace(remove_char, "", 1)
print("String after removing first occurrence:", first_removed)

# d. Remove all occurrences of a character
all_removed = text.replace(remove_char, "")
print("String after removing all occurrences:", all_removed)
```

## 6. Write a program to swap the first n characters of two strings.
```
# Input strings
str1 = input("Enter the first string: ")
str2 = input("Enter the second string: ")

# Input n
n = int(input("Enter the number of characters to swap: "))

# Ensure n is not greater than the length of any string
if n > len(str1) or n > len(str2):
    print("Error: n is greater than the length of one of the strings.")
else:
    # Swap first n characters
    new_str1 = str2[:n] + str1[n:]
    new_str2 = str1[:n] + str2[n:]

    print("Strings after swapping:")
    print("First string:", new_str1)
    print("Second string:", new_str2)
```

## 7. Write a function that accepts two strings and returns the indices of all the occurrences of the second string in the first string as a list. If the second string is not present in the first string then it should return -1.
```
# Function to find all occurrences of substring
def find_occurrences(main_str, sub_str):
    indices = []
    start = 0
    while True:
        index = main_str.find(sub_str, start)
        if index == -1:
            break
        indices.append(index)
        start = index + 1  # move past the last found index
    return indices if indices else -1

# Main program
string1 = input("Enter the main string: ")
string2 = input("Enter the substring to search: ")

result = find_occurrences(string1, string2)
print("Indices of occurrences:", result)
```
## 8. Write a program to create a list of the cubes of only the even integers appearing in the input list (may have elements of other types also) using the following:
1. 'for' loop
2. list comprehension
```
# Input list (can have numbers and other types)
input_list = [1, 2, 3, 4, 5, 6, 'a', 8.5, 8]

# a. Using for loop
cubes_even_for = []
for item in input_list:
    if isinstance(item, int) and item % 2 == 0:  # check if item is an even integer
        cubes_even_for.append(item**3)
print("Cubes of even integers using for loop:", cubes_even_for)

# b. Using list comprehension
cubes_even_comp = [item**3 for item in input_list if isinstance(item, int) and item % 2 == 0]
print("Cubes of even integers using list comprehension:", cubes_even_comp)
```

## 9. Write a program to read a file and
1. Print the total number of characters, words and lines in the file.
2. Calculate the frequency of each character in the file. Use a variable of dictionary type
to maintain the count.
3. Print the words in reverse order.
4. Copy even lines of the file to a file named ‘File1’ and odd lines to another file named
‘File2’.
```
# Input file name
filename = input("Enter the file name to read: ")

# Initialize variables
char_count = 0
word_count = 0
line_count = 0
char_freq = {}
words_list = []

even_lines = []
odd_lines = []

# Read the file
with open(filename, 'r') as file:
    lines = file.readlines()
    line_count = len(lines)
    
    for idx, line in enumerate(lines, start=1):
        char_count += len(line)
        words = line.split()
        word_count += len(words)
        words_list.extend(words)
        
        # Character frequency
        for ch in line:
            char_freq[ch] = char_freq.get(ch, 0) + 1
        
        # Separate even and odd lines
        if idx % 2 == 0:
            even_lines.append(line)
        else:
            odd_lines.append(line)

# a. Print counts
print("Total characters:", char_count)
print("Total words:", word_count)
print("Total lines:", line_count)

# b. Character frequency
print("\nCharacter Frequency:")
for ch, freq in char_freq.items():
    print(f"'{ch}': {freq}")

# c. Words in reverse order
print("\nWords in reverse order:")
print(' '.join(words_list[::-1]))

# d. Copy even lines to File1 and odd lines to File2
with open("File1.txt", 'w') as f1:
    f1.writelines(even_lines)

with open("File2.txt", 'w') as f2:
    f2.writelines(odd_lines)

print("\nEven lines copied to File1.txt")
print("Odd lines copied to File2.txt")
```
## 10. Write a program to define a class Point with coordinates x and y as attributes. Create relevant methods and print the objects. Also define a method distance to calculate the distance between any two point objects.
```
import math

# Define the Point class
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    # Method to print the point
    def __str__(self):
        return f"Point({self.x}, {self.y})"

    # Method to calculate distance between two points
    def distance(self, other):
        return math.sqrt((self.x - other.x)**2 + (self.y - other.y)**2)


# Main program
p1 = Point(3, 4)
p2 = Point(7, 1)

print("Point 1:", p1)
print("Point 2:", p2)

# Calculate distance
dist = p1.distance(p2)
print(f"Distance between {p1} and {p2} is {dist:.2f}")
```

## 11. Write a function that prints a dictionary where the keys are numbers between 1 and 5 and the values are cubes of the keys.
```
# Function to create and print dictionary with cubes
def print_cubes():
    cube_dict = {}
    for i in range(1, 6):
        cube_dict[i] = i**3
    print(cube_dict)

# Call the function
print_cubes()
```

## 12. Consider a tuple t1=(1, 2, 5, 7, 9, 2, 4, 6, 8, 10). Write a program to perform following operations:

1. Print half the values of the tuple in one line and the other half in the next line.
2. Print another tuple whose values are even numbers in the given tuple.
3. Concatenate a tuple t2=(11,13,15) with t1.
4. Return maximum and minimum value from this tuple
```
# Given tuple
t1 = (1, 2, 5, 7, 9, 2, 4, 6, 8, 10)

# 1. Print half the values in one line and the other half in the next line
half = len(t1) // 2
print("First half:", t1[:half])
print("Second half:", t1[half:])

# 2. Create another tuple with only even numbers
even_tuple = tuple(x for x in t1 if x % 2 == 0)
print("Tuple with even numbers:", even_tuple)

# 3. Concatenate t1 with t2
t2 = (11, 13, 15)
concatenated_tuple = t1 + t2
print("Concatenated tuple:", concatenated_tuple)

# 4. Return maximum and minimum value from the tuple
max_val = max(concatenated_tuple)
min_val = min(concatenated_tuple)
print("Maximum value:", max_val)
print("Minimum value:", min_val)
```

## 13. Write a program to accept a name from a user. Raise and handle appropriate exception(s) if the text entered by the user contains digits and/or special characters.
```
# Custom exception for invalid names
class InvalidNameError(Exception):
    pass

# Function to accept and validate name
def get_name():
    name = input("Enter your name: ")
    
    # Check for digits or special characters
    if not name.isalpha():
        raise InvalidNameError("Name should contain only letters.")
    
    return name

# Main program
try:
    name = get_name()
    print("Hello,", name)
except InvalidNameError as e:
    print("Error:", e)
```
