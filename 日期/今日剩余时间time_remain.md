.action{$tomorrow := (now | date_modify "24h") | date "2006-01-02 "}
.action{$tomorrow := nospace $tomorrow}
.action{$nextDay := toDate "2006-01-02" $tomorrow}
现在时间： .action{now | date "15:04:05"}
距离今天结束还有.action{$nextDay.Sub now}
