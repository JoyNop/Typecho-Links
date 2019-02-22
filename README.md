# Typecho-Links

HANNY老师写的东西感觉都成了typecho的精品了，非常感谢在茫茫人海中还有这样一位好的互联网知识推动者，有幸使用到HANNY老师的Links插件，怎能不记录一下呢？但是HANNY的链接好像打不开了emmm

>本版基于原版修改，适配于[Dolphin - 海豚 - Typecho主题](https://www.ryongyon.com/dolphin.html)

本插件上传到`usr/plugins`

修改Dolpin主题

`/usr/themes/Dolphin/page-links.php`

```php
<?php
/**
* Template Page of Links
*
* @package custom
*/
if (!defined('__TYPECHO_ROOT_DIR__')) exit;
$this->need('header.php');
?>
<div class="container grid-<?php $this->options->page_width(); ?> s-content">
    <div class="column col-12" style="background:#fff;border-radius:5px;padding:20px 15px;margin-bottom:20px">
        <div class="links">
            <ul>
              <?php Links_Plugin::output("SHOW_DOLPHIN"); ?>
            </ul>
            <?php $this->content(); ?>
        </div>
    </div>
</div>

<?php $this->need('footer.php'); ?>


```


## Links 插件介绍
通过该插件，博主可以方便地在侧边栏添加友情链接；

支持两种输出方式。

一种为函数输出方式，主要用于侧边栏的友情链接，或者模板开发者设计的友情链接模板等；

另一种方式为HTML标签式输出，主要方便用户建立自己的友情链接页面。支持文字链接、图片链接、图文混合链接等。

内设这三种默认的输出方式，支持自定议设定输出规则。

支持链接分类，方便管理。

支持增加自定义字段，方便用户做一些个性扩展。

## Links 插件使用方法

下载Links插件，并上传至`usr/plugins/`目录下

登陆博客后台，点击控制台选项下的插件选项进入插件列表界面

### 启动Links插件

后台 → 管理 → 友情链接 处可新增链接

使用如下调用代码在对应的地方调用即可

`<?php Links_Plugin::output();?>`

### Links 调用方式

最简单的调用方式为，列出所有的链接：

`<?php Links_Plugin::output(); ?>`

如果想调用的为图片链接，则调用方式为：

`<?php Links_Plugin::output("SHOW_IMG"); ?>`

如果是图文的混合链接，则调用方式为：

`<?php Links_Plugin::output("SHOW_MIX"); ?>`

如果想限制侧边栏的链接数量，比如说为10个，则可调用：

`<?php Links_Plugin::output("SHOW_TEXT", 10); ?>`

如果想列出某个类别的链接，则可调用：

`<?php Links_Plugin::output("SHOW_TEXT", 0, "testsort"); ?>`

#### 建立独立的友情链接页面

最简单的引用方式为：

`<links></links>`

如果想调用的为图片链接，则调用方式为：

`<links>SHOW_IMG</links>`

如果是图文的混合链接，则调用方式为：

`<links>SHOW_MIX</links>`

如果想限制侧边栏的链接数量，比如说为10个，则可调用：

`<links 10>SHOW_TEXT</links>`

如果想列出某个类别的链接，则可调用：

`<links 0 testsort></links>`

也可以用

`<links testsort></links>`

后者要求分类必须以字母开头。

提醒：分类名只能包含字母及数字！


参考链接：
[typecho友情链接插件 - Links](https://plugins.typecho.me/plugins/links-for-imhan.html)
[HANNY老师博客地址 ](http://www.molerose.com/archives/26/)