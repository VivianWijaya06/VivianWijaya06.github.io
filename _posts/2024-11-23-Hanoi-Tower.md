---
title: "Hanoi Tower"
date: 2024-11-23 00:00:00 +0800
categories: [Hanoi Tower]
tags: [Game]
image:
    path: HanoiTower.jpeg

---
# Hanoi Tower Game
```python
jumlah_cincin = input("Masukkan jumlah cincin (min 3, max 8): ")
n = int(jumlah_cincin)

if n < 3:
    n = 3
elif n > 8:
    n = 8

towerA = list(range(n, 0, -1)) 
towerB = []  
towerC = [] 

colors = [
    "\033[91m",  
    "\033[92m",  
    "\033[93m", 
    "\033[94m", 
    "\033[95m",  
    "\033[96m",  
    "\033[97m",  
    "\033[90m"   
]
reset_color = "\033[0m"  

def towers():
    for level in range(n, 0, -1):
        for tower in [towerA, towerB, towerC]:
            if len(tower) >= level:
                ring_size = tower[level - 1] 
                color = colors[ring_size - 1]  
                print(" " * (n - ring_size) + color + "[" + "=" * (ring_size * 2) + "]" + reset_color + " " * (n - ring_size), end="   ")  
            else:
                print(" " * (n + 1) + "|" + " " * (n + 1), end="   ") 
        print()
    print(" " * (n - 1) + "A" + " " * (n * 2 + 1) + "B" + " " * (n * 2 + 1) + "C")

while True:
    towers()  

    if len(towerB) == n or len(towerC) == n:
        print("\nYOU WINNNNNN!!!!!!")
        break

    source = input("Pindahkan cincin dari menara (A, B, C): ").upper()
    target = input("Pindahkan cincin ke menara (A, B, C): ").upper()

    if source == 'A':
        source_tower = towerA
    elif source == 'B':
        source_tower = towerB
    else:
        source_tower = towerC

    if target == 'A':
        target_tower = towerA
    elif target == 'B':
        target_tower = towerB
    else:
        target_tower = towerC

    if len(source_tower) == 0:
        print(f"Menara {source} tidak ada cincin yang dapat dipindahkan")
    elif len(target_tower) > 0 and source_tower[-1] > target_tower[-1]:
        print("Ukuran cincin yang dipindahkan lebih besar.")
    else:
        target_tower.append(source_tower.pop())
```
![Desktop View](hanoitower.png)
