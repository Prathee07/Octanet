import time

def atm_simulation():
    print("Please insert Your CARD")
    time.sleep(5)  # Simulating card processing time

    # Initialize account data
    password = 1234
    balance = 5000
    transaction_history = []  # List to store transaction history

    # Taking ATM pin from user
    try:
        pin = int(input("Enter your ATM PIN: "))
    except ValueError:
        print("Invalid input. Please enter a numeric PIN.")
        return

    # Checking if the PIN is valid
    if pin == password:
        while True:
            # Showing menu options
            print("""
            1 - Check balance
            2 - Withdraw balance
            3 - Deposit balance
            4 - Change PIN
            5 - View transaction history
            6 - Exit
            """)

            try:
                # Taking an option from user
                option = int(input("Please enter your choice: "))
            except ValueError:
                print("Invalid input. Please enter a number.")
                continue

            # Option 1: Check balance
            if option == 1:
                print(f"Your current balance is ${balance:.2f}")

            # Option 2: Withdraw balance
            elif option == 2:
                try:
                    withdraw_amount = float(input("Please enter amount to withdraw: "))
                    if withdraw_amount <= 0:
                        print("Amount must be positive.")
                    elif withdraw_amount > balance:
                        print("Insufficient funds.")
                    else:
                        balance -= withdraw_amount
                        transaction_history.append(f"Withdrew ${withdraw_amount:.2f}")
                        print(f"${withdraw_amount:.2f} has been debited from your account.")
                        print(f"Your updated balance is ${balance:.2f}")
                except ValueError:
                    print("Invalid input. Please enter a numeric amount.")

            # Option 3: Deposit balance
            elif option == 3:
                try:
                    deposit_amount = float(input("Please enter amount to deposit: "))
                    if deposit_amount <= 0:
                        print("Amount must be positive.")
                    else:
                        balance += deposit_amount
                        transaction_history.append(f"Deposited ${deposit_amount:.2f}")
                        print(f"${deposit_amount:.2f} has been credited to your account.")
                        print(f"Your updated balance is ${balance:.2f}")
                except ValueError:
                    print("Invalid input. Please enter a numeric amount.")

            # Option 4: Change PIN
            elif option == 4:
                try:
                    old_pin = int(input("Enter your current PIN: "))
                    if old_pin != password:
                        print("Incorrect current PIN.")
                        continue
                    new_pin = int(input("Enter your new PIN: "))
                    if new_pin == password:
                        print("New PIN cannot be the same as the old PIN.")
                        continue
                    password = new_pin
                    print("PIN changed successfully.")
                except ValueError:
                    print("Invalid input. Please enter a numeric PIN.")

            # Option 5: View transaction history
            elif option == 5:
                print("Transaction History:")
                if not transaction_history:
                    print("No transactions yet.")
                for transaction in transaction_history:
                    print(transaction)

            # Option 6: Exit
            elif option == 6:
                print("Exiting... Thank you for using the ATM.")
                break

            # Invalid option
            else:
                print("Invalid option. Please select a valid option.")
    else:
        print("Incorrect PIN. Please try again.")

# Run the ATM simulation
atm_simulation()
