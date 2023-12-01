# SoftwareDevPortfolio

Welcome to my portfolio, this will show some of the projects I have worked on this year

 ## Pig
 Code for pig:
 ```python
 import random

## Functions##
def turnSystem(iPlayerScore):
   iTurnNumb=0
   while iPlayerScore<100:
    print(f"Turn number: {iTurnNumb}\nCurrent score: {iPlayerScore}")
    while True:
        sHold=input("Would you like to hold? (Y/N)")
        if sHold.upper()!="Y" and sHold.upper()!="N":
           print("Please enter in a valid input")
        else:
           break
    if sHold.upper()=="Y":
       print(f"You have decided to hold. {iTurnNumb} will be added to your score")
       return iPlayerScore
    elif sHold.upper()=="N":
        iPlayerRoll=random.randint(1,diceCount)
        print(f"You have rolled: {iPlayerRoll}")
        if iPlayerRoll==1:
            print("You have rolled a 1, it is now the next player's turn")
            return iPlayerScore
        else:
            print("Your roll has been added to your score")
            iPlayerScore=iPlayerScore+iPlayerRoll
            iTurnNumb+=1
    if iPlayerScore>=100:
       return iPlayerScore


## Main ##
iPlayer1Score=0
iPlayer2Score=0
while True:
   diceType=int(input("What dice type do you want to use? \n1.d4\n2.d6\n3.d8\n4.d10\n5.d12\n6.d20"))
   if diceType<1 or diceType>6:
      print("Plese enter a valid input")
   else:
      break
diceNumbers=[4,6,8,10,12,20]
diceCount=diceNumbers[diceType-1]
sPlayer1Name=input("Enter player 1's name: ")
sPlayer2Name=input("Enter player 2's name: ")
i1Or2=random.randint(1,2)
while True:
    if i1Or2==1:
        print(f"It is {sPlayer1Name}s turn to play")
        iPlayer1Score=turnSystem(iPlayer1Score)
        if iPlayer1Score>=100:
           print(f"{sPlayer1Name} WON!!!")
           exit()
        else:
            i1Or2=2
    else:
        print(f"It is {sPlayer2Name}s turn to play")
        iPlayer2Score=turnSystem(iPlayer2Score)
        if iPlayer2Score>=100:
           print(f"{sPlayer2Name} WON!!!")
           exit()
        else:
            i1Or2=1
 ```