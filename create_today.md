## .action{ now | date "2006-01-02  Mon "} 创建的笔记

{{SELECT * FROM blocks WHERE created >= ".action{now | date "20060102"}" AND created <= ".action{(now | date_modify "+24h")| date "20060102"}" AND type ='d' AND root_id != '.action{.id}' order by created }}
