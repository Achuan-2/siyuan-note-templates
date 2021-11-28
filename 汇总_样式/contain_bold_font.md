.action{$keywords := "**%**"}

.action{.title}文档内加粗汇总
包含加粗文字的段落汇总
{{SELECT * FROM blocks WHERE path LIKE '%/.action{.id}.sy' AND markdown LIKE '%.action{$keywords}%' AND  (type = 'p' AND parent_id not in (SELECT id FROM blocks WHERE path LIKE '%/.action{.id}.sy' AND type = 'i') )  OR (type = 'i' AND id in (SELECT parent_id FROM blocks WHERE path LIKE '%/.action{.id}.sy' AND type ='p' AND markdown LIKE '%.action{$keywords}%' )) ORDER BY created}}

单独以块引展示包含加粗文字的的标题
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'h' AND path LIKE '%/?.sy' AND markdown LIKE '%?%' ORDER BY created " .id $keywords)}

.action{range $v:=$block} 
- ((.action{$v.ID} ".action{$v.Content}")) 
.action{end}
