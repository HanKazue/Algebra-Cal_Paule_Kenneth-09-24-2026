# Algebra-Cal_Paule_Kenneth-09-24-2026
#----- MAIN PROGRAM -----
def main():
    print("ALGEBRA & CALCULUS 1")
    print("FIND THE VALUE OF (x) = FORMULA: f(x)=(ax^2bx+c)")

    while True:
        print("\n1. Solve a linear equation(ax + b =c)")
        print("2. Solve a quadratic equaiton (ax^2 +bx+x = 0)")
        print("3. Evaluate f(x)= ax^ 2+ bx + c")
        print("4. Find the derivative f' (x) ata point")
        print("5. Estimate a limit as x approaches a value")
        print("6. Compute a definite intergal of f(x)")
        print("7. Quit")

        choice= input("Choose an option: ").strip()
        
        if choice =="1":
            a,b,c = get_float("a: "), get_float("b: "), get_float("c: ")
            print(solve_linear(a,b,c))

        elif choice =="2":
            a,b,c = get_float("a:"), get_float("b:"), get_float("c:")
            print(solve_quadratic(a,b,c))

        elif choice =="3":
            a,b,c = get_float("a:"), get_float("b:"), get_float("c:")
            x = get_float("x:")
            print(f"f({x})= {f(a,b,c)}")

        elif choice =="4":
            a,b,c = get_float("a:"), get_float("b:"), get_float("c:")
            x = get_float("x:")
            exact = derivative_exact(a,b,x)
            numeric = derivative_numeric(a,b,c,x)
            print(f"Exact f'({x}) = {exact}")
            print (f" Numeric f' ({x})= {numeiric:.6f} (via central difference)")

        elif choice =="5":
            a,b,c = get_float("a:"), get_float("b:"), get_float("c:")
            x0= get_float("x0(the value of x approaches):")
            print(estimate_limit(a,b,c))

        elif choice == "6":
            a,b,c = get_float("a:"), get_float("b:"), get_float("c:")
            x1 = get_float("Lower bound x1: ")
            x2 = get_float("Upper bound x2: ")
            exact = integral_exact(a,b,c, x1, x2)
            numeric = integral_trapezoid(a,b,c, x1, x2)
            print(f"Exact integral= {exact:.6f}")
            print(f"Numeric integral = {numeric:.6f} (via trapezoidal rule, n = 1000)")

        elif choice =="7":
            print("Goodbye!")
            break
        else:
            print("Invalid choice:please choose 1-7.")

        if__name__=="main__":
            main()
