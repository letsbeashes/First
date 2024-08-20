def display_menu():
    print("\nMenu:")
    print("1. Add item to cart")
    print("2. View cart")
    print("3. Remove item from cart")
    print("4. Exit")

def add_item_to_cart(cart, items):
    member_ch = input("Enter the code of the item you want to add: ")
    for item in items:
        if member_ch == item["code"]:
            cart.append(item)
            print("Item added to your cart.")
            return
    print("Invalid item code.")

def view_cart(cart):
    if not cart:
        print("Your cart is empty.")
    else:
        print("Your cart contains:")
        for idx, item in enumerate(cart, 1):
            print(f"\nItem {idx}:")
            for key, value in item.items():
                print(f"  {key.capitalize()}: {value}")

def remove_item_from_cart(cart):
    if not cart:
        print("Sorry, there is nothing to remove!")
        return
    
    choice = input("Enter the code of the item you want to remove: ")
    for item in cart:
        if choice == item["code"]:
            cart.remove(item)
            print("Item removed from your cart.")
            return
    print("Invalid item code.")

def main():
    items = [
        {"code": "1", "name": "computer", "brand": "sus", "cost": 124_000},
        {"code": "2", "name": "com", "brand": "a", "cost": 12_000},
        {"code": "3", "name": "ter", "brand": "as", "cost": 13_000},
        {"code": "4", "name": "coter", "brand": "us", "cost": 23_000}
    ]
    cart = []

    while True:
        display_menu()
        try:
            choice = int(input("\nEnter your choice (1-4): "))
        except ValueError:
            print("Invalid input. Please enter a number between 1 and 4.")
            continue

        if choice == 1:
            add_item_to_cart(cart, items)
        elif choice == 2:
            view_cart(cart)
        elif choice == 3:
            remove_item_from_cart(cart)
        elif choice == 4:
            print("Thank you! Have a nice day!")
            break
        else:
            print("Invalid choice. Please select a number between 1 and 4.")

if __name__ == "__main__":
    main()
