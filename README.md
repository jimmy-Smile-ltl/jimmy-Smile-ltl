<div align="center">
  <picture>
    <source media="(min-width: 641px)" srcset="assets/observer.svg">
    <img src="assets/observer-tall.svg" alt="观测者，旧时代的余孽，在聆听时代的声音" width="100%">
  </picture>
</div>

<div align="center">
<p>目次 · <a href="#新的时代来了">新时代</a> · <a href="#试图征服世界">试图征服世界</a> · <a href="#征服之路上的坐标">坐标</a> · <a href="#一些旧物">旧物</a> · <a href="#毕业记录">毕业</a></p>
</div>

## 新的时代来了

何谓新时代？世人总以为它会敲锣打鼓地来。它不。它只留下证据，像潮水留下贝壳。旧时代的余孽，不过是其中一枚。

- **2016.03 · AlphaGo** —— 机器在人类自以为独属的直觉领域落子，并且赢了。
- **2022.11.30 · ChatGPT** —— 对话框成为新的入口，凡人排队走了进去。
- **2025.05.22 · Claude Code 正式发布** —— 从对话到做事：Agent 走进终端，读仓库、改代码、留下提交。人只负责签字。
- **2026.11.20 · 黎曼猜想** —— 一份六周，一千七百万行 Lean，形式化核验通过；一份十二年，九百四十页人类手稿仍在修订。

凡人称之为历史。观测者只看见，又一批人照例老去。

> 道心受损，照例值夜。<br>
> 观测者的前行，不过是把今夜写完。

听完了。夜班开始。

<div align="center">
<h2>试图征服世界</h2>
<i>有些事业注定不会成功，但那正是它每晚重启的理由。</i>
</div>

> *"Gee, Brain, what do you want to do tonight?"*
> *"The same thing we do every night, Pinky — try to take over the world!"*
>
> 「哎呀，大脑鼠，你今晚想做什么？」
> 「和我们每晚一样，粉红鼠——试图征服世界！」

这句台词出自 1995 年的动画《粉红鼠与大脑鼠》（*Pinky and the Brain*）。两只实验室小鼠每晚重复同一个问题，也重复同一个答案。多年以后，它成了全世界夜行者的接头暗号——

深夜十一点，办公室亮着最后一盏灯。有人问：今晚加班做什么？

> 和每天晚上一样，试图征服世界。

<div align="center">
<i>推石头的人不期待山顶。应当设想，大脑鼠是幸福的。</i>
</div>

<div align="center">
  <img src="assets/divider.svg" alt="" width="100%">
</div>

## 征服之路上的坐标

一些在深夜里写下的东西，按用途归档。标着「已归档」的坐标已经停更，留在这里，权当考古现场。

### LLM Agent · 智能采集

| 项目 | 简介 |
| --- | --- |
| [forager-faculty](https://github.com/jimmy-Smile-ltl/forager-faculty) | LLM 驱动的自适应高校教师信息采集框架：评估-修复-再评估闭环、四阶段流水线、五级反 WAF 请求栈 <details><summary>详情</summary><br>· evaluate-fix-re-evaluate 自愈闭环，质量不达标自动诊断重跑<br>· 四阶段流水线：学校 → 院系 → 教师名录 → 教师详情<br>· 五级反 WAF 请求栈：curl_cffi TLS 伪装、浏览器兜底<br>· 实战：144 所高校、40.5 万教师无人值守跑完</details> |
| [forager-epaper](https://github.com/jimmy-Smile-ltl/forager-epaper) | Paper Daily：中文日报自动采集流水线，一条命令生成生产级爬虫，自愈反馈环 + 零配置降级 <details><summary>详情</summary><br>· 一条命令：报纸名 → 发现入口 → 侦查结构 → 生成 spider → 验证打分 → 入库<br>· LLM 只在三个固定工位工作，管线控制流由代码固定<br>· 质量分 <60 自动诊断改进（≤3 轮），失败自愈<br>· 无 MySQL / PG / Mongo 时自动降级本地 JSONL，零配置可跑<br>· 20 个开箱示例站点 + 上千站点知识库</details> |
| [forager-gov](https://github.com/jimmy-Smile-ltl/forager-gov) | 中国政府网站体系图谱：从中央到省、市、县梳理各级人民政府及人大、政协、法院、检察院、监委、群团等条线官网，块 × 条双维树 + 列表 / 树图 / 地图三视图。线上站点：<https://forager-gov.pages.dev> <details><summary>详情</summary><br>· 规模：31 省区市 + 新疆兵团 · 333 地级市 · 近 3,000 县级，3 万+ 机构与区划节点<br>· 双维：块视图按行政区划逐级下钻；条视图把 16 个垂直系统按省—市—县重组<br>· 视图：机构清单 / 思维导图式树图 / 三级下钻地图，覆盖率着色 + 数据健康面板<br>· 采集纪律：零域名猜测，URL 全部来自上级官网名录、政府门户导航或严格验证的官方页面<br>· 数据：统一机构记录（USR）落 tree.json / site_registry.json，三视图同源消费<br>· 发布：Cloudflare Pages，push 自动构建</details> |

### LLM Agent · 开发工具

| 项目 | 简介 |
| --- | --- |
| [agent-multi-token](https://github.com/jimmy-Smile-ltl/agent-multi-token) <sup>已归档</sup> | 把 Claude Code / Codex CLI 的全局唯一配置变成按路径解析的身份：一个目录一个 token、一个 profile、一份互不串味的会话历史 <details><summary>详情</summary><br>· 两个零依赖 Node CLI：cmt 包装 Claude Code、cxt 包装 Codex，按 cwd 分层解析 token / baseUrl / model<br>· 分层合并：全局默认 → token → 路径绑定 → 项目内 .cmt.json / .cxt.json，CLI 参数最高；四要素缺失或 ${VAR} 未展开直接拒绝启动<br>· 一个 token 一个 profile（CLAUDE_CONFIG_DIR / CODEX_HOME），多窗口并行互不串味；run / exec 两段式启动，先清理继承环境再注入身份<br>· TUI + 本地 Web 控制台共用同一套逻辑；另有 token 池、用量费用、会话注册表、文件邮箱<br>· Node ≥ 18、零运行时依赖、无构建步骤；Windows 为主测平台<br>· 已归档，作为「带可执行证据的设计文档」发布；MIT，未发布 npm</details> |

### 爬虫框架与工程

| 项目 | 简介 |
| --- | --- |
| [jimmySpider](https://github.com/jimmy-Smile-ltl/jimmySpider) | 从 140+ 网站实战提炼的 Python 爬虫框架：6 种请求处理器、TLS 指纹伪装、断点续爬 <details><summary>详情</summary><br>· 6 种请求处理器：单线程 / 多线程 / 异步 + curl_cffi TLS 指纹伪装<br>· 断点续爬、反爬策略、配置驱动<br>· 140+ 网站实战沉淀，MIT</details> |
| [clash_proxy](https://github.com/jimmy-Smile-ltl/clash_proxy) | 把机场闲置节点管成爬虫代理池：自动测速、轮换、封禁切换、挂掉自愈 <details><summary>详情</summary><br>· 你的机场订阅有 30 个节点，爬虫只用了 1 个——剩下 29 个在吃灰<br>· 自动测速、自动轮换、被封自动切换、半夜挂掉自愈<br>· 单文件、无框架依赖</details> |

### 反爬逆向 · 指纹 · 验证码

| 项目 | 简介 |
| --- | --- |
| [eg_ruishu](https://github.com/jimmy-Smile-ltl/eg_ruishu) | 瑞数 WAF 逆向方案集：12 个真实站点、25+ 技术路线，纯算法 / 补环境 / 浏览器三大技术族 <details><summary>详情</summary><br>· 12 个真实瑞数站点 · 25+ 条技术路线 · 三大技术族<br>· 每条路线都是「能请求到数据的最小可行代码」<br>· 含实测数据与避坑记录，可直接对照落地<br>· 三档方案决策表 + 版本分类速查</details> |
| [eg_akamai](https://github.com/jimmy-Smile-ltl/eg_akamai) | gatekit：Akamai 挑战的探测 / 分析 / 求解工具包，判据全部可离线回归 <details><summary>详情</summary><br>· 判据全部可离线回归（30/30 offline tests）<br>· 过闸与拿到内容分开计数，不把别家 WAF 算成失败<br>· curl_cffi 运行时</details> |
| [captcha_example](https://github.com/jimmy-Smile-ltl/captcha_example) <sup>已归档</sup> | 国内主流验证码样本库与求解器：9 家厂商、滑动 / 点选 / 旋转 / 五子棋 / POW 等类型 <details><summary>详情</summary><br>· 9 家厂商：天爱 / 易盾 / 极验 / 腾讯 / 数美 / 顶象等<br>· 类型：滑动拼图、文字点选、图标点选、语序点选、旋转、五子棋、POW<br>· OCR / 目标检测 / 旋转角度 / 相似度匹配模型环境<br>· 已归档；无代码开源版：[eg_captcha](https://github.com/jimmy-Smile-ltl/eg_captcha)</details> |
| [eg_captcha](https://github.com/jimmy-Smile-ltl/eg_captcha) | 零代码验证码知识库：16 家厂商、88 个厂商×类型、896 组真实样本，只留样本、方法与失败档案。线上浏览器（Cloudflare Workers 部署）：<https://eg-captcha-viewer.jimmysmileltl.workers.dev/> <details><summary>详情</summary><br>· 一行 py、一行 js 都没有：只有 Markdown、JSON、图片与音频<br>· 方法标签：CV / DET / OCR / VLM / ASR / PROTO / ACT，标明是否借助多模态 LLM 与成本<br>· 覆盖极验、易盾、腾讯、数美、顶象、天爱、银联、企讯通、凯格、美团、Amazon、reCAPTCHA、hCaptcha、HUMAN、DataDome、MTCaptcha<br>· 896 组真实样本，滑块、点选、九宫格、音频、游戏题都有；失败与无解也归档<br>· 自带 Claude Code skill，可按厂商/类型/方法检索<br>· 线上浏览器支持类型浏览、官方体验入口、左右对照、过程图、人工审核与音频<br>· 公开非商业研究档案，样本版权归各厂商</details> |
| [fingerprint](https://github.com/jimmy-Smile-ltl/fingerprint) | 浏览器指纹采集与 Node.js 补环境工具集：六大指纹维度全链路复现 <details><summary>详情</summary><br>· 六大维度：Canvas / WebGL / Audio / 字体 / 硬件 / 时区<br>· 全链路：浏览器采集 → Node.js 补环境 → 真实数据注入 → 指纹一致性验证<br>· Node 22+，MIT</details> |
| [eg_js_reverse](https://github.com/jimmy-Smile-ltl/eg_js_reverse) | 41 个真实网站的 JS 逆向教案：网易云 weapi、拼多多 anti_content、京东 h5st、抖音 a_bogus、小红书 mns、BOSS 直聘 JSVMP……加密入口 → 算法还原 → 可运行验证，内置测试向量，一条命令跑通 <details><summary>详情</summary><br>· 41 个案例按 7 类归档：参数加密 20 · WASM/VM 保护 9 · WAF 逆向 5 · 混淆反调试 3 · 内容加密 2 · 环境指纹 1 · 字体反爬 1<br>· 业界公认最难的几个签名都在里面：京东 h5st、抖音 a_bogus、小红书 mns x3、BOSS 直聘 JSVMP，全部纯算法还原<br>· OTA 专题四连：去哪儿 Bella / 小猪 gatesign / 途家 Revelio / 飞猪 MTOP，纯算法 + curl_cffi 回放<br>· 最简化、可复现、文档清晰：去掉工程化外壳，只留逆向技术本身<br>· 运行不依赖网络，内置测试向量，一条命令验证<br>· 合规声明：仅用于学习、学术研究与授权测试</details> |

> 验证码专题研究已归档，代码仓库或将在未来关闭——无代码开源版已经发布：[eg_captcha](https://github.com/jimmy-Smile-ltl/eg_captcha)，并配有[在线浏览器](https://eg-captcha-viewer.jimmysmileltl.workers.dev/)。只有样本、方法与结果，一行 py、一行 js 都没有。想考古的，趁页面还在。

### 数据研究 · 方法学

| 项目 | 简介 |
| --- | --- |
| [fork-detectability](https://github.com/jimmy-Smile-ltl/fork-detectability) | 用 29.8 万个 GitHub forker 的公开数据，量化「判断一个仓库的 fork 是否异常」到底能做到什么程度：7 条判据在两组之间零重叠、4 条统计显著，并完整记录判据随对照扩大而衰减的过程 <details><summary>详情</summary><br>· 规模：17 个仓库、36.1 万 forker 名单、29.8 万账号档案（82.6%），每人 9 个维度<br>· 设计：4 个「有外部质疑」的仓 vs 4 个「无任何质疑」的仓做对照，判据不依赖分组依据<br>· 最强判据 Pull Shark（协作徽章）差 12.3 个百分点：A 侧 88–97% 的 forker 从未参与过任何协作开发<br>· 次强：有自建仓 10.2pp、零粉丝 6.8pp、零提交 6.7pp（均通过 95% 置信检验）<br>· 负面结果同样记录：21 条直觉判据大部分失效——「fork 后动过」在 A 侧跨 6.6–91.4%，完全包住 B 侧<br>· 判据衰减曲线：对照从 2 仓扩到 8 仓，最强判据从 32.3pp 缩到 12.3pp。每加一个干净对照，判据就弱一分<br>· 8 次自我否定，包括撤回自己提出的「watchers/★ 是有效筛选信号」——按预测变量选样再验证它，属循环论证<br>· 边界：只证明群体层的形态差异，不证明任何具体仓库或账号的造假行为<br>· 代码 MIT，文档 24 份，数据不入库但采集脚本完整可复现</details> |

### 一些旧物

| 项目 | 简介 |
| --- | --- |
| [show-your-heart](https://github.com/jimmy-Smile-ltl/show-your-heart) <sup>已归档</sup> | 2022 年七夕用 Canvas 拼成的一段「视频」——对 GitHub 开源表白项目的有机整合，配乐从《卡农》到《告白の夜》。线上地址：<https://show-your-heart.vercel.app/> <details><summary>详情</summary><br>· 说是项目，不如说是一场挪用：星空借自某款浏览器插件，图片来源与特效出处都在仓库开发笔记里致谢<br>· 自我批评环节：技术上乏善可陈，代码稚拙，中二浓度过高，处处是当年手忙脚乱的痕迹<br>· 但它是那两年唯一浇筑过灵魂的代码。写爬虫是为了效率，写它，是为了别的什么<br>· 仓库已经归档，Vercel 上还留着它的页面。旧物不死，只是归档</details> |
| [chooseCourseSystem](https://github.com/jimmy-Smile-ltl/chooseCourseSystem-springboot) | 从课程作业长出来的在线选课系统：最初是 JSP + Servlet + JDBC 课设，后来学前端时用 Canvas 重做登录、选课和课表，并整体重写为 Spring Boot + PostgreSQL。线上地址：<https://choosecoursesystem-springboot.onrender.com/login>（登录页自动填充演示账号，Render 免费实例，首次访问会冷启动） <details><summary>详情</summary><br>· 原版：JSP + Servlet + JDBC + MySQL，运行时按学生/课程动态建表<br>· 重写：Spring Boot 3 + Thymeleaf + PostgreSQL + Flyway + Spring Security<br>· 选课：先修、时间冲突、容量、学分上限、全局智能推荐（一键提交时服务端重新计算），学生行锁 + 课程行锁保证并发<br>· 数据：129 门演示课程由 CSV 目录驱动，启动时新课程插入、已有课程更新，覆盖计算机/数学/人文/经管/艺术/体育<br>· 前端：Canvas 粒子网络、学分星环、冲突闪电、课表极光、学分礼炮、Live2D<br>· 测试：51 个，含真实 PostgreSQL、CSV 导入和并发抢课</details> |

<div align="center">
  <img src="assets/divider.svg" alt="" width="100%">
</div>

## 毕业记录

以下坐标已从筹备表毕业，按用途迁入上面的分区；筹备表就此清空。

- 验证码无代码版 → [eg_captcha](https://github.com/jimmy-Smile-ltl/eg_captcha)，「反爬逆向 · 指纹 · 验证码」
- 政府网站图谱 → [forager-gov](https://github.com/jimmy-Smile-ltl/forager-gov)，「LLM Agent · 智能采集」
- GitHub fork 用户画像研究 → 更名为 [fork-detectability](https://github.com/jimmy-Smile-ltl/fork-detectability)，「数据研究 · 方法学」
- 多开管理器 → [agent-multi-token](https://github.com/jimmy-Smile-ltl/agent-multi-token)，「LLM Agent · 开发工具」

<div align="center">
  <img src="assets/divider.svg" alt="" width="100%">
</div>

<div align="center">
  <picture>
    <source media="(min-width: 641px)" srcset="assets/observer-dawn.svg">
    <img src="assets/observer-dawn-tall.svg" alt="和每天晚上一样，试图征服世界" width="100%">
  </picture>
</div>
