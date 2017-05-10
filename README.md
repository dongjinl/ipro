# ipro

## 前言

　　`ipro`项目创建于2017-5-10，仅仅是作为个人学习使用。

## 项目介绍

　　基于Spring+SpringMVC+Mybatis。

### 组织结构


### 技术选型

#### 后端技术:
技术 | 名称 | 官网
----|------|----
Spring Framework | 容器  | [http://projects.spring.io/spring-framework/](http://projects.spring.io/spring-framework/)
SpringMVC | MVC框架  | [http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/#mvc](http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/#mvc)
Apache Shiro | 安全框架  | [http://shiro.apache.org/](http://shiro.apache.org/)
Spring session | 分布式Session管理  | [http://projects.spring.io/spring-session/](http://projects.spring.io/spring-session/)
MyBatis | ORM框架  | [http://www.mybatis.org/mybatis-3/zh/index.html](http://www.mybatis.org/mybatis-3/zh/index.html)
MyBatis Generator | 代码生成  | [http://www.mybatis.org/generator/index.html](http://www.mybatis.org/generator/index.html)
Druid | 数据库连接池  | [https://github.com/alibaba/druid](https://github.com/alibaba/druid)
Log4J | 日志组件  | [http://logging.apache.org/log4j/1.2/](http://logging.apache.org/log4j/1.2/)
Maven | 项目构建管理  | [http://maven.apache.org/](http://maven.apache.org/)

#### 前端技术:
技术 | 名称 | 官网
----|------|----
jQuery | 函式库  | [http://jquery.com/](http://jquery.com/)
Bootstrap | 前端框架  | [http://getbootstrap.com/](http://getbootstrap.com/)
Bootstrap-table | Bootstrap数据表格  | [http://bootstrap-table.wenzhixin.net.cn/](http://bootstrap-table.wenzhixin.net.cn/)
Font-awesome | 字体图标  | [http://fontawesome.io/](http://fontawesome.io/)
Waves | 点击效果插件  | [https://github.com/fians/Waves](https://github.com/fians/Waves)
zTree | 树插件  | [http://www.treejs.cn/v3/](http://www.treejs.cn/v3/)
Select2 | 选择框插件  | [https://github.com/select2/select2](https://github.com/select2/select2)
jquery-confirm | 弹出窗口插件  | [https://github.com/craftpip/jquery-confirm](https://github.com/craftpip/jquery-confirm)
jQuery EasyUI | 基于jQuery的UI插件集合体  | [http://www.jeasyui.com](http://www.jeasyui.com)
React | 界面构建框架  | [https://github.com/facebook/react](https://github.com/facebook/react)
Editor.md | Markdown编辑器  | [https://github.com/pandao/editor.md](https://github.com/pandao/editor.md)
zheng.jprogress.js | 加载进度条插件  | [https://github.com/shuzheng/zheng.jprogress.js](https://github.com/shuzheng/zheng.jprogress.js)
zheng.jtotop.js | 返回顶部插件  | [https://github.com/shuzheng/zheng.jtotop.js](https://github.com/shuzheng/zheng.jtotop.js)

#### 架构图

#### 模块依赖

#### 模块介绍

> ipro-common

Spring+SpringMVC+Mybatis框架集成公共模块，包括公共配置、MybatisGenerator扩展插件、通用BaseService、工具类等。

> ipro-admin

基于bootstrap实现的响应式Material Design风格的通用后台管理系统。

## 环境搭建

#### 开发工具:
- MySql: 数据库
- Tomcat: 应用服务器
- Git: 版本管理
- IntelliJ IDEA: 开发IDE
- Navicat for MySQL: 数据库客户端

#### 开发环境：
- Jdk7
- Mysql5.5

### 工具安装

### 资源下载

- JDK7 [http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html](http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html "JDK7")
- Maven [http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi "Maven")

## 开发指南:

- 1、本机安装Jdk7、Mysql等并**启动相关服务**，使用默认配置默认端口即可
- 2、克隆源代码到本地并打开，**推荐使用IntelliJ IDEA**，本地编译并安装到本地maven仓库

### 启动顺序
```
- 新建ipro数据库，导入project-datamodel文件夹下的ipro.sql

- 修改各dao模块和rpc-service模块的jdbc.properties数据库连接等配置信息

```
![启动演示](project-bootstrap/start.png)
```
- 访问默认帐号密码：admin/123456

- 登录成功后，可在右上角切换已注册系统访问
```

### 部署方式

```
- war包项目：使用tomcat等web容器启动

```

### 框架规范约定

约定优于配置(convention over configuration)，此框架约定了很多编程规范，下面一一列举：

```

- service类，需要在叫名`service`的包下，并以`Service`结尾，如`CmsArticleServiceImpl`

- controller类，需要在以`controller`结尾的包下，类名以Controller结尾，如`CmsArticleController.java`，并继承`BaseController`

- spring task类，需要在叫名`task`的包下，并以`Task`结尾，如`TestTask.java`

- mapper.xml，需要在名叫`mapper`的包下，并以`Mapper.xml`结尾，如`CmsArticleMapper.xml`

- mapper接口，需要在名叫`mapper`的包下，并以`Mapper`结尾，如`CmsArticleMapper.java`

- model实体类，需要在名叫`model`的包下，命名规则为数据表转驼峰规则，如`CmsArticle.java`

- spring配置文件，命名规则为`applicationContext-*.xml`

- 类名：首字母大写驼峰规则；方法名：首字母小写驼峰规则；常量：全大写；变量：首字母小写驼峰规则，尽量非缩写

- springmvc配置加到对应模块的`springMVC-servlet.xml`文件里

- 配置文件放到`src/main/resources`目录下

- 静态资源文件放到`src/main/webapp/resources`目录下

- jsp文件，需要在`/WEB-INF/jsp`目录下

- `RequestMapping`和返回物理试图路径的url尽量写全路径，如：`@RequestMapping("/manage")`、`return "/manage/index"`

- `RequestMapping`指定method

- 模块命名为`项目`-`子项目`-`业务`，如`ipro-cms-admin`

- 数据表命名为：`子系统`_`表`，如`cms_article`

- 更多规范，参考[[阿里巴巴Java开发手册] http://git.oschina.net/shuzheng/zheng/attach_files

```

### 拓扑图
![拓扑图](project-bootstrap/distributedSystem.png)

### 开发进度
![开发进度](project-bootstrap/progress.png)

### 参与开发

首先谢谢大家支持，本项目仅为个人学习使用，暂不接受他人提交。

### 常见问题

## 附件

### 优秀文章和博客

- [创业互联网公司如何搭建自己的技术框架](http://shuzheng5201314.iteye.com/blog/2330151 "创业互联网公司如何搭建自己的技术框架")

- [微服务实战](https://segmentfault.com/a/1190000004634172 "微服务实战")

- [单点登录原理与简单实现](http://shuzheng5201314.iteye.com/blog/2343910 "单点登录原理与简单实现")

- [ITeye论坛关于权限控制的讨论](http://www.iteye.com/magazines/82 "ITeye论坛关于权限控制的讨论")

- [RBAC新解：基于资源的权限管理(Resource-Based Access Control)](http://globeeip.iteye.com/blog/1236167 "RBAC新解：基于资源的权限管理(Resource-Based Access Control)")

- [网站架构经验随笔](http://jinnianshilongnian.iteye.com/blog/2289904 "网站架构经验随笔")

- [支付系统架构](http://shuzheng5201314.iteye.com/blog/2355431 "支付系统架构")

- [Spring整合JMS](http://elim.iteye.com/blog/1893038 "Spring整合JMS")

- [跟我学Shiro目录贴](http://jinnianshilongnian.iteye.com/blog/2018398 "跟我学Shiro目录贴")

- [跟我学SpringMVC目录汇总贴](http://jinnianshilongnian.iteye.com/blog/1752171 "跟我学SpringMVC目录汇总贴")

- [跟我学spring3 目录贴](http://jinnianshilongnian.iteye.com/blog/1482071 "跟我学spring3 目录贴")

- [跟我学OpenResty(Nginx+Lua)开发目录贴](http://jinnianshilongnian.iteye.com/blog/2190344 "跟我学OpenResty(Nginx+Lua)开发目录贴")

- [Redis中文网](http://www.redis.net.cn/ "Redis中文网")

- [读懂Redis并配置主从集群及高可用部署](http://mp.weixin.qq.com/s?__biz=MzIxNTYzOTQ0Ng==&mid=2247483668&idx=1&sn=cd31574877d38cf7ff9c047b86c9bf23&chksm=979475eda0e3fcfb6b5006bcd19c5a838eca9e369252847dbdf97820bf418201dd75c1dadda3&mpshare=1&scene=23&srcid=0117KUiiITwi2ETRan16xRVg#rd "读懂Redis并配置主从集群及高可用部署")

- [Redis哨兵-实现Redis高可用](http://redis.majunwei.com/topics/sentinel.html "Redis哨兵-实现Redis高可用")

- [ELK(ElasticSearch, Logstash, Kibana)搭建实时日志分析平台](http://www.open-open.com/lib/view/open1451801542042.html "ELK(ElasticSearch, Logstash, Kibana)搭建实时日志分析平台")

- [Nginx基本功能极速入门](http://xxgblog.com/2015/05/17/nginx-start/ "Nginx基本功能极速入门")

- [mybatis-genarator 自定义插件](https://my.oschina.net/alexgaoyh/blog/702791 "mybatis-genarator 自定义插件")

- [Elasticsearch权威指南（中文版）](https://es.xiaoleilu.com/510_Deployment/20_hardware.html "Elasticsearch权威指南（中文版）")

- [springMVC对简单对象、Set、List、Map的数据绑定和常见问题.](http://blog.csdn.net/z_dendy/article/details/12648641 "springMVC对简单对象、Set、List、Map的数据绑定和常见问题.")

- [如何细粒度地控制你的MyBatis二级缓存](http://blog.csdn.net/luanlouis/article/details/41800511 "如何细粒度地控制你的MyBatis二级缓存")

- [做个男人，做个成熟的男人，做个有城府的男人](http://shuzheng5201314.iteye.com/blog/1387820 "做个男人，做个成熟的男人，做个有城府的男人")


### 在线小工具

- [在线Cron表达式生成器](http://cron.qqe2.com/ "在线Cron表达式生成器")

- [在线工具 - 程序员的工具箱](http://tool.lu/ "在线工具 - 程序员的工具箱")

### 在线文档

- [JDK7英文文档](http://tool.oschina.net/apidocs/apidoc?api=jdk_7u4 "JDK7英文文档")

- [Spring4.x文档](http://spring.oschina.mopaas.com/ "Spring4.x文档")

- [Mybatis3官网](http://www.mybatis.org/mybatis-3/zh/index.html "Mybatis3官网")

- [Dubbo官网](http://dubbo.io/ "Dubbo官网")

- [Nginx中文文档](http://tool.oschina.net/apidocs/apidoc?api=nginx-zh "Nginx中文文档")

- [Freemarker在线手册](http://freemarker.foofun.cn/ "Freemarker在线中文手册")

- [Velocity在线手册](http://velocity.apache.org/engine/devel/developer-guide.html "Velocity在线手册")

- [Bootstrap在线手册](http://www.bootcss.com/ "Bootstrap在线手册")

- [Git官网中文文档](https://git-scm.com/book/zh/v2 "Git官网中文文档")

- [Thymeleaf](http://www.thymeleaf.org/doc/tutorials/3.0/thymeleafspring.html "Thymeleaf")

## 许可证

