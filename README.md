import random

words = ["apple", "banana", "cherry", "grape", "orange"]
target_word = random.choice(words)
guessed_letters = []

while True:
    display_word = ''.join([letter if letter in guessed_letters else '_' for letter in target_word])
    print(display_word)

    if display_word == target_word:
        print(f"Congratulations! You guessed the word: {target_word}")
        break

    guess = input("Guess a letter: ").lower()

    if guess in guessed_letters:
        print("You already guessed that letter.")
    elif guess in target_word:
        print("Correct guess!")
        guessed_letters.append(guess)
    else:
        print("Incorrect guess. Try again.")
