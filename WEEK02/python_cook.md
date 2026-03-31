io是一个模块，StringIO是一个类：io是一个标准库里的模块，StringIO用作一个内存缓冲区，在内存里模拟文件操作。  
unittest是一个模块，TestCase是一个类  ：unittest是标准库里的单元测试框架，TestCse是最核心的基类，所以类都必须继承它。  
unittest.mock是子模块,unittest.mocj.patch是一个函数。  


unittest.mock.patch有三个作用：  
  -装饰器：对一个函数用mock来对目标对象建一个虚拟对象，从而进行测试  
  -上下文管理器：也是建一个虚拟对象来进行测试，不过可以用with()控制作用域  
  -单独使用：就是单独建一个patch(),手动控制patch.start(),手动控制patch.stop()  


io.path是一个模块io.path.exists是函数，exist函数用来检查文件是否存在，如：  
下面这个是普通查询，需要真实文件存在，无法控制返回值。
```
import os
def exist(path)；
  try:
    os.stat(path)
  except(OSError,ValueError):
    return False
return False
```


用MagicMock可以更安全的测试，直接从内存中返回，无需外部依赖，可验证参数和调用次数（assert_called_once_with）。
```
import os
import unittest
from unittest.mock import patch
def test_exist(path):
    try:
        os.path.exists(path)
    except:
        return False
    return True

class TestFileExist(unittest.TestCase):
    @patch("os.path.exists")
    def test_file_exist(self,mock_exists):
        mock_exists.return_value = True
        result=read_config(r"C:/Users/48218/Desktop/plan.txt")
        self.assertEqual(result,True)
        mock_exists.assert_called_once_with("C:/Users/48218/Desktop/plan.txt")
    
    @patch("os.path.exists")
    def test_file_not_exist(self,mock_exists):
        mock_exists.return_value= False
        result=read_config(r"C:/Users/48218/Desktop/plan.txt")
        self.assertEqual(result,False)

if __name__ == "__main__":
    unittest.main()
```

MagicMock是一个实例，可以代表任何，像函数一样被调用，可以模仿类的实例，可以创建断言（见上）.可以记录日志。
```
from unittest.mock import MagicMock
mock_exist = MagicMock(return_value=True)
mock_exist("C:/users/48218/Desktop/plan.txt")
mock_exist("C:/users/48218/Desktop/try_except.txt")
print(mock_exist.called)
print(mock_exist.call_count)
print(mock_exist.call_args)
print(mock_exist.call_args_list)
```


urllib包，urllib.request模块，from urllib.request import urlopen函数


