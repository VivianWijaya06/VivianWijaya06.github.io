---
title: "Tic Tac Toe"
date: 2024-10-31 00:00:00 +0800
categories: [Tic Toe Toe]
tags: [Game]
image:
    path: TicTacToe.jpeg
---
# Tic Tac Toe Game
```python
print("TICTACTOE")
print("=========")
board = {1:"1",2:"2",3:"3",
         4:"4",5:"5",6:"6",
         7:"7",8:"8",9:"9"}

def tampilkanBoard():
    print()
    print ("|", board[1], "|", board[2], "|", board[3], "|" )
    print("------------")
    print ("|", board[4], "|", board[5], "|", board[6], "|" )
    print("------------")
    print ("|", board[7], "|", board[8], "|", board[9], "|" )

def menangKalah(player):
#kiri ke kanan/kanan ke kiri
    if board[1]==board[2] and board[1]==board[3] and board[1] == player:
        return True
    if board[4]==board[5] and board[4]==board[6] and board[4] == player:
        return True
    if board[7]==board[8] and board[7]==board[9] and board[7] == player:
        return True
#atas ke bawah/bawah ke atas
    if board[1]==board[4] and board[1]==board[7] and board[1] == player:
        return True
    if board[2]==board[5] and board[2]==board[8] and board[2] == player:
        return True
    if board[3]==board[6] and board[3]==board[9] and board[3] == player:
        return True
#diagonal 
    if board[1]==board[5] and board[1]==board[9] and board[1] == player:
        return True
    if board[3]==board[5] and board[3]==board[7] and board[3] == player:
        return True

def insert(player, posisi, nama_player):
    board[posisi]= player
    tampilkanBoard()
    if menangKalah(player):
        print(nama_player,"WIN!!!!")
        quit()
tampilkanBoard()

player1 = "X"
player2 = "O"

while True:
    posisi = int(input("Player 1: "))
    insert(player1, posisi, "Player 1")
    posisi = int(input("Player 2: "))
    insert(player2, posisi, "Player 2")
```
![Desktop View](tictactoe.png)
