## 🎯周计划
{: id="20250707192516-jsuuds4"}


.action{/* 获取当前文档路径 */}
.action{$docid:=.id}
.action{$blocks:= (queryBlocks "SELECT * FROM blocks WHERE id = '?' AND type = 'd'" $docid )}
.action{$currentDoc:= first $blocks }
.action{$currentpath:= $currentDoc.Path}

.action{/* 获取父文档id*/}

.action{$pathParts:= splitList "/" $currentpath}
.action{$parentDocId:= index $pathParts (sub (len $pathParts) 2)}

.action{/* 根据父文档id，查询父文档里h2标题为“周计划的标题”，以嵌入块方式进行展示*/}

{{SELECT * FROM blocks WHERE root_id = '.action{$parentDocId}' AND type = 'h' AND subtype = 'h2' AND content LIKE '周计划'}}

## 📋计划
{: id="20250707192516-cg7qy36"}

> 日记只是一个快速索引，最终目的是链接回待办背后相关的「任务笔记」去进一步处理与记录。但不是在日志上完成记录
> {: id="20250707192516-f0vw4vu"}
{: id="20250707192516-gq7jkf0"}

- {: id="20250707192617-7a0ciof"}[ ] 论文进展计划
  {: id="20250707192617-4k281ww"}

  - {: id="20250707192617-2gz8yhc"}[ ] 
    {: id="20250707192617-mbmgg7p"}
  - {: id="20250707192617-8xqbcid"}[ ] 
    {: id="20250707192617-w2br6sa"}
  {: id="20250707192620-5qxet96"}
{: id="20250707192617-xc1175x"}

## 📊实际进展
{: id="20250707192516-hz733rb"}

### 🔬科研进展
{: id="20250707192516-317w7ju" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}

### 📚专业精进
{: style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);" id="20250707192516-0tkzjo7"}

### 🎈生活娱乐
{: id="20250707192516-9gwbocp" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}

### 🏋️健康锻炼
{: id="20250707192516-fk8yh19" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}

### 🤝人际关系
{: id="20250707192516-hejtvar" style="background-color: var(--b3-font-background7); --b3-parent-background: var(--b3-font-background7);"}

## 🏆今日成就
{: id="20250707192516-8nsab0i"}

- {: id="20250707192543-4jvwf6a"}
  {: id="20250707192543-hm5kwvz"}
- {: id="20250707192545-9uf1ivd"}
  {: id="20250707192545-vad0qb5"}
- {: id="20250707192548-nxxtvim"}
  {: id="20250707192548-dby86m6"}
{: id="20250707192543-y2t6u8r"}

## 💭反思
{: id="20250707192516-roo0en4"}

- {: id="20250707192555-twl4aub"}
  {: id="20250707192555-ffp3dmz"}
- {: id="20250707192555-7ircji4"}
  {: id="20250707192555-obr3ahr"}
- {: id="20250707192555-sisb87n"}
  {: id="20250707192555-n1uhbwc"}
{: id="20250707192555-mp76sar"}

## 📅明日计划
{: id="20250707192516-c7vss3m"}

- {: id="20250707192600-1tuby3t"}[ ] 
  {: id="20250707192559-cqwwkc3"}
- {: id="20250707192602-lnqncin"}[ ] 
  {: id="20250707192602-s7p7gn0"}
- {: id="20250707192603-oe9xb6e"}[ ] 
  {: id="20250707192603-397keux"}
{: id="20250707192600-tuq7727"}







.action{/* 获取今天日期和星期 */}
.action{$today := now | date "2006-01-02" }
.action{$today2 := now | date "20060102" }
.action{$today3 := now | date "2006.01.02" }
.action{$today4 := now | date "2006/01/02" }
.action{$weekday := now | date "Mon" }
.action{/* 工作日用红色图标，周末用蓝色图标，%23代表#号，URL不能直接输入#号，所以用URL编码%23代替 */}
.action{$color := "%23d13d51"}
.action{if or (eq $weekday "Sat")  (eq $weekday "Sun") }
.action{$color = "%233eb0ea"}
.action{end} 
.action{/* 设置文档图标：选择type6，仅返回星期样式 */}

{: icon="api/icon/getDynamicIcon?type=6&date=.action{$today}&color=.action{$color}" alias=".action{$today},.action{$today2},.action{$today3},.action{$today4}"  type="doc"}
