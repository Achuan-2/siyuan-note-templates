.action{/* 在这里更新查询的起始时间*/}
.action{$from:= toDate "2006-01-02 15:04:05" "2022-03-01 00:00:00"}
.action{$to := toDate "2006-01-02 15:04:05" "2022-03-31 23:59:59"}

## .action{$from | date "2006.01.02  Mon"} \~  .action{$to | date "2006.01.02  Mon"} 期间更新的笔记文档


.action{$from:= $from | date "20060102150405"}
.action{$to:= $to | date "20060102150405"}

.action{/* 按文档名升序排列 */}
.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE root_id != '?' AND (created >= '?' AND created <= '?' OR updated >= '?' AND updated <= '?') ) order by HPath LIMIT -1" .id $from $to $from $to }


.action{range $v := $blocks}
- [.action{$v.HPath}](siyuan://blocks/.action{$v.ID})  
.action{end}
