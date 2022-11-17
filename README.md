<div id="cnblogs_post_body" class="blogpost-body blogpost-body-html">
<h1 class="_1RuRku">微信小程序中显示html富文本的方法<button class="cnblogs-toc-button" title="显示目录导航" aria-expanded="false"></button></h1>
<p>使用方法：<br>git地址：<a href="https://link.jianshu.com/?t=https%3A%2F%2Fgithub.com%2Ficindy%2FwxParse" rel="noopener" target="_blank">https://github.com/icindy/wxParse</a></p>
<h5><span style="font-size: 16px">一、下载wxParse文件</span><button class="cnblogs-toc-button" title="显示目录导航" aria-expanded="false"></button></h5>
<p><img src="https://img2018.cnblogs.com/blog/1086124/201911/1086124-20191126155252376-1570953495.png" alt=""></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<h5><span style="font-size: 16px">二、在要引入的页面的js文件中，引入文件</span><button class="cnblogs-toc-button" title="显示目录导航" aria-expanded="false"></button></h5>
<p>js文件中</p>
<div class="cnblogs_code">
<pre><span style="color: rgba(0, 0, 255, 1)">var</span> WxParse = require(<span style="color: rgba(128, 0, 0, 1)">'</span><span style="color: rgba(128, 0, 0, 1)">../../../weui/wxParse/wxParse.js</span><span style="color: rgba(128, 0, 0, 1)">'</span>);</pre>
</div>
<p>css文件中</p>
<div class="cnblogs_code">
<pre>@import <span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">../../../weui/wxParse/wxParse.wxss</span><span style="color: rgba(128, 0, 0, 1)">"</span>;</pre>
</div>
<p>页面中</p>
<div class="cnblogs_code">
<pre>&lt;import src=<span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">../../../weui/wxParse/wxParse.wxml</span><span style="color: rgba(128, 0, 0, 1)">"</span> /&gt;</pre>
</div>
<h5><span style="font-size: 16px">三、数据绑定</span><button class="cnblogs-toc-button" title="显示目录导航" aria-expanded="false"></button></h5>
<p>在page.js文件中绑定数据<br>如：</p>
<div class="cnblogs_code">
<pre><span style="color: rgba(0, 0, 0, 1)">onLoad: function (options) {
</span><span style="color: rgba(0, 0, 255, 1)">var</span> that = <span style="color: rgba(0, 0, 255, 1)">this</span><span style="color: rgba(0, 0, 0, 1)">;
</span><span style="color: rgba(0, 0, 255, 1)">var</span> detail_content =<span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">&lt;div&gt;我是HTML代码&lt;/div&gt;</span><span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(0, 0, 0, 1)">;
WxParse.wxParse(</span><span style="color: rgba(128, 0, 0, 1)">'</span><span style="color: rgba(128, 0, 0, 1)">detail_content</span><span style="color: rgba(128, 0, 0, 1)">'</span>, <span style="color: rgba(128, 0, 0, 1)">'</span><span style="color: rgba(128, 0, 0, 1)">html</span><span style="color: rgba(128, 0, 0, 1)">'</span>, detail_content, that, <span style="color: rgba(128, 0, 128, 1)">5</span><span style="color: rgba(0, 0, 0, 1)">);
} </span><span style="color: rgba(0, 128, 0, 1)">//</span><span style="color: rgba(0, 128, 0, 1)">注意第一个参数需要与wxml中的一致</span></pre>
</div>
<h4><span style="font-size: 16px">四、在page的wxml中引入模板</span><button class="cnblogs-toc-button" title="显示目录导航" aria-expanded="false"></button></h4>
<div class="cnblogs_code">
<pre>&lt;view <span style="color: rgba(0, 0, 255, 1)">class</span>=<span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">newsDt_wrap</span><span style="color: rgba(128, 0, 0, 1)">"</span>&gt;
        &lt;template <span style="color: rgba(0, 0, 255, 1)">is</span>=<span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">wxParse</span><span style="color: rgba(128, 0, 0, 1)">"</span> data=<span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">{{wxParseData:detail_content.nodes}}</span><span style="color: rgba(128, 0, 0, 1)">"</span> /&gt;
        &lt;view <span style="color: rgba(0, 0, 255, 1)">class</span>=<span style="color: rgba(128, 0, 0, 1)">"</span><span style="color: rgba(128, 0, 0, 1)">last_date</span><span style="color: rgba(128, 0, 0, 1)">"</span>&gt;最后更新于：{{initDate.publish_time}}&lt;/view&gt;
    &lt;/view&gt;</pre>
</div>
<p>&nbsp;</p>
</div>
