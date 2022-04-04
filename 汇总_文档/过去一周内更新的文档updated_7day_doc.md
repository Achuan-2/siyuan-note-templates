## .action{ now | date "2006-01-02 Mon "} 过去7天更新的笔记文档

.action{$from := (now | date_modify "-144h") | date "20060102"}
.action{$to := (now | date_modify "+24h") | date "20060102"}

.action{/* 按文档名升序排列 */}
.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE root_id != '?' AND (created >= '?' AND created <= '?' OR updated >= '?' AND updated <= '?') ) order by HPath LIMIT -1" .id $from $to $from $to }

.action{range $v := $blocks}
- [.action{$v.HPath}](siyuan://blocks/.action{$v.ID})  
.action{end}
