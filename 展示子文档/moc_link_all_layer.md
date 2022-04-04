.action{/*------定义变量------*/}
.action{$tab:="  "}
.action{$list:="- "}

.action{/*--得到当前文档的路径--*/}
.action{$getdocInfo := (queryBlocks "SELECT * FROM blocks WHERE id='?' and type='d' " .id )}
.action{$docPath:=""}
.action{range $v:= $getdocInfo}
	.action{$docPath =$v.Path}
.action{end}

.action{/*--得到当前文档的层次数--*/}
.action{$temp:= (splitList "/" $docPath)}
.action{$p_len:=len $temp}

.action{/*--查询子文档--*/}
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'd' AND path like '%/?/%.sy' Order BY path" .id )}

.action{/*--先以列表展示当前文档--*/}
- [.action{.title}](siyuan://blocks/.action{.id})
.action{/*--再以列表展示父文档--*/}
.action{range $v:=$block}
.action{$a:=splitList "/" $v.Path}
.action{/*--注释：slice list num 相当于 list[num:]，这一步相当于是只计算子文档相对于当前文档的层次数 --*/}
.action{$a:=slice $a $p_len}
.action{range $i:= $a}.action{$tab}.action{end}.action{$list}[.action{$v.Content}](siyuan://blocks/.action{$v.ID})
.action{end}

