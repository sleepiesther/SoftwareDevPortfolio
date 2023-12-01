```python
def encryption(word):
    reverse=word[::-1]
    encrypt=str.maketrans({"a":"0","e":"1","i":"2","o":"3","u":"4"})
    final=reverse.translate(encrypt)
    print(final+"aca")


encryption(input("Enter in a word you would like to encrypt\n"))
```

### Output 
![Karaca output example](images/Karaca%20screenshot.png)