## .action{ now | date "2006-01-02  Mon "} 更新笔记汇总
{{SELECT * FROM blocks WHERE ( (created >= ".action{now | date "20060102"}" AND created <= ".action{(now | date_modify "+24h")| date "20060102"}" ) OR (updated >= ".action{now | date "20060102"}" AND updated <= ".action{(now | date_modify "+24h")| date "20060102"}")  )  AND root_id != '.action{.id}'  order by created }}
