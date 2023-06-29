---
title: CS Class Lesson 3
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
