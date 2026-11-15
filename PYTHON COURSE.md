
import ast
import math

# ==========================================
#           PYTHON LEARNING HUB
#          LEARN • PRACTICE • GROW
# ==========================================

# COLORS
P = "\033[95m"
C = "\033[96m"
G = "\033[92m"
R = "\033[91m"
Y = "\033[93m"
PK = "\033[38;5;213m"
X = "\033[0m"

colors = [PK, C, G, Y, P]

# ==========================================
#                 LESSONS
# ==========================================

lessons = [
    ("Basic Python Syntax", 50,
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
     "        print(i, j)")
]

# ==========================================
#             CODING CHALLENGES
# ==========================================

tasks = [
    ("Print Hello World!", 'print("Hello World!")'),

    ("Store a name in student_name.",
     'student_name = "Ana"'),

    ("Create integer age and decimal price.",
     "age = 18\nprice = 19.99"),

    ("Assign 3.14159 to PI.",
     "PI = 3.14159"),

    ("Calculate 2 + 3 * 4.",
     "result = 2 + 3 * 4"),

    ("Write an if and else statement.",
     'if age >= 18:\n'
     '    print("Adult")\n'
     'else:\n'
     '    print("Minor")'),

    ("Compare 10 and 5 using >.",
     "comparison = 10 > 5"),

    ("Use the logical and operator.",
     "allowed = age >= 18 and has_id"),

    ("Print numbers 1 to 5 using a for loop.",
     "for i in range(1, 6):\n"
     "    print(i)"),

    ("Create two nested for loops.",
     "for i in range(2):\n"
     "    for j in range(2):\n"
     "        print(i, j)")
]

# ==========================================
#           LEARNING RESOURCE LINKS
# ==========================================

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
    "https://www.youtube.com/watch?v=APWy6Pc83gE"
]

# Link for purchasing the complete course
all_lessons_link = "https://bit.ly/3WKLK4j"

# Program records
bought = set()
completed = set()
spent = 0

# ==========================================
#             HELPER FUNCTIONS
# ==========================================

def title(message):
    print(f"\n{P}{'=' * 54}")
    print(message.center(54))
    print(f"{'=' * 54}{X}\n")


def error(message):
    print(f"\n{R}[!] ERROR: {message}{X}\n")


def success(message):
    print(f"\n{G}[OK] {message}{X}\n")


def ask_choice(prompt, valid):
    while True:
        answer = input(f"{C}{prompt}{X}").strip().upper()

        if answer in valid:
            return answer

        error("Invalid choice. Please try again.")


# ==========================================
#               VIEW LESSON
# ==========================================

def show_lesson(i):
    name, price, description = lessons[i]
    color = colors[i % len(colors)]

    title(f"LESSON {i + 1}")
    print(f"{color}{name.upper()}{X}\n")

    for line in description.split("\n"):
        if (line.startswith("Example:")
                or line.startswith("Modulus Example:")):
            print(f"{C}{line}{X}")
        else:
            print(line)

    print(f"\n{C}LESSON PRICE: P{price:.2f}{X}\n")


# ==========================================
#             CODING PRACTICE
# ==========================================

def practice():
    while True:
        title("PRACTICE CODING LAB")

        for i, lesson in enumerate(lessons, 1):
            color = colors[(i - 1) % len(colors)]

            status = (
                "COMPLETED"
                if i - 1 in completed
                else "NOT COMPLETED"
            )

            print(
                f"{color}[{i:>2}] "
                f"{lesson[0]} - {status}{X}\n"
            )

        print(f"{G}YOUR SCORE: {len(completed) * 10}/100{X}")
        print(f"{R}[0] Return to Main Menu{X}\n")

        choice = ask_choice(
            "Choose a challenge: ",
            [str(n) for n in range(11)]
        )

        if choice == "0":
            return

        i = int(choice) - 1
        task, example = tasks[i]

        while True:
            title(f"CODING CHALLENGE {i + 1}")

            print(f"{Y}YOUR MISSION: {task}{X}\n")
            print("Write your Python code below.")
            print("Type DONE on a separate line to submit.")
            print("Use 4 spaces for indentation.\n")

            lines = []

            while True:
                line = input(">>> " if not lines else "... ")

                if line.strip().upper() == "DONE":
                    break

                lines.append(line)

            answer = "\n".join(lines)

            if not answer.strip():
                error("You did not enter any code.")
                continue

            print(f"\n{C}CHECKING YOUR CODE...{X}\n")

            try:
                submitted = ast.parse(answer)
                expected = ast.parse(example)

                valid = (
                    ast.dump(
                        submitted,
                        include_attributes=False
                    )
                    ==
                    ast.dump(
                        expected,
                        include_attributes=False
                    )
                )

                # Allow any nonempty string for Lesson 2.
                if i == 1 and len(submitted.body) == 1:
                    node = submitted.body[0]

                    valid = (
                        isinstance(node, ast.Assign)
                        and len(node.targets) == 1
                        and isinstance(
                            node.targets[0],
                            ast.Name
                        )
                        and node.targets[0].id == "student_name"
                        and isinstance(
                            node.value,
                            ast.Constant
                        )
                        and isinstance(
                            node.value.value,
                            str
                        )
                        and bool(node.value.value.strip())
                    )

            except SyntaxError as issue:
                error(f"Syntax error: {issue.msg}")
                valid = False

            if valid:
                if i not in completed:
                    completed.add(i)

                    success(
                        "CORRECT ANSWER! "
                        "YOU EARNED 10 POINTS!"
                    )

                else:
                    success(
                        "CORRECT! You already earned "
                        "points for this challenge."
                    )

                print(
                    f"{G}CURRENT SCORE: "
                    f"{len(completed) * 10}/100{X}\n"
                )

                input(
                    "Press ENTER to return to Coding Lab..."
                )

                break

            else:
                error("INCORRECT ANSWER!")

                if i == 0:
                    print(
                        f"{Y}Your Python syntax may be valid, "
                        "but the output must be exactly "
                        "'Hello World!'.{X}\n"
                    )

                print(f"{C}EXAMPLE CORRECT SOLUTION:{X}")
                print(example)
                print()

                print(
                    f"{Y}[1] Try This Challenge Again{X}"
                )
                print(
                    f"{C}[2] Return to Coding Lab Menu{X}\n"
                )

                retry = ask_choice(
                    "Choose an option: ",
                    ["1", "2"]
                )

                if retry == "2":
                    break


# ==========================================
#                  RECEIPT
# ==========================================

def receipt(cart, subtotal, discount, total, payment):
    title("OFFICIAL PURCHASE RECEIPT")

    print("              PYTHON LEARNING HUB")
    print("-" * 54)

    for i in cart:
        name, price, _ = lessons[i]
        print(f"{name:<42} P{price:.2f}")

    print("-" * 54)
    print(f"Subtotal:        P{subtotal:.2f}")
    print(
        f"Discount ({discount:.0%}): "
        f"   -P{subtotal - total:.2f}"
    )
    print(f"{C}TOTAL:           P{total:.2f}{X}")
    print(f"Cash Received:   P{payment:.2f}")
    print(
        f"{G}CHANGE:          "
        f"P{payment - total:.2f}{X}"
    )
    print("-" * 54)

    success("PAYMENT SUCCESSFUL!")
    print("Thank you for purchasing! Happy learning!\n")


# ==========================================
#              PURCHASE SYSTEM
# ==========================================

def purchase(indices, purchase_all=False):
    global spent

    cart = [
        i for i in indices
        if i not in bought
    ]

    if not cart:
        error("You already purchased these lessons.")
        return

    subtotal = sum(
        lessons[i][1]
        for i in cart
    )

    discount = (
        0.10 if subtotal >= 300
        else 0.05 if subtotal >= 150
        else 0
    )

    total = round(subtotal * (1 - discount), 2)

    title("SHOPPING CART")

    for i in cart:
        color = colors[i % len(colors)]

        print(
            f"{color}{lessons[i][0]}{X} "
            f"- P{lessons[i][1]:.2f}"
        )

    print(f"\nSubtotal: P{subtotal:.2f}")
    print(f"Discount: {discount:.0%}")
    print(f"{C}TOTAL TO PAY: P{total:.2f}{X}\n")

    confirmation = ask_choice(
        "Purchase now? (YES/NO): ",
        ["YES", "NO"]
    )

    if confirmation == "NO":
        print("\nPurchase cancelled.\n")
        return

    while True:
        try:
            payment = float(
                input("Enter payment: P")
            )

        except ValueError:
            error("Please enter a valid number.")
            continue

        if not math.isfinite(payment) or payment < 0:
            error("Invalid payment amount.")

        elif payment < total:
            error(
                f"Insufficient payment! "
                f"You need P{total - payment:.2f} more."
            )

            retry = ask_choice(
                "Try again? (YES/NO): ",
                ["YES", "NO"]
            )

            if retry == "NO":
                return

        else:
            break

    bought.update(cart)
    spent += total

    receipt(
        cart,
        subtotal,
        discount,
        total,
        payment
    )

    title("YOUR LEARNING RESOURCE")

    # Purchase All displays only the complete-course link.
    if purchase_all:
        print(f"{P}COMPLETE PYTHON COURSE:{X}")
        print(f"{C}{all_lessons_link}{X}\n")

    # Individual purchases display the lesson's own link.
    else:
        for i in cart:
            color = colors[i % len(colors)]
            print(f"{color}{lessons[i][0]}{X}")
            print(f"{C}{links[i]}{X}\n")


# ==========================================
#          DISCOVER THE WORLD OF PYTHON
# ==========================================

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


# ==========================================
#                MAIN MENU
# ==========================================

def main():
    title("WELCOME TO PYTHON LEARNING HUB")

    print("            LEARN • PRACTICE • GROW")

    while True:
        title("MAIN MENU")

        print(
            f"{PK}[1] Browse and Purchase Lessons{X}\n"
        )

        print(
            f"{C}[2] Discover the World of Python{X}\n"
        )

        print(
            f"{G}[3] View Purchased Lessons{X}\n"
        )

        print(
            f"{Y}[4] Practice Coding Lab{X}\n"
        )

        print(f"{R}[5] Exit{X}\n")

        option = ask_choice(
            "Choose an option (1-5): ",
            ["1", "2", "3", "4", "5"]
        )

        if option == "1":
            while True:
                title("AVAILABLE PYTHON LESSONS")

                for i, lesson in enumerate(lessons, 1):
                    color = colors[
                        (i - 1) % len(colors)
                    ]

                    print(
                        f"{color}[{i:>2}] "
                        f"{lesson[0]:<38}{X} "
                        f"P{lesson[1]:.2f}\n"
                    )

                print(
                    f"{G}[11] Purchase All Lessons{X}\n"
                )

                print(
                    f"{R}[ 0] Return to Main Menu{X}\n"
                )

                choice = ask_choice(
                    "Select a lesson: ",
                    [str(n) for n in range(12)]
                )

                if choice == "0":
                    break

                elif choice == "11":
                    purchase(
                        range(10),
                        purchase_all=True
                    )

                else:
                    i = int(choice) - 1

                    show_lesson(i)
                    purchase([i])

        elif option == "2":
            discover_python()

        elif option == "3":
            title("MY PURCHASED LESSONS")

            if not bought:
                print("No lessons purchased yet.\n")

            elif len(bought) == len(lessons):
                print(f"{P}COMPLETE PYTHON COURSE:{X}")
                print(f"{C}{all_lessons_link}{X}\n")

            else:
                for i in sorted(bought):
                    color = colors[i % len(colors)]

                    print(
                        f"{color}{lessons[i][0]}{X}"
                    )

                    print(f"{C}{links[i]}{X}\n")

            print(
                f"{G}TOTAL SPENT: "
                f"P{spent:.2f}{X}\n"
            )

        elif option == "4":
            practice()

        elif option == "5":
            title("THANK YOU FOR LEARNING!")

            print(
                "Keep practicing and never "
                "stop improving!"
            )

            break


if __name__ == "__main__":
    main()

