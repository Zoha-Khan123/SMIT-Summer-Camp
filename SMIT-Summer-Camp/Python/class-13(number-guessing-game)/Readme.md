# 📘 Lecture 13: Number Guessing Game
## 🎮 Your First Python Game!

Welcome to Python Summer Camp Class 13!

In this lecture, we will create our **first Python game** - a Number Guessing Game!

In **Class 12**, we learned about **Modules** - what they are and how to use them. Now we will use the `random` module to create an interactive game!

---

# 🎮 Game Description

## How the Game Works:

1. Computer randomly selects a number between 1 and 100
2. Player tries to guess the number
3. Computer gives hints:
   - "Too High!" if guess is higher
   - "Too Low!" if guess is lower
   - "Correct!" when player guesses right
4. Game shows how many attempts it took
5. Player can play again if they want

---

# 📦 Using the Random Module

In **Class 12**, we learned about the `random` module. Let's use it in our game!

## Quick Recap

```python
import random

# Generate random number between 1 and 100
number = random.randint(1, 100)
print(number)
```

This is exactly what we need for our game - the computer will pick a random number and the player will try to guess it!

---

# 🎯 Game Flow Diagram

```
    START
      ↓
   Welcome Message
      ↓
   Computer Picks Random Number
      ↓
   Player Guesses ←─────────┐
      ↓                     │
   Check Guess              │
      ↓                     │
   Is Correct?              │
    /    \                  │
  NO     YES                │
   │      ↓                 │
   │   Show Success         │
   │      ↓                 │
   │   Play Again?          │
   │    /    \              │
   │  YES    NO             │
   │   │      │             │
   └───┘      ↓             │
         Give Hint          │
              └─────────────┘
              
              END
```

---

# 📝 Complete Game Code

```python
import random

def welcome():
    """Display welcome message"""
    print("=" * 50)
    print("🎮 Welcome to Number Guessing Game! 🎮")
    print("=" * 50)
    print("I'm thinking of a number between 1 and 100.")
    print("Can you guess it?")
    print("=" * 50)

def play_game():
    """Main game logic"""
    # Computer selects a random number (using random module from Class 12)
    secret_number = random.randint(1, 100)
    
    attempts = 0
    guessed = False
    
    while not guessed:
        # Get player's guess
        guess = int(input("\nEnter your guess: "))
        attempts += 1
        
        # Check the guess
        if guess < secret_number:
            print("📉 Too Low! Try a higher number.")
        elif guess > secret_number:
            print("📈 Too High! Try a lower number.")
        else:
            print(f"🎉 Congratulations! You guessed it in {attempts} attempts!")
            guessed = True

def play_again():
    """Ask if player wants to play again"""
    choice = input("\nDo you want to play again? (yes/no): ").lower()
    return choice == "yes" or choice == "y"

def main():
    """Main program"""
    welcome()
    
    playing = True
    
    while playing:
        play_game()
        playing = play_again()
    
    print("\n👋 Thanks for playing! Goodbye!")

# Run the game
if __name__ == "__main__":
    main()
```

---

# 💡 How to Run the Game

1. Create a new file: `number_game.py`
2. Copy the complete code
3. Save the file
4. Run in VS Code or terminal:
   ```bash
   python number_game.py
   ```
5. Play the game!

---

# 🎮 Sample Game Play

```
==================================================
🎮 Welcome to Number Guessing Game! 🎮
==================================================
I'm thinking of a number between 1 and 100.
Can you guess it?
==================================================

Enter your guess: 50
📈 Too High! Try a lower number.

Enter your guess: 25
📉 Too Low! Try a higher number.

Enter your guess: 37
📉 Too Low! Try a higher number.

Enter your guess: 43
📈 Too High! Try a lower number.

Enter your guess: 40
🎉 Congratulations! You guessed it in 5 attempts!

Do you want to play again? (yes/no): no

👋 Thanks for playing! Goodbye!
```

---

# 🎓 Concepts Used in This Game

| Concept | Where Used | Learned In |
|---------|-----------|-----------|
| **Import Statement** | `import random` | Class 12 |
| **Random Module** | `random.randint(1, 100)` | Class 12 |
| **Functions** | `welcome()`, `play_game()`, `main()` | Class 11 |
| **Variables** | `secret_number`, `attempts`, `guessed` | Class 03 |
| **Input** | `int(input())` | Class 05 |
| **Type Conversion** | `int()` | Class 05 |
| **Conditionals** | `if-elif-else` | Class 07 |
| **While Loop** | Game loop | Class 10 |
| **Boolean Values** | `guessed = True/False` | Class 03 |
| **Return Statement** | Functions returning values | Class 11 |
| **String Formatting** | f-strings | Class 06 |
| **Operators** | Comparison operators | Class 04 |

---

# 🔄 Code Explanation

## Step 1: Import Module
```python
import random
```
We import the `random` module (learned in Class 12) to generate random numbers.

## Step 2: Welcome Function
```python
def welcome():
    print("=" * 50)
    print("🎮 Welcome to Number Guessing Game! 🎮")
    # ... more print statements
```
Displays a welcome message to the player.

## Step 3: Game Logic Function
```python
def play_game():
    secret_number = random.randint(1, 100)  # Random number
    attempts = 0
    guessed = False
    
    while not guessed:
        guess = int(input("\nEnter your guess: "))
        attempts += 1
        # Check and give hints
```
Main game logic - generates random number and handles guessing.

## Step 4: Play Again Function
```python
def play_again():
    choice = input("\nDo you want to play again? (yes/no): ").lower()
    return choice == "yes" or choice == "y"
```
Asks if player wants another round.

## Step 5: Main Function
```python
def main():
    welcome()
    playing = True
    while playing:
        play_game()
        playing = play_again()
```
Controls the overall game flow.

---

# 🏆 Challenge: Improve the Game

Try adding these features:

## Level 1: Easy
1. **Count total games played**
   ```python
   total_games = 0
   ```

2. **Show best score** (minimum attempts)
   ```python
   best_score = float('inf')
   ```

## Level 2: Medium
3. **Add difficulty levels**
   - Easy: 1-50
   - Medium: 1-100
   - Hard: 1-500

4. **Limit maximum attempts**
   - Give only 7 tries
   - Game over if attempts exceed limit

5. **Better hints**
   - "Very close!" if within 5
   - "Getting warm!" if within 10
   - "Cold!" if far away

---

# 📊 Class Activity (1 Hour Plan)

**0-10 mins:** Review random module from Class 12  
**10-20 mins:** Explain game logic and flow  
**20-40 mins:** Code the game step by step together  
**40-50 mins:** Run and test the game  
**50-60 mins:** Students try the challenges  

---

# 🎯 Learning Outcomes

After this lecture, students can:

✅ Apply random module in real programs  
✅ Create complete interactive programs  
✅ Use multiple functions together  
✅ Handle user input and validation  
✅ Implement game logic with loops and conditions  
✅ Build confidence in programming  

---

**Happy Gaming! 🎮✨**
