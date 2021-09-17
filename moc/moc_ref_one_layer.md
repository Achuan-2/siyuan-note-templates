.action{.title}

.action{$docid:=.id}
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'd' AND path like '%/?/______________-_______.sy' Order BY hpath" $docid )}

.action{range $v:=$block} 
- ((.action{$v.ID} ".action{$v.Content}")) 
.action{end}
