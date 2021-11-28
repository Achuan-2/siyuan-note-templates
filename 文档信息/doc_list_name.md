展示所有ID
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'd'  ORDER BY hpath LIMIT 5000 ")}

| 文档名路径 | ID |
| -------- | ---- |
.action{range $v:=$block} | .action{$v.HPath} | .action{$v.ID}|
.action{end}

