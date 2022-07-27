.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$day := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{if eq $day 0}
.action{$day = 7}
.action{end}
.action{$leftday :=mul (sub $day 1)  24}
.action{$rightday :=mul (sub 7 $day) 24}
.action{$leftHour :=nospace (cat "-" $leftday "h") }
.action{$rightHour :=nospace (cat "+" $rightday "h")}
### .action{(now | date_modify $leftHour) | date "2006.01.02"} ~ .action{(now | date_modify $rightHour) | date "2006.01.02"}
这周一定要完成的任务
* 愿望1
* 愿望2
{{{col
{{{row
周一
{: style="color: var(--b3-card-error-color); background-color: var(--b3-card-error-background);"}
1. 空
}}}
{{{row
周二
{: style="color: var(--b3-card-warning-color); background-color: var(--b3-card-warning-background);"}
1. 空
}}}
{{{row
周三
{: style="color: var(--b3-card-info-color); background-color: var(--b3-card-info-background);"}
1. 空
}}}
{{{row
周四
{: style="background-color: var(--b3-font-background5);"}
1. 空
}}}
{{{row
周五
{: style="background-color: var(--b3-font-background7);"}
1. 空
}}}
{{{row
周六
{: style="background-color: var(--b3-font-background11);"}
1. 空
}}}
{{{row
周七
{: style="background-color: var(--b3-font-background10);"}
1. 空
}}}
}}}
这周的进步
* 
这周的问题
* 
* 
