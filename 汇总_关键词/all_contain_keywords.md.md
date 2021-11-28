.action{$keywords := "关键词"}

所有文档内包含关键词(.action{$keywords})的段落文字汇总（不包含本文档）
{{SELECT * FROM blocks WHERE path NOT LIKE '%/.action{.id}.sy' AND markdown LIKE '%.action{$keywords}%' AND  ((type = 'p' AND parent_id not in (SELECT id FROM blocks WHERE  type = 'i') )  OR (type = 'i' AND id in (SELECT parent_id FROM blocks WHERE  type ='p' AND markdown LIKE '%.action{$keywords}%' )) ) ORDER BY created LIMIT 10000 }}

单独以块引展示包含关键词(.action{$keywords})的标题
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE type= 'h' AND path NOT LIKE '%/.action{.id}.sy' AND markdown LIKE '%?%'  ORDER BY created LIMIT 10000" $keywords)}

.action{range $v:=$block} 
- ((.action{$v.ID} ".action{$v.Content}")) (.action{$v.HPath})
.action{end}
