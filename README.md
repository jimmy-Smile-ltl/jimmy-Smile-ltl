<div align="center">
  <picture>
    <source media="(min-width: 641px)" srcset="assets/observer.svg">
    <img src="assets/observer-tall.svg" alt="观测者，旧时代的余孽，在聆听时代的声音" width="100%">
  </picture>
</div>

&nbsp;

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

---

## 征服之路上的坐标

一些在深夜里写下的东西，按用途归档。标着「已归档」的坐标早已废弃，留在这里，权当考古现场。

### LLM Agent · 智能采集

| 项目 | 简介 |
| --- | --- |
| [forager-faculty](https://github.com/jimmy-Smile-ltl/forager-faculty) | LLM 驱动的自适应高校教师信息采集框架：评估-修复-再评估闭环、四阶段流水线、五级反 WAF 请求栈 |
| [forager-epaper](https://github.com/jimmy-Smile-ltl/forager-epaper) | Paper Daily：中文日报自动采集流水线，一条命令生成生产级爬虫，自愈反馈环 + 零配置降级 |

### 爬虫框架与工程

| 项目 | 简介 |
| --- | --- |
| [jimmySpider](https://github.com/jimmy-Smile-ltl/jimmySpider) | 从 140+ 网站实战提炼的 Python 爬虫框架：6 种请求处理器、TLS 指纹伪装、断点续爬 |
| [clash_proxy](https://github.com/jimmy-Smile-ltl/clash_proxy) | 把机场闲置节点管成爬虫代理池：自动测速、轮换、封禁切换、挂掉自愈 |

### 反爬逆向 · 指纹 · 验证码

| 项目 | 简介 |
| --- | --- |
| [eg_ruishu](https://github.com/jimmy-Smile-ltl/eg_ruishu) | 瑞数 WAF 逆向方案集：12 个真实站点、25+ 技术路线，纯算法 / 补环境 / 浏览器三大技术族 |
| [eg_akamai](https://github.com/jimmy-Smile-ltl/eg_akamai) | gatekit：Akamai 挑战的探测 / 分析 / 求解工具包，判据全部可离线回归 |
| [captcha_example](https://github.com/jimmy-Smile-ltl/captcha_example) <sup>已归档</sup> | 国内主流验证码样本库与求解器：9 家厂商、滑动 / 点选 / 旋转 / 五子棋 / POW 等类型 |
| [fingerprint](https://github.com/jimmy-Smile-ltl/fingerprint) | 浏览器指纹采集与 Node.js 补环境工具集：六大指纹维度全链路复现 |
| [eg_js_reverse](https://github.com/jimmy-Smile-ltl/eg_js_reverse) | JS 逆向最小化复现集：加密入口 → 算法还原 → 可运行验证 |

> 验证码专题研究已归档，代码仓库或将在未来关闭——但会另出一个无代码开源版：只有初始样本、最终求解结果与求解思路（见下文「筹备中的坐标」）。想考古的，趁页面还在。

### 一件旧物

> [show-your-heart](https://github.com/jimmy-Smile-ltl/show-your-heart) · 线上地址：<https://show-your-heart.vercel.app/>

2022 年七夕（8 月 4 日）动工的产物。说是项目，不如说是一场挪用：把 GitHub 上散落各处的开源表白项目做了一次有机整合，本质上是用 Canvas 拼出的一段「视频」——星空借自某款浏览器插件，配乐从《卡农》排到《告白の夜》。

自我批评环节：技术上乏善可陈，代码稚拙，中二浓度过高，处处是当年手忙脚乱的痕迹。它称不上工程，勉强列在这里，权当反面教材。

但它是那两年唯一浇筑过灵魂的代码。写爬虫是为了效率，写它，是为了别的什么——至于「别的什么」是什么，打开页面，它会自己说。

仓库已经归档，Vercel 上还留着它的页面。旧物不死，只是归档。

---

## 筹备中的坐标

一些尚未写完的东西，先记在这里。

- **GitHub 仓库造假专项** —— 拿到一个仓库的全部 fork 用户，逐个做真人鉴定：注册时间、默认头像、关注比例、fork 时间戳的聚集度。给「这个仓库里有多少真人」一个可复现的答案。
- **多开管理器**（重构中）—— Claude Code / Codex 会话多开，每个会话独立 token 与 API 地址，外加项目状态管理。目前的形态太丑、逻辑不顺，super agent 框架兴起后正在重写定位。开源时间待定。
- **验证码无代码版** —— 代码仓库关闭后的赎罪之作：只有初始样本、最终求解结果与求解思路。一行 py、一行 js 都没有。知识留下来，武器不发放。

---

<div align="center">
  <picture>
    <source media="(min-width: 641px)" srcset="assets/observer-dawn.svg">
    <img src="assets/observer-dawn-tall.svg" alt="和每天晚上一样，试图征服世界" width="100%">
  </picture>
</div>
