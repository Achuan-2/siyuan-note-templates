.action{$keywords := "var(--b3-font-color4)"}


.action{.title}文档内以纯文本形式展示包含绿色文字的段落
.action{$block:= (queryBlocks "SELECT * FROM blocks WHERE path LIKE '%/?.sy' AND markdown LIKE '%?%' AND (type='p' OR type='h') " .id $keywords)}

.action{range $v:=$block} 
.action{$v.Markdown} 
.action{end}
