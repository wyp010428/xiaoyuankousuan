# 小猿口算0秒十题 傻瓜教程 2024/10/11 12:20更新

配合连点器可以达到几乎0s
![微信图片_20241010175313](https://github.com/user-attachments/assets/afb3d32c-7c43-4e14-af53-ad0200b4e9ac)
实现原理非常简单，小猿口算在匹配成功时会直接下载所有题目及答案，修改响应体把答案全部改成1即可

# Storm Sniffer傻瓜教程-支持20题等
1. 买月卡或者终身B
2. 把证书配置了
3. 打开重写规则，复制口令粘进去
4. 打开MITM和重写，完成

口令：改答案口令: SSC#UqEBYriRBy# 复制本段文本并打开Storm Sniffer(http://dcuvu.oukd.cn/c2)
![db1d35938a529a3d53c4e428f16a219](https://github.com/user-attachments/assets/fcd75c46-f530-4c20-a2fa-781afb6dd7f3)


# 这里以Quantumult X为例，其他软件类似：

注意Quantumult X的本地重写不支持太大的响应体，所以20题后会失效，可以用Storm Sniffer或者其他软件
1. 新建一个重写规则
2. 依此填入以下内容：

类型：response-body

用以匹配的URL：
```
^https?:\/\/xyks\.yuanfudao\.com\/leo-game-pk\/iphone\/math\/pk\/match.+  （iPhone用户 PK）
^https?:\/\/xyks\.yuanfudao\.com\/leo-math\/iphone\/exams.+               （iPhone用户 练习场）
^https?:\/\/xyks\.yuanfudao\.com\/leo-game-pk\/android\/math\/pk\/match.+ （Android用户 PK）
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

# 使用效果：
https://b23.tv/TZ7civa
![IMG_3058(20241011-005444)](https://github.com/user-attachments/assets/10a621f5-815d-4e81-9122-39d766965b87)
