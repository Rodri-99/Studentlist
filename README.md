# Studentlist

names = ["Alice", "Bob", "Charlie", "David"]
hometowns = ["New York", "Los Angeles", "Chicago", "Houston"]
favorite_foods = ["Pizza", "Sushi", "Burgers", "Tacos"]

def validate_input(prompt, options):
    while True:
        user_input = input(prompt).strip().lower()
        if user_input in options:
            return user_input
        else:
            print("Invalid input. Please enter a valid option.")

while True:
    print("Enter the number of the student you want to learn about:")
    for i, name in enumerate(names, 1):
        print(f"{i}. {name}")
    student_num = int(input("Number: "))

    # Validate user number
    if student_num < 1 or student_num > len(names):
        print("Invalid student number. Please enter a number within the range.")
        continue

    # Print student's name
    print(f"\nStudent's name: {names[student_num - 1]}")

    # Ask user for category to display
    category = validate_input("Which category would you like to display? (Hometown/Favorite Food): ",
                              ["hometown", "favorite food"])

    # Display relevant information
    if category == "hometown":
        print(f"Hometown: {hometowns[student_num - 1]}")
    else:
        print(f"Favorite Food: {favorite_foods[student_num - 1]}")

    # Ask user if they want to learn about another student
    repeat = input("Would you like to learn about another student? (yes/no): ").strip().lower()
    if repeat != "yes":
        break
