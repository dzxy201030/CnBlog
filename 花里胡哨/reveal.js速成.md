# reveal.js速成

`reveal.js`是能够让我们很轻易地使用 HTML 创建一个漂亮的演示文稿的插件

## 下载

1. 上官网 https://revealjs.com/
2. 下载 https://github.com/hakimel/reveal.js/releases
我下载的是最新版（5.0.4）解压到相对应的文件夹，
![QQ截图20240203184920](C:\Users\29608\Desktop\QQ截图20240203184920.png)

3. 新建一个文件夹，将 dist，plugin 文件夹移过去。新建 index.html，因为要用到图片比较多，可以在根目录下新建一个 img 文件夹。之后的目录![](C:\Users\29608\Desktop\QQ截图20240203185502.png)

## 速通

### HTML模板

```html
<html>

<head>
	// 引入样式文件
    <link rel="stylesheet" href="dist/reveal.css">
    // 主题颜色（可自主选择）
    <link rel="stylesheet" href="dist/theme/serif.css">
</head>

<body>
    <div class="reveal">
        <div class="slides">
        </div>
    </div>

    <script src="dist/reveal.js"></script>
    <script src="plugin/notes/notes.js"></script>
    <script src="plugin/markdown/markdown.js"></script>
    <script src="plugin/highlight/highlight.js"></script>
    <script>
        Reveal.initialize({
            hash: true,
            // 是否在右下角展示控制条
            controls: true,
            // 是否显示演示的进度条
            progress: true,
            // 是否显示当前幻灯片的页数
            slideNumber: 'c/t',
            plugins: [RevealMarkdown, RevealHighlight, RevealNotes]
        });
    </script>
</body>

</html>
```

### 主题

![](C:\Users\29608\Desktop\QQ截图20240203185725.png)

### 配置

1. 一个<section>标签就是一张ppt。
2. reveal的动画有grow，shrink，fade-out，fade-right，fade-up，fade-down，fade-left，fade-in-then-out，fade-in-then-semi-out
3. Markdown支持需要加载Markdown.js插件，并且在section标签中加入data-markdown属性。
4. 代码高亮需要加载插件highlight.js
5. 可以单独给每个section设置背景，包括背景颜色，背景图片，视频

![](C:\Users\29608\Desktop\20200715081756642.png)

```js
<script src="dist/reveal.js"></script>
	<script src="plugin/notes/notes.js"></script>
	<script src="plugin/markdown/markdown.js"></script>
	<script src="plugin/highlight/highlight.js"></script>
	<script>
		Reveal.initialize({
			// 代码语法高亮
			plugins: [RevealMarkdown, RevealHighlight],

			// 在右下角显示控制面板
			controls: true,

			// 显示演示进度条
			progress: true,

			// 显示幻灯片页码
			// 可使用代码 slideNumber: 'c/t'，表示 '当前页/总页数'
			slideNumber: false,

			// 幻灯片切换时写入浏览器历史记录
			history: false,

			// 启用键盘快捷键
			keyboard: true,

			// 启用幻灯片概览
			overview: true,

			// 幻灯片垂直居中
			center: true,

			// 在触屏设备上启用触摸滑动切换
			touch: true,

			// 循环演示
			loop: false,

			// 演示方向为右往左，即向左切换为下一张，向右切换为上一张
			rtl: false,

			// 打乱幻灯片顺序
			shuffle: false,

			// 启用幻灯片分段
			fragments: true,

			// 演示文稿是否运行于嵌入模式（如只占页面的一部分）
			// 译者注：与触屏相关
			// false：所有在演示文稿上触发的 "touchmove" 的默认行为都会被阻止
			// true：只有在 "touchmove" 触发了演示文稿事件时才会阻止默认行为
			embedded: false,

			// 是否在按下 ? 键时显示快捷键帮助面板
			help: true,

			// 演讲备注是否对所有人可见
			showNotes: false,

			// 两个幻灯片之间自动播放的时间间隔（毫秒），当设置为 0 时，则禁止自动播放。
			// 该值可以被幻灯片上的 `data-autoslide` 属性覆盖
			autoSlide: 0,

			// 允许停止自动播放
			// 在手动切换分段或幻灯片后暂停自动播放
			// 按 a 键暂停或恢复自动播放
			autoSlideStoppable: true,

			// 使用该函数执行自动播放操作
			autoSlideMethod: Reveal.navigateNext,

			// 启用鼠标滚轮切换幻灯片，作用与 SPACE 相同
			mouseWheel: false,

			// 在移动设备上隐藏地址栏
			hideAddressBar: true,

			// 在 iframe 预览弹框中打开链接
			previewLinks: false,

			// 切换过渡效果
			// none-无/fade-渐变/slide-飞入/convex-凸面/concave-凹面/zoom-缩放
			transition: 'slide', // none/fade/slide/convex/concave/zoom

			// 切换过渡速度
			// default-中速/fast-快速/slow-慢速
			transitionSpeed: 'default', // default/fast/slow

			// 背景切换过渡效果
			backgroundTransition: 'fade', // none/fade/slide/convex/concave/zoom

			// 预加载幻灯片数
			viewDistance: 3,

			// 视差背景图
			parallaxBackgroundImage: '', // 示例："'https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg'"

			// 视察背景图尺寸
			parallaxBackgroundSize: '', // CSS 写法，示例："2100px 900px"（目前只支持像素值，不支持 % 和 auto）

			// 相邻两张幻灯片间，视差背景移动的像素值
			// - 如果不设置则自动计算
			// - 当设置为 0 时，则禁止视差动画
			parallaxBackgroundHorizontal: null,
			parallaxBackgroundVertical: null

		});

	</script>
```



## 演示

### 第一页

```html
<section data-background-image="./img/goforward.jpg" data-background-opacity=".4">
				<h1>zhaoxiuying</h1>
				<p>you are always in my heart</p>
			</section>
```



![QQ截图20240204035927](C:\Users\29608\Desktop\QQ截图20240204035927.png)

### 第二页

```html
<section>
				<p class="fragment grow">安静</p>
				<p class="fragment shrink">沉默</p>
				<p class="fragment fade-out">内向</p>
				<p>
					<span style="display: inline-block;" class="fragment fade-right">迷茫</span>
					<span style="display: inline-block;" class="fragment fade-up">没有狠心</span>
					<span style="display: inline-block;" class="fragment fade-down">失去方向</span>
					<span style="display: inline-block;" class="fragment fade-left">间歇emo</span>
				</p>
				<h3 class="fragment fade-in-then-out">这些才是我</h3>
				<h3 class="fragment fade-in-then-semi-out">往后的我</h3>
				<p><span class="fragment highlight-red">努力向上，要猛</span> <span class="fragment highlight-blue">认真学习</span>
					<span class="fragment 
			highlight-green">向阳生活</span>
				</p>
			</section>
```



![QQ截图20240204035946](C:\Users\29608\Desktop\QQ截图20240204035946.png)

### 第三页

```html
<section>
				<section data-transition="fade" data-background-color="#CCFBFF">
					<h2>伸手不可得，山月与故人</h2>
				</section>
				<section data-transition="convex" data-background-color="#EF96C5">
					<h2>春昼短，秋夜长，从此余生好景独看</h2>
				</section>
				<section data-transition="concave" data-background-color="#EAD6EE">
					<h2>知世故而不世故，善自嘲而不嘲人</h2>
				</section>
				<section data-transition="zoom" data-background-color="#A0F1EA">
					<h2>观星觅云难悲喜，闻风听雨也见你</h2>
				</section>
			</section>
```



![QQ截图20240204040000](C:\Users\29608\Desktop\QQ截图20240204040000.png)

### 第四页

```html
<section data-background-video="./video/goforward.mp4" data-background-video-loop
				data-background-video-muted>
				
				<h1>Freedom</h1>
			</section>
```



![QQ截图20240204040022](C:\Users\29608\Desktop\QQ截图20240204040022.png)

### 第五页

```html
<section>
				<h1>Cpp</h1>
				<pre>
					<code data-trim data-noescape>
						<script type="text/template">
							#include <bits/stdc++.h>
							using namespace std;

							int main() {
							cout << "hello world..." <<endl; 
							return 0; 
							}
						</script>
					</code>
				</pre>
			</section>
```



![QQ截图20240204040030](C:\Users\29608\Desktop\QQ截图20240204040030.png)

### 第六页

```html
<section data-markdown>
				<textarea data-template>
					## Slide 1
					This is my Blog [link](https://www.cnblogs.com/daizixuan).
					---
					## Slide 2
					```Cpp
						#include <bits/stdc++.h>
						using namespace std;
						
						int main() {
						cout << "hello world..." <<endl; 
						return 0; 
						}
					```
					---
					## Slide 3
					<!-- ...写一些内容 -->
				</textarea>
			</section>
```



![QQ截图20240204040044](C:\Users\29608\Desktop\QQ截图20240204040044.png)

### 第七页

```html
<section data-background-image="./img/goforward.jpg" data-background-opacity=".4">
				<p class="fragment">你见，或者不见我 我就在那里 不悲不喜</p>
				<p class="fragment">你念或者不念我 情就在那里 不来不去</p>
				<p class="fragment">你爱，或者不爱我 爱就在那里 不增不减</p>
				<p class="fragment">你跟，或者不跟我</p>
				<p class="fragment">我的手就在你手里</p>
				<p class="fragment">不舍不弃</p>
				<p class="fragment">来我的怀里</p>
				<p class="fragment">或者</p>
				<p class="fragment">让我住进你的心里</p>
			</section>
```



![QQ截图20240204040055](C:\Users\29608\Desktop\QQ截图20240204040055.png)
