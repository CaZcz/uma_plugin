## uma_info

这是一个适用hoshinobot的赛马娘功能插件，数据来自马娘官网和bwiki，所有功能的数据均可自动更新

这里包含了之前开源了的功能以及新开发的一大堆功能，其他功能仍在锐意开发中，有问题请提交issue，致力于解决所有issue（~~解决不了问题就解决出问题的人~~）

如遇安装问题可以先看看历史issue有没有类似的参考一下。

### ★ 如果你喜欢的话，请给仓库点一个star支持一下23333 ★

<details>
<summary>点我查看主要的几个功能模块</summary>

（具体命令请看本页面下方功能命令和描述）

+ [马娘新闻播报](https://github.com/azmiao/umamusume_news) 

+ [马娘模拟抽卡](https://github.com/azmiao/uma_gacha)

+ 马娘基础数据库

+ 支援卡节奏榜

+ 相性计算器

+ 马娘黄历

+ 马娘耐力计算器

+ 马娘表情包

+ 马娘漫画

+ 马娘限时任务

+ 马娘技能查询

</details>

<details>
<summary>点我查看独立版和整合版的区别</summary>

+ v1.5.2开始图片文件夹目录不一致，因此和独立版的马娘抽卡稍有不一致，但是删除独立版马娘抽卡后再装本整合版插件，理论上可以直接使用之前的图片文件

+ 另外后续关于 [马娘新闻播报](https://github.com/azmiao/umamusume_news) [马娘模拟抽卡](https://github.com/azmiao/uma_gacha) 的代码更新将会在原仓库和本仓库同步更新

+ 其他所有整合版里功能都不能单独拿出来直接用，必须带上 `uma_info` 才行

</details>

## 本项目地址：
https://github.com/azmiao/uma_plugin/

## 最近的更新日志

22-05-05    v2.0.1  优化更新逻辑，当更新失败自动回退防止再次更新时出错，同时更换数据镜像站提高更新速度

22-04-25    v2.0    大版本更新，强烈推荐，之后可无需APIKEY，注意：更新后需要更新安装依赖，并重新“手动更新马娘数据”

<details>
<summary>v2.0版本更新日志</summary>

1. 采用新方案来处理马娘基础数据库，目前采用方案如下：

    我在Github新建了一个仓库 [uma_info_data](https://github.com/azmiao/uma_info_data) ，该仓库使用了Github提供的Action，以workflow的形式运行获取马娘数据的代码，使用本人的APIKEY运行，已通过环境变量设置保护其内容，运行完成后自动上传到该仓库。

    因此，只要在本地img目录下持续git pull该仓库就可以获取最新数据，采用gitpython运行

2. 调整目录结构，将部分文件(字体文件)移动到根目录，以减小插件大小

3. 马娘黄历支持当日再次签到，不过还是之前签到过的内容，仅供查看

4. 文件图片目录调整， `img/umamusume` 文件夹下将马娘数据的图片分为 `base_data` 和 `extra_data `，以便基础数据库的更新

5. 整合首次启动和自动更新的代码，防止太多线程同时工作被反爬虫

6. 以及其他我也不记得哪里的修改

</details>

<details>
<summary>更以前的更新日志</summary>

22-04-24    v1.7    新增马娘技能查询功能

22-04-15    v1.6    新增马娘限时任务功能，并修复一些描述，此版本开始需要更新依赖

22-04-11    v1.5.3  修复图片文件夹的问题，并修复由于也文摄辉背景图分辨率过高导致OCR无结果的问题

22-04-10    v1.5.2  将所有的图片文件夹移动至umamusume文件夹下

22-03-30    v1.5.1  重构支援卡节奏榜代码，理论上性能更好，冗余更低

22-03-28    v1.5    新增马娘一格漫画功能

22-03-28    v1.4    新增马娘表情包功能

22-03-20    v1.3.3    节奏榜新增了 友人卡节奏榜

22-03-19    v1.3.2  新增了更新数据时自动下载语音文件，更新到此版本后需要手动更新一下数据，当然等半夜的自动更新也行

22-03-18    v1.3.1  调整了自动更新策略，将在更新时生成一个缓存文件，更新完再复制过去，以防止更新期间部分功能不能用，顺便新增手动更新相性信息功能

22-03-09    v1.3    新增了“马娘耐力计算器”功能，但数据为 根性与下坡 改版前的数据，且为非常理想的数值

22-03-09    v1.2    一些调整，以及修改部分文件使之规范化github储存库，方便 git pull, [pull #4](https://github.com/azmiao/uma_plugin/pull/4)

22-03-06    v1.1    新增了“马娘签到”功能

22-03-04    v1.0    first commit

</details>

## 注意事项

### 如何更新

#### 如何监控更新：建议使用 RSS 或者我之前的插件 [github_reminder](https://github.com/azmiao/github_reminder) 添加[本仓库链接](https://github.com/azmiao/uma_plugin/)监控本仓库commit，以便跟随功能更新和BUG修复

> 若是从 v1.2 版本之后(包括 v1.2)的版本更新到最新版，直接在你的 `hoshino/modules/uma_plugin文件夹里，打开powershell输入下方命令，运行完重启hoshinobot即可：

（注：v2.0开始请删除您的APIKEY.txt后再使用命令）

```
git pull
```

> 若是从 v1.2 版本之前(不包括 v1.2)的版本更新到最新版，建议直接把 `uma_plugin` 文件夹删了，再按照本页面最底下的安装教程重新安装一遍。并且建议删除前，把文件 `/uma_info/config.json` 备份出来，这样重新安装完就不用再手动更新马娘数据了。否则重装后需要重新使用群命令："手动更新马娘数据" 更新基础数据

</details>

## 功能命令和描述

### 注：群内查看功能帮助可以发送：“马娘帮助”

<details>
<summary><font size = 4>维护组的所有命令</font></summary>

马娘数据库的：

 - 手动更新马娘数据

马娘相性的：

 - 手动更新相性信息

马娘抽卡的：

 - 更新马娘信息

 - 重载赛马娘卡池

马娘表情包的：

 - 手动更新马娘表情包

马娘漫画的：

 - 手动更新马娘漫画

马娘限时任务的：

 - 手动更新限时任务

马娘技能的：

 - 手动更新马娘技能

</details>

<details>
<summary><font size = 4>马娘基础数据库模块</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 查今天生日马娘 | 看看今天哪只马娘生日(仅限马娘) |
| 查马娘生日 xx | xx为马娘名字，查询这只马娘是哪天生日(仅限马娘) |
| 查生日马娘 m-d | m-d就是 m月d日 ，查询这天有哪些马娘生日(仅限马娘) |
| 查角色id xx | xx为角色名字 |
| 查角色日文名 xx | xx为角色名字 |
| 查角色中文名 xx | xx为角色名字 |
| 查角色英文名 xx | xx为角色名字 |
| 查角色分类 xx | xx为角色名字 |
| 查角色语音 xx | xx为角色名字 |
| 查角色头像 xx | xx为角色名字 |
| 查角色cv xx | xx为角色名字 |
| 查角色身高 xx | xx为角色名字 |
| 查角色体重 xx | xx为角色名字 |
| 查角色三围 xx | xx为角色名字 |
| 查角色制服 xx | xx为角色名字 |
| 查角色决胜服 xx | xx为角色名字 |
| 查角色原案 xx | xx为角色名字 |
| 查角色适应性 xx | xx为角色名字 |
| 查角色详细信息 xx | xx为角色名字(显示全部信息) |
| 手动更新马娘数据 | 功能限维护组 |
| (每天1:31自动更新马娘数据) | 该功能没有命令 |
| (每天9:31自动推送该日生日的马娘) | 该功能没有命令，且本功能需额外开启 |

</details>

<details>
<summary><font size = 4>相性计算器</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘相性帮助 | 看看详细帮助内容 |
| 查相性 本体 父母1 祖父母1 祖父母2 父母2 祖父母3 祖父母4 胜鞍数 | 1.直接按照下面的指令写马名即可，请按顺序写，注意空格别漏<br>2.胜鞍数为胜鞍+金牌的总个数，类型为整数，且可写可不写<br>3.判断胜鞍：(父母1和祖父母1相同的重赏胜场数)+(父母1和祖父母2相同的重赏胜场数)+(父母2和祖父母3相同的重赏胜场数)+(父母2和祖父母4相同的重赏胜场数) |
| 查相性 本体 父母1 祖父母1 祖父母2 父母2 祖父母3 祖父母4 | 同上，表示可以不加胜鞍 |
| 查相性 马娘1 马娘2 | 查两只马娘之间的相性，这里不可以加胜鞍 |
| 相性榜 马娘 | 相性榜是指生成对这只马娘相性最好的马娘排行榜 |

</details>

<details>
<summary><font size = 4>支援卡节奏榜</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 速卡节奏榜 | 对应速度卡 |
| 耐卡节奏榜 | 对应耐力卡 |
| 力卡节奏榜 | 对应力量卡 |
| 根卡节奏榜 | 对应根性卡 |
| 智卡节奏榜 | 对应智力卡 |

</details>

<details>
<summary><font size = 4>马娘新闻播报</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘新闻 | 查看最近五条新闻 |
| 新闻翻译 | 查看翻译命令和新闻编号（限近5条） |
| 新闻翻译 1 | 翻译第1条新闻，编号可选值(1/2/3/4/5) |
| (马娘新闻推送) | 该功能没有命令，且本功能需额外开启 |

</details>

<details>
<summary><font size = 4>马娘模拟抽卡</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 查看马娘卡池 | 看马娘当前的池子 |
| @bot马娘单抽 | 马娘池子单抽 |
| @bot马娘十连 | 马娘池子十连 |
| @bot马之井 | 马娘池子抽一井 |
| @bot育成卡单抽 | 育成卡池子单抽 |
| @bot育成卡十连 | 育成卡池子十连 |
| @bot育成卡井 | 育成卡池子抽一井 |
| 更新马娘信息 | 更新图片数据等并自动重载赛马娘卡池，功能限维护组 |
| 重载赛马娘卡池 | 仅刷新马娘当前UP卡池的信息（不含图片数据），功能限维护组 |
| (每天4点自动更新马娘信息) | 该功能没有命令 |

</details>

<details>
<summary><font size = 4>马娘黄历</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘签到 | 看看今日的黄历？ |

</details>

<details>
<summary><font size = 4>马娘耐力计算器</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘耐力帮助 | 看看详细帮助内容 |
| 举个例子： |  |
| 算耐力<br>属性:1200 600 1200 600 700<br>适应性:逃马-A 芝-A 1600-A<br>干劲:绝好调 状况:良<br>固回:0 普回:0 金回:1 | 计算最低耐力需求 |

</details>

<details>
<summary><font size = 4>马娘表情包</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘表情包帮助 | 看看详细帮助内容 |
| 马娘表情包 | 随机一张马娘游戏内的表情包 |
| xxx表情包 | xxx为角色名字，没有该角色的表情包就不会有反应 |
| x号表情包 | x为数字，是表情包的编号，编号不是整数就不会有反应 |
| 查表情包含义 xxx | xxx为角色名字，没有该角色的表情包就不会有反应 |
| 查表情包含义 x号 | x为数字，是表情包的编号，编号不是整数就不会有反应 |

</details>

<details>
<summary><font size = 4>马娘漫画</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘漫画帮助 | 看看详细帮助内容 |
| 马娘漫画 | 随机一张马娘游戏内的一格漫画 |
| 马娘漫画 xxx | xxx为角色名字，没有该角色的一格漫画就不会有反应 |
| 马娘漫画 x号 | x为数字，是一格漫画的编号，编号不是整数就不会有反应 |

</details>

<details>
<summary><font size = 4>马娘限时任务</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘限时任务帮助 | 看看详细帮助内容 |
| 限时任务列表 | 查看所有的限定任务标题对应编号 |
| 限时任务x | x为列表中的编号，查看限时任务的内容 |
| 手动更新限时任务 | 强制刷新列表，限维护组 |

</details>

<details>
<summary><font size = 4>马娘技能查询</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘技能帮助 | 看看详细帮助内容 |
| 查技能 xxx | xxx为中/日文技能名<br>注意继承后的固有名为 "继承技/(固有名)"<br>例如"继承技/113転び114起き" |
| 查技能 (条件1) (条件2)... | 查技能后面可以加任意1个或多个条件，用空格隔开<br>例如"查技能 通用 妨害（速度）"，条件可选项如下 |
| TIP | 不需要的可不选，另外由于存在复合技能，因此技能类型可多选 |
| 稀有度可选 | ['普通', '传说', '独特', '普通·继承', '独特·继承', '剧情', '活动'] |
| 条件限制可选 | ['通用', '短距离', '英里', '中距离', '长距离', '泥地', '逃马', '先行', '差行', '追马'] |
| 技能颜色可选 | ['绿色', '紫色', '黄色', '蓝色', '红色'] |
| 技能类型可多选 | ['被动（速度）', '被动（耐力）', '被动（力量）', '被动（毅力）', '被动（智力）',<br>'耐力恢复', '速度', '加速度', '出闸', '视野', '切换跑道',<br>'妨害（速度）', '妨害（加速度）', '妨害（心态）', '妨害（智力）', '妨害（耐力恢复）', '妨害（视野）',<br>'(未知)'
] |

</details>

## 食用教程：

<details>
<summary>点我展开</summary>

1. git clone本插件（注：一定要git clone，不要下载压缩包，另外请确保git环境变量正常）：

    在 HoshinoBot\hoshino\modules 目录下使用以下命令拉取本项目
    ```
    git clone https://github.com/azmiao/uma_plugin
    ```

2. 如果之前装过独立版的 [马娘新闻播报](https://github.com/azmiao/umamusume_news) 和 [马娘模拟抽卡](https://github.com/azmiao/uma_gacha) 的，请先删除那两个文件夹，没有就跳过这一步

3. 安装依赖：

    到HoshinoBot\hoshino\modules\uma_plugin目录下，管理员方式打开powershell
    ```
    pip install -r requirements.txt -i http://mirrors.aliyun.com/pypi/simple --user
    ```

4. 在 HoshinoBot\hoshino\config\ `__bot__.py` 文件的 MODULES_ON 加入 'uma_plugin'

    然后重启 HoshinoBot

    装完插件后首次启动时会更新马娘各种数据，按带宽的大小可能需要3-10分钟不等，请耐心等待，您可以看着控制台看他有没有报错，除了在首次启动本插件的时候会在更新马娘基础数据库（要下好多语音文件和图片）的时候更新一段时间和马娘抽卡（要下好多图片）的时候更新一段时间，其他和再次启动的时候都会很快的。

6. 额外功能：（自动提醒）

    在某个群里发消息输入下文以开启马娘生日提醒
    ```
    开启 uma_bir_push
    ```

    在某个群里发消息输入下文以开启马娘新闻播报
    ```
    开启 umamusume-news-poller
    ```

    可以通过发消息输入"lssv"查看这个功能前面是不是⚪来确认是否开启成功

</details>

## 另有图片预览，请看：

https://www.594594.xyz/2022/03/04/uma_plugin/