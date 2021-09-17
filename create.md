## .action{ now | date "2006-01-02  Mon "} 今天更新的笔记文档
{{SELECT * FROM blocks WHERE (id in (select root_id from blocks where (updated >= ".action{now | date "20060102"}" AND updated <= ".action{(now | date_modify "+24h")| date "20060102"}")))  AND root_id != '.action{.id}' order by created DESC}}
