<!---Created By Daniel Michel--->
# Chapter 3 Collections and Enum
***
## Generic Class

When Creating a Class that can be used a storage or a data structure (example: Linked list) we may need to have a specific class for each primative datatype (int, char, string, etc...).
To solve this limitation we can use a Generic Class that acts as a template that can be then customized for each datatype .

```java
Class TemplateClass<Item> //Notice that alongside the Class name there is a generic data type 'Item'
{
    private Item attribute1;

    public Item getAttribute1(){
        return this.attribute1;
    }
}
```
From the previous we can deduce that we need to pass the datatype along side the class name when creating an object that the datatype passed alongside the object is used to replace ```Item``` in the code with the datatype passed.

Example: 
```java
TemplateClass<Integer> TC_int = new TemplateClass<Integer>; //Here an Object of TemplateClass is Created with attribute1 type being an Integer.
TemplateClass<String> TC_Str = new TemplateClass<String>;   //Here an Object of TemplateClass is Created with attribute1 type being a String instead of Integer.
```

#### Type Erasure
Notice in the previous code that when creating an object of TemplateClass with an Int as the datatype Integer was used instead of int.

This is because dring runtime the ```TemplateClassItem<Item>``` is replaced with ```TemplateClass<Object>``` therefore the direct use of the primative data type isn't possible.
<!---Created By Daniel Michel--->


## Wrapper Class

In Java a wrapper class is the mechanism that allows conversion between primative datatypes and Objects in a way that each datatype has it's own wrapper class.

<table>
<tr>
<th>
Primative Datatype
</th>
<th>
Wrapper Class
</th>
</tr>
<tr>
<td>int</td><td>Integer</td>
</tr>
<tr>
<td>char</td><td>Character</td>
</tr>
<tr>
<td>byte</td><td>Byte</td>
</tr>
<tr>
<td>boolean</td><td>Boolean</td>
</tr>
<tr>
<td>short</td><td>Short</td>
</tr>
<tr>
<td>long</td><td>Long</td>
</tr>
<tr>
<td>float</td><td>Float</td>
</tr>
<tr>
<td>double</td><td>Double</td>
</tr>
</table>

<!---Created By Daniel Michel--->

#### Boxing And Un-Boxing
Boxing is simply the Conversion from primative datatypes and their Wrapper class and vice-versa.
Boxing can be done in 2 ways, Either explicitly using the ```.valueOf();``` method or implicitly by the compiler (Auto-Boxing).

###### Note:
<details>
<summary>Heterogeneous Arrays</summary>
It's an array that takes leverage of boxing and unboxing to construct an array of different data types.

```java
Object[3] array = new Object[3]{1,true,"Hello"};
```
<!---Created By Daniel Michel--->
</details>

***
## Collections 

The Java Collections Framework is a framework within java that implements some data structures (Example: Linked list, ArrayList, stacks, etc...).

###### Examples of some java collections frameork datastructures:

<details>
<summary>ArrayList</summary>
An ArrayList workes based on index, meaning that any value can be accessed based on the index it's storedd at inside the Arraylist.

###### Creating ArrayList in Java:
```java
ArrayList<Integer> intArrList = new ArrayList<Integer>; ////Note the use of the int wrapper class instead of the primative data type.
intArrList.add(25); //adding values to the ArrayList

```
Removing values can be done using the ```.remove();``` method which can either take an index(primative Datatype) or a Value to look for and remove(Wrapper type ex: ```Integer.valueOf(40)```; this will search for the value 40 and remove it).
Another method in the ArrayList Collection is the ```.isEmpty()``` method which checks if the array....you guessed it is Empty.

##### Some Important functions: 
###### .set();
The use of the ```.set()``` method which can change the value of an element in the ArrayList based on an index passed to it.

Example:
```java
    intArrList.set(2,30);//This would set the value at index to to 30
```
###### .get()
Also note the ```.get()``` method which gets the value stored at a specific index in the ArrayList.

Example:
```java
    intArrList.get(2);//this wwould return the value stored at index 2
```
###### .search();

The ```.search()``` method can take a value as it's parameter and return the index in which the value is stored in the ArrayList.

###### .trimToSize()

The ```.trimToSize()``` method can reduce the size of the array to the  current size incase the Capacity is greater than the size.


</details>


***

## Enums

Enums is a special datatype that allows a dev to create a datatype specific to an application. 
Example: Directions which in a specific application may only have one of four values (North, South, East, West).

Enums can be created in java as follows:
```java
Enum Direction{
    North,
    South,
    East,
    West
}
```
And inside the main function an object of said enum can be created as follows:

```java
Direction dir = Direction.North;

```

***

Thanks! <3



Created by: Daniel Michel
2/1/2024

<!---Created By Daniel Michel>




