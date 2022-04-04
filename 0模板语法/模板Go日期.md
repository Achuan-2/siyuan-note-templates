.action{now.Year}
.action{now.Month}

.action{$this_month :=now | date "1"} 
.action{$last_month :=sub $this_month 1} 
.action{$last_month} 

.action{now.Hour}：.action{now.Minute}：.action{now.Second}
.action{$this_month :=now | date "1"} 
.action{$last_month := sub $this_month 1} 
.action{if gt $last_month 10}
.action{$last_month := $last_month}
.action{else}
.action{$last_month :=nospace (cat "0" $last_month)}
.action{$last_month}
.action{$last_month}
.action{end}