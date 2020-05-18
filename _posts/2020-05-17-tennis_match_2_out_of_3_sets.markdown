---
layout: post
title:      "Tennis Match 2 out of 3 Sets"
date:       2020-05-18 02:23:49 +0000
permalink:  tennis_match_2_out_of_3_sets
---


This Ruby program will randomly simulate a 2 out of 3 sets tennis match, game by game. We start out by asking the user to enter the competitors names.

```
puts "Enter player name: "
player_1 = gets.strip

puts "Enter other player name: "
player_2 = gets.strip
```

We now need three things. We need to keep track of player 1 and player 2's game scores and the amount of sets they have won. We also need to set the limit of games they can win in a set in order to complete one set and move on to the next one.

```
p1_score = 0
p2_score = 0

p1_set = 0
p2_set = 0

set = 6
```

Now that we have player one and player two's scores and set wins identified, we can then proceed to create a while loop. The while loop will continue to run unless player 1 or player two reaches 6, whoever can get their first.

```
while p1_score < set && p2_score < set

end
```

Since the match will be simulated, we will need a random number to generate to determine who will score a game.

```
while p1_score < set && p2_score < set
    outcome = rand(1..2)
end
```

If outcome is equal to 1, then player 1 will score a game. If outcome isn't 1, outcome will equal to 2, so player 2 will score a game instead.

```
while p1_score < set && p2_score < set
    outcome = rand(1..2)
		
		if outcome == 1
    p1_score += 1
  else
    p2_score += 1
  end
	
end
```

We need to puts out statements that will let us keep track of who is winning. Here is how we do it.

```
while p1_score < set && p2_score < set
    outcome = rand(1..2)
		
		if outcome == 1
    p1_score += 1
  else
    p2_score += 1
  end
	
	gets.chomp()

  puts "#{player_1}: #{p1_score}"
  puts "#{player_2}: #{p2_score}"
	
end
```

We added a gets.chomp() because it will let us keep track of the match game by game. All we need to do is press enter and another game will be added to a player depending on the outcome.

In a tennis match, when it gets to 5-5, the player would now need to reach 7 in order to win the set. With that in mind, I added an if statement to prevent a set from ever finishing at 6-5.

```
while p1_score < set && p2_score < set
    outcome = rand(1..2)
		
		if outcome == 1
    p1_score += 1
  else
    p2_score += 1
  end
	
	gets.chomp()

  puts "#{player_1}: #{p1_score}"
  puts "#{player_2}: #{p2_score}"
	
	if p1_score == 5 && p2_score == 5
    set = 7
  end
	
end
```

And with these three additional lines of code, we have now completed the while loop for the First Set. For the finishing touch, we can add a ternary statement outside the while loop so we can increment the winning players set count.

```
while p1_score < set && p2_score < set
    outcome = rand(1..2)
		
		if outcome == 1
    p1_score += 1
  else
    p2_score += 1
  end
	
	gets.chomp()

  puts "#{player_1}: #{p1_score}"
  puts "#{player_2}: #{p2_score}"
	
	if p1_score == 5 && p2_score == 5
    set = 7
  end
	
end

p1_score > p2_score ? p1_set += 1 : p2_set += 1
```

Moving on to the Second Set, it will be pretty much be the same as the First Set, we would just need to add variables for the games in the second set and reset our set limit to 6.

```
p11_score = 0
p22_score = 0
set = 6

# Second Set

while p11_score < set && p22_score < set
  outcome = rand(1..2)

  if outcome == 1
    p11_score += 1
  else
    p22_score += 1
  end

  gets.chomp()

  puts "#{player_1}: #{p1_score} #{p11_score}"
  puts "#{player_2}: #{p2_score} #{p22_score}"

  if p11_score == 5 && p22_score == 5
    set = 7
  end

end

p11_score > p22_score ? p1_set += 1 : p2_set += 1
```

No what if both players are 1 set all? I applied an if statement to see if thats the case.

```
# Third Set
if p1_score > p2_score && p22_score > p11_score || p1_score < p2_score && p22_score < p11_score

end
```

If they are indeed 1 set all, then we would need to add yet another while loop.

```
# Third Set
if p1_score > p2_score && p22_score > p11_score || p1_score < p2_score && p22_score < p11_score
  while p111_score < set && p222_score < set
    outcome = rand(1..2)

    if outcome == 1
      p111_score += 1
    else
      p222_score += 1
    end

    gets.chomp()

    puts "#{player_1}: #{p1_score} #{p11_score} #{p111_score}"
    puts "#{player_2}: #{p2_score} #{p22_score} #{p222_score}"

    if p111_score == 5 && p222_score == 5
      set = 7
    end

  end
  p111_score > p222_score ? p1_set += 1 : p2_set += 1
end
```

Now for the final touches, we need to announce the winner of the match. 

```
if p1_set > p2_set
  puts "#{player_1} wins!"
else
  puts "#{player_2} wins!"
end
```

This finalizes our tennis match (2 out of 3 sets) scoring simulation.



