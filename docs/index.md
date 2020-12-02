### ITFnd100-Mod07
# Pickling and Error/Exception Handling in Python
JRushing-Crocker, 12.1.2020

## Introduction
The object of this assignment was to research and utilize Pickling and Error/Exception Handling in program code. Both are extremely useful as the size and complexity grows they help to keep the script organized. I will show the use of both by modifying a couple of programs or pieces of programs I had previously written.

## Pickling
”Python pickle module is used for serializing and de-serializing a Python object structure . Any object in Python can be pickled so that it can be saved on disk. What pickle does is that it " serializes" the object first before writing it to file. Pickling is a way to convert a python object (list, dict, etc.) into a character stream. The idea is that this character stream contains all the information necessary to reconstruct the object in another python script.” (GeeksforGeeks, https://www.geeksforgeeks.org/understanding-python-pickling-example/ 2020) (External site)
I modified an existing program, I wrote in a previous assignment, Home Inventory. 
“Use pickle.dump (object, filename) method to save the object into file <filename>: this will save the object in this file in byte format. Use pickle.load (filename): to load back python object from the file where it was dumped before.” (Educba, https://www.educba.com/python-pickle/, 2020) (External site)
The changes for pickling the data are below: 
```
# ------------------------------------------------- #
# Title: Pickling Data
# Description: Using Pickle Module to pickle data written and read to a file
# ChangeLog: (Who, When, What)
# J.Rushing-Crocker, 11.30.2020, Created Script
# ------------------------------------------------- #
import pickle  # This imports code from another code file!

# Data -------------------------------------------- #
strFileItems = 'HomeInventory.dat' #Data File
lstHomeInv = []

# Processing -------------------------------------- #
def save_data_to_file(file_name, list_of_data): # Saving Data to file by writing to file
     file = open(file_name, 'wb')
     pickle.dump(list_of_data, file)
     file.close()

def read_data_from_file(file_name): # Reading data from file to read
    file=(file_name, 'rb')
    list_of_data = pickle.load(file)
    file.close()
    return list_of_data

# Presentation ------------------------------------ #
print("Type in item and value")             #
strName = str(input("Enter Item Name:"))          # Name of household items
fltstrValue = str(input("Enter Item Value:"))     # Estimated value of item
lstHomeInv = [strName, fltstrValue]
save_data_to_file(strFileItems,lstHomeInv)
with open(strFileItems, "rb") as f:
    lstHomeInv = pickle.load(f)
print(lstHomeInv)
```
Figure 1




![Fig.3-Pickling Results in OSCommand Window](https://github.com/jrushing-crocker/ITFnd100-Mod07/blob/main/Assignment07_OSCmd.png "Fig.3-Pickling Results in OSCommand Window")

Figure 3-Pickling Results in OSCommand Window

## Error/Exception Handling
What is Exception? An exception is an event, which occurs during the execution of a program that disrupts the normal flow of the program's instructions. In general, when a Python script encounters a situation that it cannot cope with, it raises an exception. An exception is a Python object that represents an error. When a Python script raises an exception, it must either handle the exception immediately otherwise it terminates and quits.
Handling an exception.  If you have some suspicious code that may raise an exception, you can defend your program by placing the suspicious code in a try: block. After the try: block, include an except: statement, followed by a block of code which handles the problem as elegantly as possible. (Tutorialspoint, https://www.tutorialspoint.com/python/python_exceptions.htm , 2020) (External site)
I used a simple quotient program to demonstrate the use of the Try-Exception event. The try: starts the event followed by simple script to run.  This starts the except: else: area. If the result is not an integer or is divied by zero on of the except: Error will return a statement. If the result is not divided by zero and is an integer then else: is used and the result is printed.
```
# ------------------------------------------------- #
# Title: Exception Handling
# Description: Handling an error with input data
# ChangeLog: (Who, When, What)
# J.Rushing-Crocker, 11.30.2020, Created Script
# ------------------------------------------------- #

#Exception Handling

try:
    num1 = int(input("Enter first number: "))
    num2 = int(input ("Enter second number: "))
    result = num1/num2
except ValueError:
    print("Number entered is not an integer")
except ZeroDivisionError:
    print("Second number can't be zero")
else:
    print("The Answer is:",result)
```

## Conclusion
I have use previous code to show the use of Pickling and Exception Handling and run ethe code in both PyCharm and OS Command Window. I have also researched and provided information on the uses for both Pickling and Exception Handling.  




