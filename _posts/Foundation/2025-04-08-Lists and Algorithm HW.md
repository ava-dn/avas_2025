#### List and Algorithm Hw


## Popcorn Hack #1

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



## Popcorn Hack #2 


```python 
ages = [15, 20, 34, 16, 18, 21, 14, 19]

# Using list comprehension to filter eligible ages
eligible_ages = [age for age in ages if age >= 18]

print(eligible_ages)
```