<div align='center'>
  
# Python List Methods
</div>

> [!TIP]
> Memorise the Sequence

> append, extend, insert, remove, pop\
> pop, clear, index, count\
> count, sort, sorted, reverse, reversed\
> copy, len, min, max, sum, in, listComprehension\
> all, any ,enumerate, zip, map, filter, del\
> *, +=

<div align='center'>
  
# Examples
</div>

<details>

  <summary>Append, Extend, Insert, Remove & Pop</summary>
  
## 1. `Append`
<div align = 'center'>
  
|***Defination***|The append() method adds a single element to the end of a list.|
|--:|:--|
|***Syntax***|list.append(element)|
|***Arguments***|element: (Required) — The item to be added to the list. It can be of any data type (e.g., int, str, list, object).|
</div>

### ***Examples***:
```python
daily_tasks = ["Exercise", "Study"]
daily_tasks.append("Meditation")
print(daily_tasks) #['Exercise', 'Study', 'Meditation']
```
```python
student_data = []
student_data.append({"name": "Kiran", "score": 95})
print(student_data) # [{'name': 'Kiran', 'score': 95}]
```
```python
playlist = ["Chill Vibes", "Workout Beats"]
playlist.append(["Lo-Fi", "Jazz"])
print(playlist) # ['Chill Vibes', 'Workout Beats', ['Lo-Fi', 'Jazz']]
```

## 2. `Extend()`
<div align = 'center'>
  
|***Defination***|The extend() method adds all elements of an iterable (list, tuple, set, etc.) to the end of the current list.|
|--:|:--|
|***Syntax***|list1.extend(iterable)|
|***Arguments***|iterable: Required. Any iterable (like list, tuple, set, or string) whose elements will be added to the list.|
</div>

### ***Examples***:
```python
todo_list = ["exercise", "read"]
new_tasks = ["code", "review", "sleep"]
todo_list.extend(new_tasks)
print(todo_list) # ['exercise', 'read', 'code', 'review', 'sleep']
```
```python
letters = ['A', 'B']
more_letters = "CDE"
letters.extend(more_letters)
print(letters) # ['A', 'B', 'C', 'D', 'E']
```
```python
sensor_data = [23.5, 24.1]
new_readings = (24.3, 24.0, 23.9)
sensor_data.extend(new_readings)
print(sensor_data) # [23.5, 24.1, 24.3, 24.0, 23.9]
```

## 3. `Insert()`
<div align = 'center'>
  
|***Defination***|The insert() method inserts an element at a specified index in a list. It does not replace any element but shifts existing elements to the right.|
|--:|:--|
|***Syntax***|list.insert(index, element)|
|***Arguments***|index (int) – The position where the element should be inserted.</br>element – The item to insert into the list (can be any data type: number, string, object, etc.).|
</div>

### ***Examples***:
```python
colors = ["red", "blue", "green"]
colors.insert(1, "turquoise")
print(colors) # ['red', 'turquoise', 'blue', 'green']
```
```python
tasks = ["wake up", "brush teeth", "start work"]
tasks.insert(2, "meditate")
print(tasks) # ['wake up', 'brush teeth', 'meditate', 'start work']
```
```python
route = [(0, 0), (1, 1), (3, 3)]
route.insert(2, (2, 2))
print(route) # [(0, 0), (1, 1), (2, 2), (3, 3)]
```

## 4. `Remove()`
<div align = 'center'>
  
|***Defination***|The remove() method removes the first matching element (by value) from the list. If the value is not found, it raises a ValueError.|
|--:|:--|
|***Syntax***|	list.remove(element)|
|***Arguments***|element – The item to be removed from the list. Must exist in the list, or an error will be thrown.|
</div>

### ***Examples***:
```python
fruits = ["apple", "banana", "cherry", "banana"]
fruits.remove("banana")
print(fruits) # ['apple', 'cherry', 'banana']
```
```python
numbers = [10, 20, 30, 40]
numbers.remove(30)
print(numbers) # [10, 20, 40]
```
```python
tasks = ["email", "meeting", "lunch"]
tasks.remove("email")
print(tasks) # ['meeting', 'lunch']
```

## 5. `Pop()`
<div align = 'center'>
  
|***Defination***|The pop() method removes and returns an element from a list at the given index. If no index is specified, it removes and returns the last item in the list.|
|--:|:--|
|***Syntax***|list.pop(index)|
|***Arguments***|index (optional, int) – The position of the element to remove and return. If omitted, the last element is removed.</br>Return Value – The removed element.|
</div>

### ***Examples***:
```python
fruits = ["apple", "banana", "cherry"]
last_fruit = fruits.pop()
print(last_fruit)   # cherry
print(fruits)       # ['apple', 'banana']
```
```python
numbers = [10, 20, 30, 40, 50]
second_item = numbers.pop(1)
print(second_item)  # 20
print(numbers)      # [10, 30, 40, 50]
```
```python
stack = ["first", "second", "third"]
removed = stack.pop(-2)
print(removed)      # second
print(stack)        # ['first', 'third']
```
</div>
</details>
  
<details>
  <summary>Clear, Index, Count, Sort, Sorted</summary>

  ## 5. `Pop()`
<div align = 'center'>
  
|***Defination***|The pop() method removes and returns an element from a list at the given index. If no index is specified, it removes and returns the last item in the list.|
|--:|:--|
|***Syntax***|list.pop(index)|
|***Arguments***|index (optional, int) – The position of the element to remove and return. If omitted, the last element is removed.</br>Return Value – The removed element.|
</div>

### ***Examples***:
```python
fruits = ["apple", "banana", "cherry"]
last_fruit = fruits.pop()
print(last_fruit)   # cherry
print(fruits)       # ['apple', 'banana']
```
```python
numbers = [10, 20, 30, 40, 50]
second_item = numbers.pop(1)
print(second_item)  # 20
print(numbers)      # [10, 30, 40, 50]
```
```python
stack = ["first", "second", "third"]
removed = stack.pop(-2)
print(removed)      # second
print(stack)        # ['first', 'third']
```
</details>
