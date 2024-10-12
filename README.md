# 小猿口算-练习场0.0秒/题-支持PK场 附iOS端详细教程

### 使用效果：www.bilibili.com/video/BV1L82VYQEpx 
### 配合连点器可以达到0.0s：www.bilibili.com/video/BV1fx2mYWE2J
### 详细视频教程：www.bilibili.com/video/BV14D2mYTEC9
### 目录
- [1. Storm Sniffer傻瓜教程-练习场刷速度](#1-storm-sniffer-----------)
  * [口令：改答案口令: SSC#yWerXhCWQQ# 复制本段文本并打开Storm Sniffer](#----------ssc-ywerxhcwqq-----------storm-sniffer)
- [2. Storm Sniffer改pk场](#2-storm-sniffer-pk-)
- [3. 以Quantumult X为例，其他软件类似：](#3--quantumult-x----------)
- [4. 直接修改题目数量的方法](#4------------)
- [5. PK结果](#5-pk--)
- 
![屏幕截图 2024-10-11 144803](https://github.com/user-attachments/assets/5ae735ae-330d-41af-a704-f47dbc22ed62)

实现原理非常简单，小猿口算在匹配成功时会直接下载所有题目及答案，修改响应体把答案全部改成小数点【.】即可

# 1. Storm Sniffer傻瓜教程-练习场刷速度
1. 买月卡或者终身B
2. 把证书配置了
3. 打开重写规则，复制口令粘进去
4. 打开MITM和重写，完成
效果是只有一个题目，只要点一下即可完成
## 口令：改答案口令: SSC#yWerXhCWQQ# 复制本段文本并打开Storm Sniffer

![db1d35938a529a3d53c4e428f16a219](https://github.com/user-attachments/assets/fcd75c46-f530-4c20-a2fa-781afb6dd7f3)

# 2. Storm Sniffer改pk场
思路来自：https://github.com/cr4n5/XiaoYuanKouSuan/blob/main/Re_js/README.md

经测试iOS直接可用，具体设置方法如下：

url正则匹配设置为：
```
^https?:\/\/leo\.fbcontent\.cn\/bh5\/leo-web-oral-pk\/exercise_\w+\.js
```
重写规则为替换响应体为本地/远程文件（quanx同理）https://github.com/cr4n5/XiaoYuanKouSuan/blob/main/exercise.js

卸载并重新安装小猿口算清除数据，保持重写打开并重新启动小猿口算即可
![IMG_3106(20241012-183426)](https://github.com/user-attachments/assets/d4c123fd-ee46-49e8-b0c0-d0518033f60d)

# 3. 以Quantumult X为例，其他软件类似：

注意Quantumult X的本地重写不支持太大的响应体，所以20题后会失效，可以用Storm Sniffer或者其他软件
1. 配置MITM证书
2. 新建一个重写规则
3. 依此填入以下内容：
4. 打开MITM、重写、HTTP抓取，还有Quan X代理

类型：response-body

用以匹配的URL：
```
^https?:\/\/xyks\.yuanfudao\.com\/leo-math\/iphone\/exams.+               （iPhone用户 练习场）
^https?:\/\/xyks\.yuanfudao\.com\/leo-math\/android\/exams.+              （Android用户 练习场）
```
用以匹配的Body：
```
\["[0123456789<>\.\\frac\{\},"=]+"\]
```
替换：
```
["."]
```

iPhone用户PK修改的重写规则示例：
![IMG_3055(20241010-234413)](https://github.com/user-attachments/assets/8c443a8a-8d45-42ae-bd3d-906b6a29c461)

# 4. 直接修改题目数量的方法
练习可以用这个刷0.0s，pk可以实现，但是不能上传结果，具体修改方法
```
用以匹配的body: "questionCnt":\s*\d+,"correctCnt":0,"costTime":0,"questions":\s*\[.*\],
替换："questionCnt":1,"correctCnt":0,"costTime":0,"questions": [{"id": 1,"content": "9+\\\\square=12","answer": "1","userAnswer": null,"answers": ["."],"script": null,"wrongScript": null,"status": 0,"errorState": 0,"costTime": 0}],
```
修改后效果
![075447f6711ee0296187b3a25a19010](https://github.com/user-attachments/assets/a902a38c-e55c-41c1-9d97-3062770fd733)

# 5. PK结果
![微信图片_20241010175313](https://github.com/user-attachments/assets/afb3d32c-7c43-4e14-af53-ad0200b4e9ac)
