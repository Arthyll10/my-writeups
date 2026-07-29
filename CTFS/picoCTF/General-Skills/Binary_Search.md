# Binary Search — picoCTF 2024

- **Category:** General Skills
- **Difficulty:** Easy
- **Author:** Jeffery John
- **Event:** picoCTF 2024
- **Challenge Link:** [CyLab Academy / picoCTF Challenge](https://learn.cylabacademy.org/library/442?page=1)
- **Flag:** `picoCTF{g00d_gu355_1597707f}`

---

## 💡 What is this challenge about?

Imagine playing a guessing game with a friend who picks a secret number between **1 and 1,000**. Every time you guess, they only tell you **"Higher"** or **"Lower"**. You have to find the exact number, but you only have **10 tries**.

If you guess randomly or count up one by one ($1, 2, 3...$), you will run out of tries quickly. 

Instead, the trick is to **cut the choices in half every single time**. This method is a well-known computer concept called **Binary Search**.

---

## 🛠️ The Strategy: Divide and Conquer

1. Start right in the middle (**500**).
2. If the game says **"Higher"**, you immediately throw away all numbers from 1 to 500.
3. If the game says **"Lower"**, you throw away everything above your guess.
4. Pick a new number near the middle of what's left and repeat!

---

## 🎯 Walkthrough & Solving the Game

Here is exactly how I solved it in **6 guesses**:

1. **Guess 1: `500`**
   - **Response:** *Higher!*
   - **What it means:** The secret number is somewhere between **501 and 1,000**. I just eliminated half of all possibilities!

2. **Guess 2: `800`**
   - **Response:** *Lower!*
   - **What it means:** The secret number is between **501 and 799**.

3. **Guess 3: `600`**
   - **Response:** *Lower!*
   - **What it means:** Now the range is down to **501 to 599** (less than 100 choices left!).

4. **Guess 4: `550`**
   - **Response:** *Higher!*
   - **What it means:** The number is between **551 and 599**.

5. **Guess 5: `570`**
   - **Response:** *Higher!*
   - **What it means:** Down to between **571 and 599** (only 29 possibilities left!).

6. **Guess 6: `580`**
   - **Response:** *Correct!*
   - **Result:** The server printed out the flag!

---

## 🚩 Flag

```text
picoCTF{g00d_gu355_1597707f}