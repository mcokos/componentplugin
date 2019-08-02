#### 一、插件的主要配置

根项目的`gradle.properties`中必须配置`mainmodulename`属性,指定主项目名

```properties
#指定项目的主module
mainmodulename = app
```

各个组件中的`gradle.properties`文件中必须配置`isRunAlone`属性，来指定是否可以独立运行"

```properties
isRunAlone=true
```

主项目的`gradle.properties`文件中需要配置的属性

```properties
#指定项目的Application 必须设置
applicationName=com.gfd.video.app.MainApplication
#是否可以独立允许
isRunAlone=true
#自动添加依赖，只在运行assemble任务的才会添加依赖，因此在开发期间组件之间是完全感知不到的，这是做到完全隔
#离的关键 
#支持两种语法：module或者modulePackage:module,前者之间引用module工程，后者使用componentrelease中
#已经发布的aar
debugComponent=Home,Crosstalk,Music,Player
compileComponent=Home,Crosstalk,Music,Player
#设置组件 注册 卸载接口
applicationLike=com.gfd。provider.router.component.IApplicationLoad
```

#### 二、各个组件独立运行时 manifest.xml 配置

在各个组件的*/src/main* 下建**runalone**文件夹

在文件下新建*AndroidManifest.xml* ，配置启动activity的配置
