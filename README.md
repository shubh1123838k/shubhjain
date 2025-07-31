# shubhjain
import random as rn

elements = {1: "🪨", 2: "🧻", 3: "✂️"}
score = 0  # global score counter

def play_game():
    global score
    print("\n########################")
    print("Welcome To ROCK Paper Scissors Game!!!")
    print("1:🪨  2:🧻  3:✂️")

    try:
        x = int(input("Enter Your Choice (1/2/3): "))
        if x not in elements:
            print("Invalid choice! Choose 1, 2, or 3 only.")
            return
    except ValueError:
        print("Bruhhh type a number 😑")
        return

    y = rn.randint(1, 3)  # Computer's choice

    print(f"You chose {elements[x]}")
    print(f"Computer chose {elements[y]}")

    if x == y:
        print("It's a Tie! 🤝")
    elif (x == 1 and y == 3) or (x == 2 and y == 1) or (x == 3 and y == 2):
        print("You Won! 🎉")
        score += 1
    else:
        print("Computer Won! 😈")

def replay():
    while True:
        play_game()
        again = input("\nWanna play again? (y/n): ").lower()
        if again != "y":
            print(f"\nYour final score: {score} ✨")
            print("Thanks for playing, main character 💖👑")
            break

replay()
