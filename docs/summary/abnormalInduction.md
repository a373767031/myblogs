# thymeleaf模板解析错误

1. controller传参有误，无法使用modelAndView传参

   定义局部变量model传参，String返回页面即可，不使用modelAndView

2. 项目启动时未扫描到static文件目录下的html文件

   在pom文件加入扫描文件配置，扫描后，重新编译即可

   ```java
   <resources>
       <resource>
           <directory>src/main/resources</directory>
           <includes>
               <include>**/*.**</include>
           </includes>
       </resource>
   </resources>
   ```

--------

# 数据库访问失败

1. 账号密码错误

   SpringBoot工程，在.properties里寻找数据库配置信息，正确配置账户密码即可

   ```
   spring.datasource.username=root
   spring.datasource.password=123456
   ```

2. 账号密码正确，权限不足，拒绝访问（工作中询问领导）

   Linux，进入mysql的bin目录  

   ```
   ./mysql -u root -p
   ```

   再输入密码，进入mysql客户端

   更改你连接数据库账户的权限 、‘root’ 为你的用户名，后面‘123456’为你的密码

   ```
   grant all privileges on *.*  to 'root'@'%' identified by '123456';
   ```

   刷新权限

   ```
   flush privileges
   ```

   重新连接即可

------

