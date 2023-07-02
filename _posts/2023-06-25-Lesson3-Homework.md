---
title: CS Class Lessons
date: 2023-06-24 19:00:00 -0500
categories: [School, Class]
tags: [class]     # TAG names should always be lowercase
---

# Lesson 3 - Text Based Adventure Game & If Statements

## Homework

- Change adventure game to have for loops and while loops. Make a separate file for each version!
- Keep practicing your If-Statements. Change up your if statements in your game, or add different questions to ask. (E.g., Instead of asking how old someone is, ask a true/false question!)
- No DMOJ homework questions this week! 

## Code

```
player_health = int(input())
player_gold = int(input())
player_damage = int(input())

enemy_health = int(input())
enemy_gold = int(input())
enemy_damage = int(input())

name = input("Enter your name: ")
age = int(input("Enter your age: "))

if (age > 12):
    print("Player attacks!")
    enemy_health -= player_damage
    print("Enemy health is now:", enemy_health)

    print("Enemy attacks!")
    player_health -= enemy_damage
    print("Player health is now:", player_health)

    print("Player attacks!")
    enemy_health -= player_damage
    print("Enemy health is now:", enemy_health)

    print("Player attacks!")
    player_health -= enemy_damage
    print("Player health is now:", player_health)

    if player_health > enemy_health:
        print("YOU WIN!")
    elif player_health == enemy_health:
        print("You tie and both walk away in defeat")
    else:
        print("You lose")

else:
    print("you are not old enough")
    quit()

```

# Lesson 4 - Loops

## Homework

- Have fun doing DMOJ: https://dmoj.ca/problem/valentines19j1 (For this question, it's just a combination of using a loop and some if statements. The first number is just how many numbers you have to loop through. So for example, if the first number is 5, you have check 5 numbers and print out their rank). Here is some starter code for the DMOJ question:

```
number_of_ranks = int(input())

for i in range(number_of_ranks):
  # do if statements and print out their rank!

```

- If-Statement Practice Test Problems
- Try this one: https://dmoj.ca/problem/ccc21j2
