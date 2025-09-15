# Loops
- PowerShells loop syntax is consistent with its object-oriented nature.
- Bash, being a Unix-based shell, has a syntax that is more text-oriented and focused on manipulating strings and streams.

## For Loops
- Can iterate a specific number of times.
***
1. Create an array that contains different types of cars.
2. Initiate a loop variable that starts at 0.
3. The loop continues running as long as the variable is less than the length of the array.
4. Increment the loop variable after each iteration.
5. Finally, the loop prints a message indicating that the current car is being washed.

```
# Define an array of car types
$cartypes = "sedan", "SUV", "truck", "convertible"
# For loop to wash each car
for ($i = 0; $i -lt $cartypes.Length; $i++) {
    $currentcar = $cartypes[$i]
    Write-Output "Washing $currentcar."
}
```

> [!NOTE]
> Use the **Count** method to determine the number of elements in an array or the number of characters in a string.

## While Loop
