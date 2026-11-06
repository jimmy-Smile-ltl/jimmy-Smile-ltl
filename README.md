<div align="center">
  <picture>
    <source media="(min-width: 641px)" srcset="assets/observer.svg">
    <img src="assets/observer-tall.svg" alt="观测者，旧时代的余孽，在聆听时代的声音" width="100%">
  </picture>
</div>

<div align="center">
<p>目次 · <a href="#试图征服世界">试图征服世界</a> · <a href="#征服之路上的坐标">坐标</a> · <a href="#一些旧物">旧物</a> · <a href="#筹备中的坐标">筹备</a></p>
</div>

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

一些在深夜里写下的东西，按用途归档。标着「已归档」的坐标早已废弃，留在这里，权当考古现场。

### LLM Agent · 智能采集

| 项目 | 简介 |
| --- | --- |
| [forager-faculty](https://github.com/jimmy-Smile-ltl/forager-faculty) | LLM 驱动的自适应高校教师信息采集框架：评估-修复-再评估闭环、四阶段流水线、五级反 WAF 请求栈 <details><summary>详情</summary><br>· evaluate-fix-re-evaluate 自愈闭环，质量不达标自动诊断重跑<br>· 四阶段流水线：学校 → 院系 → 教师名录 → 教师详情<br>· 五级反 WAF 请求栈：curl_cffi TLS 伪装、浏览器兜底<br>· 实战：144 所高校、40.5 万教师无人值守跑完</details> |
| [forager-epaper](https://github.com/jimmy-Smile-ltl/forager-epaper) | Paper Daily：中文日报自动采集流水线，一条命令生成生产级爬虫，自愈反馈环 + 零配置降级 <details><summary>详情</summary><br>· 一条命令：报纸名 → 发现入口 → 侦查结构 → 生成 spider → 验证打分 → 入库<br>· LLM 只在三个固定工位工作，管线控制流由代码固定<br>· 质量分 <60 自动诊断改进（≤3 轮），失败自愈<br>· 无 MySQL / PG / Mongo 时自动降级本地 JSONL，零配置可跑<br>· 20 个开箱示例站点 + 上千站点知识库</details> |

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
| [captcha_example](https://github.com/jimmy-Smile-ltl/captcha_example) <sup>已归档</sup> | 国内主流验证码样本库与求解器：9 家厂商、滑动 / 点选 / 旋转 / 五子棋 / POW 等类型 <details><summary>详情</summary><br>· 9 家厂商：天爱 / 易盾 / 极验 / 腾讯 / 数美 / 顶象等<br>· 类型：滑动拼图、文字点选、图标点选、语序点选、旋转、五子棋、POW<br>· OCR / 目标检测 / 旋转角度 / 相似度匹配模型环境<br>· 已归档，无代码开源版见「筹备中的坐标」</details> |
| [fingerprint](https://github.com/jimmy-Smile-ltl/fingerprint) | 浏览器指纹采集与 Node.js 补环境工具集：六大指纹维度全链路复现 <details><summary>详情</summary><br>· 六大维度：Canvas / WebGL / Audio / 字体 / 硬件 / 时区<br>· 全链路：浏览器采集 → Node.js 补环境 → 真实数据注入 → 指纹一致性验证<br>· Node 22+，MIT</details> |
| [eg_js_reverse](https://github.com/jimmy-Smile-ltl/eg_js_reverse) | JS 逆向最小化复现集：加密入口 → 算法还原 → 可运行验证 <details><summary>详情</summary><br>· 从实战爬虫项目提取，最简化、可复现、文档清晰<br>· 去掉工程化外壳，只留逆向技术本身<br>· 运行不依赖网络，内置测试向量，一条命令验证<br>· 合规声明：仅用于学习、学术研究与授权测试</details> |

> 验证码专题研究已归档，代码仓库或将在未来关闭——但会另出一个无代码开源版：只有初始样本、最终求解结果与求解思路（见下文「筹备中的坐标」）。想考古的，趁页面还在。

### 一些旧物

| 项目 | 简介 |
| --- | --- |
| [show-your-heart](https://github.com/jimmy-Smile-ltl/show-your-heart) <sup>已归档</sup> | 2022 年七夕用 Canvas 拼成的一段「视频」——对 GitHub 开源表白项目的有机整合，配乐从《卡农》到《告白の夜》。线上地址：<https://show-your-heart.vercel.app/> <details><summary>详情</summary><br>· 说是项目，不如说是一场挪用：星空借自某款浏览器插件，图片来源与特效出处都在仓库开发笔记里致谢<br>· 自我批评环节：技术上乏善可陈，代码稚拙，中二浓度过高，处处是当年手忙脚乱的痕迹<br>· 但它是那两年唯一浇筑过灵魂的代码。写爬虫是为了效率，写它，是为了别的什么<br>· 仓库已经归档，Vercel 上还留着它的页面。旧物不死，只是归档</details> |

<div align="center">
  <img src="assets/divider.svg" alt="" width="100%">
</div>

## 筹备中的坐标

一些尚未写完的东西，先记在这里。

| 项目 | 简介 |
| --- | --- |
| **GitHub fork 用户画像研究** | 对仓库的全部 fork 用户做账号形态刻画：注册时间、头像、关注比例、fork 时间戳分布。给「fork 背后是怎样的社区」一个可复现的数据答案，也为识别异常活跃模式提供参考。 <details><summary>详情</summary><br>· 输入：任意仓库的 fork 列表<br>· 信号：注册时间 / 默认头像 / 关注比例 / fork 时间戳分布<br>· 输出：社区构成数据画像，异常活跃模式仅作参考提示<br>· 原则：中性研究，不针对任何个体</details> |
| **多开管理器**（重构中） | Claude Code / Codex 会话多开，每个会话独立 token 与 API 地址，外加项目状态管理。目前的形态太丑、逻辑不顺，super agent 框架兴起后正在重写定位。开源时间待定。 <details><summary>详情</summary><br>· 会话隔离：每个会话独立 token 与 API 地址，互不串扰<br>· 项目状态管理：上下文 / 进度 / 配置按项目隔离<br>· 重构方向：「多开」降级为手段，「会话与项目状态管理」升格为主题<br>· 为什么重构：super agent 框架（Claude Agent SDK 等）兴起后原定位被架空</details> |
| **验证码无代码版** | 代码仓库关闭后的赎罪之作：只有初始样本、最终求解结果与求解思路。一行 py、一行 js 都没有。知识留下来，武器不发放。 <details><summary>详情</summary><br>· 结构设想：samples/ 原始样本 · solved/ 求解结果 · docs/ 每家厂商一篇思路复盘<br>· 零代码：一行 py、一行 js 都没有<br>· 定位：知识传播，不提供工具——想滥用的人得自己动手写</details> |

<div align="center">
  <img src="assets/divider.svg" alt="" width="100%">
</div>

<div align="center">
  <picture>
    <source media="(min-width: 641px)" srcset="assets/observer-dawn.svg">
    <img src="assets/observer-dawn-tall.svg" alt="和每天晚上一样，试图征服世界" width="100%">
  </picture>
</div>
