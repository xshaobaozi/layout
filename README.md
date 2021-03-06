#关于移动端的布局
* 圣杯布局
* 双飞翼布局
* Rem布局

#圣杯布局
 圣杯布局主要通过在父元素上使用padding给 子类left right 元素空出空间 然而通过width:100% 给center 使center可以自适应屏幕的宽度调整大小
 <pre>
    <code>
    .container {
        padding-left: 200px;
    	padding-right: 150px;
    }
    .center {
        background-color: #00ffff;
    	width: 100%;
    }
    .left {
    	background-color: blue;
    	width: 200px;
    	margin-left:-100%;
    	left: -200px;
    }
    .right {
    	background-color: orange;
    	width: 150px;
    	right: -150px;
    	margin-left: -150px; 
    }
    </code>
 </pre>
#双飞翼布局
 双飞翼布局感觉上其实跟圣杯布局差不多 不同的是 双飞翼布局通过给center增加一个 inner元素 给定margin 给left 和right空出了空调 手法跟上面的圣杯布局差不多
 
 <pre>
    <code>
    .center .center-inner  {
        margin-left: 200px;
    	margin-right: 150px;
    }
    .center {
        background-color: #00ffff;
    	width: 100%;
    }
    .left {
        width: 200px;
    	margin-left:-100%;
    }
    .right {
        width: 150px;
        margin-left: -150px; 
    }
    </code>
 </pre>
 
# Rem布局

>相对长度单位。相对于根元素(即html元素)font-size计算值的倍数

关于Rem布局 参考<a href="https://segmentfault.com/a/1190000003690140">关于移动端Rem布局的一些总结</a>

通过给根元素一个 指定值 子元素通过 相对根元素的 值的大小 进行计算
比如 html font-size='100px'
那么 1rem = 100px

通常可以通过获取屏幕的window.innerWidth 通过js计算出符合设计稿基准值设置html的fontSize

看淘宝<a href="http://www.w3cplus.com/mobile/lib-flexible-for-html5-layout.html">使用Flexible实现手淘H5页面的终端适配</a>
主要通过这段代码

<code>
    width && (docEle.style.fontSize = 20 * (width / 320) + "px");
</code>

根据屏幕设置基准在320px的屏幕大小下标准为20px的根元素大小, width/320 是一个比例 即 计算20px不管在640px，750px下 都能够按照需要的一个比例进行符合320px设计稿的缩放

 




