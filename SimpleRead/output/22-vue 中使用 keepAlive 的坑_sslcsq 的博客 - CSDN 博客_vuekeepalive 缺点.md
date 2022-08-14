> [vue 中使用 keepAlive 的坑_sslcsq 的博客 - CSDN 博客_vuekeepalive 缺点](https://blog.csdn.net/sslcsq/article/details/119674119)
    Tags:
    Date:  [[2022_05_28  ]]
    Describe:前言：vue中使用keepAlive数据不刷新，只缓存第一次进入的页面数据。需求：首页进入列表页，根据不同id刷新列表页面数据，列表页进入详情页，详情页返回列表页时不刷新。&lt;keep-alive&gt;		&lt;router-view v-if="$route.meta.keepAlive"&gt;&lt;/router-view&gt;&lt;/keep-alive&gt;		&lt;router-view v-if="!$route.meta.keepAlive"&gt;&lt;

- >vue 中使用 keepAlive 数据不刷新，只缓存第一次进入的页面数据。
	-
	-