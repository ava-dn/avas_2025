---
layout: post
title: Simulation
permalink: /simulation/
description: Simulation Games and Random Algorithms P1 HW
comments: True
sticky_rank: 1
---

**Random Algorithms**

### Popcorn Hack #1

A random algorithm is code that picks stuff randomly, like rolling dice. It doesn’t always do the same thing every time.

We use it in real life for games, making things feel real (like weather or traffic), or testing how stuff works.

College Board might ask what the code does, what the chances are, or why using random stuff can help.

### Popcorn Hack #2


```python
import random

activities = [
    'Paint something weird',
    'Dance like nobody’s watching',
    'Eat ice cream for breakfast',
    'Make a silly TikTok',
    'Text your BFF a random emoji',
    'Take a power nap',
    'Make up a superhero name for yourself',
    'Google “fun facts” and learn 3',
    'Do absolutely nothing for 5 minutes',
    'Try to draw with your non-dominant hand'
]

random_activity = random.choice(activities)

print(f"Today’s random activity: {random_activity}")

```

    Today’s random activity: Dance like nobody’s watching


### Popcorn Hack #3


```python
import random

hosts = ['Jake', 'Luna', 'Maya', 'Leo', 'Sophie']

activities = ['DJ booth', 'food table', 'photo wall', 'party games', 'welcome area']

random.shuffle(activities)

for i in range(len(hosts)):
    print(f"{hosts[i]} will be in charge of the {activities[i]}!")

```

    Jake will be in charge of the photo wall!
    Luna will be in charge of the food table!
    Maya will be in charge of the party games!
    Leo will be in charge of the DJ booth!
    Sophie will be in charge of the welcome area!


**Simulations**

### Popcorn Hack #1


```python
import random

min_num = 1
max_num = 12

spin_result = random.randint(min_num, max_num)

print(f"The spinner landed on: {spin_result}")

```

    The spinner landed on: 8



```python
import random

def play_rock_paper_scissors():
    choices = ['rock', 'paper', 'scissors']
    computer_choice = random.choice(choices)
    user_choice = input("Enter your choice (rock, paper, or scissors): ")

    if user_choice not in choices:
        print("Invalid choice. Please try again.")
        return

    print("Computer chose:", computer_choice)
    print("You chose:", user_choice)

    if user_choice == computer_choice:
        print("It's a tie!")
    elif (user_choice == 'rock' and computer_choice == 'scissors') or (user_choice == 'paper' and computer_choice == 'rock') or (user_choice == 'scissors' and computer_choice == 'paper'):
        print("You win!")
    else:
        print("You lose!")

play_rock_paper_scissors()
```

    Computer chose: scissors
    You chose: paper
    You lose!

