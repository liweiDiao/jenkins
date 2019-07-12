
### Linux安装Jenkins    
### Jenkins依赖jdk和git，请先安装jdk和git，这里不再做详细说明。    
     如：安装git    
  ![Image git](https://github.com/liweiDiao/jenkins/blob/master/image/1.png)    
#### 1、安装Jenkins    
     先执行：    
     wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo    
     再执行：    
     rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key   
     最后执行：    
     yum install -y jenkins 
     
   ![Image 步骤1](https://github.com/liweiDiao/jenkins/blob/master/image/2.png)    
   
   ![Image 步骤2](https://github.com/liweiDiao/jenkins/blob/master/image/3.png)    
   
#### 2、启动Jenkins
     执行：    
     service jenkins start    
     报错：    
   ![Image 步骤3](https://github.com/liweiDiao/jenkins/blob/master/image/4.png)    

#### 3、解决Jenkins启动错误    
     根据错误提示，输入：systemctl status jenkins.service    
   ![Image 步骤4](https://github.com/liweiDiao/jenkins/blob/master/image/5.png)    
     
     查看了一下jdk的目录 ： echo $JAVA_HOME    
   ![Image 步骤5](https://github.com/liweiDiao/jenkins/blob/master/image/6.png)    
     
     找到etc/init.d 下的jenkins文件    
   ![Image 步骤6](https://github.com/liweiDiao/jenkins/blob/master/image/7.png)    
     
     修改jenkins文件，添加jdk的目录： 当前的是：/home/java/jdk1.8.0_161/bin/java    
   ![Image 步骤7](https://github.com/liweiDiao/jenkins/blob/master/image/8.png)
     
     重新启动jenkins服务    
   ![Image 步骤8](https://github.com/liweiDiao/jenkins/blob/master/image/9.png)
     
#### 4、访问Jenkins    
     访问jenkins,  浏览器输入： http://21*.***.***.***:8080    
   ![Image 步骤9](https://github.com/liweiDiao/jenkins/blob/master/image/10.png)    
     
     然后将/var/lib/jenkins/secrets/initialAdminPassword 中的密码复制到管理员密码处，然后点 “继续”    
   ![Image 步骤10](https://github.com/liweiDiao/jenkins/blob/master/image/11.png)    
     
     选择插件， 我在这里选择推荐的插件    
   ![Image 步骤11](https://github.com/liweiDiao/jenkins/blob/master/image/19.png)   
   
   ![Image 步骤12](https://github.com/liweiDiao/jenkins/blob/master/image/13.png)    
     
     创建一个Jenkins管理员用户    
   ![Image 步骤13](https://github.com/liweiDiao/jenkins/blob/master/image/15.png)    
     
     保存并完成后，显示实例配置；这里我选择的是现在不要    
   ![Image 步骤14](https://github.com/liweiDiao/jenkins/blob/master/image/16.png)    
     
     最后配置完成，开始使用Jenkins；    
   ![Image 步骤15](https://github.com/liweiDiao/jenkins/blob/master/image/17.png)    
   
   ![Image 步骤16](https://github.com/liweiDiao/jenkins/blob/master/image/18.png)    
   
   #### 5、插件安装（如果在安装Jenkins的时候没有安装相关插件，可以按照如下方式安装，已经安装，则不需要）  系统管理>>插件管理    
      gitlab插件：    
   ![Image 步骤16](https://github.com/liweiDiao/jenkins/blob/master/image/20.png)  
   
      maven插件：    
   ![Image 步骤16](https://github.com/liweiDiao/jenkins/blob/master/image/21.png)      
      
      常用的插件    
      Deploy to container plugin（部署用）    
      Git plugin（GIt插件）    
      Github Integration Plugin（Git集成）    
      Publish Over SSH（通过SSH来执行命令）    
      Maven Integration（maven插件）    
      postbuildscript（用于执行shell命令）    
      build with parameters（用于构建时可以选择分支，而不是写死要构建的分支名字）    
      
   #### 6、配置邮件功能  系统管理>>系统设置    
   ![Image 步骤16](https://github.com/liweiDiao/jenkins/blob/master/image/22.png)    
      
      设置邮箱：     
   ![Image 步骤16](https://github.com/liweiDiao/jenkins/blob/master/image/23.png)    
      
      设置邮箱配置:    
   ![Image 步骤24](https://github.com/liweiDiao/jenkins/blob/master/image/24.png)    
      
   ![Image 步骤25](https://github.com/liweiDiao/jenkins/blob/master/image/25.png)    
      
      测试邮件是否正常：    
   ![Image 步骤25](https://github.com/liweiDiao/jenkins/blob/master/image/26.png)    
   
   #### 7、安装maven  下载maven包，这里下载3.6.1  ，下载地址：http://mirror.bit.edu.cn/apache/maven/maven-3/3.6.1/binaries/    
   


   
 
   
     
