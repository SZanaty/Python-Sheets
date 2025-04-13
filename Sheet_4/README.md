Code 1:
```
import random
def generate_password(length, chars):
 password="".join(random.choice(chars) for x in range(length))
 return password
password=generate_password(8, "abcde")
print(password)
```
Output: `cbbbadce`


Code 2:
```
for c in range(8):
    print(chr (c + ord('0')))
```
Output: `01234567`
    

Code 3:
```
Names=["Seif","Sedfy","Zain","Saif","Amir"]
s=set()
for Names in Names:
 for Letters in Names:
  s.add(Letters)
{Letter for Names in Names for Letter in Names}
print(s)
```
Output: `{'S', 'y', 'd', 'A', 'r', 'a', 'i', 'e', 'Z', 'f', 'm', 'n'}`
 

Code 4:
```
def func(*args):
 return sum(args) / len(args)
print(func(1,2,3,4,5,6))
```
Output: `3.5`


#Code 5:
```
def key(equation, **var):
 for key, value in var.items():
  equation=equation.replace(key, str (value))
 return(equation)
res=key("a + b = c", a=1, b=2, c=3)
print(res)
```
Output: `1 + 2 = 3`
