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
{: id="20250707190901-1593cp9"}

### 总体目标
{: id="20250707193151-2n3xd4p"}

- {: id="20250707190901-ns7wt18"}[ ] 工作计划
  {: id="20250707190901-idhj251"}

  - {: id="20250707190901-k0v48qb"}[ ] 论文计划
    {: id="20250707190901-u3dlxn5"}

    - {: id="20250707190901-m67xx2y"}[ ] 论文写作进度
      {: id="20250707190901-uvjkirj"}
    - {: id="20250707190901-n5csvlh"}[ ] 实验
      {: id="20250707190901-t29o1zq"}
    - {: id="20250707190901-j92abgv"}[ ] 软件
      {: id="20250707190901-xnoot7s"}
    {: id="20250707190901-fwygwqj"}
  {: id="20250707190901-b409u7t"}
- {: id="20250707190901-bxqjs2k"}[ ] 专业精进
  {: id="20250707190901-5zft132"}

  - {: id="20250707190901-36lsxfr"}[ ] 
    {: id="20250707190901-rizwdev"}
  {: id="20250707190901-vhadvum"}
- {: id="20250707190901-7tsypqo"}[ ] 生活娱乐
  {: id="20250707190901-1j0xlcn"}
- {: id="20250707193513-54mylcv"}[ ] 健康锻炼
  {: id="20250707193513-oit846h"}
- {: id="20250707193516-23d9jnr"}[ ] 人际关系
  {: id="20250707193516-nwajwpa"}
{: id="20250707190901-ihqejye"}

### 每日计划
{: id="20250707193143-rgoi54i"}

- {: id="20250708114714-d3cxkd2" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$monday| date "20060102 Mon"}
  {: id="20250708114714-6aja5w6"}

  - {: id="20250708114914-ijynu3y" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
    {: id="20250708114914-fox0syv"}

    - {: id="20250708114914-gywerru"}[ ] 
      {: id="20250708114914-8yt5ijf"}
    - {: id="20250708114914-8x3551z"}[ ] 
      {: id="20250708114914-l6c588m"}
    - {: id="20250708114914-gqulghy"}[ ] 
      {: id="20250708114914-zhdzmcz"}
    {: id="20250708114914-6u1byqd"}
  - {: id="20250708114914-l9ofw7l" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
    {: id="20250708114914-qox7s2l"}

    - {: id="20250708114914-oaatcuq"}
      {: id="20250708114914-2r2a2yu"}
    - {: id="20250708114914-2t946iy"}
      {: id="20250708114914-06m8cz4"}
    - {: id="20250708114914-noekc1p"}
      {: id="20250708114914-nhcx1x5"}
    {: id="20250708114914-jmq23zv"}
  - {: id="20250708114914-08vf28r" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
    {: id="20250708114914-pc0ay89"}

    - {: id="20250708114914-zo9k2ae"}
      {: id="20250708114914-uohj91d"}
    {: id="20250708114914-2xmshew"}
  {: id="20250708114914-zqjcgvr"}
- {: id="20250708114714-s95hei6" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$tuesday| date "20060102 Tue"}
  {: id="20250708114714-n8bi1ki"}

  - {: id="20250708114714-py8wy65" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
    {: id="20250708114714-0qwm7kq"}

    - {: id="20250708114714-7rthu7j"}[ ] 
      {: id="20250708114714-1cws4yb"}
    - {: id="20250708114714-vjc2b1q"}[ ] 
      {: id="20250708114714-v7kujqt"}
    - {: id="20250708114714-1gl474j"}[ ] 
      {: id="20250708114714-sp750va"}
    {: id="20250708114714-vewvbti"}
  - {: id="20250708114714-qh9un52" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
    {: id="20250708114714-26c64le"}

    - {: id="20250708114714-illslzg"}
      {: id="20250708114714-i3k6l0b"}
    - {: id="20250708114714-ew13x8m"}
      {: id="20250708114714-vh4ctgm"}
    - {: id="20250708114714-vekoygz"}
      {: id="20250708114714-5644ued"}
    {: id="20250708114714-h1oczop"}
  - {: style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);" id="20250708114714-zwwc4zg"}明天如何改进
    {: id="20250708114714-xqnoghu"}

    - {: id="20250708114714-vxme7j0"}
      {: id="20250708114714-8robp47"}
    {: id="20250708114714-gbf4zhc"}
  {: id="20250708114714-phsg2h9"}
- {: id="20250708114714-chkwkn8" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$wednesday| date "20060102 Wed"}
  {: id="20250708114714-238zr76"}

  - {: style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);" id="20250708114714-xzl9b1k"}计划
    {: id="20250708114714-pzy0dn9"}

    - {: id="20250708114714-2shqurn"}[ ] 
      {: id="20250708114714-rofmilb"}
    - {: id="20250708114714-aaxfn4f"}[ ] 
      {: id="20250708114714-rtnnyaq"}
    - {: id="20250708114714-xr62zrz"}[ ] 
      {: id="20250708114714-o5kaoox"}
    {: id="20250708114714-jmv26nw"}
  - {: id="20250708114714-mn9rzw4" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
    {: id="20250708114714-c93t4y3"}

    - {: id="20250708114714-zcjh2p6"}
      {: id="20250708114714-76h8aa2"}
    - {: id="20250708114714-gzapzfn"}
      {: id="20250708114714-g65j9cq"}
    - {: id="20250708114714-bsxvg4l"}
      {: id="20250708114714-il2kd29"}
    {: id="20250708114714-n71an7b"}
  - {: style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);" id="20250708114714-8cn41cf"}明天如何改进
    {: id="20250708114714-wvjmim2"}

    - {: id="20250708114714-mxpj3do"}
      {: id="20250708114714-rnk8vqb"}
    {: id="20250708114714-53eyhvk"}
  {: id="20250708114714-gk0pakb"}
- {: id="20250708114714-ybfsy9d" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$thursday| date "20060102 Thu"}
  {: id="20250708114714-5ibjpdw"}

  - {: id="20250708114714-g7et9uf" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
    {: id="20250708114714-kqrqia0"}

    - {: id="20250708114714-xd6gsvi"}[ ] 
      {: id="20250708114714-pegm8n1"}
    - {: id="20250708114714-7fj1wjg"}[ ] 
      {: id="20250708114714-nkxgq47"}
    - {: id="20250708114714-xc5ebsi"}[ ] 
      {: id="20250708114714-rlrgqoq"}
    {: id="20250708114714-o4i9ci3"}
  - {: id="20250708114714-s5bbld7" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
    {: id="20250708114714-d9enbw3"}

    - {: id="20250708114714-fv2ic2p"}
      {: id="20250708114714-evkzs0i"}
    - {: id="20250708114714-8s56i2h"}
      {: id="20250708114714-abclv3i"}
    - {: id="20250708114714-otfrrmr"}
      {: id="20250708114714-68ivhve"}
    {: id="20250708114714-c5v1fwp"}
  - {: id="20250708114714-16j67hx" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
    {: id="20250708114714-07adx54"}

    - {: id="20250708114714-418oph2"}
      {: id="20250708114714-21f4dww"}
    {: id="20250708114714-dbdvmc3"}
  {: id="20250708114714-wh7igwc"}
- {: id="20250708114714-ac1dje8" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$friday| date "20060102 Fri"}
  {: id="20250708114714-ldqyvpv"}

  - {: id="20250708114714-42uiguv" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
    {: id="20250708114714-8txgm1q"}

    - {: id="20250708114714-08kihyc"}[ ] 
      {: id="20250708114714-iebkyrk"}
    - {: id="20250708114714-sah52bf"}[ ] 
      {: id="20250708114714-7i4avz0"}
    - {: id="20250708114714-6s695qr"}[ ] 
      {: id="20250708114714-l3iri9t"}
    {: id="20250708114714-cw8j1tv"}
  - {: id="20250708114714-ppp46gs" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
    {: id="20250708114714-03djvax"}

    - {: id="20250708114714-v4rg64v"}
      {: id="20250708114714-j69xawo"}
    - {: id="20250708114714-3yshfwy"}
      {: id="20250708114714-z4rpv9q"}
    - {: id="20250708114714-o8kq1dy"}
      {: id="20250708114714-n9n883p"}
    {: id="20250708114714-7ktiyad"}
  - {: id="20250708114714-6fxxoss" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
    {: id="20250708114714-qwrrubz"}

    - {: id="20250708114714-jjimdxj"}
      {: id="20250708114714-i22h3i9"}
    {: id="20250708114714-reus7ga"}
  {: id="20250708114714-z4j1mcd"}
- {: id="20250708114714-ljhm3yq" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$saturday| date "20060102 Sat"}
  {: id="20250708114714-6ne8ryu"}

  - {: style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);" id="20250708114714-964jvp4"}计划
    {: id="20250708114714-bvgwo6e"}

    - {: id="20250708114714-u45et8f"}[ ] 
      {: id="20250708114714-zcwlnuw"}
    - {: id="20250708114714-w7e0504"}[ ] 
      {: id="20250708114714-rtl6wye"}
    - {: id="20250708114714-c1asyju"}[ ] 
      {: id="20250708114714-bx9yqks"}
    {: id="20250708114714-o5z9waj"}
  - {: style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);" id="20250708114714-dhxb3sm"}实际完成情况
    {: id="20250708114714-y2lry3l"}

    - {: id="20250708114714-6l4ygt7"}
      {: id="20250708114714-qe3thuc"}
    - {: id="20250708114714-vfarsia"}
      {: id="20250708114714-6pc0xws"}
    - {: id="20250708114714-wgaznto"}
      {: id="20250708114714-8fpe24y"}
    {: id="20250708114714-763ryiu"}
  - {: id="20250708114714-8snsdtu" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
    {: id="20250708114714-12yzpde"}

    - {: id="20250708114714-vbrnfnp"}
      {: id="20250708114714-co6kzmx"}
    {: id="20250708114714-d9zm7ga"}
  {: id="20250708114714-6pq5hx2"}
- {: id="20250708114714-1zio8hu" style="background-color: var(--b3-font-background3); --b3-parent-background: var(--b3-font-background3);"}### .action{$sunday| date "20060102 Sun"}
  {: id="20250708114714-i9s1vsw"}

  - {: id="20250708114714-rgs5aa7" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
    {: id="20250708114714-xt0z0yj"}

    - {: id="20250708114714-9xrsr6l"}[ ] 
      {: id="20250708114714-jjwr3k2"}
    - {: id="20250708114714-xeyt6gu"}[ ] 
      {: id="20250708114714-cvwqdmn"}
    - {: id="20250708114714-93avt2x"}[ ] 
      {: id="20250708114714-gsp9wjh"}
    {: id="20250708114714-pxg24kj"}
  - {: id="20250708114714-n12i886" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
    {: id="20250708114714-2z62uc0"}

    - {: id="20250708114714-3bpqqd6"}
      {: id="20250708114714-vyjwm2q"}
    - {: id="20250708114714-l225aj4"}
      {: id="20250708114714-bbg3uem"}
    - {: id="20250708114714-p8ndi56"}
      {: id="20250708114714-wztz3t7"}
    {: id="20250708114714-f2hw11e"}
  - {: id="20250708114714-xoqkijj" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
    {: id="20250708114714-vn2t5gp"}

    - {: id="20250708114714-3mr6mpt"}
      {: id="20250708114714-omfhcr5"}
    {: id="20250708114714-dtwvt5v"}
  {: id="20250708114714-jqeqyt6"}
{: custom-f="bg" id="20250708114714-x9spsfk"}


## 习惯打卡
{: id="20250120224352-qq1axd7"}

长期主义，做对自己长期有益的事，养成微习惯，让自己不断变好
{: id="20250120224352-k41yrut"}

| 习惯（✅🟠❌）                                              | 星期一 | 星期二 | 星期三 | 星期四 | 星期五 | 星期六 | 星期日                         |
| -------------------------------------------------------- | ------ | ------ | ------ | ------ | ------ | ------ | ------------------------------ |
| 起床后不要在床上玩手机<br />直接下床，下床再看手机<br /> |        |        |        |        |        |        |                                |
| 九点到工位                                               |        |        |        |        |        |        |                                |
| 为尽早发论文而努力                                       |        |        |        |        |        |        |                                |
| <br />每周至少读一篇论文                                 |        |        |        |        |        |        |                                |
| 健身                                                     |        |        |        |        |        |        |                                |
| 读神经科学公众号（追问等）                               |        |        |        |        |        |        |                                |
{: colgroup="|||||||" id="20250120224352-0x3nbpi"}

## 本周复盘
{: id="20240523002309-96h0acf"}

> 📝总结：
> {: id="20240806111949-1wlwayi"}
>
> {: id="20240806111949-6i1zueu"}
{: id="20240806111949-8ykpmfb" style="background-color: var(--b3-card-warning-background); color: var(--b3-card-warning-color);"}


### 本周成就
{: id="20250120224352-l9prpz1"}

* {: id="20250120224352-l34kjr9"}Project进展
  {: id="20250120224352-0dw239a"}

  * {: id="20250120224352-ywrrxvb"}ROI成像模块
    {: id="20250120224352-knlx0cv"}

    * {: id="20250120224352-8907s7k"}论文
      {: id="20250120224352-6mxdmxy"}
    * {: id="20250120224352-mi9osr1"}软件
      {: id="20250120224352-kgpznpm"}
    * {: id="20250120224352-qfffpbg"}实验
      {: id="20250120224352-kjdpnax"}
    {: id="20250120224352-9dwbrbr"}
  * {: id="20250120224352-0nk10fk"}完成了xxx
    {: id="20250120224352-uegurzs"}
  * {: id="20250120224352-tk9jfg0"}完成了xxx
    {: id="20250120224352-lemljpv"}
  {: id="20250120224352-maitgo0"}
* {: id="20250120224352-qbaf7nh"}Area进展
  {: id="20250120224352-cu1q77f"}

  * {: id="20250120224352-j1nrfuo"}深度学习
    {: id="20250120224352-6ekfyu4"}
  * {: id="20250120224352-159q178"}统计分析
    {: id="20250120224352-8et05c8"}
  * {: id="20250120224352-7w4m9ib"}神经科学
    {: id="20250120224352-1gayxjx"}
  * {: id="20250120224352-527b7bk"}编程
    {: id="20250120224352-1xzfvru"}
  {: id="20250120224352-qlrq3ag"}
* {: id="20250120224352-5ulm5t4"}Resources进展
  {: id="20250120224352-b2dirl6"}

  * {: id="20250120224352-afst16t"}阅读学习
    {: id="20250120224352-ostkufc"}
  * {: id="20250120224352-x40zjh9"}百科
    {: id="20250120224352-uv7q69q"}
  * {: id="20250120224352-nyjzt8p"}折腾
    {: id="20250120224352-euhrfub"}
  {: id="20250120224352-a1tsb11"}
* {: id="20250120224352-x4nvksw"}Life进展
  {: id="20250120224352-3x098fe"}

  * {: id="20250120224352-0lio882"}碎碎念
    {: id="20250120224352-dyxx2q2"}
  * {: id="20250120224352-v05xbhp"}遇见
    {: id="20250120224352-96xqzlj"}
  * {: id="20250120224352-kpiseww"}爱情进展
    {: id="20250120224352-xljcy4k"}

    * {: id="20250120224352-b6l27rd"}
      {: id="20250120224352-a5ha5ix"}
    {: id="20250120224352-mijpcuz"}
  * {: id="20250120224352-zufu4pi"}兴趣爱好
    {: id="20250120224352-y8cj7jy"}

    * {: id="20250120224352-znp8kks"}笔记方法
      {: id="20250120224352-lkpex0z"}
    * {: id="20250120224352-x985v46"}摄影
      {: id="20250120224352-u128d9q"}
    * {: id="20250120224352-2e4o26i"}尤克里里
      {: id="20250120224352-cr7yzms"}
    * {: id="20250120224352-53ehrmr"}游戏
      {: id="20250120224352-u9asbsk"}
    {: id="20250120224352-3ej0cdm"}
  * {: id="20250120224352-zxixv05"}健康
    {: id="20250120224352-lof48r4"}
  {: id="20250120224352-rtxp4yh"}
{: custom-f="dt" id="20250120224352-lm15jqj"}


### 本周问题清单&解决攻略
{: id="20240523002325-9su1wie"}

* {: id="20240523002409-vzsfqca"}
  {: id="20240523002409-5qthk73"}
{: id="20240523002409-tpwfulj"}

### 下周目标设定&下周计划
{: id="20240523002329-1wgqddc"}

* {: id="20240523002413-bew3e25"}
  {: id="20240523002413-uazoj1t"}
{: id="20240523002410-twzyyqj"}

{: id="20240523001634-fd42s8d" alias="weekplan" name="周复盘" title="思源笔记模板丨周复盘" type="doc"}