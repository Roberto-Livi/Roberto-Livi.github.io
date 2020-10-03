---
layout: post
title:      "Java OOP (this vs super)"
date:       2020-10-03 16:11:44 +0000
permalink:  java_oop_this_vs_super
---


In this post, I am going to cover two topics:

* this vs super

* Method Overloading vs Method Overriding


**this vs super**


* super

People who have experience with Ruby will most likely be familiar with super and thats great since its used quite similarly in Java. super is used to call the parent class, which includes its methods and variables. If you want to use *super* to call the parent class, you would need acquire that class by inheriting from it like so:

```
public class Dinosaur { 

}

public class Velociraptor extends Dinosaur {

}
```

Here you see the Velociraptor class inheriting from its parent class (Dinosaur). Lets now give both of these classes a method.

```
public class Dinosaur { 

     public void eat() { 
		 
		          System.out.println("Dinosaur eats");
		 
		 }

}

public class Velociraptor extends Dinosaur {

       public void eat() { 
		 
		          super.eat();
							System.out.println("Eat method printed in Velociraptor class");
		 
		 }

}
```

Here we are seeing an implementation of the *super* keyword in action. By applying super.eat(); in the eat method at the Velociraptor class, we are calling the eat method from its parent class (Dinosaur). We call that method which then prints out "Dinosaur eats" followed by the printline statement "Eat method printed in Velociraptor class." 




* this

Unlike *super*, where it calls the parent class to call the methods and variables of the parent class its inheriting from, *this* is used to call its own classes methods and variables. You can use *this* to call a constructor from another overloaded constructor. Note that the overloaded constructor is in the same class since unlike *super*, it can only call methods from its own class. Lets walk you through an example when implenting *this*:

```
class Dinosaur {

    private String eyes;
		private String favoriteFood;
	  private int width;
		private int height;
		
		public Dinosaur() {
		     this(0, 0);  // calls the second constructor
		}
		
		
		public Dinosaur(int width, int height) {
		    this(0, 0, width, height); // this calls the third constructor
		}
		
		
		public Dinosaur(String eyes, String favoriteFood, int width, int height) {
		    this.eyes = eyes;
				this.favoriteFood = favoriteFood;
				this.width = width;
				this.height = height;
		}


}
```


Here we see something called constructor chaining by using *this*. What this means is that we are giving the last constructor the responsibility of initializing the variables. This implementation of *this* avoids for us to have to use duplicate code to initialize variables.

**Conclusion**

To conclude, lets see how we can implement both *super* and *this*. We aren't going to follow up with the code above for this example:

```
class Dinosaur {

   private String eyes;
	 private String favoriteFood;
	 
	 public Dinosaur(String eyes, String favoriteFood) {
	      this.eyes = eyes;
				this.favoriteFood = favoriteFood;
	 }

}

class Velociraptor extends Dinosaur {

     private int width;
		 private int height;
		 
		 public Velociraptor() {
		     this(0, 0, width, height);
		 }
		 
		 public Velociraptor(String eyes, String favoriteFood, int width, int height) {
		      super(eyes, favoriteFood);
					this.width = width;
					this.height = height;
		 }

}
```


Here we see the first constructor of Velociraptor calling its second constructor that uses *super* to initialize eyes and favoriteFood from the parent classes constructor. Then it goes on and initializes both width and height, making use of both *super* and *this* to create an instance for the Velociraptor class. 

This concludes the topic for *this* vs *super*, I hope you enjoyed it and till next time!







