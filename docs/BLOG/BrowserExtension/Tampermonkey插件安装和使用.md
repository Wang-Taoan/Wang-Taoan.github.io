# Tampermonkey插件安装和使用
"没有安装扩展程序的浏览器是不完整的。"

科技发展的今天，我们深知浏览器的强大和便利，但是有时我们想做一些特殊的操作，会发现这个网页的开发者，并没有开发某些功能，这时候浏览器(browser)扩展程序可以提供这些功能。比如下载Tampermonkey插件，你可以下载你需要的插件，比如视频网站去广告，修改浏览器主题，自动刷无聊的网课……

## Tampermonkey介绍
![](https://pic.imgdb.cn/item/63dbb959ac6ef8601607d7b6.jpg)
* 一款现在很流行的浏览器插件，中文俗称油猴。
* 你可以把它当作一个脚本管理器和脚本搜索工具。它里面收录了各大开源社区提供的JavaScript脚本，你可以根据个人需要在search里寻找你要的脚本。



![](https://cn.bing.com/images/search?view=detailV2&ccid=MO7yGLpi&id=8F85B320236ABDDE6142A9D0E9C8CE4223697AF0&thid=OIP.MO7yGLpisFociNNSe_YjEQHaEl&mediaurl=https%3a%2f%2fimg.onlinedown.net%2fdownload%2f202007%2f182845-5f117d5dc464a.jpg&exph=375&expw=605&q=tampermonkey&simid=607992023234013640&FORM=IRPRST&ck=6858785527A1A71EFBB8CF084C792B8C&selectedIndex=3)
## 下载和安装

* 前期准备：chrome浏览器
> 最好使用chrome浏览器，所有的脚本几乎都是适配chrome的
> 
> 其他Microsoft Edge、safari当然也可以，safari可能存在部分脚本不兼容情况。


* 方法一(最方便)：
	* 打开chrome应用商店<chrome://extensions/>，直接搜索`Tampermonkey` 进行下载
> 这个方法需要科学上网。因为国内原因，无法使用goole搜索，如果没有科学上网工具，可能打不开chrome应用商店

* 方法二(通用)：
	* 通过别的渠道下载`tampermonkey.crx`文件,然后加载到chrome的扩展程序即可。
	
	1. <https://wmhl.lanzoui.com/ib8glab>下载zip压缩包，并解压出来一个`.crx`文件
	2. 打开chrome浏览器
		1. 进入扩展程序界面
		2. 打开开发者模式
		3. 加载已解压的扩展程序。选择刚下载的`.crx`文件
![](https://pic.imgdb.cn/item/63dbb705ac6ef86016047836.png)
* 方法三(仅适合macos)：
	* 在appstore中下载`Tampermonkey`
> appstore里需要12元购买，不推荐。 (以前不懂竟然傻傻地花了12元购买过这个(捂脸))

## 使用插件与安装脚本
当我们安装完插件后，在浏览器的右上方会出现它的图标
![](https://pic.imgdb.cn/item/63dbb9dcac6ef86016087fec.png)


![](https://www.google.com/search?q=tampermonkey&tbm=isch&chips=q:tampermonkey,online_chips:tampermonkey+logo:zoNXZK18GYM%3D&bih=764&biw=1440&hl=zh-CN&sa=X&ved=2ahUKEwiu_Nnp9vb8AhVHzIsBHfnMDSYQ4lYoAXoECAEQJA)
**获取新脚本**这个会是我们最常用的功能，我们可以进入脚本市场寻找自己需要的脚本。

**添加新脚本** 给了解js脚本的开发者使用的，当然也可以导入你信任的第三方脚本，前面说过tampermonkey也是一个脚本管理器。普通人基本用不到。

**管理面板** 可以管理你下载的脚本，启用脚本-停用脚本-删除脚本等功能


* 获取脚本，进入页面。
![](https://pic.imgdb.cn/item/63dbbbc3ac6ef860160bdad2.png)
* 可以看见俩个脚本市场`Userscript.Zone` -`GreasyFork` ,推荐使用`GreasyFork`,可以直观看到脚本的得分、安装量，方便帮你辨识好用的脚本
![](https://pic.imgdb.cn/item/63dbbceeac6ef860160e41fc.png)
* 接下来你可以根据自己的需要在search中搜索你要的脚本咯，找到之后点击`安装`即可

## 删除脚本
到`管理面板`即可删除。

> 管理面板具体位置见前文

## 推荐脚本
1. `懒人专用，全网VIP视频免费破解去广告、全网音乐直接下载`
我用它看来三体可真好啊！
![](https://pic.imgdb.cn/item/63dbbf40ac6ef860161245a5.png)
2. ` CSDN广告完全过滤、人性化脚本优化` 
国内知名的开发者交流社区，不说文章质量如何，竟然广告这么多，复制代码还要登陆账号、开会员。
这个脚本剔除了这些广告部分，实现免登陆复制代码……打造了一个绿色简洁的学习环境。
![](https://pic.imgdb.cn/item/63dbc11fac6ef860161582ed.png)

3. `OCS 网课助手`
我使用它来刷学习通的知识点，还挺稳定好用的。
> 它可以刷学习通、智慧树的课程。
> 如果是别的课程网站，可以寻找相应的其他脚本。