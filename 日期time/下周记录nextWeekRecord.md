.action{/*<!-- 计算下周每一天的日期 -->*/}
.action{$weekday := ternary 7 (int (now | Weekday)) (eq (int (now | Weekday)) 0)}
.action{$monday := now.AddDate 0 0 (int (sub 8 $weekday))}
.action{$tuesday := $monday.AddDate 0 0 1}
.action{$wednesday := $monday.AddDate 0 0 2}
.action{$thursday := $monday.AddDate 0 0 3}
.action{$friday := $monday.AddDate 0 0 4}
.action{$saturday := $monday.AddDate 0 0 5}
.action{$sunday := $monday.AddDate 0 0 6}

.action{/*<!-- 获取今天的日期用于标记 -->*/}
.action{$today := (now | date "20060102")}

### 下周记录（.action{$monday | date "20060102"} ~ .action{$sunday | date "20060102"}）

| 日期                          | 白天是否有摸鱼       | 晚上是否有充电 | 明天如何改进                                |
| ----------------------------- | -------------------- | -------------- | ------------------------------------------- |
| .action{$monday               | date "20060102 Mon"} |                |                                             |  |
| .action{$tuesday              | date "20060102 Mon"} |                |                                             |  |
| .action{$wednesday            | date "20060102 Mon"} |                |                                             |  |
| .action{$thursday             | date "20060102 Mon"} |                |                                             |  |
| .action{$friday               | date "20060102 Mon"} |                |                                             |  |
| .action{$saturday             | date "20060102 Mon"} |                |                                             |  |
| .action{$sunday               | date "20060102 Mon"} |                |                                             |  |
{: colgroup="min-width: 60px; | width: 250px;        | width: 145px;  | width: 100px;" id="20250617161045-w2cpg8c"}