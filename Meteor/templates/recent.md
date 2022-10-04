> 24h为一天，默认72h是3天前的笔记
>

{{SELECT * FROM blocks WHERE type='d' and created >'.action{(now | date_modify "-72h") | date "20060102"}' order by created DESC}}