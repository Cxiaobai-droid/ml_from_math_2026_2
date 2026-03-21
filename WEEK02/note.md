### 切片
1.[]本质是：Python 看到 a[i, j] 时，不是把它当成两个独立参数，而是会把 i 和 j 组成一个元组，再交给 __getitem__ 处理，所以它等价于 a.__getitem__((i, j))) 这一类调用。  
普通切片 seq[start:stop:step] 本质上也会转换成把一个 slice 对象传给 __getitem__ 的调用。  
numpy里的ndarray也用这套机制，所以它的多维切片和多维多维索引同。  


2.python里，...是一个真实对象，内置对象Ellipsis，代表“其余维度全部照选”。  

3.星号初始化嵌套列表的陷阱：
如
```python
w=[[None]*3]*2
w[0][0]=5
print(w)
#[5,None],[5,None],[5,None]
```
列表乘法不会复制列表本身，而是会生成对现有对象的多个引用。  
所以推荐用列表推导式改
```python
m,n=2,3
w=[None] * n for _ in range(m)
w[0][0]=5
print(w)
#[5,None],[None,None],[None,None]
```


4.我们知道，+=和*=属于增量赋值运算符，它们是否原地修改对象取决于左操作数的类型。  
背后支持 += 运算符的是特殊方法 __iadd__（就地相加），*=是 __imul__。  
对于可变对象如list,array.array,bytearray,就地修改对象，对于不可变对象如tuple，会生成新对象并在新对象进行修改。  
性能上，不可变对象重复拼接效率低下，因为要不停生成新对象，而可变对象由于可以在原对象上进行修改，所以性能更好。


5.一个谜题
```python
t=(1,2,[30,40])
t[2]+=[50,60]
print(t)
```
<img width="1161" height="579" alt="image" src="https://github.com/user-attachments/assets/630db1ee-5f70-4361-b335-024bf37a55a2" />
出现两个结果：首先会生成[1,2,[30,40,50,60]],然后会报错typeError  
因为列表[30,40]被修改，变成了[30,40,50,60]✅ ，但是元组t里的值是引用指针，不可变，同时抛出了 TypeError：tuple object does not support item assignment❌。  

