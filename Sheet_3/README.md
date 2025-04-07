Code 1: (Using time 20 and 10
```
print("Type the time for the 10km run, type 0 to end")
number = 0
time = 0
time_input = float(input("Enter time you ran for 10km"))
while time_input!=0:
 number += 1
 time = time_input + time
 time_input=float(input("Enter time you ran for 10km"))
else:
 print("Your average time is " , time / number)
```
`Enter time you ran for 10km: 20
Enter time you ran for 10km: 10
Enter time you ran for 10km: 0
Your average time is  15`

Code 2:
```
```

Code 3:
```
s = "Tom Jerry Harry"
words = s.split()
words.sort()
s = ", ".join(words)
print(s)
```
`Harry, Jerry, Tom`

Code 4:
```
sequence = [10, 20, 30, 40, 50, 60]
even_sum = 0
odd_sum = 0
for i in range(len(sequence)):
    if i % 2 == 0:
        even_sum = even_sum + sequence[i]
    else:
        odd_sum = odd_sum + sequence[i]
print("Even index sum:", even_sum)
print("Odd index sum:", odd_sum)
```
`Even index sum: 90
Odd index sum: 120`

Code 5:
```
users = {'user1': 'password1', 'user2': 'password2'} 
name_input = input("Type your username: ")
password_input = input("Type your Password: ")
if name_input in users and users[name_input] == password_input:
    print("Logged in")
else:
    print("Username or password is incorrect")
```
Output if its right `Username: user1
Password: password1
Logged in`

Output if its wrong `Username: 2
Password: 3
Username or password is incorrect`


Code 6:
```
d1 = {'a': 1}
d2 = {'a': 2}
d3 = {'b': 3}
all_dicts = [d1, d2, d3]
fin_di = {}
for i in all_dicts:
    fin_di.update(i)
print(fin_di)
```
`{'a': 2, 'b': 3}`

Code 7:
```
numbers1=[10, 20, 30]
numbers2=[10, 20, 30, 10, 20, 30]
print(len(set(numbers1)))
print(len(set(numbers2)))
```
`3
3`
