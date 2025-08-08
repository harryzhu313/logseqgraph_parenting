public:: true
tags:: #[[⚙️ system files 系统文件]] 
exclude-from-graph-view:: true

- ## 📥 inbox 收集箱
	- #000-📥inbox
- ## 🏗️ projects 项目
	- {{query (page-property :tags "#🏗️projects-项目")}}
- ## 🌲 BoK 个人知识体系
	- #[[🌲 BoK-知识树]]
	- {{query (page-property :tags [[🌲 BoK-知识树]])}}
- ## 🔎 分类查看
	- ### 1 按领域分类 areas
		- #[[300-🌈life 生活]]
			- #301-BabyMoonshine-小蘑菇成长记
			- #[[👫friends&people 人是社会动物]]
			- #[[🏃‍♂️health&activity 运动健康]]
			- #[[jokes]]
			- #302-LifeBank-生活资料库
			- #303-LifeExperience-生活经验，积累与体会
			- #304-Tour-旅游规划
	- ### 2 按流程分类 GTD
		- #000-📥inbox
		- #[[zzz-📦archive 归档库]]
		  collapsed:: true
			- #[[zzz-📤outbox 费曼输出]]
				- #[[zzz-📤outbox 费曼输出/卡片输出]]
				- #[[zzz-📤outbox 费曼输出/文章输出]]
				- #[[zzz-📤outbox 费曼输出/视频输出]]
				- #[[zzz-📤outbox 费曼输出/podcast输出]]
				- #[[zzz-📤outbox 费曼输出/直播输出]]
	- ### 3 按成熟度分类 maturity
		- #p1-🫐seed-种子
		- #p2-🌱sprout-萌芽
		- #p3-🪴budding-抽条
		- #p4-🌸flowering-开花
		- #p5-🌲evergreen-长青
	- ### 4 按重要性分类 importance
		- #s5-★★★★★
		- #s4-★★★★☆
		- #s3-★★★☆☆
		- #s2-★★☆☆☆
		- #s1-★☆☆☆☆
	- ### 5 知识砖块分类 blocks
		- #[[🧱bricks 知识砖块]]
			- #[[🧱bricks 知识砖块/facts 事实性知识]]
			- #[[🧱bricks 知识砖块/concepts 概念]]
			- #[[🧱bricks 知识砖块/mental models 心理模型]]
	- ### 6. 资源
		- #[[💎resources 资源]]
			- #[[💎resources 资源/TV]]
			- #[[💎resources 资源/books]]
			- #[[💎resources 资源/music]]
			- #[[💎resources 资源/tools]]
			- #[[💎resources 资源/movies]]
			- #[[💎resources 资源/videos]]
			- #[[💎resources 资源/courses]]
			- #[[💎resources 资源/articles]]
			- #[[💎resources 资源/podcasts]]
			- #[[💎resources 资源/documentaries]]
	- ### 6 [[用标签组合筛选透视]]
	- #+BEGIN_QUERY
	  {:title [:h3 "7. 最新新增页面 (Top 15)"]
	   :query  [:find (pull ?p [*])
	            :where
	            [?p :block/created-at ?t]
	            ;; 关联页面属性，防止漏掉 page-level 的 metadata
	            [?b :block/page ?p]]
	   :result-transform
	   (fn [rs]
	     (->> rs
	          (sort-by (comp - :block/created-at)) ; 时间戳倒序
	          (take 15)))
	   :collapsed? false}
	  #+END_QUERY
- ## reference
	- [[🗒️ notes/home 页面]]