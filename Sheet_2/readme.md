#Sheet 2

##Contains all sheet 1 codes

1.Code (Name= Seif, Age=21)
~~~
Name = input("Enter your name: ") # Enter your name
Age = input("Enter your age: ") #Enter your age 
print ("Hello " + Name + " ,Your age is " + Age) #Print outputs with greetings
~~~
Output: `Hello Seif ,Your age is 21`


2.Code (Name= Seif, Age=21)
~~~
Name1 = input("Enter your name: ") # Enter your name
Age1 = int(input("Enter your age: ")) #Enter your age - as int data type
print ( Name1 * Age1) #Print your name x age
~~~
Output: `SeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeifSeif`


3.Code
~~~
file_name = "/home/user/projects/my_project/file.txt"
~~~
Didnt figure it out


4.Code
~~~
my_str = "    hello           world          "

my_str = my_str.strip()
my_str = my_str.title()
sub_strs = my_str.split(' ')
my_str = sub_strs[0].upper() + ', ' + "python".title() + '!'
print(my_str)
~~~
Output `HELLO, Python!`


5.Code (Name= Seif)
~~~
HW = "Hello world"
Name2 = input("Enter your name ") #Enter your name
HW = HW.replace("world", Name2) #Changes world with the typed name
print(HW)
~~~
Output `Hello Seif`


6.Code
~~~
H = "Hello"
find_o = H.find("o")
find_ao = ("o is in the ", find_o + 1 ,"index")
print (find_ao)
~~~
Output `('o is in the ', 5, 'index')`  I dont know why it has '' but i tried


7.Code 
~~~
Count_o = H.count("o")
print (Count_o)
~~~
Output `1`


8.Code
~~~
a = 1 / 3
b = 2 / 3
print(f"{a:.4f} + {b:.4f} = {a + b:.4f}")
print(f"0.1 + 0.2 = {0.1 + 0.2}")
print(chr(72) + chr(111) + chr(119) + chr(33))
~~~
Output `0.3333 + 0.6667 = 1.0000
0.1 + 0.2 = 0.30000000000000004
How!`


9.Code
~~~
s = "Hello world"
print(s[-5:] + ' ' + s[0:5])
~~~
Output `world Hello` Replaced the 2 words

#List

1 to 8 in the same code
~~~
List = [1,2,3] #Create list with 1,2,3
List.extend([5,6,7]) #Extend it with 5,6,7
List.insert(3,4) #Adds 3,4
List.pop() #Removes last element
List.remove(6) #Removes 6
List_3 = List.index(3) #Find 3
List.reverse() #Reverse it
List2 = List[:3] #Make new list from the first 3 index
~~~
I added "Print" after everyline to get the output which is 
`[1, 2, 3]
[1, 2, 3, 5, 6, 7]
[1, 2, 3, 4, 5, 6, 7]
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 4, 5]
2
[5, 4, 3, 2, 1]
[5, 4, 3]`

9. I dont know

10. I dont know
