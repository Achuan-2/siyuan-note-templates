.action{/* 设置想查询的年份和月份 */}
.action{$this_year := 2021} 
.action{$this_month := 7} 


.action{/* -------1.获取今年年份和上个月的月份数字------- */}

.action{/* 处理月份为两位整数，小于10，则为0x */}
.action{if gt $this_month 10}
.action{/* if语句内如果想要给外部的全局变量赋值，需要用=而不是:=*/}
.action{$this_month = $this_month}
.action{else}
.action{$this_month = nospace (cat "0" $this_month)}
.action{end}

.action{/* -------2.判断今年是否为闰年，得到这个月的最后一天------- */}

.action{/* 2.1判断闰年，相当于if year % 4 == 0 and year % 100 != 0 or year % 400 == 0 */}
.action{$is_leap := any (all (empty (mod $this_year  4)) (not (empty (mod $this_year  100)))) (empty (mod $this_year  400))}
.action{$MonthDict1 := dict "01" "31" "02" "28" "03" "31" "04" "30" "05" "31" "06" "30" "07" "31" "08" "31" "09" "30" "10" "31" "11" "30" "12" "31"}
.action{$MonthDict2 := dict "01" "31" "02" "29" "03" "31" "04" "30" "05" "31" "06" "30" "07" "31" "08" "31" "09" "30" "10" "31" "11" "30" "12" "31"}
.action{$Dicts := dict "true" $MonthDict2 "false" $MonthDict1}
.action{$MonthDict := get $Dicts (toString $is_leap)}

.action{/* 2.2得到这个月的最后一天 */}
.action{$last_day := get $MonthDict (toString $this_month)}
.action{$this_month_first :=nospace (cat $this_year "-" $this_month "-01")}
.action{$this_month_last :=nospace (cat $this_year "-" $this_month "-" $last_day)}

.action{/* 2.3格式化这个月的第一天和最后一天 */}
.action{$from:= toDate "2006-01-02 15:04:05" (cat $this_month_first "00:00:00")}
.action{$to := toDate "2006-01-02 15:04:05" (cat $this_month_last "23:59:59")}


.action{/* -------3.获得上个月更新的所有笔记文档------- */}
## .action{$from | date "2006.01.02  Mon"} \~  .action{$to | date "2006.01.02  Mon"} 期间更新的笔记文档

.action{$from:= $from | date "20060102150405"}
.action{$to:= $to | date "20060102150405"}

.action{/* 按文档名升序排列 */}
.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE root_id != '?' AND (created >= '?' AND created <= '?' OR updated >= '?' AND updated <= '?') ) order by HPath LIMIT -1" .id $from $to $from $to }


.action{range $v := $blocks}
- [.action{$v.HPath}](siyuan://blocks/.action{$v.ID})  
.action{end}
