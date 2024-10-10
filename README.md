# 小猿口算抓包后修改所有答案为1实现快速答题
![微信图片_20241010175313](https://github.com/user-attachments/assets/afb3d32c-7c43-4e14-af53-ad0200b4e9ac)
实现原理非常简单，小猿口算在匹配成功时会直接下载所有题目及答案，修改响应体把答案全部改成1即可

这里以Quantumult X为例，其他软件类似：
1. 新建一个重写规则
2. 依此填入以下内容：

类型：response-body

用以匹配的URL：

^https?:\/\/xyks\.yuanfudao\.com\/leo-game-pk\/iphone\/math\/pk\/match.+  （iPhone用户）
^https?:\/\/xyks\.yuanfudao\.com\/leo-game-pk\/android\/math\/pk\/match.+ （Android用户）

用以匹配的Body："answer":"[0-9]+","userAnswer":null,"answers":\["[0-9]+"\],"status":0,"script":null,"wrongScript":null,"ruleType":"ARITHMETIC"

替换："answer":"1","userAnswer":null,"answers":["1"],"status":0,"script":null,"wrongScript":null,"ruleType":"ARITHMETIC"
![微信图片_20241010175448](https://github.com/user-attachments/assets/c441d403-5406-4280-8a84-2210d4138fde)

使用示例：
https://www.bilibili.com/video/BV1tC23YKEk6/?spm_id_from=333.999.0.0&vd_source=87515e1e048871f3a938e1a5153d1f81
