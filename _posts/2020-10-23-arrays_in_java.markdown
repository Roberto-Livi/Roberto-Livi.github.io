---
layout: post
title:      "Arrays in Java"
date:       2020-10-23 21:38:47 +0000
permalink:  arrays_in_java
---


There are two ways you can create an array in Java (Array and ArrayList). ArrayList is much more flexible since you are able to change the length of the array with methods that are acquired by importing ArrayList and Collections. We will first go over the Array before getting into the ArrayList.

If you were to create an array thats not an ArrayList, you won't be able to change the length of that array. You can, however, modify the elements that are in the array.  Let's start with creating an array first with this example:

```
String[] cars = {"Volvo", "Audi", "BMW"};
Integer[] nums = {1, 2, 3};
```

Here we have created two arrays. The first one is an array that contains elements of type string. We need to specify the type when declaring an array in Java. Since the second array contains elements of type integer, we start off with Integer[] before giving the array a name. We named our first array cars and our second array nums. We could have called it anything else if we wanted to.

The index element of an array starts at 0. That would mean that "Volvo" is located at cars[0]. If we were to input this in our main method:

```
System.out.println(cars[0]);
```

If we run the console, it would output: "Volvo"

If we were to input:

```
System.out.println(cars[1]);
```

It would output: "Audi"

If we were to input:

```
System.out.println(cars[5]);
```

It would give us an error because there is no element located at cars[5]. The cars array holds only three elements and goes up to cars[2].

If we want to modify an element in an array, we can do:

```
cars[0] = "Lexus"; 
```

This will replace the element "Volvo" in the array.

If you want to print out all the elements that the array contains, you can use Arrays.toString(cars);


**ArrayList**

With ArrayList you can do much more. Not only can you modify elements in the array, but you can also add, remove, and much more.

To declare an array with ArrayList:

```
ArrayList<String> list = new ArrayList<String>();
```

ArrayList elements are accessed through methods. We need to import them in order to use them.

import java.util.ArrayList;
import java.util.Collections;

The list array is currently empty but we can certainly add an element by using the add method:

```
list.add("Roy");
list.add("Kevin");
list.add("Leo");
```

To check the number of elements an array has, you can use the size method:

```
list.size();
```

To remove an element from an array, you can use the remove method, inputting the index position of the element that you want removed:

```
list.remove(1);
```

This would remove "Kevin" from the array list. Now we are left with two elements in the array. If we want to replace/modify an element in the array, we can use the set method that accepts two arguments. The first one, is the index position of the element you want replaced, and the second argument is the element you want to replace the position you selected.

```
list.set(1, "Leonardo");
```

In order to search to see if an element exists in an array, you can use the contains method:

```
list.contains("Leonardo");
```

The output of this would be true, because "Leonardo" exists in the list array.


**Conclusion**

As you can see, you can a lot more with ArrayList. It depends how you want to handle your array. If you need to change the length of the array, you can use ArrayList, if you know the length of the array won't change, you can use the standard array declaration. I hope you were able to learn something from this post from the explanations and examples given. Till next time!











