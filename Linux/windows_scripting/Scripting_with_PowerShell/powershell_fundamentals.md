# PowerShell Fundamentals
- Bash and PowerShell share several fundamental elements that give you the ability
to manage and manipulate date effectively.
- Both shells support variables for storing and retrieving information, arrays
for organizing collections of data, and hashtables for associating keys
with their corresponding values.

## Getting Started with Variables
To declare a variable use the **$** followed by a name
```
$myVariable
```

- PowerShell variable names are **not** case-sensitive.  
The following two variable names refer to the same variable
```
$myVariable
$MyVariable
```
<br>

- We have a variable named **$carType** with the value of **Sedan**.
- Use **Write-Host** to display the value of the variable.
```
# Variable to store car type
$carType = "SUV"

# Display the car type
Write-Host "Car Type: $carType"
```

## Arrays
- We create an array named **$carModels** with three elements.
- To display the first model use **$carModels[0]**
```
# Creating an array of car models
$carModels = "Sedan", "SUV", "Convertible"

#Accessing array elements
 $firstModel = $carModels[0]
Write-Host "First car model: $firstModel"
```

## Hashtables
- A hashtable is a collection of key-value pairs that give the ability to store
and retrieve data based on unique keys.
- To declare a hashtable use **@{}** syntax.
```
$myHashtable = @{ Key = 'Value'}
```

- We created a hashtable **$carWashPrices** with keys ("Basic", "Premium", "Deluxe"))
```
# Creating a hashtable of car wash prices
$carWashPrices = @{
    "Basic" = 10
    "Premium" = 20
    "Deluxe" = 30
}

# Accessing values using keys
$basicPrice = $carWashPrices["Basic"]
Write-Host "Price for Basic wash: $basicPrice"
```

## Functions
- To define a function use the **function** keyword followed by the function name
and a pair of curly braces that enclose the function body.

```
function MyFunction {
    # Function body
}
```
- Functions can accept parameters.
- Parameters can have specific data types to enforce the type of values they can accept.
- Define parameters with parentheses.

```
function StartCarWash {
    param (
        [string]$CarType
    )
        Write-Host "Washing $CarType."
    }
StartCarWash -CarType "Sedan"
```