---
title: 首次部署的一篇文章
published: 2026-09-13
tags: [Markdown, 博客, 演示, 第一篇文章]
category: 在最后的秋天
draft: false
---

# 首次记录

这是第一篇文章，篇幅不会很长，今后也不会在短篇和动态中使用任何生成式AI。
显而易见的是，这里的说明显得很幼稚，不简明，比起那些冷冰冰的只剩技术性的文章差别极其的大。

这个博客在一周前我就开始计划了，我无意间发现了这个有趣的开源项目，让制作个人博客如此简单。在友链中保留了原作者的博客，感兴趣可以去看看。下面是原项目的GitHub链接:
::github{repo="CuteLeaf/Firefly"}
现在我会说说在离线开发时遇到的一些无法解决的问题：

你一定发现，音乐部分加载速度很慢，甚至无法正确加载。
```markdown
---
meting: {
		// Meting API 地址
		// 默认使用官方 API，也可以使用自定义 API
		api: "https://api.i-meto.com/meting/api?server=:server&type=:type&id=:id&r=:r",
		// 音乐平台：netease=网易云音乐, tencent=QQ音乐, kugou=酷狗音乐, xiami=虾米音乐, baidu=百度音乐
		server: "netease",
		// 类型：song=单曲, playlist=歌单, album=专辑, search=搜索, artist=艺术家
		type: "playlist",
		// 歌单/专辑/单曲 ID 或搜索关键词
		id: "89203273",
		// 认证 token（可选）
		auth: "",
		// 备用 API 配置（当主 API 失败时使用）
		fallbackApis: [
			"https://api.injahow.cn/meting/?server=:server&type=:type&id=:id",
			"https://api.moeyao.cn/meting/?server=:server&type=:type&id=:id",
		],
	},
---
```
如上所示，我并没有使用离线音乐，而是使用Meting API和网易云音乐，Meting API本身是一个开源项目，我使用的是免费提供的公共节点，不稳定的问题常会发生。网易云的对第三方API管控十分严格，Meting API时常无法获取真实播放地址，并且API不是直接存储音频文件，这导致了播放的速度都很慢甚至会出现无法播放的问题，这些说明显得不是很完整，但你估计知道了大致原因。我第一次接触这玩意，我觉得这功能可有可无，没人想在访问网页时错误的播放音频，设备的声音没有设置的时候，要么带着耳机体验耳膜被攻击的酥脆，要么手机外放的时候让你变得尴尬无比。

接下来是Bangumi的封面加载慢和无法显示的问题，这里可以简要说明：Bangumi已经无法通过中国大陆护联网正常访问了，我使用了dynamic模式,它会在浏览器中实时请求 API，始终显示最新数据，缺点就是你会等上一段时间，像开盲盒一样加载番剧，书籍，游戏和音乐作品的封面。
```markdown
---
bangumi: {
		userId: "pr1tea",
		mode: "dynamic",
		apiUrl: "https://api.bangumi.pro",
		subjectBaseUrl: "https://api.bangumi.pro/subject/",
		categoryOrder: ["anime", "book", "music", "game"],
		nsfw: "hide",
    }
---
```  
以上是最主要的两个问题，其他的现在来看无关紧要。
这篇文章收录在了【最后的秋天】这个合集中，最后的秋天来自俄罗斯摇滚乐队DDT的一首歌，这是为数不多至今人在活跃的在苏联时期所创建的乐队。
以后博客里面会有很多关于思想和哲学的文章，还有随手记下的自己都没明白的东西。

