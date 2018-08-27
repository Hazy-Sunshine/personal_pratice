## 基本python装饰器（带参数）
'''python

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
	
'''
