---
layout: article
tags: Arcgis
title: ArcGIS字段自动增加编号
mathjax: true
---

## 添加字段 ##
![添加字段][1]
## 进行字段计算（可以选中部分来计算） ##
下面为计算方法和实现效果
![字段计算][2]

重要提示：解析程序一定要选Python，并将“显示代码块”勾选！
{:.warning}

## 代码块 ##
 - 预逻辑脚本代码：
```
base=0
def autoIncrement():
 global base
 pStart = 1 #初始值
 pInterval = 1 #间隔值
 if (rec == 0): 
  rec = pStart 
 else: 
  rec = rec + pInterval 
 return base
```
 - 函数调用
实现常规编号
```
autoIncrement()
```
实现给定长度编号，5为长度是5，如00001
```
(str(autoIncrement())).zfill(5)
```
实现从某个数字开始编号，下为从1000开始编号
```
autoIncrement()+1000
```

提示：如果你想给编号前加上字母，比如加上“BH”，请将 `return base` 修改为 `return "BH"+str(base)`即可。
{:.warning}



  [1]: http://blog.icehui.com/usr/uploads/2019/03/3958569915.png
  [2]: http://blog.icehui.com/usr/uploads/2019/03/3156433454.png
