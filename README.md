# Python Lab Practical Questions

## 1. Write a program to demonstrate the use of different operators in python.

```python
a = 10
b = 3
c = input("Operation: ")
if c == "+":
    print(a + b)
elif c == "-":
    print(a - b)
elif c == "*":
    print(a * b)
elif c == "/":
    print(a / b)
elif c == "**":
    print(a ** b)
else:
    print("Invalid Input")
```

## 2. Write a program to print Fibonacci Series 0 1 1 2 3 5 8 ... N.

```python
n = int(input("Enter number of terms: "))
a = 0
b = 1
for i in range(n):
    print(a, end="    ")
    a, b = b, a + b
```

## 3. Write a program to print the sum of first n prime numbers.

```python
def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True

def sum_first_n_primes(n):
    prime_sum = 0
    count = 0
    current_number = 2
    
    while count < n:
        if is_prime(current_number):
            prime_sum += current_number
            count += 1
        current_number += 1
        
    return prime_sum

# Example: Sum of the first 5 prime numbers (2, 3, 5, 7, 11)
n = int(input("Enter the limit of prime numbers: "))
print(f"The sum of the first {n} prime numbers is: {sum_first_n_primes(n)}")
```

## 4. Create a function Pall and to print of all the palindrome numbers between two ranges.

```python
def Pall(st, end):
    "All palindrome numbers between {st} and {end}."
    for num in range(st, end + 1):
        s = str(num)
        if s == s[::-1]:
            print(num)
```

## 5. Write a Python program to perform the string slicing.

```python
s = "Hello, World!"

print("Original String: ", s)
print("s[0:5]: ", s[:5])
print("s[7:12]: ", s[7:12])
print("s[::2]: ", s[::2])
print("s[::-1]: ", s[::-1])
print("s[5:]: ", s[5:])
print("s[:5]: ", s[:5])
print("s[-6:-1]: ", s[-6:-1])
```

## 6. Write a program to check odd and even number form a list.

```python
l = [10, 21, 34, 45, 57, 69]

for i in l:
    if i % 2 == 0:
        print("Even", end=" ")
    else:
        print("Odd", end=" ")
```

## 7. Write a Python program to demonstrate the use of List, Tuple, Dictionary.

```python
my_tuple = ()
my_list = []
my_dict = {}

while True:
    print("====== Menu ======")
    print("1. Create a Tuple")
    print("2. Create a List")
    print("3. Create a Dictionary")
    print("4. Exit")
    choice = input("Enter your choice: ")
    if choice == '1':
        n = int(input("Enter the number of elements in the tuple: "))
        for i in range(n):
            element = input(f"Enter element {i + 1}: ")
            my_tuple += (element,)
    elif choice == '2':
        n = int(input("Enter the number of elements in the list: "))
        my_list = []
        for i in range(n):
            element = input(f"Enter element {i + 1}: ")
            my_list.append(element)
    elif choice == '3':
        n = int(input("Enter the number of key-value pairs in the dictionary: "))
        my_dict = {}
        for i in range(n):
            key = input(f"Enter key {i + 1}: ")
            value = input(f"Enter value for key '{key}': ")
            my_dict[key] = value
    elif choice == '4':
        print("Exiting the program.")
        break
    else:
        print("Invalid choice. Please try again.")
```

## 8. Write a Python program to demonstrate the use of recursion.

```python
def func_factorial(n):
    print(f"Recursive function for calculating factorial of {n}")
    if n == 0:
        return 1
    else:
        return n * func_factorial(n - 1)

print(func_factorial(5))
```

## 9. Write a program illustrating various functions of mathematical library in python.

```python
import math

print("Functions of Math module")

print("Square root of 16:", math.sqrt(16))
print("Factorial of 5:", math.factorial(5))
print("Ceiling of 4.2:", math.ceil(4.2))
print("Floor of 4.2:", math.floor(4.2))
```

## 10. Write a program to show the working of Bar Graphs

```python
import matplotlib.pyplot as plt
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]
plt.plot(x, y)
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.title("Simple Line Plot")
plt.show()
```

## 11. Write a program to show the working of Pie Chart

```python
import matplotlib.pyplot as plt
x = [10, 20, 30, 40]
labels = ['A', 'B', 'C', 'D']
plt.pie(x, labels=labels)
plt.title("Simple Pie Chart")
plt.show()
```

## 12. Write a Python program to copy the contents of a file to another file in a text file.

```python
source_file = input("Enter the source file name: ")
destination_file = input("Enter the destination file name: ")

with open(source_file, "r") as src:
    with open(destination_file, "w") as dst:
        dst.write(src.read())
        print(f"Contents of '{source_file}' copied to '{destination_file}' successfully.")
```

## 13. Write a program illustrating load() and dump() in binary file

```python
import pickle

# Example data to be serialized
data = {'name': 'Snow', 'age': 30, 'city': 'New York'}

# Writing data to a binary file
with open('data.pkl', 'wb') as f:
    pickle.dump(data, f)

# Reading data from the binary file
with open('data.pkl', 'rb') as f:
    loaded_data = pickle.load(f)

print(loaded_data)
```

## 14. Write a python program to insert data into CSV file and display it.

```python
import csv

# Data to be inserted into the CSV file
data = [
    ['Name', 'Age', 'City'],
    ['Cris', 30, 'New York'],
    ['Rin', 25, 'Los Angeles'],
    ['Snow', 35, 'Chicago']
]

# Inserting data into the CSV file
with open('data.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerows(data)

# Displaying the contents of the CSV file
with open('data.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

## 15. Write a python program to create a Numpy array and perform the basic matrix operation.

```python
import numpy as np

# Create a 2x2 matrix
matrix1 = np.array([[1, 2], [3, 4]])
matrix2 = np.array([[5, 6], [7, 8]])

# Perform matrix operations
sum_matrix = np.add(matrix1, matrix2)
product_matrix = np.dot(matrix1, matrix2)

print("Matrix 1:")
print(matrix1)
print("Matrix 2:")
print(matrix2)
print("Sum of matrices:")
print(sum_matrix)
print("Product of matrices:")
print(product_matrix)
```

## Application Based Practicals (Any 5)

- Write a program to perform Linear Search
- Write a function to find all duplicates in two different list
- Make a list of first 10 letters of the alphabet, then use the slicing to do the following operations:
  - Print the first 3 letters of the list
  - Print any 3 letters from the middle.
  - Print the letter from any particular index to the end of the list.
- Write a function to print the sum of numbers in list having 3 at their unitâ€™s place.
- Demonstrate the use of inheritance.
- Write a Python program that takes a text file as input and returns the number of words of a given text file.
- Write a program to read a binary file having employee data in the form of list and search for the record of a particular employee entered by user.
- Write a program to create an array with 3 rows and 4 columns with each element set to 0 using Numpy.
- Write a program to perform Transpose using NumPy.
- Write a program to Create a CSV file by entering user-id and password, read and search the password for given user id.