---
layout: post
title:      "Guess a number from 1-10 in Ruby"
date:       2020-03-28 00:26:43 -0400
permalink:  guess_a_number_from_1-10_in_ruby
---

This is the first, very simple game that I made with Ruby. Just like the title suggests, you have to guess a number from 1-10 and hope that you guess the random number that the computer picked out. In this game, you have 4 chances to guess the correct number.

The method name I will be using will be called guess_the_number.

```
def guess_the_number

end
```

The first thing to do in this method is to have the computer pick a random number from 1-10 and assign it to a variable.

```
def guess_the_number

secret_number = rand(1..10)

end
```

rand(1..10) will generate a random number from 1-10 and assign it to the variable secret_number. Now that we have our secret number assigned, we need to also include variables for the number of guesses we can make and the count for each guess that we make. Lets call our count variable count and our guess limit variable guess_limit.

```
def guess_the_number

secret_number = rand(1..10)
guess_limit = 4
count = 0

end
```

Here we set our guess_limit variable to 4, which represents the total number of guesses that we can make, and our count to 0 since we haven't made any guesses yet. Now its time to add a boolean called correct, which will tell us whether or not we got it correct. We will set it to false since we haven't gotten it correct, yet! We also need to add a guess variable and set it to 0 just so we can declare it.

```
def guess_the_number

secret_number = rand(1..10)
guess_limit = 4
count = 0
guess = 0
correct = false

end
```


Now we will create a while loop. The while loop will say "We will continue this while loop while guess_limit(4) isn't greater than count(0) AND secret_number doesn't equal your guess." In this while loop, we will ask you to enter a guess and if you don't get it right, count will be incremented by 1.

```
def guess_the_number

secret_number = rand(1..10)
guess_limit = 4
count = 0
guess = 0
correct = false

while guess_limit > count && secret_number.to_i != guess.to_i

   puts "Guess a number from 1-10: "
         guess = gets.chomp()
         count += 1
end

end
```

Now we need the correct boolean to be true if the person gets it correct. We will add an if statement that will say "if secret_number is equal to guess AND guess_limit is less than 5, correct will become true."

```
def guess_the_number

secret_number = rand(1..10)
guess_limit = 4
count = 0
guess = 0
correct = false

while guess_limit > count && secret_number.to_i != guess.to_i

   puts "Guess a number from 1-10: "
         guess = gets.chomp()
         count += 1
				 
    if secret_number.to_i == guess.to_i && guess_limit < 5
      correct = true
    end
end

end
```

We are close. Now for the finishing touch, we will add a ternary statement saying "if correct is true, you win, and if it isn't, you lose."

```
def guess_the_number

secret_number = rand(1..10)
guess_limit = 4
count = 0
guess = 0
correct = false

while guess_limit > count && secret_number.to_i != guess.to_i

   puts "Guess a number from 1-10: "
         guess = gets.chomp()
         count += 1
				 
	 if secret_number.to_i == guess.to_i && guess_limit < 5
          correct = true
   end
	 
	 end
     puts correct ? "You Win" : "You Lose"
end
```

And thats it! All we would need to do is call guess_the_number in order to play the game.
