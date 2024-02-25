1. How do you tell what OO system (S3 vs. S4) an object is associated with?
These techniques can be used to ascertain whether an object is related to S3 or S4:
To determine whether an object is not an S4 object, use is.object(x) &!isS4(x). 
To obtain the object type, use sloop::otype(x). It is connected to S3 if it yields "S3". 
While base objects lack a class attribute, S3 objects do. 

2. How do you determine the base type (like integer or list) of an object?
To find an object's base type, use typeof(x). As an illustration, 
typeof(1:10) yields "integer". 
To differentiate between base and object-oriented (OO) objects: Use is.object()
Every object has a base type. These types are most important in C code but are relevant for R programming as well.
Some common base types include:
NULL: Represents missing or undefined values.
logical: Holds Boolean values (TRUE or FALSE).
integer: Stores whole numbers.
double: Represents floating-point numbers.
complex: Deals with complex numbers.
character: Stores text.
list: Contains heterogeneous elements.

3. What is a generic function?
A generic function is a function that establishes a shared interface for functions that are related. It enables you to call methods according to the input object's class.
S3 generic functions are non-formal and determine which method to call by means of a unique kind of function known as a generic function. 
    S3: The original and simpler system.
        - Uses informal class definitions.
        - Methods are associated with the class attribute of an object.
        - Example: `plot()` and `summary()`.
   
Generic functions in S4 support multiple dispatch and have formal class definitions. 
S4: A more formal system.
        - Has formal class definitions.
        - Provides helper functions for defining generics and methods.
        - Example: Bioconductor packages often use S4.

5. What are the main differences between S3 and S4?
S3:
Informal system.
No formal class definitions.
Methods belong to generic functions.
Objects can belong to multiple classes.
S4:
Formal system.
Has formal class definitions.
Methods are explicitly defined.
Objects belong to a single class.

6. Examples of S3 and S4: 
Here are a few condensed examples: 
#create s3 object.
s3 = list(name = 'Venky', age = 22, GPA = 4.0)
print(s3)
typeof(s3)

#create  s4 object.
setClass('student', slot = c(name = 'character', age = 'numeric', GPA = 'numeric'))
s4 = list(name = 'venky', age = 22, GPA = 4.0)
print(s4)
typeof(s4)
