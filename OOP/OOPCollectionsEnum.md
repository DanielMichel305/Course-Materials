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

</details>

***
## Collections 
Still Not done... ;(


