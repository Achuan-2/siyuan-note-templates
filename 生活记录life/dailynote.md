
.action{/* ============搜索昨日的笔记 Start============  */}
.action{$yesterday := (now | date_modify "-24h")| date "2006.01.02 Mon"}
.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE HPath like '%/?' ) order by HPath LIMIT -1" $yesterday }
.action{range $v := $blocks}
[昨日](siyuan://blocks/.action{$v.ID}) ｜明日
.action{end}
.action{/*  ============搜索昨日的笔记  End ============*/}

笔记
{: style="color: var(--b3-card-warning-color); background-color: var(--b3-card-warning-background);"}

* 今天重要的两件事
*  工作与学习
* 碎碎念
  * ((20220819153146-6e34cgk '📧遇见'))



