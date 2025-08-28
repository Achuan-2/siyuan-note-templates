## 思源笔记内置变量和函数

### 独有变量

- ​`title`：该变量用于插入当前文档名。比如模板内容为 `# .action{.title}`，则调用后会以一级标题语法插入到当前文档内容中
- ​`id`：该变量用于插入当前文档 ID
- ​`name`：该变量用于插入当前文档命名
- ​`alias`：该变量用于插入当前文档别名

```template
这个是当前插入文档块的标题：.action{.title}
这个是当前插入文档块的ID：.action{.id}
这个是当前插入文档块的命名：.action{.name}
这个是当前插入文档块的别名：.action{.alias}
```

> 注意这里使用的时候必须前面要加上 `.`，也就是 `.title` 而非 `title`。因为 `.`表示当前对象，有兴趣可以参考这个：[Template · Go 语言中文文档](https://ld246.com/forward?goto=https%3A%2F%2Fwww.topgoer.com%2F%25E5%25B8%25B8%25E7%2594%25A8%25E6%25A0%2587%25E5%2587%2586%25E5%25BA%2593%2Ftemplate.html%23%25E6%25A8%25A1%25E6%259D%25BF%25E8%25AF%25AD%25E6%25B3%2595 "Template · Go语言中文文档")。

### 独有函数

- ​`getHPathByID`：该函数用于返回块 ID 对应块的可读路径

  ```template
  .action{getHPathByID .id}
  ```
- ​`getBlock`：该函数用于根据块 ID 查询数据库，返回值为 block

  ```template
  .action{getBlock "20250331162928-53comqi"}
  ```
- ​`queryBlocks`：该函数用于查询数据库，返回值为 blocks 列表

  ```template
  .action{$today := now | date "20060102150405"}
  .action{$blocks := queryBlocks "SELECT * FROM blocks WHERE content LIKE '?' AND updated > '?' LIMIT ?" "%foo%" $today "3"}
  ```
- ​`querySpans`：该函数用于查询数据库，返回值为 spans 列表

  ```template
   .action{querySpans "SELECT * FROM spans LIMIT ?" "3"}
  ```
- ​`querySQL`：该函数用于查询数据库，返回值为结果集

  ```template
   .action{querySQL "SELECT * FROM refs LIMIT 3"}
  ```
- ​`statBlock`：该函数用于统计块内容

  ```template
  .action{ (statBlock .id).RuneCount} .action{ (statBlock .id).WordCount}
  ```

  - RuneCount：字符数
  - WordCount：字数
  - LinkCount：链接数
  - ImageCount：图片数
  - RefCount：引用数
  - BlockCount：块数
- ​`runeCount`：该函数用于返回字符串中的字符数
- ​`wordCount`：该函数用于返回字符串中的字数
- ​`parseTime`：该函数用于将时间格式的字符串解析为 `time.Time` 类型，以便使用更多格式化方法渲染该时间

  ```template
  .action{$customDate :=parseTime "2025-08-27"}
  .action{$month := $customDate | ISOMonth}
  2025-08-27的ISOMonth是`.action{ternary (nospace (cat "0" $month)) $month (lt $month 10)}`
  ```
- ​`Weekday`：该函数用于返回周几 `Sunday=0, Monday=1, ..., Saturday=6`​
- ​`WeekdayCN`：该函数用于返回周几 `Sunday=日, Monday=一, ..., Saturday=六`​
- ​`WeekdayCN2`：该函数用于返回周几 `Sunday=天, Monday=一, ..., Saturday=六`​
- ​`ISOWeek`：该函数用于返回第几周
- ​`ISOYear`：返回ISOWeek所在的年份
- ​`ISOMonth`： 返回指定日期所属的 ISO 8601 周的第一天所在的月份。
- ​`pow`：指数计算，返回整数
- ​`powf`：指数计算，返回浮点数
- ​`log`：对数计算，返回整数
- ​`logf`：对数计算，返回浮点数
- ​`toPrettyJson`​

​`queryBlocks` 和 `querySpans` 、`querySQL`支持类似 SQL 预编译语句的变参列表，方便传入参数，下面是一个示例，向SQL语句传入了三个参数，使用`?`占位

```template
.action{$today := now | date "20060102150405"}
.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE content LIKE '?' AND updated > '?' LIMIT ?" "%foo%" $today "3"}
```

## 思源特有功能：kramdown、分栏、sql查询

### 模板如何字体颜色、背景色等样式

使用 [kramdown](https://kramdown.gettalong.org/?utm_source=ld246.com) 语法，

- 如果想要给部分文字加字体样式，就需要使用两个星号包裹（即加粗样式），后面带上 css style 样式（`{:`后需要注意有一个**空格**，否则不能正确渲染）
- 如果是给整个块加样式，直接把`{: style="`放在紧贴着这个块的下一行。

```markdown
**红色卡片**{: style="color: var(--b3-card-error-color);background-color: var(--b3-card-error-background);"}
**橙色卡片**{: style="color: var(--b3-card-warning-color);background-color: var(--b3-card-warning-background);"}
**蓝色卡片**{: style="color: var(--b3-card-info-color);background-color: var(--b3-card-info-background);"}
**绿色卡片**{: style="color: var(--b3-card-success-color);background-color: var(--b3-card-success-background);"}
```

### 模板分栏

分栏语法是思源特有的超级块语法，使用三个大括号包裹 `{{{col`，col 代表按列，即横排；row 代表行，即竖排。类似于代码块语法，而需要分几栏其实只要按 enter 换行就好。

横排

```markdown
{{{col
栏1

栏2

栏3

栏4
}}}
```

竖排

竖排的作用主要用于比如用于比如两个标题横排，如果还需要往标题添加新内容，就需要给标题及其内容加上竖向超级块，否则按enter就又会添加新的横排栏

```
{{{row
栏1

栏2

栏3

栏4
}}}
```

分两栏（`{: style=...`就是运用前面提到的 kmarkdown 进行 css 内嵌样式配置）

```markdown

{{{col
{{{row
### ✨ fisrt
{: style="color: var(--b3-card-error-color);background-color: var(--b3-card-error-background);"}
- text

}}}

{{{row
### 🎉 second
{: style="color: var(--b3-card-info-color);background-color: var(--b3-card-info-background);"}
- text
}}}

}}}
```

分四栏

```markdown

{{{col
{{{row
### ✨ fisrt
{: style="color: var(--b3-card-error-color);background-color: var(--b3-card-error-background);"}
- text

}}}

{{{row
### 🎉 second
{: style="color: var(--b3-card-info-color);background-color: var(--b3-card-info-background);"}
- text
}}}

{{{row
### ✏ three
{: style="color: var(--b3-card-success-color);background-color: var(--b3-card-success-background);"}
- text

}}}

{{{row
### 🎯 four 
{: style="color: var(--b3-card-warning-color);background-color: var(--b3-card-warning-background);"}
- text

}}}
}}}
```

### 模板嵌入

```sql

.action{/* ---------------模板嵌入----------------------- */}

.action{/* 模板块嵌入例子1：本文档加粗文字汇总 */}
本文档加粗文字汇总
{{SELECT * FROM blocks WHERE path LIKE '%/.action{.title}.sy' AND markdown LIKE '%**%**%' AND type ='p'}}

.action{/* END */}


.action{/* 模板块嵌入例子2：查询今天更新的所有笔记，root_id != '.action{.id}'排除了查询页面的内容 */}
.action{$week := add (mod (div ((toDate "2006-01-02" "2050-03-13").Sub now).Hours 24) 7) 1}
## .action{now | date "2006-01-02"} .action{last (slice (list "星期六" "星期五" "星期四" "星期三" "星期二" "星期一" " 星期天") 0 $week )} 笔记汇总

{{SELECT * FROM blocks WHERE updated > ".action{now | date "20060102"}" AND type !='d' AND root_id != '.action{.id}' order by created }}

.action{/* END*/}


.action{/* 模板块嵌入例子3：查询近3天更新的所有笔记，date_modify "-72h" 是调用函数=当前时间-h */}
<!--  -->
## .action{(now | date_modify "-72h")| date "20060102"} -  .action{now | date "2006-01-02"} 创建笔记汇总

{{SELECT * FROM blocks WHERE updated > ".action{(now | date_modify "-72h") | date "20060102"}" AND type !='d' AND root_id != '.action{.id}' order by created }}

.action{/* END*/}
```

### 模板静态展示 sql 查询结果

很多小伙伴对于模板查询，只知道通过 sql 查询可以作为嵌入块，其实通过循环语法是可以直接把查询的文字以纯文本形式或者块引方式展示出来的。语法如下，通过 `range` 对查询的块进行查询，再选择块的基本属性进行展示。需要注意的是这里**块的属性是大写**，而 sql 查询时块的属性表都是小写，如类型为 `$b.Type` 而不是 `$b.type`。

```markdown
<!-- 模板sql查询循环语法 -->
.action{range $b := $blocks} // 相当于for 循环
.action{$b}
.action{$b.ID} | .action{$b.Path} 

Type: .action{$b.Type}
Markdown: .action{$b.Markdown} 
Content: .action{$b.Content} 

.action{end}
<!-- 循环结束 -->
```

如果我要在笔记中查询今天或者特定日期内的所有笔记，而使用块嵌入的话，鉴于思源不支持折叠块查询的子结果，会让页面特别长。这时候使用块引展示笔记文档就很合适。

#### 以块引形式展示今天更新的笔记

```markdown
## .action{ now | date "2006-01-02  Mon "} 今天更新的笔记文档


.action{$today := now | date "20060102"}
.action{$next := (now | date_modify "+24h")| date "20060102"}


.action{$blocks :=queryBlocks "SELECT * FROM blocks WHERE id in (SELECT root_id FROM blocks WHERE (updated >= '?' AND updated <= '?' AND root_id != '?')) order by updated DESC " $today $next .id}


.action{range $v := $blocks}
- ((.action{$v.RootID} ".action{$v.HPath}"))
.action{end}

```

## 模板编程相关基本语法

复杂的模板函数文档可见：[sprig](http://masterminds.github.io/sprig/)

### Golang 模板语法和 Sprig

#### 模板引擎

- 思源的模板的语法是基于 Golang 的模板引擎来实现的
- Golang 的模板引擎并没有提供多少好用的模板函数，所以思源又内置了 Sprig 库——这个库提供了大量丰富的模板函数，来增强模板的功能性

#### ​`{{ }}` vs `.action{}`​

- 原始的 Golang 模板语法是 `{{ xxx }}`​
- 但是在思源中 `{{ }}` 又是嵌入块的声明语法，为了避免冲突，开发者就自定义了 `.action{ xxx }` 语法来替换原始的 `{{ xxx }}`​

#### 什么场景用`{{}}`语法，什么场景用`.action{}`语法？

- 在配置路径模板(如日记)时，使用`{{}}`语法，显得更简洁
- 在markdown模板片段中，需要用`.action{}`语法，避免与嵌入块冲突
- 在数据库模板列中，使用`.action{}`语法

### 变量的赋值

- 如果使用 `{{ now }}` 这种语法，模板引擎会直接将其渲染为具体的值
- 但是如果使用 `{{ $t := now}}` 这种语法，那么 `now` 的返回值会存储在变量 `$t` 中而不会渲染内部具体的值，此后就可以使用 `$t` 来引用这个变量

```template
{{ now }} /*渲染为具体的值*/
{{ $t := now}} /*存储在变量*/
```

### 基本关键字

```template
not /*如果后面是一个表达式要加括号，如要判断变量不为空if not (empty $date) */
lg、gt、eq、empty
if else end
range end
```

### `printf `：格式化与字符串拼接

- 小于10的月份，自动加上0

  ```template
  .action{parseTime "2025-08-27" | ISOMonth | printf "%02d"}
  ```
- 获取今年年份，与12-28组成日期格式

  ```template
  .action{$this_year :=now | date "2006"} 
  .action{$this_year_last :=toDate "2006-01-02" ( printf "%s-12-28" $this_year)}


  第`.action{now | ISOWeek}`周/共`.action{$this_year_last | ISOWeek}`周
  ```

### 注释

```template
.action{/* 用斜杠和星号括起来的内容是注释 */}
```

### if-else if-else-end 条件语句

通过条件判断来**有选择性**地渲染、执行一部分模板语法

基本的用法是：如果 `condition` 中的条件被判定为 true，则渲染 `T1` 否则渲染 `T2`​

- if结束必须用end（有点像Matlab，但是Matlab不强制）
- 赋值需要用= （if语句内如果想要给外部的全局变量赋值，需要用`=`而不是`:=`，因为在golang里如果直接在if语句用`:=`就相当于是在创建局部变量）

案例：给月份补0

```template
.action{$this_year := 2021} 
.action{$this_month := 7} 

.action{/* 处理月份为两位整数，小于10，则为0x */}
.action{if gt $this_month 10}
.action{/* 坑：这里是=而不能是:= */}
.action{$this_month = $this_month}
.action{else}
.action{$this_month = nospace (cat "0" $this_month)}
.action{end}
.action{$this_month}
```

### 常用逻辑判断

- 布尔运算

  - ​`and [<interface{}>,]`：`interface{}`，如果所有参数都为真，则返回最后一个参数；否则返回第一个为假的参数
  - ​`or [<interface{}>,]`：`interface{}`，如果任一参数为真，则返回第一个为真的参数；否则返回最后一个参数
  - ​`not <interface{}>`：`bool`，对单个参数进行逻辑非运算；如果参数为真则返回假，为假则返回真
- 比较运算：对两个类型进行比较，注意这里的参数必须要是同样的类型

  - ​`eq <interface{}>, <interface{}>`：`bool`，判断两个参数是否相等；相等返回真，不等返回假
  - ​`ne <interface{}>, <interface{}>`：`bool`，判断两个参数是否不相等；不相等返回真，相等返回假
  - ​`lt <interface{}>, <interface{}>`：`bool`，比较两个参数，如果第一个小于第二个，则返回真，否则返回假
  - ​`le <interface{}>, <interface{}>`：`bool`，比较两个参数，如果第一个小于等于第二个，则返回真，否则返回假
  - ​`gt <interface{}>, <interface{}>`：`bool`，比较两个参数，如果第一个大于第二个，则返回真，否则返回假
  - ​`ge <interface{}>, <interface{}>`：`bool`，比较两个参数，如果第一个大于等于第二个，则返回真，否则返回假

举例

- 判断是否等于 `eq`​

  ```template
  .action{ if eq (Weekday now) 1 }
  ```
- 判断变量是否为空

  ```template
  .action{if empty $date}
  ```
- 判断不为空

  ```template
  .action{if not (empty $date)}
  ```
- 用or（注意or不是放在中间！而是放在前面）

  ```template
  .action{if or (eq $weekday "Sat")  (eq $weekday "Sun") }
  ```

在常规的逻辑运算函数之外，还有必要介绍一类列表、对象判断类函数，这部份函数由 [Default Functions | sprig](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fdefaults.html "Default Functions | sprig") 提供

- ​`empty <interface{}>`：`bool`，判断给定的对象是否为空

  - 在思源中，最常见的用法是判断一个列表是不是空的
- ​`all [<interface{}>,]`：`bool`，判断给定一系列对象，是否每个都是非空的
- ​`any [<interface{}>,]`：`bool`，判断给定一系列对象，是否存在某一个是非空的



### 使用 ternary 函数计算内联条件

我们上面谈到了最常用的 if 条件语句：

```template
.action{ if eq 1 2 }
1
.action{ else }
2
.action{ end }
```

如果对编程比较有经验的人应该知道，很多语言中都支持计算内联条件，以 js 为例子

```js
const x = (1 == 2)? 1 : 2;
```

在模板函数中，这个内联条件计算可以用 `ternary` 函数来完成，基本用法为：`ternary <arg1> <arg2> <cond bool>`：

```template
.action{ ternary "Show 1" "Show 2" (eq 1 2) }
```

格式化ISOMont

```template
.action{$customDate :=parseTime "2025-08-27"}
.action{$month := $customDate | ISOMonth}
2025-08-27的ISOMonth是`.action{ternary (nospace (cat "0" $month)) $month (lt $month 10)}`
```



### range循环语句

range 语句被用来在一个序列当中进行迭代，最常见的语法如下

```template
.action{ range $v := <List> }
  {{ $v }}
.action{ end }
```

这里的含义是：

- 在一个可迭代的列表 `List` 中迭代
- 每次取出一个值赋值给 `$v`​
- 我们就可以在 range 块内部访问这个 `$v` 变量

一个简单的案例如下：

```template
.action{ $list := list 1 2 3 4 }
.action{ range $v := $list }
  - Index: .action{ $v }
.action{ end }
```

实际举例：用`range`语法展示SQL查询结果

```template
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

```

### 变量类型

#### 常用变量类型

- ​`int`：整数类型

  - ​`int64`：64 位的整数类型，需要通过类型转换函数和 `int` 类型做转换
- ​`float`：浮点数类型

  - ​`float64`：64 位的浮点数类型，需要通过类型转换函数和 `float` 类型做转换
- ​`list`：列表类型
- ​`str`：字符串类型
- ​`bool`：布尔类型（`true` 或者 `false`）
- ​`Time`：时间对象类型



#### 字典

示例：通过日期获取对应icon路径

```template
.action{ $weekday := now | date "Mon" }

.action{$docIconDict := dict "Mon" "day_Today_1_Monday.png" "Tue" "day_Today_2_Tuesday.png" "Wed" "day_Today_3_Wednesday.png" "Thu" "day_Today_4_Thursday.png" "Fri" "day_Today_5_Friday.png" "Sat" "day_Today_6_Saturday.png" "Sun" "day_Today_7_Sunday.png"} 
.action{$docIconUrl := get $docIconDict $weekday}


{: icon="time/.action{$docIconUrl}"   type="doc"}
```

#### 列表

```template
.action{/*--注释：slice list num 相当于 list[num:]，这一步相当于是只计算子文档相对于当前文档的层次数 --*/}
.action{$a:=slice $a $p_len}
```

#### 常用数值计算函数

- Sprig 函数

  - 整型 int 计算：完整文档见 [https://masterminds.github.io/sprig/math.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fmath.html)

    - ​`add [<int64>,]`：`int64`，累加
    - ​`sub <int64> <int64>`：`int64`，减法
    - ​`mul [<int64>,]`：`int64`，累乘
    - ​`div <int64> <int64>` ：`int64`，整除
    - ​`mod <int64> <int64>`：`int64`，求余
    - ​`min [<int64>,]` 和 `max [<int64>,]`：`int64`，求最小值和最大值
  - 浮点型 float 计算：完整文档见 [https://masterminds.github.io/sprig/mathf.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fmathf.html)
  - > **注：Sprig 的数值运算是在 int64 和 float64 类型上进行的，但是很多函数只接受 int 或 float 类型，所以很多时候要配合类型转换函数来使用，这一点会在下面的小节中详细说明**
    >
- 思源内置数值函数

  - ​`pow <int>`：指数计算，返回整数
  - ​`powf <float>`：指数计算，返回浮点数
  - ​`log <int>`：对数计算，返回整数
  - ​`logf <float>`：对数计算，返回浮点数
  - ​`FormatFloat <format str> <n float64>`：`string`，说老实话我不能理解这个函数，这是一个老外要求加的，请参考

    - [https://pkg.go.dev/github.com/dustin/go-humanize#FormatFloat](https://ld246.com/forward?goto=https%3A%2F%2Fpkg.go.dev%2Fgithub.com%2Fdustin%2Fgo-humanize%23FormatFloat)
    - [https://github.com/siyuan-note/siyuan/issues/11158](https://ld246.com/forward?goto=https%3A%2F%2Fgithub.com%2Fsiyuan-note%2Fsiyuan%2Fissues%2F11158)
    - [https://liuyun.io/article/1713131424994](https://ld246.com/forward?goto=https%3A%2F%2Fliuyun.io%2Farticle%2F1713131424994)



案例:

```template
- add
  - {{ add 1 2 3 4 }} -> 10
- sub
  - {{ sub 4 1 }} -> 3
- mul
  - {{ mul 1 2 3 4 }} -> 24
- div
  - {{ div 5 2 }} -> 2.5
- mod
  - {{ mod 5 2 }} -> 1
- min/max
  - {{ min 5 1 }} -> 1
  - {{ max 5 1 }} -> 5
- pow
  - {{ pow 5 2 }} -> 25
- powf
  - {{ powf 2.5 2 }} -> 6.25
- log
  - {{ log 5 2 }} -> 2
- logf
  - {{ logf 5 2 }} -> 约 2.32
- FormatFloat
  - {{ FormatFloat "#,###.##" 2345.6789 }} -> 2,345.68
```

#### 常用的时间函数

- Sprig 常用函数

  - 所有函数见：[https://masterminds.github.io/sprig/date.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fdate.html)
  - ​`now`：`Time`，返回当前的时间
  - ​`date <fmt str> <Time>`：`str`, 将输入的时间对象格式化为字符串

    - ​`fmt` 使用 `2006-01-02 15:04:05` 这个固定时间格式（[知乎讨论](https://ld246.com/forward?goto=https%3A%2F%2Fwww.zhihu.com%2Fquestion%2F366830553)）
    - 教你如何记忆这个 🗑️ 垃圾到 😡 爆炸的 magin number

      - 首先年份固定是 2006
      - 后面的月日时分秒从 01 开始依次递增到 05
      - 所以标准格式为：`2006-01-02 03:04:05`​
      - 但是 `03:04:05` 是 12 小时制，所以如果想用 24 小时制，要换算成 `2006-01-02 15:04:05`​
  - ​`toDate <fmt str> <str>`：`Time` ，将一个字符串转换为一个时间对象

    - 注：思源内置的 `parseTime` 函数使用体验比这个函数要好一点
  - ​`duratioin <second: int>`：`Duration`, 将传入的秒数（int）转换为 `Duration` 对象
  - ​`date_modify`​

    ```template
    .action{$tomorrow := (now | date_modify "24h") | date "2006-01-02 "}
    ```
- 思源内置时间函数

  - ​`ISOWeek <Time>`：`int`，返回对应的时间对应今天的第几周
  - ​`Weekday <Time>`：`int`，返回对应的时间是星期几 ；`Sunday=0, Monday=1, ..., Saturday=6`​
  - ​`WeekdayCN <Time>`：`str`，返回对应的时间是星期几；`Sunday=日, Monday=一, ..., Saturday=六`​
  - ​`WeekdayCN2 <Time>`：`str`，返回对应的时间是星期几；`Sunday=天, Monday=一, ..., Saturday=六`​
  - ​`parseTime <string>`：`Time`，解析传入的时间字符串，返回一个时间类型

    ```template
    .action{$customDate :=parseTime "2025-08-27"}
    .action{$month := $customDate | ISOMonth}
    2025-08-27的ISOMonth是`.action{ternary (nospace (cat "0" $month)) $month (lt $month 10)}`
    ```
- ​`Time`：Golang 的 time.Time 类型，这个类型里面有不少有用的属性可以访问

  - **完整函数参考**：[https://pkg.go.dev/time#Time](https://ld246.com/forward?goto=https%3A%2F%2Fpkg.go.dev%2Ftime%23Time)

    - 请查找格式为 `func (t Time) Func(xxx) XXX` 的 API 文档
    - 这类函数（属性）都可以在模板中通过 `t.Func` 来调用
  - ​`Year`:  `int`​
  - ​`Month`: `Month`，这是一个枚举类型

    - 虽然显示是英文字符串，但是可以当作数值类型参与计算，例如 `add 1 now.Month`​
    - 详情参考：[https://pkg.go.dev/time#Month](https://ld246.com/forward?goto=https%3A%2F%2Fpkg.go.dev%2Ftime%23Month)
  - ​`Day`: `int`​
  - ​`Hour`: `int`​
  - ​`Minute`: `int`​
  - ​`Second`: `int`​
  - ​`Sub <Time>`: 计算两个时间之间的差，返回 `Duration`​
  - ​`Compare <Time>`：比较两个时间对象，返回 `int`, -1 或 0 或 1
  - ​`AddDate <year int> <month int> <day int>`: `int`，在当前的时间对象的基础上计算 N 天（月、 年）后的日期（参数可以为负数）

    ```template
    .action{$tomorrow := now.AddDate 0 0 1 | date "2006-01-02 "}
    ```

    - 注意，这个函数对月份的处理比较坑，只建议使用 year 和 day 这两个参数
    - 详情参考：[令人困惑的 Go time.AddDate](https://ld246.com/forward?goto=https%3A%2F%2Flearnku.com%2Farticles%2F71760)
- ​`Duration`: Golang 的 time.Duration 类型

  - **完整文档见**：[https://pkg.go.dev/time#Duration](https://ld246.com/forward?goto=https%3A%2F%2Fpkg.go.dev%2Ftime%23Duration)

    - 请查找格式为 `func (d Duration) Func(xxx) XXX` 的 API 文档
    - 这类函数是可以在模板中通过 `t.Func` 来调用
  - ​`Hours`：`float64`，将 Duration 转换为以小时为单位的数值
  - ​`Minutes`: `float64`，将 Duration 转换为以分钟为单位的数值
  - ​`Seconds`: `float64`，将 Duration 转换为以秒为单位的数值
  - ​`String`: `str`, 将 Duration 按照小时制转换为字符串，显示的格式为 "72h3m0.5s"

案例：

```template
- now
  - {{ now }}
- date
  - {{ date "2006-01-02 15:04:05" now }}
- toDate
  - {{ toDate "2006-01-02" "2020-01-01" }}
- duration
  - 1800 second: {{ duration 1800 }}
- ISOWeek
  - 第 {{ now | ISOWeek }} 周
- Weekday
  - 今天是星期:
  - {{ now | Weekday }} {{ now | WeekdayCN }} {{ now | WeekdayCN2 }}
- parseTime
  - {{ parseTime "2020-01-01 12:00:00" }}
- Time 对象
  - {{ $t := parseTime "2020-01-01 12:00:00" }}
  - {{ $t.Year }}/{{ $t.Month }}/{{ $t.Day }} {{ $t.Hour }}:{{ $t.Minute }}:{{ $t.Second }}
  - {{ now.Sub $t }}
  - {{ $t.Compare now }}
  - {{ $t.AddDate 0 0 7}}
- Duration 对象
  - {{ $du := now.Sub $t }}
  - {{ $du }}
  - {{ $du.Hours }}; {{ $du.Minutes }}; {{ $du.Seconds }}
  - {{ $du.String }}
```

日期计算可能是思源用户最常接触到的函数了，如果你是一个 daily note 用户，现在打开你主日记本，查看一下你日记的模板会发现它可能是这个样子:

```md
/daily note/{{now | date "2006/01"}}/{{now | date "2006-01-02"}}
```

现在我们有了理论基础，不妨就这个案例来看一下这个日记模板是怎么回事：

1. ​`{{}}` 是 Golang 标准的模板语法，没什么好说的
2. ​`now` 函数返回了一个 `Time` 对象
3. ​`|` 通过管道运算，把 `now` 的结果传给后面，所以相当于在运行 `date "2006/01"`​

    > 你可以把 `{{now | date "2006/01"}` 换成 `{{date "2006/01" now}}`；他们两个是完全等价的
    >
4. ​`date <fmt str> <Time>` 是固定搭配的用法，这里 `"2006/01"` 也是固定的用法
5. 所以最后，这个模板会被渲染为 `yyyy/mm` 这样的格式，和前面的组合起来，就会形成 `/daily note/<年份>/<月份>` 这样的路径字符串

#### 常用字符串操作函数

字符串操作函数在正常 md 模板里面用的没那么多，但是在数据库模板列里面可能会大量用到。

> 只列举了很小的一部分，完整文档见 [https://masterminds.github.io/sprig/strings.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fstrings.html) 和 [https://masterminds.github.io/sprig/string_slice.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fstring_slice.html)

- ​`trim <str>`: `str`， 将前后的空白字符去掉
- ​`repeat <int> <str>`：`str`，将给定的字符串重复若干次
- ​`substr <start int> <end int> <str>`: `str`，提取子字符串，index 从 0 开始
- ​`trunc <int> <str>`: `str`，将给定的字符串按照最大长度来截断；`<int>` 参数可以是负数，代表从末尾反向截断
- ​`abbrev <int> <str>`: `str`，同样是截断字符串，但是会在后面加上一个 `...`​
- ​`contains <part str> <whole str>`: `bool`，检测 `whole` 中是否包含 `part`​
- ​`cat [<str>,]`: `str`，将若干字符串拼接起来，中间通过空格间隔

  - cat默认是用空格间隔的，不太好用，可以用printf
- ​`replace <from str> <to str> <src str>` : `str`，将 `src` 中所有的 `from` 替换成 `to`​
- 正则表达式系列的函数（请自行翻阅[文档](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fstrings.html)）
- ​`join <ch str> <List[str]>`: `str`，将给定的字符串列表通过 `ch` 连接起来
- ​`splitList <ch str> <src str>`: `List[str]`，将给定的 `src` 字符串根据 `ch` 字符分割为列表

案例：

```template
- trim
  - {{ trim "   aa   " }} -> "aa"
- repeat
  - {{ repeat 5 "12" }} -> "1212121212"
- substr
  - {{ substr 1 3 "abcedfg" }} -> "bc"
- trunc
  - {{ trunc 3 "abcedfg" }} -> "abc"
  - {{ trunc -3 "abcedfg" }} -> "efg"
- abbrev
  - {{ abbrev 5 "hello world" }} -> "he..."
- contains
  - {{ contains "bb" "aabb" }} -> true
- cat
  - {{ cat "1" "2" "3" }} -> "1 2 3"
- replace
  - {{ replace "aa" "bb" "11aaccaa" }} -> "11bbccbb"
- join
  - {{ list "hello" "siyuan" | join "？" }} -> "hello？siyuan"
- splitList
  - {{ splitList "$" "foo$bar$baz" }} -> ["foo", "bar", "baz"]
```

#### 列表操作函数

列表类函数常常会配合 queryBlocks （见后面的小节） 一同使用。

完整文档请见：[https://masterminds.github.io/sprig/lists.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Flists.html)

- ​`list [<value>,]`：`List`，将后面传入的参数变成一个列表（类型要相同）
- ​`first <List>`：返回第一个列表项
- ​`last <List>`：返回最后一个列表项
- ​`append <List> <value>`：`List`，在列表后面增加一个元素
- ​`prepend <List> <value>`：`List`，在列表前面增加一个元素
- ​`concat [<List>,]`：`List`，将多个列表合并成一个
- ​`reverse <List>`：`List`，将列表逆序
- ​`has <value> <List>`：`bool`，检查给定的项目是否在列表中
- ​`index <List> <int>`：`List`，根据后面的索引值，索引列表中的内容
- ​`slice <List> <beg int> {<end int>}`：`List`，对给定的列表进行切片

  - ​`slice $myList` returns `[1 2 3 4 5]`. It is same as `myList[:]`.
  - ​`slice $myList 3` returns `[4 5]`. It is same as `myList[3:]`.
  - ​`slice $myList 1 3` returns `[2 3]`. It is same as `myList[1:3]`.
  - ​`slice $myList 0 3` returns `[1 2 3]`. It is same as `myList[:3]`.
- ​`empty <List>`：`bool`，检查列表是否为空
- ​`len <List>`：`int`，获取列表的长度

```template
- list
  - {{ list 1 2 3 4 }} -> [1 2 3 4]
  - {{ list "a" "b" "c" }} -> ["a" "b" "c"]
- first
  - {{ first (list 1 2 3) }} -> 1
  - {{ first (list "a" "b" "c") }} -> "a"
- last
  - {{ last (list 1 2 3) }} -> 3
  - {{ last (list "a" "b" "c") }} -> "c"
- append
  - {{ append (list 1 2 3) 4 }} -> [1 2 3 4]
  - {{ append (list "a" "b" "c") "d" }} -> ["a" "b" "c" "d"]
- prepend
  - {{ prepend (list 1 2 3) 0 }} -> [0 1 2 3]
  - {{ prepend (list "a" "b" "c") "z" }} -> ["z" "a" "b" "c"]
- concat
  - {{ concat (list 1 2) (list 3 4) }} -> [1 2 3 4]
  - {{ concat (list "a" "b") (list "c" "d") }} -> ["a" "b" "c" "d"]
- reverse
  - {{ reverse (list 1 2 3) }} -> [3 2 1]
  - {{ reverse (list "a" "b" "c") }} -> ["c" "b" "a"]
- has
  - {{ has 2 (list 1 2 3) }} -> true
  - {{ has "d" (list "a" "b" "c") }} -> false
- index
  - {{ index (list 1 2 3 4) 2 }} -> 3
  - {{ index (list "a" "b" "c" "d") 0}} -> "a"
- slice
  - {{ slice (list 1 2 3 4 5) 1 3 }} -> [2 3]
  - {{ slice (list "a" "b" "c" "d") 2 }} -> ["c" "d"]
- len
  - {{ list 1 2 3 4 | len }} -> 4
```

#### 类型转换函数

在思源一个笔记软件里面，纠结数据类型这种纯编程性的问题挺古怪的——但是只要你开始用模板功能，有些时候偏偏就会出现类型兼容性问题。

例如这个例子，他的作用是计算上一个周日的日期（这里我们姑且认为每周从周一开始）。

- 首先我们使用 `Weekday` 函数获取今天是星期几，数值范围为 0\~6
- 然后调用 AddDate 函数，减去星期数，就获得了周日的日期

```template
{{ $weekday := Weekday now }}
{{ now.AddDate 0 0 (mul -1 $weekday) }}
```

不过运行的这个模板的时候会报错，无法运行：

> 模板解析失败：template: :2:27: executing "" at \<\$weekday\>: wrong type for value; expected int; got int64 v3.0.12

> 附：顺便教一下怎么看这个报错信息。
>
> - 关注 `template: :2:27`，这代表了传入的模板的第二行，第二十七个字符的地方出现了错误
> - 具体的错误就是：「wrong type for value; expected int; got int64」，也就是传入的值的类型出了错。

报错的原因在于，`mul` 这些 Sprig 算术函数返回的类型是 `int64`，而 `Time.AddDate` 函数接受的类型却是 `int`，所以出现了类型不兼容问题。😡

为了解决这一问题，我们不得不进行使用类型转换函数，把 in64 转成 int 类型：

```template
{{ $weekday := Weekday now }}
{{ now.AddDate 0 0 (mul -1 $weekday | int) }}
```

**类型转换函数**同样是 Sprig 提供的，文档见：[https://masterminds.github.io/sprig/conversion.html](https://ld246.com/forward?goto=https%3A%2F%2Fmasterminds.github.io%2Fsprig%2Fconversion.html)

- atoi：将字符串转换为整数。
- float64：转换为 float64，即 64 位浮点数值。
- int：在系统宽度下转换为 int 整形数值。
- int64：转换为 64 位的整形数值。
- toDecimal：将 Unix 八进制转换为 int64。
- toString：转换为字符串。
- toStrings：将列表、切片或数组转换为字符串列表。

以下是一个简单的案例：

```template
- {{atoi "11"}} -> 11
- {{float64 1}} -> 1.0
- {{int "12"}} -> 12
- {{int64 1}} -> 1
  - 注意：有些函数的参数只接受 int，而有些只接受 int64，所以某些情况下不得不需要对 int 进行类型转换
- {{toDecimal "20"}} -> 16
  - 八进制的 "20" 就是十进制的 16
- {{toString 120}} -> "120"
- {{toStrings (list 1 2 3 4)}} -> [1 2 3 4]
```


