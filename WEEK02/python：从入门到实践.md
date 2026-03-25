```python
with open("pi_million_digits.txt") as object:
  lines=object.readlines()
pi_string=""
for line in lines:
  pi_string+=line.strip()
```


```python
with open("pi_million_digits.txt") as object:
  lines=object.readlines()
pi_string=""
for line in lines:
  pi_string+=line.strip()
birthday=input("请输入你的生日")
if birthday in pi_string:
  print("你的生日出现在圆周率前100万数字里")
else:
  print("你的生日未出现在圆周率前100万数字里")
```
