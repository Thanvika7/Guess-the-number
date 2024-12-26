#Guess the number

    import random

    def guessing_game():
        print("😁 Welcome to the Number Guessing Game!")
        print("Choose your difficulty level:")
        print("1. Easy 😂   (Range: 1-10, Attempts: 5)")
        print("2. Medium 😨 (Range: 1-50, Attempts: 7)")
        print("3. Hard 😵   (Range: 1-100, Attempts: 10)")
    
    while True:
        try:
            choice = int(input("Enter your choice (1, 2, or 3): "))
            if choice == 1:
                range_end, attempts = 10, 5
                break
            elif choice == 2:
                range_end, attempts = 50, 7
                break
            elif choice == 3:
                range_end, attempts = 100, 10
                break
            else:
                print("Invalid choice! Please enter 1, 2, or 3.")
        except ValueError:
            print("Please enter a valid number.")

    secret_number = random.randint(1, range_end)
    print(f"\nGreat! You have chosen difficulty level with range 1-{range_end} and {attempts} attempts.")
    print("Let the game begin😏!")

    for attempt in range(attempts):
        try:
            guess = int(input(f"Attempt {attempt + 1}/{attempts}: Guess the number: "))
            if guess == secret_number:
                print("🎉🥳 Congratulations! You guessed the number correctly!")
                break
            elif guess < secret_number:
                print("Too low😒! Try again.")
            else:  
                print("Too high😤! Try again.")
        except ValueError:
            print("Please enter a valid number.")
    else:
        print(f"😢 Game Over! The number was {secret_number}.")

    print("Thanks for playing😊!")

    if __name__ == "__main__":
        guessing_game()

