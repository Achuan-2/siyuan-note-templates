
.action{$docid:=.id}
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'd' AND path like '%/?/______________-_______.sy' ORDER BY hpath" $docid )}

.action{range $v:=$block} 
- [.action{$v.Content}](siyuan://blocks/.action{$v.ID})
.action{end}
