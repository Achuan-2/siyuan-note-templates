快捷入口：[实验记录本](siyuan://blocks/20241009113128-gbxgj3m)丨[Life](siyuan://blocks/20230304225859-8xlywce) 丨 [人生改善计划！](siyuan://blocks/20230330111337-bfoss5l)
{: id="20240903002458-fak0ips" style="text-align: center;"}

## <span data-type="text">✅ Anticipation</span>{: style="background-color: var(--b3-font-background1); color: var(--b3-font-color1);"}


* 

## <span data-type="text">🗑Inbox</span>{: style="background-color: var(--b3-font-background5); color: var(--b3-font-color5);"}


* 

## <span data-type="text">📂Notes</span>{: style="background-color: var(--b3-card-success-background); color: var(--b3-card-success-color)"}

* 📂**Research**
* 📂**Project**
* 📂**Area**
* 📂**Resources**
* 📂**Life**


## <span data-type="text">🤔 Reflection</span>{: style="background-color: var(--b3-font-background8); color: var(--b3-font-color8);"}


🤨回顾一天

❤️我的进步

💔我的不足

🤔我的反思



.action{/* 获取今天日期和星期 */}
.action{$today := now | date "2006-01-02" }
.action{$weekday := now | date "Mon" }
.action{/* 工作日用红色图标，周末用蓝色图标，%23代表#号，URL不能直接输入#号，所以用URL编码%23代替 */}
.action{$color := "%23d13d51"}
.action{if or (eq $weekday "Sat")  (eq $weekday "Sun") }
.action{$color = "%233eb0ea"}
.action{end} 
.action{/* 设置文档图标：选择type6，仅返回星期样式 */}

{: icon="api/icon/getDynamicIcon?type=6&date=.action{$today}&color=.action{$color}"   type="doc"}
