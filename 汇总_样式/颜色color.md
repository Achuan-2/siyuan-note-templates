
.action{$keywords := "var(--b3-font-background"}

{{SELECT * FROM blocks WHERE path LIKE '%/.action{.id}.sy' AND markdown LIKE '%.action{$keywords}%' AND  (type = 'p' AND parent_id not in (SELECT id FROM blocks WHERE path LIKE '%/.action{.id}.sy' AND type = 'i') )  OR (type = 'i' AND id in (SELECT parent_id FROM blocks WHERE path LIKE '%/.action{.id}.sy' AND type ='p' AND markdown LIKE '%.action{$keywords}%' ))  ORDER BY created LIMIT -1}}

