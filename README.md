# interactive-calculator-unit-converter
A menu-driven Python application that performs basic arithmetic operations and unit conversions (Kilometers to Miles and Celsius to Fahrenheit). Includes input validation, functions, loops, and error handling.



# Menu Driven Calculator and Unit Converter

def get_number(message):
    while True:
        try:
            return float(input(message))
        except ValueError:
            print("Invalid input! Please enter a valid number.")


def calculator():
    print("\n--- Basic Calculator ---")
    print("1. Addition (+)")
    print("2. Subtraction (-)")
    print("3. Multiplication (*)")
    print("4. Division (/)")

    while True:
        choice = input("Choose operation (1-4): ")

        if choice in ["1", "2", "3", "4"]:
            break
        print("Invalid choice! Try again.")

    num1 = get_number("Enter first number: ")
    num2 = get_number("Enter second number: ")

    if choice == "1":
        print("Result:", num1 + num2)
    elif choice == "2":
        print("Result:", num1 - num2)
    elif choice == "3":
        print("Result:", num1 * num2)
    elif choice == "4":
        if num2 == 0:
            print("Error: Cannot divide by zero!")
        else:
            print("Result:", num1 / num2)


def km_to_miles():
    km = get_number("Enter distance in kilometers: ")
    miles = km * 0.621371
    print("Distance in miles:", round(miles, 3))


def celsius_to_fahrenheit():
    celsius = get_number("Enter temperature in Celsius: ")
    fahrenheit = (celsius * 9/5) + 32
    print("Temperature in Fahrenheit:", round(fahrenheit, 2))


def main():
    while True:
        print("\n===== MAIN MENU =====")
        print("1. Calculator")
        print("2. Kilometer to Miles")
        print("3. Celsius to Fahrenheit")
        print("4. Quit")

        choice = input("Enter your choice (1-4): ")

        if choice == "1":
            calculator()
        elif choice == "2":
            km_to_miles()
        elif choice == "3":
            celsius_to_fahrenheit()
        elif choice == "4":
            print("Thank you for using the program!")
            break
        else:
            print("Invalid choice! Please select 1 to 4.")


if __name__ == "__main__":
    main()
