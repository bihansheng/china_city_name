# china_city_name
最近发现项目中使用的省市区数据库很旧了，很多新增区的数据没有。网上找了很多，都不是最新了。

找到一篇博客，他是自己去国家统计局上取的，

https://blog.csdn.net/z_wen_quan/article/details/79737567

不过他使用的php，我没有php环境，而且数据库的格式不一样，所以自己重新写了一个工具类。

思路是：

通过统计局网站上找到的各个省市区的ID可以 拼接出相关界面的URL
通过网络请求可以通过URL获取到当前界面的源码
通过正则表达式 截取需要的数据，包括 名称、统计用区划代码、跳转下级界面ID
将获取到的数据拼接成SQL语句，或者拼接为JSON字符串输出
工具类如下，

有四个方法：

 printProvinceSQL()   printCitySQL ()    printAreaSQL()   分别在控制台打印 表 province   city  area  的 插入SQL 语句
getCitiesJson 在控制台打印 json字符串，并保持到D盘
注意，sql语句是根据我用的数据库的格式拼接的，如果使用的数据库格式和我使用的不通，可以自行修改对应的SQL语句
