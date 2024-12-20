快捷入口：[实验记录本](siyuan://blocks/20241009113128-gbxgj3m)丨[Life](siyuan://blocks/20230304225859-8xlywce) 丨 [人生改善计划！](siyuan://blocks/20230330111337-bfoss5l)
{: id="20240903002458-fak0ips" style="text-align: center;"}

## <span data-type="text">✅ Anticipation</span>{: style="background-color: var(--b3-font-background1); color: var(--b3-font-color1);"}


* 

## <span data-type="text">🗑Inbox</span>{: style="background-color: var(--b3-font-background5); color: var(--b3-font-color5);"}


* 

## <span data-type="text">📂Notes</span>{: style="background-color: var(--b3-card-success-background); color: var(--b3-card-success-color)"}
{: id="20241220113314-rpcgwkq"}

* {: id="20241220113314-f5igat2"}📂<span data-type="strong">Research Progress</span>
  {: id="20241220113314-iy2xxbr" style="background-color: var(--b3-card-error-background); color: var(--b3-card-error-color); --b3-parent-background: var(--b3-card-error-background);"}

  * {: id="20241220114309-gnk51an"}
    {: id="20241220114309-u8inwrr"}
  {: id="20241220114310-ljutd44"}
* {: id="20241220113314-5xsflc3"}📂<span data-type="strong">Project</span>
  {: id="20241220113314-j64ddg3" style="background-color: var(--b3-card-warning-background); color: var(--b3-card-warning-color); --b3-parent-background: var(--b3-card-warning-background);"}

  * {: id="20241220114311-h83658a"}
    {: id="20241220114311-xbthvmc"}
  {: id="20241220114311-ykmhqfo"}
* {: id="20241220113314-7onw5fp"}📂<span data-type="strong">Area</span>
  {: id="20241220113314-9b26s6p" style="background-color: var(--b3-card-info-background); color: var(--b3-card-info-color); --b3-parent-background: var(--b3-card-info-background);"}

  * {: id="20241220114313-qieso7k"}
    {: id="20241220114313-wgr8zfn"}
  {: id="20241220114313-0lhjrju"}
* {: id="20241220113314-gp44ek9"}📂<span data-type="strong">Resources</span>
  {: id="20241220113314-brp1don" style="background-color: var(--b3-card-success-background); color: var(--b3-card-success-color); --b3-parent-background: var(--b3-card-success-background);"}

  * {: id="20241220114314-gmyrcph"}
    {: id="20241220114314-k6chzjk"}
  {: id="20241220114314-cysvsvu"}
* {: id="20241220113314-ih9y7mo"}📂<span data-type="strong">Life</span>
  {: id="20241220113314-so6g5h0" style="background-color: var(--b3-font-background6); color: var(--b3-font-color6); --b3-parent-background: var(--b3-font-background6);"}

  * {: id="20241220114315-oswmqb4"}
    {: id="20241220114315-yama9xp"}
  {: id="20241220114315-p43v3w5"}
{: id="20241220113314-aqlu2d4"}

## <span data-type="text">🤔 Reflection</span>{: style="background-color: var(--b3-font-background8); color: var(--b3-font-color8);"}
{: id="20241220113314-7rmjgay"}

<span data-type="strong">❤️今天有什么值得记录的事情？我有什么进步？</span>
{: id="20241220113314-giilitz" style="background-color: var(--b3-font-background9); color: var(--b3-font-color9); --b3-parent-background: var(--b3-font-background9);"}

{: id="20241220113321-1tlz3hi"}

<span data-type="strong">💔我的不足！</span>
{: id="20241220113314-drgunoa" style="background-color: var(--b3-font-background9); color: var(--b3-font-color9); --b3-parent-background: var(--b3-font-background9);"}

{: id="20241220114306-idsh5yi"}

<span data-type="strong">🤔我的反思！明天有没有什么东西下定决心要改变？</span>
{: id="20241220113314-aeflnue" style="background-color: var(--b3-font-background9); color: var(--b3-font-color9); --b3-parent-background: var(--b3-font-background9);"}

{: id="20241220113314-5gjgzmg" custom-avs="20240603145957-g2zn3br" custom-dailynote-20241220="20241220" icon="api/icon/getDynamicIcon?type=6&amp;date=2024-12-20&amp;color=%23d13d51" title="20241220 Fri" type="doc"}





.action{/* 获取今天日期和星期 */}
.action{$today := now | date "2006-01-02" }
.action{$weekday := now | date "Mon" }
.action{/* 工作日用红色图标，周末用蓝色图标，%23代表#号，URL不能直接输入#号，所以用URL编码%23代替 */}
.action{$color := "%23d13d51"}
.action{if or (eq $weekday "Sat")  (eq $weekday "Sun") }
.action{$color = "%233eb0ea"}
.action{end} 
.action{/* 设置文档图标：选择type6，仅返回星期样式 */}

{: icon="api/icon/getDynamicIcon?type=6&date=.action{$today}&color=.action{$color}"   type="doc"}
