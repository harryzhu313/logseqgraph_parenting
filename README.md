



- ## what
	- 把logseq仓库公开为一个网页；；
	- 用 GitHub 和 GitHub action将logseq graph发布为一个网站
	- logseq内容有更新，将本地仓库同步 GitHub 仓库后，GitHub会自动触发 GitHub action，更新网页；
	- 本仓库的源代码代码来自[logseq/publish-spa: A github action and CLI to publish logseq graphs as a SPA app](https://github.com/logseq/publish-spa),[https://github.com/howie-serious/feynman_OS](https://github.com/howie-serious/feynman_OS)。
- ## how
	- ## 修改 Logseq 设置
		- 打开页面publish设置: 
			- ![](https://docs.logseq.com/assets/image_1638393320509_0.png)
		- 单击右上角的三个点，然后选择`Export graph`。然后选择一个文件夹，Logseq 将导出发布所需的所有文件；
			- ![](https://docs.logseq.com/assets/pages_Publishing_1615917396171_0.png)
			- 查询`config.edn`页面，可以看到`all-pages-public?true`
		- 修改logseq设置，把journals、whiteboard和flash cards关闭。
	- ## 下载源代码
		- 下载源代码：https://github.com/howie-serious/feynman_OS/releases；
		- 修改文件名为自己的源代码文件名
		- 将`src`中的`feynman_OS`替换成自己的 Logseq 仓库，并在仓库中添加`publish_spa.cljs`文件；
		- 修改`.gitignore`中的内容；
		- 修改 `publish.yml`中的Logseq 仓库路径。
	- ## publish to github
		- 创建一个新的GitHub 仓库，一定是`public`，否则无法用 GitHub pages；
		- 把源代码文件夹同步到github。
	- ## github pages
		- 开启git仓库的pages：
			- setting-pages
			- `source`：选择 deploy from branch；
			- `branch`: gh-pages / root；
				- 用 GitHub pages 生成的网页都会多一个叫做`gh-pages`的 branch 来存储`build`  后的文件；
				- `main` 下是源代码；
			- 选择好后就会生产访问链接了。
			- ![](https://image.harryrou.wiki/2024-07-03-CleanShot%202024-07-03%20at%2017.21.36%402x.png)
		- 绑定域名
			- baby.harryrou.wiki；
			- 在域名解析中添加 cname；
				- 值（Value）: username.github.io （将 username 替换为你的 GitHub 用户名）；
			- GitHub会自动发放tls、https证书；
			- 设置强制https；
			- ![](https://image.harryrou.wiki/2024-07-03-CleanShot%202024-07-03%20at%2017.58.11%402x.png)
	- ## 日常维护
		- graph发生变化后，git push一下，会自动触发 GitHub actions 自动更新页面：
			- `Actions`1：git push to main；
			- `Actions`2：pages build and deployment （这一步生成页面）；
		-
- ## ref.
	- [logseq官方案例](https://docs.logseq.com/#/page/contents)
	- [logseq/publish-spa: A github action and CLI to publish logseq graphs as a SPA app](https://github.com/logseq/publish-spa)
	- https://github.com/howie-serious/feynman_OS



