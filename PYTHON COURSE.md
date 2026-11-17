PINK = "\033[95m"
CYAN = "\033[96m"
GREEN = "\033[92m"
RED = "\033[91m"
YELLOW = "\033[93m"
RESET = "\033[0m"

lessons = [("Basic Python Syntax", 50,
     "Syntax refers to the rules for writing Python.\n"
     "Indentation: Spaces that organize code blocks.\n"
     "Case sensitivity: name and Name are different.\n"
     "print(): Displays information on the screen.\n"
     "Comments: Begin with # and explain code.\n"
     "Example: print('Hello World!')"),

    ("Variables and Naming Rules", 50,
     "Variables store information in a program.\n"
     "Names must begin with a letter or underscore.\n"
     "Names cannot contain spaces or start with numbers.\n"
     "Python keywords cannot be variable names.\n"
     "Names are case-sensitive.\n"
     "Example: student_name = 'Ana'"),

    ("Basic Data Types", 50,
     "int: Whole numbers such as 10 and 25.\n"
     "float: Decimal numbers such as 10.50.\n"
     "str: Text enclosed in quotation marks.\n"
     "bool: True or False values.\n"
     "type(): Identifies a variable's data type.\n"
     "Example: age = 18; price = 19.99"),

    ("Constants", 50,
     "Constants are values intended to remain fixed.\n"
     "Python uses uppercase names for constants.\n"
     "Python does not strictly enforce constants.\n"
     "Examples: PI = 3.14159, TAX_RATE = 0.12"),

    ("Arithmetic Operators and PEMDAS", 60,
     "+ Addition       - Subtraction\n"
     "* Multiplication / Division\n"
     "// Floor Division\n"
     "% Modulus (Remainder)\n"
     "** Exponentiation\n"
     "PEMDAS determines the order of calculations.\n"
     "P - Parentheses\n"
     "E - Exponents\n"
     "MD - Multiplication and Division\n"
     "AS - Addition and Subtraction\n"
     "Equal-priority operations run left to right.\n"
     "Example: result = 2 + 3 * 4  # 14\n"
     "Modulus Example: 10 % 3 = 1"),

    ("Conditional Statements", 60,
     "if: Runs code when a condition is True.\n"
     "elif: Checks another condition.\n"
     "else: Runs when previous conditions are False.\n"
     "Nested if: An if statement inside another if.\n"
     "Example:\n"
     "if age >= 18:\n"
     "    print('Adult')\n"
     "else:\n"
     "    print('Minor')"),

    ("Relational Operators", 50,
     "Relational operators compare two values.\n"
     "== Equal to       != Not equal to\n"
     "> Greater than   < Less than\n"
     ">= Greater/equal <= Less/equal\n"
     "Comparisons return True or False.\n"
     "Example: comparison = 10 > 5"),

    ("Logical Operators and Truth Tables", 60,
     "and: True when both conditions are True.\n"
     "or: True when at least one condition is True.\n"
     "not: Reverses a Boolean value.\n"
     "TRUTH TABLE:\n"
     "A      B      AND     OR\n"
     "True   True   True    True\n"
     "True   False  False   True\n"
     "False  True   False   True\n"
     "False  False  False   False\n"
     "not True = False; not False = True.\n"
     "Example: allowed = age >= 18 and has_id"),

    ("Loops and Iteration", 60,
     "Loops repeat instructions in a program.\n"
     "for: Repeats over a sequence or range.\n"
     "while: Repeats while a condition is True.\n"
     "break: Immediately stops a loop.\n"
     "continue: Skips the current iteration.\n"
     "Example:\n"
     "for i in range(1, 6):\n"
     "    print(i)"),

    ("Nested Loops", 60,
     "A nested loop is a loop inside another loop.\n"
     "The inner loop repeats for each outer iteration.\n"
     "Useful for patterns, tables, and grids.\n"
     "Example:\n"
     "for i in range(2):\n"
     "    for j in range(2):\n"
     "        print(i, j)")]

links = [
    # 1. Basic Python Syntax
    "https://canva.link/aunic5rllaa4c9f",

    # 2. Variables and Naming Rules
    "https://canva.link/xk3rk8lfqfn239i",

    # 3. Basic Data Types
    "https://canva.link/i9sjoh9klfo11m6",

    # 4. Constants
    "https://canva.link/3oe81dzfhure5y0",

    # 5. Arithmetic Operators and PEMDAS
    "https://canva.link/siqzazvdige5etk",

    # 6. Conditional Statements
    "https://www.youtube.com/watch?v=FvMPfrgGeKs&t=352s",

    # 7. Relational Operators
    "https://www.youtube.com/watch?v=tORtXAjQ5PA",

    # 8. Logical Operators and Truth Tables
    "https://www.youtube.com/watch?v=vNdYpmJt3Qc",

    # 9. Loops and Iteration
    "https://www.youtube.com/watch?v=6iF8Xb7Z3wQ",

    # 10. Nested Loops
    "https://www.youtube.com/watch?v=APWy6Pc83gE"]

all_lessons_link = "https://bit.ly/3WKLK4j"

customer_name = ""
purchased = []
total_spent = 0


WIDTH = 60

def title(message):
    print(f"{PINK}\n{'=' * WIDTH}")
    print(message.center(WIDTH))
    print(f"{'=' * WIDTH}{RESET}")

def menu_item(number, label, color=CYAN):
    # Each menu item starts at the same position.
    print(f"{color}    [{number:>2}]  {label}{RESET}")

def price_line(label, amount):
    # Left-align the label and right-align the peso amount.
    print(f"    {label:<38} ₱{amount:>10,.2f}")

def get_name():
    global customer_name
    while customer_name == "":
        customer_name = input(CYAN + "    Customer name: " + RESET).strip()
        if customer_name == "":
            print(RED + "    Please enter your name." + RESET)

def show_lessons():
    title("AVAILABLE PYTHON LESSONS")
    print(f"    {'LESSON':<38} {'PRICE':>11}")
    print("    " + "-" * 53)
    for i in range(len(lessons)):
        name, price, description = lessons[i]
        status = " ✓" if i in purchased else ""
        print(f"{CYAN}    [{i + 1:>2}] {name:<36} ₱{price:>6,.2f}{GREEN if status else CYAN}{status}{RESET}")
    print("    " + "-" * 53)
    menu_item(11, "Purchase All Lessons", YELLOW)
    menu_item(0, "Return to Main Menu", RED)

def show_description(i):
    name, price, description = lessons[i]
    title(name.upper())
    for line in description.split("\n"):
        if line.startswith("Example:") or line.startswith("Modulus Example:"):
            print(f"{CYAN}    {line}{RESET}")
        else:
            print("    " + line)
    print("    " + "-" * 53)
    price_line("LESSON PRICE", price)

def purchase(items, purchase_all=False):
    global total_spent
    cart = []
    for i in items:
        if i not in purchased:
            cart.append(i)
    if len(cart) == 0:
        print(RED + "    You already purchased these lessons." + RESET)
        return

    title("SHOPPING CART")
    subtotal = 0
    for i in cart:
        price_line(lessons[i][0], lessons[i][1])
        subtotal = subtotal + lessons[i][1]
    # No discounts: customer pays the full lesson price.
    total = subtotal

    print("    " + "-" * 53)
    price_line("TOTAL", total)

    confirm = input("\n    Proceed to payment? (YES/NO): ").strip().upper()
    if confirm != "YES":
        print(RED + "    Purchase cancelled." + RESET)
        return
    get_name()
    while True:
        amount = input(CYAN + "    Enter payment: ₱" + RESET).strip()
        try:
            payment = float(amount)
        except ValueError:
            print(RED + "    Please enter a number." + RESET)
            continue
        if payment != payment or payment == float("inf") or payment == float("-inf") or payment < 0:
            print(RED + "    Invalid payment amount." + RESET)
        elif payment < total:
            print(RED + f"    Insufficient payment. Need ₱{total - payment:.2f} more." + RESET)
            again = input("    Try again? (YES/NO): ").strip().upper()
            if again != "YES":
                print("    Purchase cancelled.")
                return
        else:
            break

    for i in cart:
        purchased.append(i)
    total_spent = total_spent + total
    title("OFFICIAL PAYMENT RECEIPT")
    print(f"    Customer: {customer_name}")
    print("    " + "-" * 53)
    for i in cart:
        price_line(lessons[i][0], lessons[i][1])
    print("    " + "-" * 53)
    price_line("TOTAL", total)
    price_line("Payment", payment)
    price_line("Change", payment - total)
    print(GREEN + "\n" + "PAYMENT SUCCESSFUL!".center(WIDTH) + RESET)
    title("YOUR LESSON LINKS")
    if purchase_all or len(purchased) == len(lessons):
        print("    Complete course:", all_lessons_link)
    else:
        for i in cart:
            print("    " + lessons[i][0])
            print("    " + links[i])
    print(GREEN + "\n" + f"Thank you, {customer_name}!".center(WIDTH) + RESET)


def view_purchased():
    title("MY PURCHASED LESSONS")
    if len(purchased) == 0:
        print("    You have not purchased any lessons.")
        return
    print("    Customer:", customer_name)
    for i in purchased:
        print(f"{GREEN}    {lessons[i][0]}{RESET}")
        print("    Link:", links[i])
    if len(purchased) == len(lessons):
        print("    Complete course:", all_lessons_link)
    print("    " + "-" * 53)
    price_line("Total spent", total_spent)


def discover_python():
    title("DISCOVER THE WORLD OF PYTHON")

    print("""WHAT IS PYTHON?

Python is a high-level, general-purpose programming
language known for readable, beginner-friendly code.

WHO CREATED PYTHON?

Guido van Rossum, a Dutch programmer, created Python
while working at CWI in the Netherlands.

WHEN WAS IT CREATED?

Development started in December 1989.
The first public release was in February 1991.
Python 1.0 was released in January 1994.

WHERE DID THE NAME COME FROM?

It was inspired by Monty Python's Flying Circus,
a British comedy show, not the snake!

WHAT CAN YOU DO WITH PYTHON?

  * Create websites and software
  * Automate repetitive tasks
  * Analyze data and build reports
  * Explore AI and machine learning

WHY LEARN PYTHON?

It helps develop problem-solving and coding skills.
With practice, you can explore freelance projects
and careers in development, data, and automation.

LEARNING REFERENCE

https://bit.ly/4exylmf

>> Keep learning. Every line of code is progress!
""")


def main():
    title("WELCOME TO PYTHON LEARNING HUB")
    print(GREEN + "LEARN • SHOP • GROW".center(WIDTH) + RESET)
    while True:
        title("MAIN MENU")
        menu_item(1, "Browse and Purchase Lessons", PINK)
        menu_item(2, "Discover Python", CYAN)
        menu_item(3, "View Purchased Lessons", GREEN)
        menu_item(4, "Exit", RED)
        choice = input("\n    Choose an option: ").strip()
        if choice == "1":
            while True:
                show_lessons()
                selected = input("\n    Choose a lesson (0-11): ").strip()
                if selected == "0":
                    break
                elif selected == "11":
                    purchase(range(len(lessons)), purchase_all=True)
                elif selected.isdigit() and 1 <= int(selected) <= len(lessons):
                    i = int(selected) - 1
                    show_description(i)
                    if i in purchased:
                        print(GREEN + "    You already own this lesson." + RESET)
                    else:
                        answer = input("\n    Purchase this lesson? (YES/NO): ").strip().upper()
                        if answer == "YES":
                            purchase([i])
                else:
                    print(RED + "    Invalid lesson choice." + RESET)
        elif choice == "2":
            discover_python()
        elif choice == "3":
            view_purchased()
        elif choice == "4":
            title("THANK YOU FOR LEARNING!")
            goodbye = "Adiós!, " + customer_name + "!" if customer_name else "See you again!"
            print(GREEN + goodbye.center(WIDTH) + RESET)
            break
        else:
            print(RED + "    Invalid menu choice." + RESET)


if __name__ == "__main__":
    main()
