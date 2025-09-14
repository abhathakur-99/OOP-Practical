#1. Write a program to find the nature of the roots of a quadratic equation
# Quadratic Equation: ax^2 + bx + c = 0

a = float(input("Enter coefficient a: "))
b = float(input("Enter coefficient b: "))
c = float(input("Enter coefficient c: "))

# Calculate discriminant
D = b**2 - 4*a*c

print("Discriminant (D) =", D)

# Nature of roots
if D > 0:
    print("The equation has real and distinct roots.")
elif D == 0:
    print("The equation has real and equal roots.")
else:
    print("The equation has imaginary (complex) roots.")
