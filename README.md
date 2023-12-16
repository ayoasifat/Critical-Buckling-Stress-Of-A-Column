# Critical Buckling Stress Of A Column
This Python code implements JB Johnson's Parabolic Formula, a mathematical model used in structural engineering to analyze the critical load-carrying capacity of columns before they buckle. The formula considers parameters such as diameter, length, material properties, and end conditions to calculate the critical load.

## Usage
Input the corresponding values for your column in the params object. For unknown values, assign None. The JPF (Johnson Parabolic Formula) model will dynamically calculate any missing values.

```python
# Example Usage
params = {
    'diameter_value': None,
    'length_value': None,
    'sigma_value': None,  # safe stress
    'sigma_yp_value': None,  # elastic limit stress
    'E_value': None,  # modulus of elasticity (e.g., 210e9)
    'P_value': None,  # safe load
    'N_value': None  # coefficient of end-condition
}

J = JPF(*params.values()) 
J.calculate()
```

## Class: JPF (Johnson Parabolic Formula)
### Attributes
- diameter_value: Diameter of the column.
- length_value: Length of the column.
- sigma_value: Safe stress.
- sigma_yp_value: Elastic limit stress.
- E_value: Modulus of elasticity.
- P_value: Safe load.
- N_value: Coefficient of end condition.

### Methods
- calculate(): Computes the critical load based on the provided parameters or any missing variables.
- __init__(): Class constructor that initializes the attributes.

## Additional Information
- The code uses the sympy library for symbolic mathematics.
- Default values for parameters are set to None, and the code calculates them if not provided explicitly.
- The class employs JB Johnson's Parabolic Formula to determine the critical load of a column.
- The formula accounts for factors such as diameter, length, material properties, and end conditions.