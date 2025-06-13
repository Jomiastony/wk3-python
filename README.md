# wk3-python

def calculate_discount(price, discount_percent):
    """
    Calculate the final price after applying discount.
    Only applies discount if discount_percent >= 20.
    """
    if discount_percent >= 20:
        discount_amount = price * (discount_percent / 100)
        final_price = price - discount_amount
        return final_price
    else:
        return price

def get_float_input(prompt):
    """
    Prompt user for a valid float input.
    Keeps asking until a valid number is entered.
    """
    while True:
        try:
            value = float(input(prompt))
            if value < 0:
                print("Please enter a non-negative number.")
                continue
            return value
        except ValueError:
            print("Invalid input. Please enter a numeric value.")

def main():
    print("=== Discount Calculator ===")
    
    price = get_float_input("Enter the original price of the item: ")
    discount_percent = get_float_input("Enter the discount percentage: ")

    final_price = calculate_discount(price, discount_percent)

    if discount_percent >= 20:
        print(f"\nDiscount applied. The final price is: ${final_price:.2f}")
    else:
        print(f"\nNo discount applied. The price remains: ${price:.2f}")

if __name__ == "__main__":
    main()
