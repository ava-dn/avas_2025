## List and Algorithm Hw


#### Popcorn Hack #1

```python
# Create the original list
movies = ["Despicable Me", "Mean Girls", "Zapped", "Legally Blonde"]

# Replace the second movie with a new one
movies[1] = "Lean on Me"

# Add another movie to the list
movies.append("Clueless")

# Display the updated list
print(movies)
```

```python
['Despicable Me', 'Lean on Me', 'Zapped', 'Legally Blonde', 'Clueless']
```



#### Popcorn Hack #2 


```python 
ages = [15, 20, 34, 16, 18, 21, 14, 19]

# Using list comprehension to filter eligible ages
eligible_ages = [age for age in ages if age >= 18]

print(eligible_ages)
```



## HW HACK 1



#### Notes from video #1

- In python, lists are a built in data structure for storing and accessing objects which belong in a specific sequence.
- There are 2 ways to build a list: one way is to use the list constructor but a simpler way is to use brackets
- When creating a list you can prepopulate it with values
- You can always add values later by using the append method
- Lists conserve the order of the data which is different from sets
- In lists order is everything
- You do not have to view the entire list if you want to see a specific value you can access it by its index



#### Notes from video #2

- A list comprehension is an easier and more readable way to create a list.
- Brackets mean that you are creating a list
- List comprehensions are much easier to write and print the same result from the 4 loop
-  the benefits of using comprehensions over conventional loops, such as reduced code length and improved clarity
- while comprehensions are powerful, they should be used carefully to maintain code readability, especially when dealing with complex operations
- comprehensions are a way to concisely create new sequences (like lists, sets, or dictionaries) from existing ones, often using a single line of code
- Set comprehension is a method for creating sets in python using the elements from other iterables like lists, sets, or tuples


## HW HACK 2


```py
# Initialize the list with numbers from 1 to 30
numbers = list(range(1, 31))

# Filter out numbers divisible by 3 but not by 5
filtered_numbers = [num for num in numbers if num % 3 == 0 and num % 5 != 0]

# Print the original and filtered lists
print("Original List:", numbers)
print("Filtered List (divisible by 3 but not 5):", filtered_numbers)
```

**Output:**

```py
Original List: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30]
Filtered List (divisible by 3 but not 5): [3, 6, 9, 12, 18, 21, 24, 27]
```


## HW HACK 3


```py
import csv

def filter_spotify_data(csv_file):
    # Initialize an empty list to store filtered songs
    filtered_songs = []

    # Open the CSV file and read the data
    with open(csv_file, mode='r', encoding='utf-8') as file:
        reader = csv.DictReader(file)
        
        # Loop through each row in the CSV file
        for row in reader:
            # Convert the 'Streams' value to an integer
            streams = int(row["Streams"])

            # Check if the song has more than 10 million streams
            if streams > 10000000:
                filtered_songs.append(row)
    
    # Display the filtered songs
    if filtered_songs:
        print(f"Songs with over 10 million streams:\n")
        for song in filtered_songs:
            print(f"Song: {song['Song Name']}, Artist: {song['Artist']}, Streams: {song['Streams']}")
    else:
        print("No songs found with more than 10 million streams.")

filter_spotify_data("spotify_data_2024.csv")
```


**Output:**

```py
Songs with over 10 million streams:

Song: Shape of You, Artist: Ed Sheeran, Streams: 50000000
Song: Blinding Lights, Artist: The Weeknd, Streams: 12000000
```


## Review Quesitons


1. What are lists in Python and how do you use them?
Lists are used in Python to store multiple items in one place. You can change them, add new items, remove items, and look at specific items using their position (called an index). You can also loop through them and check if something is in the list.

2. Real-world example of a filtering algorithm:
A filtering algorithm is used in email spam filters. It checks emails for spammy words or known spam senders and moves them to the spam folder if needed.

3. Why is it important to check how efficient a filtering algorithm is?
Efficient filtering algorithms are faster and use less computer power. This helps apps run better, saves time, and gives users quicker results—especially when working with a lot of data.