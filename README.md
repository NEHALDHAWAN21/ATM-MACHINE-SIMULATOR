# ATM-MACHINE-SIMULATOR
class ATM:
    def __init__(self, balance=10000):
        self.balance = balance

    def check_balance(self):
        print(f"Your current balance is ₹{self.balance}")

    def withdraw(self, amount):
        if amount <= 0:
            print("Enter a valid amount to withdraw.")
        elif amount > self.balance:
            print("Insufficient balance!")
        else:
            self.balance -= amount
            print(f"₹{amount} withdrawn successfully.")

    def deposit(self, amount):
        if amount <= 0:
            print("Enter a valid amount to deposit.")
        else:
            self.balance += amount
            print(f"₹{amount} deposited successfully.")

def atm_simulator():
    atm = ATM()
    print("Welcome to the ATM Simulator!")

    while True:
        print("\nMenu:")
        print("1. Check Balance")
        print("2. Withdraw")
        print("3. Deposit")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            atm.check_balance()
        elif choice == '2':
            amount = float(input("Enter amount to withdraw: ₹"))
            atm.withdraw(amount)
        elif choice == '3':
            amount = float(input("Enter amount to deposit: ₹"))
            atm.deposit(amount)
        elif choice == '4':
            print("Thank you for using the ATM. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

# Run the simulator
atm_simulator()
