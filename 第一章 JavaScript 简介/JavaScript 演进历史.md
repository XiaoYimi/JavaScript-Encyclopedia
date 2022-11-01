<h1 align="center">JavaScript 简史<h1>



## JavaScript 历史进程

- [x] 1995 年 2 月，Netscape 公司的布兰登·艾奇开发一款名为 LiveScript 的脚本语言。
- [x] 由于当时时代下 Java 风靡一时，Netscape 为了推出该编程语言，将 LiveScript 更改为 JavaScript，即 JavaScript 1.0 就此正式发布。
- [x] JavaScript 1.0 在 Web 获得巨大成功 ，备受用户关注。同时，微软决定向自家产品 Internet Explore 投入更多资源；为了避开 Netscape 授权问题，就此命名为 JScript。
- [x] 时代下的 JavaScript 存在 2 个版本，即 Netscape JavaScript 与 Internet Explore JScript。当时 JavaScript 没有语言标准，导致出现不同版本的问题，于是 JavaScript 标准的议程就此被提出。
- [x]  1997 年，以 JavaScript 1.1 版本为蓝图提交至欧洲制造商协会(ECMA)，指定 39 号技术委员会(TC39，由Netscape，Sun，Borland，微软及其它脚本语言公司构建) 进行制定 JavaScript 标准(ECMA-262)，并命名为 ECMAScript 标准。
- [x] 1998 年，国际标准化组织和国际电工委员会(ISO/IEC)采用 ECMAScript 标准，即 ISO/IEC-16262。自此，浏览器开发商将 ECMAScript 作为 JavaScript 的实现基础。 ECMAScript 2.0 发布。
- [x] 1999 年，ECMAScript 3.0 发布。
- [x] 2000 年，ECMAScript 4.0 发布(新标准脱离原有基础,备受争议)。
- [x] 2008 年，ECMAScript 3.1 发布，修正替代 ECMAScript 4.0，并终止 ECMAScript 4.0 。
- [x] 2009 年，规定 ECMAScript 3.1 作为 ECMAScript 5.0。
- [x] 2011 年，ECMAScript 5.1 发布，成为国际标准。
- [x] 2015，ECMAScript 6 发布，是 ECMAScript 5.1 后的下一代版本。也称 ES2015，ES6。标志着 JavaScript 迎来快速发展的里程碑。







## JavaScript 在浏览器的实现

- [x] 核心部分(ECMAScript)
- [x] 文档对象模型(DOM Model)
- [x] 浏览器对象模型(BOM Model)



## ECMAScript 标准

ECMAScript 是实现 JavaScript 的基础。



- [x] 类型
- [x] 语法
- [x] 语句
- [x] 关键字
- [x] 保留字
- [x] 操作符
- [x] 对象

## DOM 标准

DOM(文档对象模型)，提供操作网页内容的方法和借口。主要是基于 XML 文档结构的的访问与操作实现标记映射，结合 HTML 的对象与方法实现标记的交互行为。



- [x] DOM1: 规定了文档结构与标记的映射关系

- [x] DOM2: 扩展了鼠标，用户界面事件，层叠样式，范围，遍历等支持

- [x] DOM3: 操作文档树的支持



## BOM 无标准，浏览器开发商制定

BOM(浏览器对象模型)，提供了浏览器交互的方法和接口。 本质上来讲是控制浏览器显示页面以外的部分。随着 HTML5 时代来临，浏览器开发商进行兼容处理：



- [x] 浏览器窗口操作(弹出、关闭，移动，缩放等行为)
- [x] 浏览器基本信息(navigator)
- [x] 浏览器页面信息(location)
- [x] 浏览器显示器信息(screen)
- [x] 浏览器缓存 Cookie，LocalStorage，SessionStorage
- [x] 浏览器请求发射器 XMLHttpRequest，ActiveXObject