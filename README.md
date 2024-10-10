# 小猿口算一秒十题 已支持全部挑战 2024/10/10 20:30更新

配合连点器可以达到几乎0s
![微信图片_20241010175313](https://github.com/user-attachments/assets/afb3d32c-7c43-4e14-af53-ad0200b4e9ac)
实现原理非常简单，小猿口算在匹配成功时会直接下载所有题目及答案，修改响应体把答案全部改成1即可

这里以Quantumult X为例，其他软件类似：
1. 新建一个重写规则
2. 依此填入以下内容：

类型：response-body

用以匹配的URL：
```
^https?:\/\/xyks\.yuanfudao\.com\/leo-game-pk\/iphone\/math\/pk\/match.+  （iPhone用户）
^https?:\/\/xyks\.yuanfudao\.com\/leo-game-pk\/android\/math\/pk\/match.+ （Android用户）
```
用以匹配的Body：
```
\["[0123456789<>\.\\frac\{\},"]+"\]
```
替换：
```
["."]
```
![IMG_3044(20241010-202737)](https://github.com/user-attachments/assets/4b1db45d-1131-4f87-a0b2-5937ba2b1973)

使用示例：
https://b23.tv/TZ7civa
