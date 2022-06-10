
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
.action{$hurry_date := "2022-05-15"}
.action{$hurry_countdown := add (div ((toDate "2006-01-02" $hurry_date).Sub now).Hours 24) 1}





# .action{ now | date "2006.01.02 Mon"} 🌞 ?分 ？

> 今年已过了 .action{$pass} 天（第 .action{$week} 周/共 .action{$all_week} 周）,距离 .action{$next_year} 年还有 .action{$countdown} 天。
> 🗓️Weather：🌞🌥☁️⛈🌧🌦🌈🌪🌀⚡❄️🔥🥶🌊🌫
> 🏠Location： 湖北省武汉市
> 🛌Sleep：? →  ？


{{{col
{{{row
## 🐼今日目标
- 什么事情今天必做


}}}
{: style="width: 40%; flex: 0 0 auto;"}

{{{row
## ⏰我的一天
- 时间段+做的事情

}}}
}}}


{{{row
## 🧠今日反省

**今日发现的问题**

* 

**今日进步**

* 

**想感恩的人和事情**

* 

}}}


---

# 随机复习

{{SELECT * FROM blocks where type = 'd' ORDER BY random() LIMIT 1}}
