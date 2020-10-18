---
layout: post
title:      "Java OOP (classes and constructors)"
date:       2020-10-18 03:29:30 +0000
permalink:  java_oop_classes_and_constructors
---


We are going to cut to the chase and start off with how to create a class in Java. We are going to start off by creating a file called Fish.java. We are going to create our Object Oriented class in the Fish.java file and afterwards, create our Fish in our Main method in the Main file inside:

```
public class Main {

    public static void main(String[] args) {
		     // create our Fish instance here after completing our Fish class
		}
		
		
}
```


Now, back to creating our Fish class inside our Fish.java file:


```
public class Fish {

}
```

What kinds of properties do we want our Animal to have? We can include properties such as age, or their name. Lets include both:

```
public class Fish {

   private String name;
   private double age;
		
}
```

The next step would be to create our constructor. The constructor allows the class to create an instance. Here we initialize both the name and the age properties:

```
public class Fish {

   private String name;
   private double age;
	 
	 public Fish(String name, double age) {
        this.name = name;
        this.age = age;
    }
		
}
```

Now we can create our Fish from out Main method from our Main file:

```
public class Main {

    public static void main(String[] args) {
		     Fish sharky = new Animal("Sharky", 5);
		}
		
		
}
```

Here we are creating an Fish and passing in two arguments for the name and age. We have to pass the arguments in order. We can't pass in the age first, and then the name.  This is because of how the constructor method in our Fish class was created:

```
public Fish(String name, double age) {
        this.name = name;
        this.age = age;
    }
```

Now that we created our Fish, we can call System.out.println(sharky.name); and it will print out "Sharky" in the console. Wrong. It would produce an error because when we declared our name property in the Fish class using private instead of public. If we were to say public, we could use sharky.name to print out our name. So how else can we get our newly created objects name? We can create getter and setter methods in our Fish class. The getter will allow for us to get our fish's name and the setter will allow us to modify the fish's name and other properties. Here is how we can apply a getter and setter for our properties in this example:

```
public class Fish {

   private String name;
   private double age;
	 
	 public Fish(String name, double age) {
        this.name = name;
        this.age = age;
    }
		
		public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getAge() {
        return age;
    }

    public void setAge(double age) {
        this.age = age;
    }
		
}
```

And now when we call:

```
System.out.println(sharky.getName());
```

We can see "Sharky" printed in our console.

To summarize this blog post, we have covered how to create a class in Java and create our constructor to create instances/objects for our class. We then went over private vs public when declaring our properties, and how to create getters and setters. We also went over how to call and receive the data that we passed in for our objects when we created them by using a getter method. I hope that you were able to learn something from this post. Till next time!






