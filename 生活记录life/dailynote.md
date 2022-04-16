
.action{$this_year :=now | date "2006"} 
.action{$next_year := add $this_year 1} 

.action{$this_year_first :=toDate "2006-01-02" ( nospace (cat $this_year "-01-01"))}
.action{$this_year_last :=toDate "2006-01-02" ( nospace (cat $this_year "-12-31"))}

.action{$next_year_first :=toDate "2006-01-02" ( nospace (cat $next_year "-01-01"))}

.action{/* 1、正数和倒数*/}
.action{$pass := add (div (now.Sub $this_year_first).Hours 24) 1}
.action{$countdown := (div ($next_year_first.Sub now).Hours 24)}



.action{/* 2、统计周数*/}
.action{/* 2.1、已过多少周*/}
.action{$dayDict := dict "Mon" 1 "Tue" 2 "Wed" 3 "Thu" 4 "Fri" 5 "Sat" 6 "Sun" 7} 
.action{$firstDay := get $dayDict ($this_year_first  | date "Mon")}
.action{$pass_days := div (now.Sub $this_year_first ).Hours 24}

.action{$week := div (add $pass_days $firstDay) 7}
.action{$remain :=mod (add $pass_days $firstDay) 7}
.action{if not (eq $remain 0)}
.action{$week = add $week 1}
.action{end}

.action{/* 2.2、已过多少周*/}
.action{$all_days := div ($this_year_last.Sub  $this_year_first ).Hours 24}
.action{$all_week := div (add $all_days  $firstDay) 7}
.action{$remain :=mod (add $all_days $firstDay) 7}
.action{if not (eq $remain 0)}
.action{$all_week = add $all_week 1}
.action{end}

.action{/* 2.2、倒数日*/}
.action{$hurry_date := "2022-04-30"}
.action{$hurry_countdown := add (div ((toDate "2006-01-02" $hurry_date).Sub now).Hours 24) 1}
> 今年已过了 .action{$pass} 天（第 .action{$week} 周/共 .action{$all_week} 周）,距离 .action{$next_year} 年还有 .action{$countdown} 天。
> 距离 .action{$hurry_date} 四月结束还有 .action{$hurry_countdown} 天。


{{{col
{{{row
## ⏰Must-To-Do
* [ ] 


}}}


{{{row
## 🐣Mini-Habits
* [ ] [记录睡眠时间](siyuan://blocks/20210827100508-3mkmbeu)
* [ ] [周打卡](siyuan://blocks/20210830231007-w7cvvku)
* [ ] [2022愿望清单](siyuan://blocks/20220107150030-vrjys3w)
* [ ] 每天拍一张照
* [ ] 每天录下自己的声音
* [ ] 每日记账
* [ ] 回顾昨天
* [ ] 每天7：30 起
* [ ] 微软日历记事
}}}
}}}

> .action{ now | date "2006.01.02 Mon"} 🌞 ?分 ？
> {: style="text-align: center;"}
> Weather：🌞🌥☁️⛈🌧🌦🌈🌪🌀⚡❄️🔥🥶🌊🌫
> 
> 🏠Location： 湖北省武汉市
> 🛌Sleep：[Bedtime] ？ | [Wake Up Time] ？
> 
> 
> ---
> #📅今天要改进的地方#
> 
> * [ ] 坚持使用番茄钟
> 
> #daily/🚀️进展#
> - 毕设：
> - 尤克里里：
> - 健康与锻炼：
> - 个人：
> 
> #daily/🧠今日反省#
> 
> #daily/✍笔记#
>
> #daily/💌遇见#
> 
> 
{: style="color: var(--b3-card-success-color); background-color: var(--b3-card-success-background);"}

## 每日反思❌✅
1. 节制。食不过饱，饮酒不醉。
2. 沉默寡言。言必于人于己有益，避免无益的聊天。
3. 生活秩序。每一样东西应有其安放的地方，做每件日常事务当有一定的时间。
4. 决心。当做必做，决心要做的事应坚持不懈。
5. 俭朴。用钱必须于人或于己有益，换言之，切戒浪费。
6. 勤勉。不浪费时间；每时每刻做些有用的事，戒掉一切不必要的行为。
7. 诚恳。不欺骗人；思想要纯洁公正，说话也要如此。
8. 公正。不做不利于人的事，不要忘记履行对人有益而又是你应尽的义务。
9. 中庸适度。避免极端；人若给你应得处罚，你当容忍之。
10. 清洁。身体、衣服和住所力求清洁。
11. 镇静。勿因小事或普通的不可避免的事故而惊慌失措。
12. 谦虚。仿效耶稣和苏格拉底。

## 🎲随机复习

{{SELECT * FROM blocks where type = 'd' ORDER BY random() LIMIT 1}}