##Code 1:
```
list1=list(range(6))
print(list1)
list2=list(range(4,11,2))
print(list2)
list3=list(range(10,5,-1))
print(list3)
list4=list(range(10,-11,-5))
print(list4)
```
Output:`[0, 1, 2, 3, 4, 5]
[4, 6, 8, 10]
[10, 9, 8, 7, 6]
[10, 5, 0, -5, -10]`


Code 2:
```
x_coor = [1, 2, 3, 4, 5]
y_coor = [2, 4, 6, 8, 10]
z_coor = [0, -1, -2, -3, -4]
points = [(x, y, z) for x, y, z in zip(x_coor, y_coor, z_coor)]
```
Output:`[(1, 2, 0), (2, 4, -1), (3, 6, -2), (4, 8, -3), (5, 10, -4)]`


Code 3:
```
def apply(lst, fn):
    result = []
    for elem in lst:
        result.append(fn(elem))
    return result
def add_1(num):
    return num + 1
r = apply([1, 2, 3], add_1)
print(r)
```
Output:`[2, 3, 4]`

Code 3 with 'map':
