# blak and ruff
在根目录下运行：
```bash
ruff check .
```

检查代码错误及规范


```bash
ruff check . --fix
```


```bash
black .
```
自动把你所有的 .py 文件重新排版（比如调整换行、引号、空格），变成符合 PEP 8 标准



# kaggle chapter2
help()可以是交互式，在cmd里输入>python，然后进入>>>界面，输入help(),就可以开始对话


文档字符串是一个三引号字符串（可能跨多行），它紧跟在函数头部之后。当我们对函数调用help()时，会显示文档字符串。


```python
def mod(x):
  return x^2
print(max(100, 51, 4),key=mod,sep="\n")
```

```python
def greet(who="Carson"):
  print("Hello," ,who)
greet()
greet(who="Edith")
greet("Sebitian")
#Hello,Carson
#Hello,Edith
#Hello,Sebitian
```


#### list
pop  
删除指定元素并返回删除值，若未指定泽尔删除最后一个值并返回值  
实现栈（LIFO）或需要获取被删元素的场景
remove  
删除第一次出现的指定值，不返回值  

#### tuple
tuple常用于返回多结果输出函数  
```python
x=0.125
x.as_integer_ratio()
#(1,8)
```
等同于
```python
num,deno=x.as_inter_ratio()
print(num/deno)
#1/8
```
