```
def f(x):
    try:
        return float(x)
    except (TypeError,ValueError):
        return x
```
```
def f(x):
    try:
        return float(x)
    except :
        pass
    else:
        return x
    finally:
        pass
```

```
f=open(r"C:/users/48218/Desktop/plan.txt")
print(f.tell())
f.read(2)
print(f.tell())
f.seek(0)
f.read(2)
print(f.tell())
f.seek(0,2)
print(f.tell())
f.close()
```


```
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


