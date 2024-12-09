# F# Mutable Variable Swap Bug
This repository demonstrates an uncommon bug in F# related to the behavior of mutable variables when passed to functions.  The `swap` function attempts to swap the values of two mutable variables, but due to pass-by-reference semantics, it fails to modify the original variables.

## Bug Description
The issue lies in the way F# handles mutable variables. When a mutable variable is passed to a function, it's passed by reference. Therefore, any modifications made to the variable within the function directly affect the original variable. However, the original intention in this case was to swap the variables' values, a behavior that would be expected in many other languages if they use pass-by-value. 

## Solution
The solution involves returning new values for the swapped variables instead of directly modifying the original ones. This approach mimics the behavior that's expected when pass-by-value is used.