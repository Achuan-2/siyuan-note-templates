
## .action{.title} 本文档引用块汇总


{{SELECT * FROM blocks WHERE path like '%/.action{.id}.sy' AND type= 'b' ORDER BY updated DESC }}

## .action{.title} 子文档引用块汇总


{{SELECT * FROM blocks WHERE path like '%/.action{.id}/%.sy' AND type= 'b' ORDER BY updated DESC }}
