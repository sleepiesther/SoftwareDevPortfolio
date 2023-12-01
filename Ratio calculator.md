
A program to find the simplest ratio of two numbers without using the in-built function

Code for the ratio calcuator:
```python
##Function##

def ratiocalculator(numb1,numb2):
    numb1fact=[]
    numb2fact=[]
    commonfact=[]
    
    for x in range(1,numb1+1):
        if numb1%x==0:
            numb1fact.append(x)
    
    for x in range(1,numb2+1):
        if numb2%x==0:
            numb2fact.append(x)
    
    for x in range(0,len(numb1fact)):
        for y in range(0,len(numb2fact)):
            if numb1fact[x]==numb2fact[y]:
                commonfact.append(numb1fact[x])
    
    hcf=commonfact[-1]
    
    if len(commonfact)==1:
        return False
    
    result=f"{int(numb1/hcf)}:{int(numb2/hcf)}"
    return result

##Main##

while True:
    try:
        input1=int(input("Enter the first number:"))
        if input1<=0:
            print("Please enter in a number above 0")
        else:
            break   
    except:
        print("Please enter in a valid input")

while True:    
    try:
        input2=int(input("Enter the second number:"))
        if input2<=0:
            print("Please enter in a number above 0")
        else:
            break   
    except:
        print("Please enter in a valid input")        

ratio=ratiocalculator(input1,input2)

if ratio==False:
    print("The ratio entered is the simplest possible ratio of those two numbers")
else:
    print("The simplest possible ratio is", ratio)
```

### Output

[Output of the ratio calculator](images/Ratio%20screenshot.png)