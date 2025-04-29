from sys import exit
import random
import time

score = 100
total_score_to_win = 200
total_score_to_lose = 0
choose_arms = ["magic wand", "sword", "gun"]
choose_enemy = ["troll", "giants and their king"]
choose_enemy_end = random.choice(choose_enemy)


# First function to start(house)
def house():
    global score
    # to use score in and out of the function
    print("\nYou approach the door of the house.")
    time.sleep(1)
    print("You are about to knock when the door opens and ",
          f"out steps a {choose_enemy_end}!")
    time.sleep(1)
    print(f"Eep! This is the {choose_enemy_end}'s house!")
    time.sleep(1)
    print(f"You are lucky the {choose_enemy_end} is not here,")
    print("but be careful, it may come back.")
    time.sleep(1)
    print("You should go somewhere to be safe & prepare to fight.")
    time.sleep(1)
    print("Enter 1 to go to the field.")
    time.sleep(1)
    print("Enter 2 to go to the cave.")
    choose2 = input("(Please enter 1 or 2): ").strip().lower()
    while True:
        try:
            if choose2 == "1" or choose2 == "number 1" or choose2 == "field":
                field()
            elif choose2 == "2" or choose2 == "number 2" or choose2 == "cave":
                cave()
                score -= 20
                print("You lost 20 points for wasting time in the cave!")
                time.sleep(1)
                print("You should go to the field now.")
                field()
            else:
                print("Invalid choice. Try again.")
        except ValueError:
            print("Invalid input. Please enter a number.")


# Second function(cave)
def cave():
    global score
    print("\nYou approach the cave.")
    time.sleep(1)
    print("It is dark and spooky.")
    time.sleep(1)
    print("You've been here before,and gotten all the good stuff.")
    time.sleep(1)
    print("It's just an empty cave now.")
    time.sleep(1)

    while True:
        try:
            print("Are you ready to go to the field ")
            time.sleep(1)
            ready = input("Enter 'yes' or 'no': ").strip().lower()
            if ready == "yes":
                print("The fight will start now!")
                time.sleep(1)
                field()
                break
            elif ready == "no":
                print("You hesitate.",
                      " Maybe you should prepare more.")
                time.sleep(1)
                print("Would you go to the house or stay cave? ")
                choice = input("(house/cave): \n").strip().lower()
                if choice == "house":
                    house()
                    break
                elif choice == "cave":
                    cave()
                    break
                else:
                    print("Invalid choice. Returning to the cave.")
            else:
                print("Invalid input. Please enter 'yes' or 'no'.")
        except ValueError:
            print("Invalid input. Please try again.")


# Third function(field)
def field():
    global score
    print("\nYou go to the field.")
    time.sleep(1)
    print(f"Here is the fight between you and the {choose_enemy_end}!")
    time.sleep(1)
    print("Choose your weapon:")
    for i, arm in enumerate(choose_arms, 1):
        print(f"{i}. {arm}")

    while True:
        try:
            print("Enter the number of your weapon")
            weapon_choice = input("or the weapon name: \n").strip().lower()
            if weapon_choice in ["1", "2", "3"]:
                weapon = choose_arms[int(weapon_choice) - 1]
                print(f"You chose the {weapon}!")
                time.sleep(1)
                fight(weapon)
                break
            elif weapon_choice in [arm.lower() for arm in choose_arms]:
                weapon = weapon_choice
                print(f"You chose the {weapon}!")
                time.sleep(1)
                fight(weapon)
                break
            else:
                print("Invalid choice. Try again.")
        except ValueError:
            print("Invalid input. Please enter a valid number or weapon name.")

# Fourth function(weapon)


def fight(weapon):
    global score
    # to use score in and out of the function
    print(f"\nYou bravely face the {choose_enemy_end} with your {weapon}!")
    time.sleep(1)
    # Random outcome for fun
    outcome = random.choice(["win", "lose"])
    if outcome == "win":
        print(f"You defeated the {choose_enemy_end}! Congratulations!")
        score += 50
        print(f"Your score is now {score}.")
        if score >= total_score_to_win:
            print("You reached the winning score! YOU WIN THE GAME!")
            play_again()
        else:
            print("Do you want to continue exploring?")
            time.sleep(1)
            print("Enter 'yes' to continue .")
            time.sleep(1)
            print("Enter 'no' to leave the game.")
            next_step = input("Enter any choice do you want").strip().lower()
            if next_step == "yes":
                start_game()
            else:
                print("Thank you for playing! Goodbye.")
                exit()
    else:
        print(f"The {choose_enemy_end} was too strong. You lost the fight.")
        score -= 50
        print(f"Your score is now {score}.")
        if score <= total_score_to_lose:
            print("You reached the losing score. GAME OVER!")
            play_again()
        else:
            print("Do you want to try again?")
            time.sleep(1)
            print("Enter 'yes' to try again.")
            time.sleep(1)
            print("Enter 'no' to leave the game.")
            try_again = input("Enter any choice do you want  ").strip().lower()
            if try_again == "yes":
                start_game()
            else:
                print("Thank you for playing! Goodbye.")
                exit()


# 5Th function(play_again)
def play_again():
    answer = input("Would you like to play again? (yes/no): ").strip().lower()
    if answer == "yes":
        global score, choose_enemy_end
        # to use score in and out of the function
        score = 100
        choose_enemy_end = random.choice(choose_enemy)
        start_game()
    else:
        print("Thank you for playing! Goodbye.")
        exit()


# 6Th function(start_game)
def start_game():
    while True:
        try:
            print("\nYou find yourself standing in an open field.")
            time.sleep(1)
            print("filled with grass and yellow wildflowers.")
            time.sleep(1)
            print("In front of you is a house.")
            time.sleep(1)
            print("To your right is a dark cave.")
            time.sleep(1)
            print("Enter 1 to knock on the door of the house.")
            time.sleep(1)
            print("Enter 2 to peer into the cave\n")
            time.sleep(1)
            print("What would you like to do?")
            time.sleep(2)
            choice = input("(Please enter 1 or 2): ").strip().lower()
            if choice in ("1", "number 1", "house"):
                house()
                break
            elif choice in ("2", "number 2", "cave"):
                cave()
                break
            else:
                print("Invalid choice. Try again.")
        except ValueError:
            print("An error occurred. Please try again.")


# Run the game
start_game()
