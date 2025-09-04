# Functions
```
function_name() {
    [block of code]
}


function_name
```

- Prints a welcome message when it's called.
```
#!/bin/bash
greet() {
    echo "Good Morning"
}

greet
```

## Function Types & Variable Scope
- Variables can have **local** or **global** scope.
- By default, all variables that are defined in Bash are **global** variables which can be accessed anywhere from within your script.
- **Local** scope variables are _only_ accessible inside the function.

<br>

```
# Global variable
length=5

# Function to calculate the area of a rectangle
calculate_area() {
    local width=3                       # Local variable for the width of a rectangle
    local area=$((length*width))        # Calculate the area
    echo "The area of the rectangle is $area sqaure units."
}

# Call the function
calculate_area
```

- Acessing the value in the global variable **length** is possible, but not for the local variable **width**.
```
# Attempt to access the local variable outside the function
echo "Outside the function"
echo "Length: $length"          # global variable
echo "Width: $width"            # local variable
```