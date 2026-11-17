def main():
    categories = [
        "Transportation",
        "Accommodation",
        "Food",
        "Entertainment"
    ]

    expenses = {}

    print("Travel Expense Analyzer\n")

    for category in categories:
        while True:
            try:
                amount = float(
                    input(f"{category} cost: ")
                )

                if amount < 0:
                    print("Cost cannot be negative.")
                    continue

                expenses[category] = amount
                break

            except ValueError:
                print("Enter a valid number.")

    total = sum(expenses.values())

    print("\n--- Travel Report ---")

    for category, amount in expenses.items():
        percentage = (
            amount / total * 100 if total > 0 else 0
        )

        print(
            f"{category}: {amount:.2f} "
            f"({percentage:.1f}%)"
        )

    print("-" * 30)
    print(f"Total travel cost: {total:.2f}")

    highest = max(expenses, key=expenses.get)

    print(f"Most expensive category: {highest}")

if __name__ == "__main__":
    main()
