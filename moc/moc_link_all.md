.action{$docid:=.id}
.action{$tab:="  "}
.action{$line:="- "}

.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'd' AND path like '%/?%' Order BY path" $docid )}
.action{range $v:=$block}
.action{$a := rest (splitList "/" $v.Path)}
.action{range $i:= $a}.action{$tab}.action{end}.action{$line} [.action{$v.Content}](siyuan://block/.action{$v.ID})
.action{end}