## 基本python装饰器（带参数）

```python

import time 

def timer(func):
	def warpper(*args,**kwargs):
		startTime = time.time()
		func(*args,**kwargs)
		endtime = time.time()
		msecs = (endtime-startTime)*1000
		print ('time is %d ms' %msecs)
	return warpper

@timer
def count(a,b):
	num = a+b
	time.sleep(1)
	print (num)
	return num


if __name__ == '__main__':
	c = count
	c(4,6)
	print ('c.__name__ is %s',c.__name__)
	
```

## 装饰器实现的单例模式
```python

def singleton(cls, *args, **kwargs):
    instance = {}
    def _instance():
        if cls not in instance:
            instance[cls] = cls(*args, *kwargs)
        return instance[cls]
    return _instance

@singleton
class Test_singleton:
    def __init__(self):
        self.num = 0

    def add(self):
        self.num = 1

ts1 = Test_singleton()
ts2 = Test_singleton()
print(ts1)
print(ts2)
ts1.add()
print(ts2.num)
```
