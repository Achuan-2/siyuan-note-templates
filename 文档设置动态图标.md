.action{/* 获取今天日期和星期 */}
.action{$today := now | date "2006-01-02" }
.action{$weekday := now | date "Mon" }
.action{/* 工作日用红色图标，周末用蓝色图标，%23代表#号，URL不能直接输入#号，所以用URL编码代替 */}
.action{$color := "%23d13d51"}
.action{if or (eq $weekday "Sat")  (eq $weekday "Sun") }
.action{$color = "%233eb0ea"}
.action{end} 
.action{/* 设置文档图标：选择type6，仅返回星期样式 */}

{: icon="api/icon/getDynamicIcon?type=6&date=.action{$today}&color=.action{$color}"   type="doc"}