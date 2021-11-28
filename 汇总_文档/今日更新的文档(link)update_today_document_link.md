## .action{ now | date "2006-01-02  Mon "} 今天更新的笔记文档


.action{$today := now | date "20060102"}
.action{$next := (now | date_modify "+24h")| date "20060102"}


.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE (updated >= '?' AND updated <= '?' AND root_id != '?')) order by updated DESC " $today $next .id}


.action{range $v := $blocks}
- [.action{$v.HPath}](siyuan://block/.action{$v.ID})  
.action{end}
