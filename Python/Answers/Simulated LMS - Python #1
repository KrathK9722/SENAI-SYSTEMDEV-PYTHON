"""
// This was a school activity developed in Python for a presentation. 

You can run it in this website:
https://python-fiddle.com/saved/34dd9a2a-309e-4d5a-b181-e60a7b00dd90

It simulates a simple Learning Management System (LMS) 
where users can create accounts, log in, and access different menus based on their roles 
(Teacher, Student, Coordinator, Developer). 
Each role has specific options for managing activities, classes, courses, and users. 

// The program continues running until the user chooses to exit.

"""

# List to store user data
users = []

# System control variables
running_program = True
access_granted = False

# Welcome message
print("\nWelcome to the School Activity Management System (LMS)!\n\n")

# Main program loop
while running_program:

    # Login or account creation
    if not access_granted:
        current_user = None

        # Prompt user to choose login or create account
        while True:
            try:
                selection = int(input("Create or Log into your account (1 = Login / 0 = Create): "))
                if selection in [0, 1]:
                    break
                print("Invalid value! Enter 0 or 1.")
            except ValueError:
                print("Error! Enter an integer (0 or 1).")

        login = selection == 1

        # Create account
        if not login:
            username = input("Create your username: ")
            password = input("Create your password: ")

            # Select role
            while True:
                try:
                    role_choice = int(input(
                        "Select your role:\n(1) Teacher\n(2) Student\n(3) Coordinator\n(4) Developer\n\nEnter a value: "
                    ))
                    if role_choice in [1, 2, 3, 4]:
                        break
                    print("Invalid value! Enter 1, 2, 3, or 4.")
                except ValueError:
                    print("Error! Enter an integer (1, 2, 3, or 4).")

            # Handle role-specific access codes
            if role_choice == 1:
                code = input("Enter teacher access code: ")
                if code == "0001":
                    users.append({'username': username, 'password': password, 'role': "Teacher"})
                    input("Account created successfully! Press Enter to continue...")
                else:
                    input("Incorrect code. Press Enter to continue...")
            elif role_choice == 2:
                users.append({'username': username, 'password': password, 'role': "Student"})
                input("Account created successfully! Press Enter to continue...")
            elif role_choice == 3:
                code = input("Enter coordinator access code: ")
                if code == "0002":
                    users.append({'username': username, 'password': password, 'role': "Coordinator"})
                    input("Account created successfully! Press Enter to continue...")
                else:
                    input("Incorrect code. Press Enter to continue...")
            elif role_choice == 4:
                code = input("Enter developer access code: ")
                if code == "0007":
                    users.append({'username': username, 'password': password, 'role': "Developer"})
                    input("Account created successfully! Press Enter to continue...")
                else:
                    input("Incorrect code. Press Enter to continue...")

        # Login
        if login:
            username = input("Enter your username: ")
            matching = [u for u in users if u['username'] == username]
            if matching:
                password = input("Enter your password: ")
                if password == matching[0]['password']:
                    current_user = matching[0]
                    role = current_user['role']
                    print(f"Welcome {role} {username}")
                    access_granted = True
                else:
                    input("Incorrect password. Press Enter to continue...")
            else:
                input("User not found. Press Enter to continue...")

    # User menus
    if access_granted:
        role = current_user['role']

        # Teacher menu
        if role == "Teacher":
            while access_granted and running_program:
                try:
                    option = int(input(
                        "\n--- Teacher Menu ---\n"
                        "(4) Manage Activities\n"
                        "(3) Manage Classes\n"
                        "(2) Manage Courses\n"
                        "(1) Logout\n"
                        "(0) Exit System\n"
                        "Enter a value: "
                    ))
                except ValueError:
                    print("Enter a valid number.")
                    continue

                if option == 4:
                    input("Managing Activities...\n\nEnter 0 to return to Teacher menu: ")
                elif option == 3:
                    input("Managing Classes...\n\nEnter 0 to return to Teacher menu: ")
                elif option == 2:
                    input("Managing Courses...\n\nEnter 0 to return to Teacher menu: ")
                elif option == 1:
                    access_granted = False
                    input("Logging out...\n\nPress Enter to continue...")
                elif option == 0:
                    running_program = False
                    access_granted = False
                else:
                    print("Invalid value.")

        # Student menu
        elif role == "Student":
            while access_granted and running_program:
                try:
                    option = int(input(
                        "\n--- Student Menu ---\n"
                        "(4) Activities\n"
                        "(3) My Class\n"
                        "(2) My Courses\n"
                        "(1) Logout\n"
                        "(0) Exit System\n"
                        "Enter a value: "
                    ))
                except ValueError:
                    print("Enter a valid number.")
                    continue

                if option == 4:
                    input("No activities available.\n\nEnter 0 to return to Student menu: ")
                elif option == 3:
                    input("No class assigned.\n\nEnter 0 to return to Student menu: ")
                elif option == 2:
                    input("No courses available.\n\nEnter 0 to return to Student menu: ")
                elif option == 1:
                    access_granted = False
                    input("Logging out...\n\nPress Enter to continue...")
                elif option == 0:
                    running_program = False
                    access_granted = False
                else:
                    print("Invalid value.")

        # Coordinator menu
        elif role == "Coordinator":
            while access_granted and running_program:
                try:
                    option = int(input(
                        "\n--- Coordinator Menu ---\n"
                        "(4) Manage Classes\n"
                        "(3) Manage Courses\n"
                        "(2) View Teachers\n"
                        "(1) Logout\n"
                        "(0) Exit System\n"
                        "Enter a value: "
                    ))
                except ValueError:
                    print("Enter a valid number.")
                    continue

                if option == 4:
                    input("Managing Classes...\n\nEnter 0 to return to Coordinator menu: ")
                elif option == 3:
                    input("Managing Courses...\n\nEnter 0 to return to Coordinator menu: ")
                elif option == 2:
                    teacher_list = "\n--- Teacher List ---"
                    for u in users:
                        if u['role'] == "Teacher":
                            teacher_list += "\nName: " + u['username']
                    input(teacher_list + "\n\nEnter 0 to return to Coordinator menu: ")
                elif option == 1:
                    access_granted = False
                    input("Logging out...\n\nPress Enter to continue...")
                elif option == 0:
                    running_program = False
                    access_granted = False
                else:
                    print("Invalid value.")

        # Developer menu
        elif role == "Developer":
            while access_granted and running_program:
                try:
                    option = int(input(
                        "\n--- Developer Menu ---\n"
                        "(3) Manage Users\n"
                        "(2) View Users\n"
                        "(1) Logout\n"
                        "(0) Exit System\n"
                        "Enter a value: "
                    ))
                except ValueError:
                    print("Enter a valid number.")
                    continue

                if option == 3:
                    response = input("What user do you want to delete? \n\nEnter the username to delete or 0 to return to Developer menu: ")
                    if response != "0":
                        matching = [u for u in users if u['username'] == response]
                        if matching:
                            user_to_delete = matching[0]
                            
                            # Check if trying to delete own account
                            if user_to_delete['username'] == current_user['username']:
                                input("You don't have permission to delete your own account. Press Enter to continue...")
                            # Check if trying to delete another Developer
                            elif user_to_delete['role'] == "Developer":
                                security_key = input("This user is a Developer. Enter the security key to confirm deletion: ")
                                if security_key == "0007":
                                    users.remove(user_to_delete)
                                    input("User deleted successfully! Press Enter to continue...")
                                else:
                                    input("Incorrect security key. Deletion cancelled. Press Enter to continue...")
                            else:
                                # Confirmation for deleting other users
                                confirm = input(f"Are you sure you want to delete user '{user_to_delete['username']}'? (yes/no): ")
                                if confirm.lower() == "yes":
                                    users.remove(user_to_delete)
                                    input("User deleted successfully! Press Enter to continue...")
                                else:
                                    input("Deletion cancelled. Press Enter to continue...")
                        else:
                            input("User not found. Press Enter to continue...")
                elif option == 2:
                    user_list = "\n--- User List ---"
                    for u in users:
                        user_list += f"\nName: {u['username']} | Role: {u['role']}"
                    input(user_list + "\n\nEnter 0 to return to Developer menu: ")
                elif option == 1:
                    access_granted = False
                    input("Logging out...\n\nPress Enter to continue...")
                elif option == 0:
                    running_program = False
                    access_granted = False
                else:
                    print("Invalid value.")

# Program exit
input("Press Enter to close the program.")
