.action{/*<!-- 计算本周每一天的日期 -->*/}
.action{$weekday := ternary 7 (int (now | Weekday)) (eq (int (now | Weekday)) 0)}
.action{$monday := now.AddDate 0 0 (int (sub 1 $weekday))}
.action{$tuesday := $monday.AddDate 0 0 1}
.action{$wednesday := $monday.AddDate 0 0 2}
.action{$thursday := $monday.AddDate 0 0 3}
.action{$friday := $monday.AddDate 0 0 4}
.action{$saturday := $monday.AddDate 0 0 5}
.action{$sunday := $monday.AddDate 0 0 6}

.action{/*<!-- 获取今天的日期用于标记 -->*/}
.action{$today := (now | date "20060102")}


## 周计划
{: id="20250721100702-0k3lhib"}

### 总体目标
{: id="20250721100702-arcn80j"}

- {: id="20250721100702-62mod5u"}[ ] 工作计划
  {: id="20250721100702-ufcggab"}

  - {: id="20250721100702-du6aw2l"}[ ] 论文计划
    {: id="20250721100702-vk6ywqh"}

    - {: id="20250721100702-xycipl8"}[ ] 论文写作进度
      {: id="20250721100702-ihzpkka"}
    - {: id="20250721100702-5bjc68q"}[ ] 实验
      {: id="20250721100702-p42kpgy"}
    - {: id="20250721100702-vpj4j6q"}[ ] 软件
      {: id="20250721100702-ojdl675"}
    {: id="20250721100702-2l46l68"}
  {: id="20250721100702-fc0zbir"}
- {: id="20250721100702-qes1596"}[ ] 专业精进
  {: id="20250721100702-p47irrz"}

  - {: id="20250721100702-arypi6c"}[ ] 
    {: id="20250721100702-y0elp9a"}
  {: id="20250721100702-okehbst"}
- {: id="20250721100702-a0j66pj"}[ ] 生活娱乐
  {: id="20250721100702-xdhd33f"}
- {: id="20250721100702-y87eevs"}[ ] 健康锻炼
  {: id="20250721100702-6fg614r"}
- {: id="20250721100702-bug7397"}[ ] 人际关系
  {: id="20250721100702-ksp2gzu"}
{: id="20250721100702-xe60ta3"}

### 每日计划
{: id="20250721100702-0i7893a"}

#### .action{$monday| date "20060102 Mon"}
{: id="20250721100702-fm5cexu"}

- {: id="20250721100702-k8ulj8r" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-4rpdp1b"}

  - {: id="20250721100702-gkzp3mk"}[ ] 整理一周笔记
    {: id="20250721100702-ri4ws4s"}
  - {: id="20250721100702-5ghhgll"}[ ] 
    {: id="20250721100702-qt6w7q4"}
  - {: id="20250721100702-sr6rk4k"}[ ] 
    {: id="20250721100702-e8j558h"}
  {: id="20250721100702-5w8c8p1"}
- {: id="20250721100702-d9ai9lm" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721100702-4572hxv"}

  - {: id="20250721100702-gsdz6sq"}
    {: id="20250721100702-8thgj7c"}
  - {: id="20250721100702-wzfkl08"}
    {: id="20250721100702-af71g75"}
  - {: id="20250721100702-aoyoewn"}
    {: id="20250721100702-doi0e2y"}
  {: id="20250721100702-e3myfn1"}
- {: id="20250721100702-h19m39b" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721100702-78x7w2n"}

  - {: id="20250721100702-tif0o74"}
    {: id="20250721100702-x6sp7vs"}
  {: id="20250721100702-ggjleap"}
{: custom-f="bg" id="20250721100702-b490eq7"}

#### .action{$tuesday| date "20060102 Tue"}
{: id="20250721100702-f6et2bh"}

- {: id="20250721100702-wo1g4yi" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-8fixuox"}

  - {: id="20250721100702-vnxv5hm"}[ ] 
    {: id="20250721100702-3udkvlf"}
  - {: id="20250721100702-jrhnbtl"}[ ] 
    {: id="20250721100702-dmp6pih"}
  - {: id="20250721100702-9w6m2lx"}[ ] 
    {: id="20250721100702-4wzn4w1"}
  {: id="20250721100702-b84xnn4"}
- {: style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);" id="20250721100702-vn5968y"}实际完成情况
  {: id="20250721100702-o5rxb18"}

  - {: id="20250721100702-73dvval"}
    {: id="20250721100702-xauhwk3"}
  - {: id="20250721100702-q4qya9b"}
    {: id="20250721100702-gduj351"}
  - {: id="20250721100702-ah611fq"}
    {: id="20250721100702-jgplhhv"}
  {: id="20250721100702-eqn7xoi"}
- {: id="20250721100702-y6algz4" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721100702-uerphvb"}

  - {: id="20250721100702-4g2vkaa"}
    {: id="20250721100702-wfpv5id"}
  {: id="20250721100702-b8qg60b"}
{: custom-f="bg" id="20250721100702-t21u4vf"}

#### .action{$wednesday| date "20060102 Wed"}
{: id="20250721100702-f49jvlk"}

- {: id="20250721100702-ikl6v35" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-c16vulu"}

  - {: id="20250721100702-lbxtyo2"}[ ] 
    {: id="20250721100702-xibhf1z"}
  - {: id="20250721100702-xk19luc"}[ ] 
    {: id="20250721100702-n1leb7s"}
  - {: id="20250721100702-20ukkrl"}[ ] 
    {: id="20250721100702-tfq6ll7"}
  {: id="20250721100702-4sk6nqs"}
- {: id="20250721100702-8nj9x0w" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721100702-0krur9w"}

  - {: id="20250721100702-k5da2dc"}
    {: id="20250721100702-910xczc"}
  - {: id="20250721100702-ltf2x4h"}
    {: id="20250721100702-2ej401j"}
  - {: id="20250721100702-pkw92da"}
    {: id="20250721100702-p8rj50m"}
  {: id="20250721100702-8sd7jyi"}
- {: id="20250721100702-gzl0snp" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721100702-aevlzfj"}

  - {: id="20250721100702-5bli0jo"}
    {: id="20250721100702-v2gzq9o"}
  {: id="20250721100702-rc1x3c7"}
{: id="20250721100702-ilkmj3e" custom-f="bg"}

#### .action{$thursday| date "20060102 Thu"}
{: id="20250721100702-dy7tblu"}

- {: id="20250721100702-hda5iwl" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-h88q047"}

  - {: id="20250721100702-0owwtrc"}[ ] 
    {: id="20250721100702-i0rzlnc"}
  - {: id="20250721100702-k8p3h5j"}[ ] 
    {: id="20250721100702-zsuipgw"}
  - {: id="20250721100702-cqeqg93"}[ ] 
    {: id="20250721100702-25izk2y"}
  {: id="20250721100702-xdn4ge0"}
- {: id="20250721100702-tm4y8jc" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721100702-96iieop"}

  - {: id="20250721100702-l2uikrb"}
    {: id="20250721100702-rz22rmh"}
  - {: id="20250721100702-f3etzi5"}
    {: id="20250721100702-z4f970q"}
  - {: id="20250721100702-olbx8lv"}
    {: id="20250721100702-t7e8qcw"}
  {: id="20250721100702-cfw7isp"}
- {: style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);" id="20250721100702-lq3jn63"}明天如何改进
  {: id="20250721100702-7ox5lk9"}

  - {: id="20250721100702-m2d1nlo"}
    {: id="20250721100702-w78yym1"}
  {: id="20250721100702-h0suol5"}
{: custom-f="bg" id="20250721100702-vb0d7o4"}

#### .action{$friday| date "20060102 Fri"}
{: id="20250721100702-fsarif7"}

- {: id="20250721100702-91iu75r" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-uzk3mfc"}

  - {: id="20250721100702-8om5ubb"}[ ] 
    {: id="20250721100702-mjakaon"}
  - {: id="20250721100702-yd9qewa"}[ ] 
    {: id="20250721100702-3mull5n"}
  - {: id="20250721100702-whm2pf2"}[ ] 
    {: id="20250721100702-5fyu29e"}
  {: id="20250721100702-bwark36"}
- {: style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);" id="20250721100702-bkeur2e"}实际完成情况
  {: id="20250721100702-4s7pys1"}

  - {: id="20250721100702-reippiz"}
    {: id="20250721100702-kb7807x"}
  - {: id="20250721100702-5keqoix"}
    {: id="20250721100702-li44s5w"}
  - {: id="20250721100702-soamrhb"}
    {: id="20250721100702-izxh0ct"}
  {: id="20250721100702-s8ro0qt"}
- {: id="20250721100702-zbpn913" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721100702-dc42j11"}

  - {: id="20250721100702-h23fw14"}
    {: id="20250721100702-zd0njva"}
  {: id="20250721100702-f0sz073"}
{: custom-f="bg" id="20250721100702-34fgh5i"}

#### .action{$saturday| date "20060102 Sat"}
{: id="20250721100702-32pc825"}

- {: id="20250721100702-0rl49gx" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-gagfw45"}

  - {: id="20250721100702-alkzekk"}[ ] 
    {: id="20250721100702-4o4w190"}
  - {: id="20250721100702-25xvl9d"}[ ] 
    {: id="20250721100702-mle098t"}
  - {: id="20250721100702-hibxxii"}[ ] 
    {: id="20250721100702-ohjbnli"}
  {: id="20250721100702-qd3b9r8"}
- {: id="20250721100702-33twd7j" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721100702-j7q25fg"}

  - {: id="20250721100702-1yb2so9"}
    {: id="20250721100702-1msp81p"}
  - {: id="20250721100702-keu5v00"}
    {: id="20250721100702-v76n04b"}
  - {: id="20250721100702-nh8o530"}
    {: id="20250721100702-8t9t1ej"}
  {: id="20250721100702-oxbcsx3"}
- {: id="20250721100702-t6812w4" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721100702-yfhrqtu"}

  - {: id="20250721100702-0wjxrd8"}
    {: id="20250721100702-vhv6jfk"}
  {: id="20250721100702-pw6b33v"}
{: custom-f="bg" id="20250721100702-87oh1nu"}

#### .action{$sunday| date "20060102 Sun"}
{: id="20250721100702-f8d38e4"}

- {: id="20250721100702-iau13qv" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721100702-lpk18eg"}

  - {: id="20250721100702-836gevy"}[ ] 
    {: id="20250721100702-lygboaw"}
  - {: id="20250721100702-c5x89td"}[ ] 
    {: id="20250721100702-kkeb6uv"}
  - {: id="20250721100702-ubw47bk"}[ ] 
    {: id="20250721100702-0d045g8"}
  {: id="20250721100702-r6gl6br"}
- {: id="20250721100702-l2x9unl" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721100702-zuhzc8d"}

  - {: id="20250721100702-1thog9a"}
    {: id="20250721100702-mazftah"}
  - {: id="20250721100702-mevamms"}
    {: id="20250721100702-vlrerry"}
  - {: id="20250721100702-jwny7tx"}
    {: id="20250721100702-sp8985d"}
  {: id="20250721100702-bgpxpqk"}
- {: id="20250721100702-cj3xsor" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721100702-ua5m3p4"}

  - {: id="20250721100702-zl5km6r"}
    {: id="20250721100702-xou9p8a"}
  {: id="20250721100702-rbusp2o"}
{: custom-f="bg" id="20250721100702-3o4rmes"}

## 习惯打卡
{: id="20250721100702-r90cpkg"}

长期主义，做对自己长期有益的事，养成微习惯，让自己不断变好
{: id="20250721100702-of0og18"}

|习惯（✅🟠❌）|星期一|星期二|星期三|星期四|星期五|星期六|星期日|
| --------------------------------------------------| --------| --------| --------| --------| --------| --------| --------|
|起床后不要在床上玩手机<br />直接下床，下床再看手机<br />||||||||
|九点到工位||||||||
|为尽早发论文而努力||||||||
|<br />每周至少读一篇论文||||||||
|健身||||||||
|读神经科学公众号（追问等）||||||||
{: colgroup="|||||||" id="20250721100702-nqhl85r"}

## 本周复盘
{: id="20250721100702-0m6jfjk"}

> 📝总结：
> {: id="20250721100702-no5hal7"}
>
> {: id="20250721100702-0gt4ui8"}
{: id="20250721100702-w39pojb" style="background-color: var(--b3-card-warning-background); color: var(--b3-card-warning-color);"}

### 本周成就
{: id="20250721100702-6806dvt"}

- {: id="20250721100702-kov501h"}Project进展
  {: id="20250721100702-jyfn6hu"}

  - {: id="20250721100702-n2yqlwu"}ROI成像模块
    {: id="20250721100702-m3yyzz4"}

    - {: id="20250721100702-x7jl33q"}论文
      {: id="20250721100702-q028w7y"}
    - {: id="20250721100702-oelol2a"}软件
      {: id="20250721100702-m44tgte"}
    - {: id="20250721100702-2qmfgj6"}实验
      {: id="20250721100702-ofijr5b"}
    {: id="20250721100702-8ni20fk"}
  - {: id="20250721100702-iskh2s8"}完成了xxx
    {: id="20250721100702-9dgtxsi"}
  - {: id="20250721100702-gl6ic9v"}完成了xxx
    {: id="20250721100702-b518aeb"}
  {: id="20250721100702-g68mnqs"}
- {: id="20250721100702-aevynry"}Area进展
  {: id="20250721100702-zimtgau"}

  - {: id="20250721100702-wj6x77r"}深度学习
    {: id="20250721100702-z4sf6f6"}
  - {: id="20250721100702-4l26l9q"}统计分析
    {: id="20250721100702-k1dzgj6"}
  - {: id="20250721100702-p3em2ob"}神经科学
    {: id="20250721100702-p3ni7gq"}
  - {: id="20250721100702-1138x10"}编程
    {: id="20250721100702-hkouxvi"}
  {: id="20250721100702-81bdmu1"}
- {: id="20250721100702-j58avnd"}Resources进展
  {: id="20250721100702-578e6rm"}

  - {: id="20250721100702-0vsfzlz"}阅读学习
    {: id="20250721100702-3xtuy4g"}
  - {: id="20250721100702-w1vfjy4"}百科
    {: id="20250721100702-z8w1r1a"}
  - {: id="20250721100702-x5faunq"}折腾
    {: id="20250721100702-ef2vc5g"}
  {: id="20250721100702-g9o5m01"}
- {: id="20250721100702-x1yugd4"}Life进展
  {: id="20250721100702-61cidq3"}

  - {: id="20250721100702-yr3ekkh"}碎碎念
    {: id="20250721100702-x05h9vj"}
  - {: id="20250721100702-d8ibbvp"}遇见
    {: id="20250721100702-499qniq"}
  - {: id="20250721100702-i5clvd1"}爱情进展
    {: id="20250721100702-44tfx5m"}

    - {: id="20250721100702-kokkz3w"}
      {: id="20250721100702-9qmtrpf"}
    {: id="20250721100702-kyw66x6"}
  - {: id="20250721100702-a4ddsqy"}兴趣爱好
    {: id="20250721100702-hd75n1t"}

    - {: id="20250721100702-iboeiyw"}笔记方法
      {: id="20250721100702-7ofysy2"}
    - {: id="20250721100702-vdakevx"}摄影
      {: id="20250721100702-1v12xtx"}
    - {: id="20250721100702-xgqiyz2"}尤克里里
      {: id="20250721100702-v4swkhy"}
    - {: id="20250721100702-mrmjy2w"}游戏
      {: id="20250721100702-x1mymh5"}
    {: id="20250721100702-mypb12l"}
  - {: id="20250721100702-u1kr8pb"}健康
    {: id="20250721100702-3zn7a9v"}
  {: id="20250721100702-b1g8tju"}
{: custom-f="dt" id="20250721100702-icna5b1"}

### 本周问题清单&解决攻略
{: id="20250721100702-bae308f"}

- {: id="20250721100702-1ppm641"}
  {: id="20250721100702-ljupgf8"}
{: id="20250721100702-8p37jv2"}

### 下周目标设定&下周计划
{: id="20250721100702-d4tqykg"}

- {: id="20250721100702-iihkfre"}
  {: id="20250721100702-pvmh6dn"}
{: id="20250721100702-4giay5r"}

{: id="20250721100702-r93l2h9" alias="weekplan" custom-dailynote-20250721="20250721" name="周复盘" title="30周(07.21-07.27)" type="doc"}