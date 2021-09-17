
## .action{(now | date_modify "-72h")| date "20060102"} -  .action{now | date "2006-01-02"} 更新笔记汇总

{{SELECT * FROM blocks WHERE updated >= ".action{(now | date_modify "-72h") | date "20060102"}" AND  updated <= ".action{(now | date_modify "+24h") | date "20060102"}" AND type !='d' AND root_id != '.action{.id}' order by updated }}