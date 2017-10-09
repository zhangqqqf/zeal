## MAVEN
* 项目信息
> _parent_ _name_ _url_ _groupId_ _artifactId_ _packaging_ _version_ ...
```
groupId：团体标识,约定是以创建这个项目的组织名称的逆向域名(reverse domain name)开头
artifactId：在groupId 下的表示一个单独项目产品的唯一标识符
version：一个项目的特定版本
packaging：项目的类型，默认是jar，描述了项目打包后的输出
```
* 项目生命周期
```
dev->test->online
```
* 标准构建
```
clean
validate
compile
test
package
verify
install
site
deploy
```
* 依赖管理
```
dependencies
```
* settings.xml
```
<localRepository>E:/apache-maven-3.3.9/repository</localRepository>

<server>
    <id>jk</id>
    <username>jkadmin</username>
    <password>abc123</password>
</server>

<mirror>
   <id>aliyun</id>
   <mirrorOf>central</mirrorOf>
   <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
</mirror>
```
* 仓库

> 默认官方repository<br>
> 第三方repository  [http://maven.aliyun.com/nexus/content/groups/public/](http://maven.aliyun.com/nexus/content/groups/public/)<br>
> 本地maven仓库 [http://132.42.43.156:8081/nexus/#welcome](http://132.42.43.156:8081/nexus/#welcome)<br>


## GIT
```
https://git.coding.net/zh_xin/msframework.git
https://git.coding.net/zh_xin/Product.git
https://git.coding.net/zh_xin/User.git
```

## 开发工具
1. 基础环境
* git
* maven
* jdk1.6 1.7 1.8
* tomcat7
2. 开发工具
* jetBrains
>> java IDEA <br>
>> web  WebStorm <br>
>> python pyCharm <br>
>> php phpStorm <br>
* Mysql
>>Navicat

## ZEAL开发框架体系
* ZEAL-MSF
基于SpringMVC Mybatis微服务框架
* ZEAL-UI
基于JQUERY 前端UI基础框架(应用开源项目作为基础二次开发)
* ZEAL-UI-MOBILE
基于ZEPTO 移动端UI基础框架(应用开源项目作为基础二次开发)
* ZEAL-APP
基于Cordova、React技术栈的Hybird APP工程框架,支持Android Ios Wechat Wap
* ZEAL-WEB
基于React技术栈前后端分离的现代WEB工程框架

## ZEAL-MSF
```
msframework
├── msf -datasource    //数据源处理包
├── msf -cache         //缓存处理包
├── msf -constant      //常量包
├── msf -common        //通用包
|    ├── model 	       //通用模型
├── msf -kit             //工具包
|    ├── http		     //http
|    ├── mail		     //邮件处理
|    ├── shortmessage    //短信处理
|    ├── office		     //excel word处理
|    ├── io		         //io相关
|    ├── json   	     //json处理
|    ├── thread          //线程处理
|    ├── text		     //文本处理
|    ├── date		     //日期时间
├── msf -security
|    ├── oauth		     //认证
|    ├── captcha         //验证码
|    ├── encryption      //加解密
├── msf -server
|    ├── upload		     //上传
|    ├── exception	     //异常处理
├── msf -template	     //模板引擎
|    ├── freemark
|    ├── jinja
```
## JAVADOC
[easy-zeal](http://132.42.43.149:8686/docs/easy-zeal/)<br>
* doc注释写法
```
/**
* 用特殊的字符连接字符串
*
* @param strings 要连接的字符串数组
* @param spilit_sign 连接字符
* @return 连接字符串
*/
public static String stringConnect(String[] strings, String spilit_sign) {}
```
* 文档生成
```
mvn javadoc:javadoc
```

## 业务服务
### 为什么ZEAL-MSF框架建议采用多模块的maven项目？

我们倡导的概念就是“低耦合，高内聚”，将项目划分多模块，可以极大的提高代码重用性。

对于一般的项目我们是这么分层的：

* dao层负责数据库的交互。
* service层对内业务逻辑。
* api层对外暴露业务逻辑接口。
* web层负责与客户端交互。
* model层存放的是模型实体类。
* common层存放常用的一些本工程公用的工具类等。
* contronller层负责请求拦截处理。

对应的，在本项目中，我们会看到一些包名：

* com.chinaunicom.zeal.xxx.dao
* com.chinaunicom.zeal.xxx.service
* com.chinaunicom.zeal.xxx.api
* com.chinaunicom.zeal.xxx.web
* com.chinaunicom.zeal.xxx.common
* com.chinaunicom.zeal.xxx.model
* com.chinaunicom.zeal.xxx.crontroller
* com.chinaunicom.zeal.xxx.restful

### 项目结构

#### 项目整体目录

```
user
├── user-common -- 公共模块，主要存放一些工具类
|    ├── src
|    ├── pom.xml -- 打包方式：jar
├── user-dao -- 存放mybatis相关的mapper接口
|    ├── src
|    ├── pom.xml -- 打包方式：jar
├── user-pojo -- 存放实体类
|    ├── src
|    ├── pom.xml -- 打包方式：jar
├── user-service -- 存放业务逻辑类
|    ├── src
|    ├── pom.xml -- 打包方式：jar
├── user-web -- 存放前台页面
|    ├── src
|    ├── pom.xml -- 打包方式：war
├── user-controller -- 存放请求交互相关的handler
|    ├── src
|    ├── pom.xml -- 打包方式：jar
├── pom.xml --打包方式为pom，一些公用的依赖
```
开发数据库
dao->jdbc.properties
```
jdbc.url=jdbc:mysql://10.124.128.176:31000/egroup?useUnicode=true&characterEncoding=utf8
jdbc.username=egroup
jdbc.password=*****
```

### 各模块的依赖关系

## EDAS-HSF
```
开发环境
10.124.128.201  jmenv.tbsite.net
本地开发
132.42.43.159  jmenv.tbsite.net
```
提供者
hsf-provider-beans.xml
```
<hsf:provider
    id="userServiceApiProvider"
    interface="com.chinaunicom.zeal.user.service.api.UserServiceApi"
    ref="userServiceApi"
    version="1.0-SNAPSHOT"
    group="zeal-user"
/hsf:provider>
```
消费者
hsf-consumer-beans.xml
```
<hsf:consumer
    id="userServiceApi"
    interface="com.chinaunicom.zeal.user.service.api.UserServiceApi"
    version="1.0-SNAPSHOT"
    group="zeal-user">
</hsf:consumer>
```


## 数据分页Mybatis-PageHelper
[Mybatis-PageHelper](https://github.com/pagehelper/Mybatis-PageHelper)
mybatis-config.xml

1. PageHelper.startPage(page,10);
2. 参数方式
```
List<Product> selectAll(@Param("pageNum") int pageNum,
                        @Param("pageSize") int pageSize);
```

## 开发部署
```
deployer/*****
SSH端口8022

10.124.134.161
10.124.134.226
10.124.134.229
10.124.134.230
```
部署web或restful项目War包到tomcat的deploy目录
```
/home/deployer
|    ├──taobao-tomcat-production-7.0.59.3
     |   ├─deploy
```
访问URL需添加context path,例如
```
http://10.124.134.226:8080/user-web/
http://10.124.134.229:8080/product-web/
```
