
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
* [ ] [每日反省](siyuan://blocks/20220423113423-9044etu)
* [ ] [随机复习](siyuan://blocks/20210722172300-eiqyduh)
}}}
}}}

# .action{ now | date "2006.01.02 Mon"} 🌞 ?分 ？

Weather：🌞🌥☁️⛈🌧🌦🌈🌪🌀⚡❄️🔥🥶🌊🌫

🏠Location： 湖北省武汉市
🛌Sleep：[Bedtime] ？ | [Wake Up Time] ？


## 🚀️进展
- [毕设](siyuan://blocks/20220214081633-0ys8z10)：
- [复旦](siyuan://blocks/20211206200739-tuj7fp7)：
- [尤克里里](siyuan://blocks/20220309110412-2nxymsz)：
- 健康与锻炼：
- 个人：

## 🧠今日反省

