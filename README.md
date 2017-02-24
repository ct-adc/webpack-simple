## 使用前提

本机已安装vue-cli

## 使用

**step1**: 初始化项目

```
vue init ct-adc/webpack-simple yourProjectName
```

**step2**: 安装依赖

```
npm install
```
安装依赖会根据package.json中定义的依赖及版本进行安装；
如果你不需要使用package.json中定义的某些依赖，可以在安装前将其从package.json中去除；

**step3**: 现在可以进行项目开发了!

## Q & A

#### 不想使用jshint检查某些第三方代码怎么办？

在moudle.rules中将jshint-loader项的exclude中加入第三方代码的路径，webpack支持你使用正则进行设置；

#### jshint检查规则怎么设置？

项目根目录下有.jshintrc文件，webpack中用于检查代码的jshint-loader检查规则就是以此为依据的。
如果不想让其检查某些项，就置其为false；

常见的jshint配置有:
strict: 是否按es5严格模式执行代码检查;
globals: 全局变量检查，如$/alert/console等；

你可以参照[jshint官方配置文档](http://jshint.com/docs/options/)进行更多个性化配置。

例如你引入了一个第三方插件，这个插件向外释放了一个变量A，那么你可以在globals中设置A:false；这样jshint就不会提示你:'A is not defined!'的错误;

#### 生成后的文件在哪里？

默认生成的文件都在项目根目录下的asset文件夹中，如果你的项目中同时用了js/css/图片/字体，那么将生成:
* asset/js: 存放js；
* asset/css: 存放css；
* asset/font: 存放字体;
* asset/img: 存放图片；

#### 上线后，项目中的asset和view不是在一个目录的，但本地又是在同一个路径下，那我本地怎么调试?

可以设置outpub.publicPath为线上的路径，如/static/asset，相应的，html中也只要引用/static/asset下面的文件；
这样本机和线上的目录引用就一致了。





