---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-tee-qb/intro-to-ds/itds-theory/"}
---


# Data Types
## Basic data types
### General Classification
```mermaid
graph TD;
    subgraph Basic Datatypes
    Integer;
    Character;
    Floating_Point;
    Double;
    end
    subgraph Enumerated Datatypes
    Enumerated_Datatypes;
    end
    subgraph Void Type
    Void_Type;
    end
    subgraph Derived Type
    Derived_Type;
    end
    Derived_Type --> Integer;
    Derived_Type --> Character;
    Derived_Type --> Floating_Point;
    Derived_Type --> Double;
    Derived_Type --> Enumerated_Datatypes;
    Void_TypeDerived_Type --> Derived_Type;
```

### Basic Datatype Classification
- Basic Datatypes (Primary Datatypes)
	- Integer
		- Signed & Unsigned
			- int
			- short int
			- long int
	- Floating Point
		- float
		- double
		- long double
	- Character
		- char
		- signed char
		- unsigned char

### Table of Data Types: Their size and Value Range
| Data Type          | Size (Bytes) | Value Range               |
| ------------------ | ------------ | ------------------------- |
| char               | 1            | -128 to 127               |
| signed char        | 1            | -128 to 127               |
| unsigned char      | 1            | 0 to 255                  |
| int                | 2            | -32k to 32k               |
| signed int         | 2            | -32k to 32k               |
| unsigned int       | 2            | 0 to 64k                  |
| short int          | 2            | -32k to 32k               |
| signed short int   | 2            | -32k to 32k               |
| unsigned short int | 2            | 0 to 64k                  |
| long int           | 4            | -2147483648 to 2147483647 |
| signed long int    | 4            | -2147483648 to 2147483647 |
| unsigned long int  | 4            | 0 to 4294967295           |
| float              | 4            | 3.4E-38 to 3.4E+38        |
| double             | 8            | 1. 7E-308 to 1. 7E+308    |
| long double        | 10           | 3.4E-4932 to 1.1E+4932    | 

## Data structure definition
- Data structure is a data organisation, management, and storage format that enables efficient access and modification
- Data structure is a collection of data values, the relationships among them, and the functions or operations that can be applied to the data.


## Need for data structures
- A way of organizing, managing, and storing data efficiently
- The data items can be traversed easily.
- Provides efficiency, reusability and abstraction.
- Enhancing the performance of a program because the main function of the program is to store and retrieve the user’s data as fast as possible.

## Classification of Data Structures
- Data Structure
	- Primitive Data Structure
	- Non-Primitive Data Structure
		- Linear
			- Static
				- Array
			- Dynamic
				- Linked List
				- Stack 
				- Queue
		- Non-Linear
			- Tree
			- Graph
## Operations on Data Structures
- Traverse
- Search
- Insert
- Delete
- Sort
- Merge
- Split
- Copy
## Abstract data type (ADT)
- An abstract data type is an abstraction of a data structure
- An ADT specifies:
	- Data stored
	- Operations on the data
	- Error conditions associated with operations

- Example: ADT modelling a simple stock trading system
- The data stored are buy/sell orders
- Operations supported are:
	- order buy(stock, shares, price)
	- order sell(stock, shares, price)
	- void cancel(order)
- Error Conditions:
	- Buy/sell a non-existent stock
	- Cancel a non-existent order

# Functions, Structures, and Pointers
## Function
### Function Declaration or Prototype
- Function Prototype:
	\[return_type] function_name( arg-type name-1,... , arg-type name-n);
- Function Definition:
	[return_type] funtion_name( arg-type name-1,..., arg-type name-n)
	{
		statements;
	}
### Function Definition
### Function Call
### Function Parameters
