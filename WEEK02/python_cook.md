io是一个模块，StringIO是一个类：io是一个标准库里的模块，StringIO用作一个内存缓冲区，在内存里模拟文件操作。  
unittest是一个模块，TestCase是一个类  ：unittest是标准库里的单元测试框架，TestCse是最核心的基类，所以类都必须继承它。  
unittest.mock是子模块,unittest.mocj.patch是一个函数。  


unittest.mock.patch有三个作用：  
  -装饰器：对一个函数用mock来对目标对象建一个虚拟对象，从而进行测试  
  -上下文管理器：也是建一个虚拟对象来进行测试，不过可以用with()控制作用域  
  -单独使用：就是单独建一个patch(),手动控制patch.start(),手动控制patch.stop()  



