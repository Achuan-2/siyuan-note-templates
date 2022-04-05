Title:.action{.title}

.action{/* 1.先通过sql把查询结果赋值保存到blocks变量中去  */}
.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE created >= '20210505' AND created <= '20210506' AND type !='d' AND type !='h'   AND type !='i'  AND root_id != '20210504004406-wc9gfh0' order by updated"}


.action{/* 2. range开始循环，把查询到的block一个个循环命名为b  */}
.action{range $b := $blocks}

.action{$b.ID} | .action{$b.Path} 
Type: .action{$b.Type}
Markdown: .action{$b.Markdown} 
Content: .action{$b.Content} 
.action{end}


.action{/*  3.循环结束  */}
