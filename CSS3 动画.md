##CSS3 @keyframes 规则

Internet Explorer 10、Firefox 以及 Opera 支持 @keyframes 规则和 animation 属性。

Chrome 和 Safari 需要前缀 -webkit-。

**注释：**Internet Explorer 9，以及更早的版本，不支持 @keyframe 规则或 animation 属性。

####一、创建动画

```css
@keyframes myfirst
{
from {background: red;}
to {background: yellow;}
}

@-moz-keyframes myfirst /* Firefox */
{
from {background: red;}
to {background: yellow;}
}

@-webkit-keyframes myfirst /* Safari 和 Chrome */
{
from {background: red;}
to {background: yellow;}
}

@-o-keyframes myfirst /* Opera */
{
from {background: red;}
to {background: yellow;}
}
```

####第二步

把 "myfirst" 动画捆绑到 div 元素，时长：5 秒：

```css
div
{
animation: myfirst 5s;
-moz-animation: myfirst 5s;	/* Firefox */
-webkit-animation: myfirst 5s;	/* Safari 和 Chrome */
-o-animation: myfirst 5s;	/* Opera */
}
```

**注释：**您必须定义动画的名称和时长。如果忽略时长，则动画不会允许，因为默认值是 0。

####当动画为 25% 及 50% 时改变背景色，然后当动画 100% 完成时再次改变

```css
@keyframes myfirst
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

@-moz-keyframes myfirst /* Firefox */
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

@-webkit-keyframes myfirst /* Safari 和 Chrome */
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

@-o-keyframes myfirst /* Opera */
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}
```

####改变背景色和位置：

```css
@keyframes myfirst
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}

@-moz-keyframes myfirst /* Firefox */
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}

@-webkit-keyframes myfirst /* Safari 和 Chrome */
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}

@-o-keyframes myfirst /* Opera */
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}
```

####运行名为 myfirst 的动画，其中设置了所有动画属性：

```css
div
{
animation-name: myfirst;             /*规定 @keyframes 动画的名称。*/
    
animation-duration: 5s;              
/*规定动画完成一个周期所花费的秒或毫秒。默认是 0。*/
    
animation-timing-function: linear;   
/*规定动画的速度曲线。默认是 "ease"。ease：默认值，逐渐变慢；
linear：匀速
ease-in：加速
ease-out：减速
ease-in-out：先加速，再减速*/
    
animation-delay: 2s;                 
/*规定动画何时开始。默认是 0。
默认0：立即执行动画
正值：延迟指定时间后，开始执行动画
负值：立即执行，但跳过指定时间后进入动画*/
    
animation-iteration-count: infinite; 
/*规定动画被播放的次数。默认是 1。
1（默认值）：表示在执行某事件后只执行1次动画。
[number]：任意正整数，表示在执行某事件后只执行[number]次动画。
infinite：表示在执行某事件后“无限次”执行动画。*/
    
animation-direction: alternate;      
/*规定动画是否在下一周期逆向地播放。默认是 "normal"。
normal：默认值；
alternate：逆向执行；*/
    
animation-play-state: running;       
/*规定动画是否正在运行或暂停。默认是 "running"。
running：播放动画；
paused：暂停动画；*/
    
animation-fill-mode:backwards;
/*backwards：让元素保持动画第一帧定义里所设置的CSS属性，直到动画开始执行。
forwards：让元素保持动画播放结束后最后一帧定义里所设置的CSS属性。
both：让元素保持动画第一帧里定义的CSS属性，直到动画开始，动画播放完成后又保持动画最后一帧的属性。*/
    
/* Firefox: */
-moz-animation-name: myfirst;
-moz-animation-duration: 5s;
-moz-animation-timing-function: linear;
-moz-animation-delay: 2s;
-moz-animation-iteration-count: infinite;
-moz-animation-direction: alternate;
-moz-animation-play-state: running;
/* Safari 和 Chrome: */
-webkit-animation-name: myfirst;
-webkit-animation-duration: 5s;
-webkit-animation-timing-function: linear;
-webkit-animation-delay: 2s;
-webkit-animation-iteration-count: infinite;
-webkit-animation-direction: alternate;
-webkit-animation-play-state: running;
/* Opera: */
-o-animation-name: myfirst;
-o-animation-duration: 5s;
-o-animation-timing-function: linear;
-o-animation-delay: 2s;
-o-animation-iteration-count: infinite;
-o-animation-direction: alternate;
-o-animation-play-state: running;
}
```

####与上面的动画相同，但是使用了简写的动画 animation 属性：

```
animation: 动画名称 持续时间 线性规律 延迟时间 播放次数 周期逆向播放 播放/暂停 首帧预设/末帧保留；
```

```css
div
{
animation: myfirst 5s linear 2s infinite alternate;
/* Firefox: */
-moz-animation: myfirst 5s linear 2s infinite alternate;
/* Safari 和 Chrome: */
-webkit-animation: myfirst 5s linear 2s infinite alternate;
/* Opera: */
-o-animation: myfirst 5s linear 2s infinite alternate;
}
```

##动画示例

####1、光晕效果

```html
<div class="box">
    <span>CHINA</span>
</div>
```

```css
body {
    background-color: #000;
}

/*定义动画*/
@keyframes shine {
    0%    { box-shadow: 0px 0px 5px  0px  #fff; }
    70%   { box-shadow: 0px 0px 20px 10px #ff0000; }
    100%  { box-shadow: 0px 0px 5px  0px  #fff; }
}

div.box {
    width:  200px;
    height: 200px;
    border-radius: 50%;

    display: flex;
    justify-content: center;
    align-items: center;

    position: absolute;
    top: 0; right: 0; bottom: 0; left: 0;
    margin: auto;

    animation: shine 1s linear infinite;
}
div.box span {
    color: #ff0000;
    letter-spacing: 5px;
    font-size: 30px;
    font-weight: bold;
    text-shadow: 1px 1px 2px #fff;
}
```

####2、气泡效果

```html
<div class="box"></div>
```

```css
.box {
	width:  40px;
	height: 40px;
	background-color: blue;
	border-radius: 50%;
	margin: 100px auto;
	-webkit-animation: fadeOut 1.0s infinite ease-in-out;
	animation: fadeOut 1.0s infinite ease-in-out;
}
@-webkit-keyframes fadeOut {
	from { -webkit-transform: scale(0.0); }
	to   { -webkit-transform: scale(1.0); opacity: 0; }
}
@keyframes fadeOut {
	from { transform: scale(0.0); }
	to   { transform: scale(1.0); opacity: 0; }
}
```

####3、嫦娥奔月

```html
<div class="translateBox">
    <div class="img"></div>
</div>
```

```css
body {
    background: #000;
}
.translateBox {
    width:  400px;
    height: 400px;
    margin: 100px auto;
    background: url("../imgs/bg.png");
    background-size: contain;
    cursor: pointer;

    -webkit-box-shadow: 0 0 3px 5px  #d3d3d3;
    -moz-box-shadow: 0 0 3px 5px  #d3d3d3;
    box-shadow: 0 0 3px 5px  #d3d3d3;

    position: relative;
}

.translateBox .img {
    width:  calc(100% / 2);
    height: calc(100% / 2);
    background: url("../imgs/change.png");
    background-size: contain;
    opacity: 0;



    transition: opacity 1s ease-in-out 0.5s, transform 1s ease-in-out;
    -webkit-transform: scale(.5, .5);
    transform: scale(.5, .5);


    position: absolute;
    top:  -90px;
    left: -90px;
}

.translateBox:hover .img {
    opacity: 1;

    -webkit-transform: translate(170px, 180px);
    transform: translate(170px, 180px);

    transition: opacity 1s ease-in-out, transform 1s ease-in-out .2s;
}
```

##动画技巧

####延迟调用

```html
<div class="box">
	<div class="line line1"></div>
	<div class="line line2"></div>
	<div class="line line3"></div>
	<div class="line line4"></div>
	<div class="line line5"></div>
</div>
```

```css
.box {
	width:  60px;
	height: 30px;
	margin: 100px auto;
	text-align: center;
}

.box > .line {
	display: inline-block;
	width: 6px;
	height: 100%;
	background-color: green;

	-webkit-animation: strechDelay 1s linear infinite;
	animation: strechDelay 1s linear infinite;
	
}
.box > .line2 {
	-webkit-animation-delay: -0.9s;
	animation-delay: -0.9s;
}
.box > .line3 {
	-webkit-animation-delay: -0.8s;
	animation-delay: -0.8s;
}
.box > .line4 {
	-webkit-animation-delay: -0.7s;
	animation-delay: -0.7s;
}
.box > .line5 {
	-webkit-animation-delay: -0.6s;
	animation-delay: -0.6s;
}

@-webkit-keyframes strechDelay {
	0%, 40%, 100% { -webkit-transform: scaleY(.4); }
	20%   { -webkit-transform: scaleY(1.0);}
}
@keyframes strechDelay {
	0%, 40%, 100% { transform: scaleY(.4); }
	20%   { transform: scaleY(1.0);}
}
```

####进度指示

```html
<div class="box"></div>
```

```css
.box {
	width:  120px;
	height: 120px;
	margin: 100px auto;

	border: 10px solid orange;
	border-left-color: purple;
	border-radius: 50%;

	animation: loading 1.2s linear infinite;
	-webkit-animation: loading 1.2s linear infinite;
}


@-webkit-keyframes loading {
	from {
		-webkit-transform: rotate(0deg);
	}
	to {
		-webkit-transform: rotate(360deg);
	}
}
@keyframes loading {
	from {
		transform: rotate(0deg);
	}
	to {
		transform: rotate(360deg);
	}
}
```

#### hover 特效

```html
<a href="javascript:;" class="wrap">
	<div class="img"></div>
	<div class="mask">
		<div class="info">
			<h3>周杰伦</h3>
			<p>十一月的肖邦</p>
		</div>
	</div>
	<div class="border"></div>
</a>
```

```css
.wrap, .img, .mask, .border {
	width:  300px;
	height: 300px;
	border-radius: 50%;
}
.wrap {
	position: relative;
	display: block;
}
.img {
	background: url('jay.jpeg') no-repeat 50% 50%;
	background-size: cover;
}
.mask, .border {
	position: absolute;
	left: 0;
	top: 0;
}
.mask {
	text-align: center;
	color: rgba(255, 255, 255, 0);
	transition: all .5s ease-in;
}
.info {
	margin-top: 50%;
	transform: translateY(-50%);
}
.border {
	border: 10px solid #072256;
	border-left-color: #E07514;
	border-top-color: #E07514;
	box-sizing: border-box;
	transition: all .5s ease-in;
}

.wrap:hover .mask {
	background: rgba(0, 0, 0, .5);
	color: rgba(255, 255, 255, 1);
}
.wrap:hover .border {
	transform: rotate(180deg);
}
```

