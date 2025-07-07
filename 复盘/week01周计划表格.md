.action{/*<!-- 计算本周每一天的日期 -->*/}
.action{$monday := now.AddDate 0 0 (int (sub 1 (int (now | Weekday))))}
.action{$tuesday := $monday.AddDate 0 0 1}
.action{$wednesday := $monday.AddDate 0 0 2}
.action{$thursday := $monday.AddDate 0 0 3}
.action{$friday := $monday.AddDate 0 0 4}
.action{$saturday := $monday.AddDate 0 0 5}
.action{$sunday := $monday.AddDate 0 0 6}

.action{/*<!-- 获取今天的日期用于标记 -->*/}
.action{$today := (now | date "20060102")}


| 日期                          | 计划                 | 实际完成情况  | 明天如何改进                                |
| ----------------------------- | -------------------- | ------------- | ------------------------------------------- |
| .action{$monday               | date "20060102 Mon"} |               |                                             |  |
| .action{$tuesday              | date "20060102 Mon"} |               |                                             |  |
| .action{$wednesday            | date "20060102 Mon"} |               |                                             |  |
| .action{$thursday             | date "20060102 Mon"} |               |                                             |  |
| .action{$friday               | date "20060102 Mon"} |               |                                             |  |
| .action{$saturday             | date "20060102 Mon"} |               |                                             |  |
| .action{$sunday               | date "20060102 Mon"} |               |                                             |  |
{: colgroup="|width: 160px;|width: 167px;|width: 300px;" id="20250707192223-2thi8bg"}