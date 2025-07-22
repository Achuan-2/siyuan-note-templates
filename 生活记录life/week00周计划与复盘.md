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

## 本周总体目标
{: id="20250721203747-8akstz6"}

1. {: id="20250721204243-7q4b59c"}<span data-type="strong">科研项目目标</span>
   {: id="20250721204243-b1414pk"}

   - {: id="20250721204243-4yzgce3"}[ ] 论文进度
     {: id="20250721204243-ypmrrne"}

     - {: id="20250721204243-sa8uu41"}[ ] 
       {: id="20250721204243-zz1e6lf"}
     {: id="20250721204243-f1y6at2"}
   - {: id="20250721204243-oh6to7p"}[ ] 实验
     {: id="20250721204243-6c5ppmm"}

     - {: id="20250721204243-lm2sexx"}[ ] 
       {: id="20250721204243-v5vrkpb"}
     {: id="20250721204243-ylh7uh6"}
   {: id="20250721204243-oyns4bs"}
2. {: id="20250721204243-gyw0oyf"}<span data-type="strong">专业精进目标</span>
   {: id="20250721204243-2hcf4kr"}

   - {: id="20250721204243-4l9s6hm"}[ ] 神经科学基础知识
     {: id="20250721204243-i36expo"}

     - {: id="20250721204243-8njai3w"}[ ] 
       {: id="20250721204243-hnbnkoh"}
     {: id="20250721204243-3tht2ps"}
   - {: id="20250721204243-y34mego"}[ ] 神经科学数据分析
     {: id="20250721204243-q7vraty"}

     - {: id="20250721204243-4m8bx2i"}[ ] 
       {: id="20250721204243-qotws5u"}
     {: id="20250721204243-m8swceu"}
   {: id="20250721204243-lhvpfo7"}
3. {: id="20250721204243-cgmtspq"}<span data-type="strong">赚钱与输出目标</span>
   {: id="20250721204243-9h9s800"}

   - {: id="20250721204243-t239ywd"}[ ] 
     {: id="20250721204243-o4s4xll"}
   {: id="20250721204243-3bz1d4z"}
4. {: id="20250721204243-r7ao4tu"}<span data-type="strong">习惯改进目标</span>
   {: id="20250721204243-7tlc5p5"}

   - {: id="20250721204243-6ve5n5g"}[ ] <span data-type="block-ref" data-subtype="s" data-id="20250609213741-645saw6">习惯改变丨早睡早起</span>：做到每天 24:30 点前睡觉，8 点起床
     {: id="20250721204243-88pchlc"}
   - {: id="20250722100908-4rvxnjw"}[ ] 每周进行至少 2 次体育锻炼（如跑步、游泳）
     {: id="20250722100908-w391gft"}

     - {: id="20250722100908-iu9cuaz"}周末安排游泳，周一、周四晚上 7-8 点进行跑步
       {: id="20250722100908-6xvrv9c"}
     {: id="20250722100908-1gwgu5x"}
   {: id="20250721204243-m94y064"}
5. {: id="20250721204243-bezgoax"}<span data-type="strong">生活娱乐目标</span>
   {: id="20250721204243-pgak6m4"}

   - {: id="20250722100913-hjtkefd"}[ ] 
     {: id="20250722100909-lkim5ke"}
   {: id="20250722100913-0lj6kjj"}
{: id="20250721204243-pevb3r5"}

## 每日计划
{: id="20250721203747-hogiuu5"}

#### .action{$monday| date "20060102 Mon"}
{: id="20250721203832-4mdisei"}

- {: style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);" id="20250721203832-8781zoz"}计划
  {: id="20250721203832-05x82ni"}

  - {: id="20250721203832-ypo79ga"}[ ] 
    {: id="20250721203832-0s4xera"}
  - {: id="20250721203832-dk81d8a"}[ ] 
    {: id="20250721203832-m13pq7n"}
  - {: id="20250721203832-i4jeh14"}[ ] 
    {: id="20250721203832-xwv8sew"}
  {: id="20250721203832-v9l9ktj"}
- {: style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);" id="20250721203832-4vehzkp"}实际完成情况
  {: id="20250721203832-k883azl"}

  - {: id="20250721203832-6z4uzr1"}
    {: id="20250721203832-vqd67zw"}
  - {: id="20250721203832-09orecu"}
    {: id="20250721203832-uytgdau"}
  - {: id="20250721203832-cur81bs"}
    {: id="20250721203832-zq2b8ya"}
  {: id="20250721203832-6qk70f2"}
- {: id="20250721203832-iilft2b" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721203832-kjpdoy0"}

  - {: id="20250721203832-7ix8x2v"}
    {: id="20250721203832-6cvthr5"}
  {: id="20250721203832-5g3mgb1"}
{: custom-f="bg" id="20250721203832-0c1ltf7"}

#### .action{$tuesday| date "20060102 Tue"}
{: id="20250721203827-3lr6q18"}

- {: id="20250721203827-xjh1q4c" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721203827-qt4sge6"}

  - {: id="20250721203827-v4i7r74"}[ ] 
    {: id="20250721203827-tqunpba"}
  - {: id="20250721203827-q16e0ks"}[ ] 
    {: id="20250721203827-555qd8h"}
  - {: id="20250721203827-iony3bw"}[ ] 
    {: id="20250721203827-ge6skx7"}
  {: id="20250721203827-qll7to1"}
- {: id="20250721203827-fmtq1id" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721203827-iz4uwui"}

  - {: id="20250721203827-pyajlf7"}
    {: id="20250721203827-y257snr"}
  - {: id="20250721203827-ooupdpl"}
    {: id="20250721203827-a18upvz"}
  - {: id="20250721203827-0gwu9l3"}
    {: id="20250721203827-j4ybovb"}
  {: id="20250721203827-3ovpoyk"}
- {: id="20250721203827-cesu35i" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721203827-0f5d7xw"}

  - {: id="20250721203827-qcgdq8k"}
    {: id="20250721203827-c86sj1x"}
  {: id="20250721203827-6i1qftq"}
{: custom-f="bg" id="20250721203827-7s4dr57"}

#### .action{$wednesday| date "20060102 Wed"}
{: id="20250721203827-1kdbq3w"}

- {: style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);" id="20250721203827-e7yxtef"}计划
  {: id="20250721203827-h2a2ln1"}

  - {: id="20250721203827-nku6ty1"}[ ] 
    {: id="20250721203827-nzej1s7"}
  - {: id="20250721203827-3auajh0"}[ ] 
    {: id="20250721203827-59yg801"}
  - {: id="20250721203827-jn875e5"}[ ] 
    {: id="20250721203827-z57regr"}
  {: id="20250721203827-wnguszm"}
- {: id="20250721203827-983a65u" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721203827-6tejqzn"}

  - {: id="20250721203827-jatcdee"}
    {: id="20250721203827-ts3m3ii"}
  - {: id="20250721203827-xvo9rd3"}
    {: id="20250721203827-s3t8jae"}
  - {: id="20250721203827-2jdcksc"}
    {: id="20250721203827-fqxalxd"}
  {: id="20250721203827-tmrhrbd"}
- {: id="20250721203827-f0zkecp" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721203827-j09h38p"}

  - {: id="20250721203827-ddzg6fd"}
    {: id="20250721203827-69yco1g"}
  {: id="20250721203827-4s87imn"}
{: custom-f="bg" id="20250721203827-3bp0uki"}

#### .action{$thursday| date "20060102 Thu"}
{: id="20250721203827-srowghe"}

- {: id="20250721203827-o1l3t4x" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721203827-a0qrmmv"}

  - {: id="20250721203827-xqu4dv8"}[ ] 
    {: id="20250721203827-vqs1t27"}
  - {: id="20250721203827-pmxlkas"}[ ] 
    {: id="20250721203827-utswf2t"}
  - {: id="20250721203827-4hmz6jq"}[ ] 
    {: id="20250721203827-az5x51l"}
  {: id="20250721203827-zkuzuet"}
- {: id="20250721203827-bcyhxst" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721203827-7gtmdk4"}

  - {: id="20250721203827-d4e9gxg"}
    {: id="20250721203827-rybhm8z"}
  - {: id="20250721203827-4sszlhs"}
    {: id="20250721203827-bxpxiv1"}
  - {: id="20250721203827-wo2t9zv"}
    {: id="20250721203827-zjirslz"}
  {: id="20250721203827-s9lggg8"}
- {: id="20250721203827-xjl6m7e" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721203827-7lz3yth"}

  - {: id="20250721203827-chner2x"}
    {: id="20250721203827-2m6hmwh"}
  {: id="20250721203827-y06j868"}
{: custom-f="bg" id="20250721203827-d2vwdzh"}

#### .action{$friday| date "20060102 Fri"}
{: id="20250721203827-0lyh5c4"}

- {: id="20250721203827-vhmh5bm" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721203827-5p0txzz"}

  - {: id="20250721203827-qs1cvo8"}[ ] 
    {: id="20250721203827-or0fm6x"}
  - {: id="20250721203827-nv88u1j"}[ ] 
    {: id="20250721203827-xibr9it"}
  - {: id="20250721203827-2g5u7ue"}[ ] 
    {: id="20250721203827-pnq1koj"}
  {: id="20250721203827-pax9tyx"}
- {: id="20250721203827-ntvpdvf" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721203827-bqgn4sb"}

  - {: id="20250721203827-gj5riex"}
    {: id="20250721203827-80hhpft"}
  - {: id="20250721203827-fe4i0pr"}
    {: id="20250721203827-jx84x6b"}
  - {: id="20250721203827-jx91uul"}
    {: id="20250721203827-9b1fbrj"}
  {: id="20250721203827-gtfolpq"}
- {: id="20250721203827-67c0gr1" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721203827-jr6mmxx"}

  - {: id="20250721203827-4ed8q8w"}
    {: id="20250721203827-k0riubf"}
  {: id="20250721203827-qs2ks76"}
{: custom-f="bg" id="20250721203827-6ee57bx"}

#### .action{$saturday| date "20060102 Sat"}
{: id="20250721203827-x7dln7x"}

- {: id="20250721203827-4649xvm" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721203827-dji4sd7"}

  - {: id="20250721203827-6srqvqn"}[ ] 
    {: id="20250721203827-0ykjjy6"}
  - {: id="20250721203827-upcph5h"}[ ] 
    {: id="20250721203827-vmfeex7"}
  - {: id="20250721203827-pf6p2nw"}[ ] 
    {: id="20250721203827-e4v19wv"}
  {: id="20250721203827-6j7icem"}
- {: id="20250721203827-ayvacxz" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721203827-wi4ntvf"}

  - {: id="20250721203827-p9xmr0w"}
    {: id="20250721203827-7m5izya"}
  - {: id="20250721203827-11l6yoc"}
    {: id="20250721203827-61kx4dp"}
  - {: id="20250721203827-uz5s7se"}
    {: id="20250721203827-b8bk2zo"}
  {: id="20250721203827-ydrsvhf"}
- {: style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);" id="20250721203827-sdfmtvb"}明天如何改进
  {: id="20250721203827-ms4tq6u"}

  - {: id="20250721203827-cx2p8re"}
    {: id="20250721203827-adn7x8v"}
  {: id="20250721203827-b0vyri8"}
{: custom-f="bg" id="20250721203827-8547row"}

#### .action{$sunday| date "20060102 Sun"}
{: id="20250721203827-5hsqx4f"}

- {: id="20250721203827-9l8c9cr" style="background-color: var(--b3-font-background2); --b3-parent-background: var(--b3-font-background2);"}计划
  {: id="20250721203827-uz2bcd6"}

  - {: id="20250721203827-yhuh3ao"}[ ] 
    {: id="20250721203827-nyzs0b2"}
  - {: id="20250721203827-o8ujpjr"}[ ] 
    {: id="20250721203827-9iatrl2"}
  - {: id="20250721203827-k4ksual"}[ ] 
    {: id="20250721203827-8d28qtw"}
  {: id="20250721203827-rzqiuoj"}
- {: id="20250721203827-evwby64" style="background-color: var(--b3-font-background1); --b3-parent-background: var(--b3-font-background1);"}实际完成情况
  {: id="20250721203827-j0kwaco"}

  - {: id="20250721203827-ohcgbon"}
    {: id="20250721203827-4nxjcdn"}
  - {: id="20250721203827-4codxyj"}
    {: id="20250721203827-eu1p6e4"}
  - {: id="20250721203827-pbqbpty"}
    {: id="20250721203827-uji6tan"}
  {: id="20250721203827-5nbn157"}
- {: id="20250721203827-y15bj8t" style="background-color: var(--b3-font-background4); --b3-parent-background: var(--b3-font-background4);"}明天如何改进
  {: id="20250721203827-7fpfemm"}

  - {: id="20250721203827-e3u8l12"}
    {: id="20250721203827-xgfr3vv"}
  {: id="20250721203827-6qr6qzq"}
{: custom-f="bg" id="20250721203827-at0spct"}

## 本周复盘
{: id="20250721203747-kdxaapn"}

### 本周成就
{: id="20250721203747-7pvy4yv"}

- {: id="20250721204026-zynnimt"}科研项目
  {: id="20250721204026-ouc0fyi"}

  - {: id="20250721204026-lopchgm"}我的项目
    {: id="20250721204026-n8wwckv"}

    - {: id="20250721204026-0rbg7rb"}论文
      {: id="20250721204026-84mkmrd"}

      - {: id="20250721204026-9k59vas"}
        {: id="20250721204026-zuz4ppb"}
      {: id="20250721204026-9b7dhux"}
    - {: id="20250721204026-vf6g5hm"}软件
      {: id="20250721204026-0tdk84i"}

      - {: id="20250721204026-x4mfymx"}
        {: id="20250721204026-9rfmtp1"}
      {: id="20250721204026-608ku6z"}
    - {: id="20250721204026-klqotg5"}实验
      {: id="20250721204026-7izfg3q"}

      - {: id="20250721204026-hnxtfk6"}
        {: id="20250721204026-ddnnal9"}
      {: id="20250721204026-psn5yjf"}
    {: id="20250721204026-u953kuo"}
  - {: id="20250721204026-zuuacbp"}其他事情
    {: id="20250721204026-ry5bj3z"}

    - {: id="20250721204026-mr9fcxs"}
      {: id="20250721204026-w0v9532"}
    {: id="20250721204026-zoivykk"}
  {: id="20250721204026-hooaqnh"}
- {: id="20250721204026-fy7q0nq"}专业精进
  {: id="20250721204026-uh3s1a7"}

  - {: id="20250721204026-1b21p0x"}神经科学基础知识
    {: id="20250721204026-kwvkygh"}

    - {: id="20250721204026-y1y7jcc"}
      {: id="20250721204026-atlw340"}
    {: id="20250721204026-nzegi48"}
  - {: id="20250721204026-c8z4sj8"}神经科学数据分析
    {: id="20250721204026-f4y7gme"}

    - {: id="20250721204026-rdhu9un"}
      {: id="20250721204026-gjdnjw1"}
    {: id="20250721204026-vd3rc5m"}
  {: id="20250721204026-o982yp4"}
- {: id="20250721204026-ben65dv"}赚钱与输出
  {: id="20250721204026-k4dpcsb"}

  - {: id="20250721204026-etmnpg4"}接单
    {: id="20250721204026-qhkgl3r"}

    - {: id="20250721204026-pxrehyz"}
      {: id="20250721204026-pw78j90"}
    {: id="20250721204026-khk67vu"}
  - {: id="20250721204026-5n4n1wz"}博客
    {: id="20250721204026-piq8nto"}

    - {: id="20250721204026-g7ewwtm"}
      {: id="20250721204026-52gjbft"}
    - {: id="20250721204026-mbzkdzu"}
      {: id="20250721204026-bh6ax3r"}
    {: id="20250721204026-bcz0ugr"}
  {: id="20250721204026-nm61tac"}
- {: id="20250721204026-b6i7krx"}习惯改进情况
  {: id="20250721204026-lugx90e"}

  - {: id="20250721204026-wcv8pdc"}早睡早起
    {: id="20250721204026-fbyxz4s"}
  - {: id="20250721204113-utrjghe"}每周锻炼至少两次
    {: id="20250721204113-5k155jr"}
  {: id="20250721204026-4o9ahp4"}
- {: id="20250721204026-jl29meo"}生活与娱乐
  {: id="20250721204026-fz58gr3"}

  - {: id="20250721204026-1qumxq2"}笔记
    {: id="20250721204026-qs7n8l4"}

    - {: id="20250721204026-xovukle"}
      {: id="20250721204026-s868pb6"}
    {: id="20250721204026-fbfwn5x"}
  - {: id="20250721204151-3q4pbs2"}有遇见有趣的事吗？
    {: id="20250721204151-4clhjvx"}

    - {: id="20250721204201-lgj4yd8"}
      {: id="20250721204201-2hn9d3r"}
    {: id="20250721204201-slgyy6r"}
  - {: id="20250721204026-p4k3pus"}爱情进展
    {: id="20250721204026-u9l25y0"}

    - {: id="20250721204026-likytkn"}
      {: id="20250721204026-9hailkm"}
    {: id="20250721204026-9apexzs"}
  - {: id="20250721204026-tcviftd"}健康
    {: id="20250721204026-3rb3ljw"}

    - {: id="20250721204026-178fv27"}
      {: id="20250721204026-oi83nug"}
    {: id="20250721204026-jcebjrm"}
  {: id="20250721204026-a5el4e9"}
{: custom-f="dt" id="20250721204026-7104vpi"}

### 本周问题清单&解决方案
{: id="20250721203747-vnrfd8y"}

- {: id="20250721203747-glp398x"}问题：
  {: id="20250721203747-nz4kzxi"}

  - {: id="20250721203747-40j1vfy"}解决方案：
    {: id="20250721203747-ea11pgz"}
  {: id="20250721203747-elicm31"}
- {: id="20250721203747-jrrxfhk"}问题：
  {: id="20250721203747-bn8nlxb"}

  - {: id="20250721203747-6vt2p51"}解决方案：
    {: id="20250721203747-v99wlgn"}
  {: id="20250721203747-xyc8uqh"}
- {: id="20250721203747-6x3fgcb"}问题：
  {: id="20250721203747-v6i2o2t"}

  - {: id="20250721203747-m96g9kc"}解决方案：
    {: id="20250721203747-n4owft0"}
  {: id="20250721203747-qb367py"}
{: id="20250721203747-mtsl8g0"}

### 下周目标设定&下周计划
{: id="20250721203747-2z00kk1"}

1. {: id="20250721203747-kuvu03g"}<span data-type="strong">科研项目目标</span>
   {: id="20250721203747-s9ryt45"}

   - {: id="20250721203747-sfyc1cz"}[ ] 论文进度
     {: id="20250721203747-1nfpybj"}

     - {: id="20250721203747-g00ssgr"}[ ] 
       {: id="20250721203747-papzv0p"}
     {: id="20250721203747-ytbro7d"}
   - {: id="20250721203747-o54y8jy"}[ ] 实验
     {: id="20250721203747-sjuihrl"}

     - {: id="20250721203747-rke1khf"}[ ] 
       {: id="20250721203747-ynzh0nu"}
     {: id="20250721203747-m8zzbjj"}
   {: id="20250721203747-ccgomw2"}
2. {: id="20250721203747-snxxr5j"}<span data-type="strong">专业精进目标</span>
   {: id="20250721203747-q0nw49i"}

   - {: id="20250721203747-3peztol"}[ ] 神经科学基础知识
     {: id="20250721203747-1sqfrn5"}

     - {: id="20250721204001-2vo8j9i"}[ ] 
       {: id="20250721204001-bs3ye18"}
     {: id="20250721204001-7fd57ca"}
   - {: id="20250721203747-0kwu1gj"}[ ] 神经科学数据分析
     {: id="20250721203747-5bfcq2s"}

     - {: id="20250721204003-gl2oj7o"}[ ] 
       {: id="20250721204003-h6yq0qd"}
     {: id="20250721204003-1ljfywg"}
   {: id="20250721203747-t62qs1b"}
3. {: id="20250721203747-pyty794"}<span data-type="strong">赚钱与输出目标</span>
   {: id="20250721203747-bq89bm3"}

   - {: id="20250721203747-3z7382s"}[ ] 
     {: id="20250721203747-ue8uwi6"}
   {: id="20250721203747-w9jq712"}
4. {: id="20250721203747-18e5q1o"}<span data-type="strong">习惯改进目标</span>
   {: id="20250721203747-7g4em7a"}

   - {: id="20250721203747-tcqe3od"}[ ] 做到每天 24:30 点前睡觉，8 点起床
     {: id="20250721203747-jc59uaj"}
   - {: id="20250722101013-nbl674q"}[ ] 每周进行至少 2 次体育锻炼（如跑步、游泳）
     {: id="20250722101013-c5bbofh"}

     - {: id="20250722101013-9a3n7dy"}周末安排游泳，周一、周四晚上 7-8 点进行跑步
       {: id="20250722101013-dusqwxy"}
     {: id="20250722101013-7msjw6n"}
   {: id="20250721203747-nf9fwd9"}
5. {: id="20250721203747-mg0kxot"}<span data-type="strong">生活与娱乐</span>
   {: id="20250721203747-j12coyy"}

   - {: id="20250722101109-smyq19h"}[ ] 
     {: id="20250722101109-y7khw2w"}
   {: id="20250722101109-b8dgzzt"}
{: id="20250721203747-satsd1y"}

{: id="20240523001634-fd42s8d" alias="weekplan" name="周复盘" title="思源笔记模板丨周复盘" type="doc"}