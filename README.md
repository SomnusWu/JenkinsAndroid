# JenkinsAndroid
#使用Jenkins自动化构建

http://www.linuxidc.com/Linux/2015-12/126423.htm

##1：搭建Jenkins环境 ，配置Gradle环境

##2：新建项目 
 "构建一个自由风格的软件项目"
##3：配置项目
![image](https://github.com/SomnusWu/JenkinsAndroid/blob/master/test1.png)
![image](https://github.com/SomnusWu/JenkinsAndroid/blob/master/test2.png)
![image](https://github.com/SomnusWu/JenkinsAndroid/blob/master/test3.png)



###构建触发器中：Execute windows batch command 
执行脚本 ： 'gradlew assembleFlavors_123Release'  
（Studio  Terminal中执行命令）

该脚本需要在AndroidProject 中app build.gradle 配置
定义不同的product flavor 可实现打包不同环境
android ->productFlavors

```java  
  
android {
  buildTypes {
      debug {
          buildConfigField "String", "API_URL","\"http://test.example.com/api\""
          buildConfigField "boolean", "LOG_HTTP_CALLS", "true"
          //getResource().getString(R.string.app_name)
          resValue "string", "app_name", "Example DEBUG"
          signingConfig signingConfigs.releaseKey
      }
      release {
          buildConfigField "String", "API_URL", "\"http://example.com/api\""
          buildConfigField "boolean", "LOG_HTTP_CALLS", "false"
          resValue "string", "app_name", "Example"
          signingConfig signingConfigs.releaseKey
      }
  }
}
  
```


#Save
##立即构建
立即构建该项目
##Console Output
打开控制台 即可看见构建输出  

......
..Finished:SUCCESS  


#构建成功!!!!






