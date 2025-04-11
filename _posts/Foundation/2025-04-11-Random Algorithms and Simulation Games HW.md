## Random Algorithms and Simulation Games HW


#### Popcorn Hack #3


```py
import random

hosts = ['Alex', 'Jordan', 'Taylor', 'Morgan', 'Riley']

activities = ['pizza station', 'DJ booth', 'game zone', 'drink bar', 'welcome table']

random.shuffle(activities)

for i in range(len(hosts)):
    print(f"{hosts[i]} will be monitoring the {activities[i]}!")
```