# Directory Lister v2.6.1 -逗比魔改版

### 魔改特点：

- 界面式样魔改
- 支持中文目录和文件名
- 支持显示各文件夹内的简介说明
- 默认调用的各种CDN文件本地化
- any else ...

### 演示示例：

逗比云 https://softs.fun

### 下载安装：

下载压缩文件后，解压并上传到已经搭建好 PHP和HTTP环境的服务器中（lnmp.org），然后即可上传文件和创建文件夹了！

Github打包：https://github.com/junnyhaha/DirectoryLister/archive/master.zip

逗比云打包：https://softs.fun/Website/Directory%20Lister%E9%AD%94%E6%94%B9%E7%89%88%28by-Toyo%29%20v2.6.1.zip

#### 文件结构
假设你的虚拟主机是 `/home/wwwroot/xxx.xx`
``` bash
/home/wwwroot/xxx.xx
├─ resources
│   ├ themes
│   │ └ bootstrap
│   │    └ .....
│   │
│   ├ DirectoryLister.php
│   ├ config.php
│   └ fileTypes.php
│
├ README.html # 文件夹内的 说明简介文件 #
├ index.php
│
├─ 测试文件夹
│   ├ 测试文件.txt
│   └ README.html # 文件夹内的 说明简介文件 #
│
└ 测试文件.txt
```
### 注意事项：

#### 不显示文件和目录

如果安装 lnmp一键包上传Directory Lister后，Directory Lister不显示文件和目录，那么可能是 PHP函数` scandir `被禁用了，取消禁用即可。
``` bash
sed -i 's/,scandir//g' /usr/local/php/etc/php.ini
# 取消scandir函数禁用
/etc/init.d/php-fpm restart
# 重启 PHP生效
```

#### README功能

使用这个功能，需要打开` resources\themes\bootstrap\index.php `文件，找到第五行的：
``` bash
$md_path = explode("com", $md_path_all);
```
把` com `改成你的域名后缀(比如` xxx.cn `就是改成` cn `)

每个文件夹下面放一个` README.html `文件，这个文件里写着简介说明内容即可。

为了避免中文乱码，把` README.html `文件用 UTF-8无BOM编码 保存！

#### 文件修改说明

修改网站中头部导航标题，去这个文件里搜索` DOUBI Soft `然后全部替换为自己要改的。

` \resources\DirectoryLister.php `

修改网站标签栏的标题，去这个文件里把开头` <title> `标签中的` DOUBI Soft `替换为自己要改的。

` \resources\themes\bootstrap\index.php `

网站头部公共文件：

` \resources\themes\bootstrap\default_header.php `

网站底部公共文件：

` \resources\themes\bootstrap\default_footer.php `

如果想要插入流量统计代码，那只需要把代码写到 default_header.php 文件内即可。

——————

Power by https://doub.io/dbrj-3/

base on Directory Lister http://www.directorylister.com/
