.action{$from:= toDate "2006-01-02 15:04:05" "2022-01-01 00:00:00"}
.action{$to := toDate "2006-01-02 15:04:05" "2022-01-31 23:59:59"}

## .action{$from | date "2006-01-02  Mon"} \~  .action{$to | date "2006-01-02  Mon"} 期间更新的笔记文档


.action{$from:= $from | date "20060102150405"}
.action{$to:= $to | date "20060102150405"}

.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE (updated >= '?' AND updated <= '?' AND root_id != '?')) order by updated DESC Limit 10000" $from $to .id}


.action{range $v := $blocks}
- ((.action{$v.RootID} ".action{$v.HPath}"))
.action{end}
