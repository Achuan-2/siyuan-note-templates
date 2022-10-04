.action{ $ppath := nospace (cat "https://b3logfile.com/siyuan/assets/pic" ((randInt 1 32) | toString) ".png")}

.action{$after := (div ((toDate "2006-01-02" "2021-11-05").Sub now).Hours 24)}

.action{$dayleft := (div ((toDate "2006-01-02" "2022-01-01").Sub now).Hours 24)}

.action{$week := add (mod (div ((toDate "2006-01-02" "2050-03-13").Sub now).Hours 24) 7) 1}


![image.png](.action{$ppath})


> 🕐 创建时间：.action{now | date "2006-01-02 15:04"} .action{last (slice (list "星期六" "星期五" "星期四" "星期三" "星期二" "星期一" "星期天") 0 $week )}, 距离 `2021-11-05` 还剩 `.action{$after}` 天


## 🧱((20210217233154-6r71zk3 "Daily work"))-.action{now | date "01/02"}


> 第一次日记模板设置方法：为方便使用汇总功能，请进入`/templates/Meteor/`下定制自己的`dailynote`模板
> 1. 新建`Daily work`或者其他名字的页面，然后复制页面的块引用
> 2. 在此模板中，找个空白的地方，粘贴块引用.  注意不要动里面的id
> 3. 把`🧱 Daily work`的ID `( (ID "文本") )`替换成你刚刚粘贴的部分的ID
> 4. 删除这段注释。找个空白文档，调用`dailynote`日记模板测试一下


{: id="20210226143641-owbh20s"}

{: id="20210226143641-konghan"}

## 📝 ((20210217233336-3akpqfr "Notes"))-.action{now | date "01/02"}
{: id="20210117173634-z3gapm0"}

{: id="20210118002650-89v936m" updated="20210226143725"}

## 🎉️ 历史待办


> 截止至 `.action{now | date "2006-01-02 15:04"} .action{last (slice (list "星期六" "星期五" "星期四" "星期三" "星期二" "星期一" "星期天") 0 $week )}`


{{SELECT * FROM blocks WHERE (id in (select parent_id from blocks where type !='l' ) and type='i' and subtype = 't' and markdown like '%[ ]%') and root_id !='.action{.id}' order by created DESC limit 15}}


## 🚴 随机复习


> 距离 `2022-01-01` 还剩 `.action{$dayleft}` 天，加油！


{{SELECT * FROM blocks where type = 'd' and path not like '%{{.title}}%' ORDER BY random() LIMIT 1}}


