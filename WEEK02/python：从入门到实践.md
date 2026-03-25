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


```python
guestname=input("输入你的姓名：")
with open(r"C:/Users/48218/guest.txt","a") as object:
	lines=object.write(guestname+"\n")
while True:
	guestname=input("输入你的姓名（输入q退出）:  ")
	if guestname=="q":
		break
	print("你好！"+guestname+"!")
	with open(r"C:/Users/48218/guestbook.txt","a") as f:
		f.write(guestname+"\n")
whilr True:
	reason=input("你为什么喜欢编程？（输入q退出）：")
	if reason=="q":
		break
	with open(r"C:/Users/48218/reasons.txt","a") as f:
		f.write(reason+"\n")
```
