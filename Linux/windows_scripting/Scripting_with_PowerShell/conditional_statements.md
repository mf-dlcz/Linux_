# Conditional Statements
- Conditionals are essential for decision-making in scripts.

## If Statements
- Is a basic conditional statement for a single condition.
```
# Car wash example
$weather = "sunny"
if ($weather -eq "sunny") {
    Write-Host "It's a good day for a car wash!"
}
```

## If-Else Statements
- Handles two conditions, but does not test multiple conditions sequentially.
```
# Car wash example
$weather = "rainy"
if ($weather -eq "sunny") {
    Write-Host "It's a good day for a car wash!"
} else {
    Write-Host "It's raining. Maybe another day."
}
```

## Else If Statements
- Used to test multiple conditions in a sequence.
```
# Car wash example
$weather = "cloudy"
if ($weather -eq "sunny") {
    Write-Host "It's a good day for a car wash!"
} elseif ($weather -eq "cloudy") {
    Write-Host "The weather is okay. You can still have a car wash."
} else {
    Write-Host "It's not the best weather for a car wash."
}
```