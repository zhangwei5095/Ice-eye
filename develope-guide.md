# 数据库
  本项目依赖mysql数据库，需要本地安装mysql，建立iceeye的database，用户名为iceeye，密码为123456，初始化脚本位于doc\install\initsql.sql里。

# Ice web工程编译运行

工程采用了spring-boot框架来简化开发和部署，下载源码工程，然后，
在eclipse中导入maven项目并执行Run As——> Maven Build，即可编译源码，编译成功以后，在target目录下生成了all in one的JAR包ice-eye-web-xxxxx.jar,它包括所有依赖库，命令行运行 java -jar ice-eye-web-xxxxx.jar即可启动Web，随后，在浏览器输入http://localhost:8080即可访问。
eclipse中调测的时候，运行Run As——>Java Application即可启动Web。
项目编译依赖JDK 7。

## 工程目录说明
src\main目录为主要源码
src\test目录为测试源码，主要为单元测试
src\main目录下如下包结构：

 - io.mycat.ice.domain目录为存放域对象，这些域对象对应mysql数据库里的一个表
 - io.mycat.ice.bean，为常规Java Bean对象，用于数据传递或转换等目的
 - io.mycat.ice.rest，为提供Rest服务的Java服务对象，用于内部或外部系统访问
 - io.mycat.ice.ctrl，为Spring MVC的Controller对象所在地方
 - io.mycat.ice.service，为Spring的Service Bean对象所在地方
 建议ctrl包与service包可以按照模块名称分子包，比如io.mycat.ice.ctrl.install.xxx

页面文件（静态，JSP、JS、Images等）则在以下目录
 - src\main\resources\static  在Web里这是ROOT目录