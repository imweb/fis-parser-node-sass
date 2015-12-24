fis-parser-node-sass-imweb
============================

## 描述

* 修改自fis官方提供的插件`fis-parser-node-sass`，支持查找lego_modules目录的组件。
* 配合`fis3-command-imweb` 插件，提供了更好的watch性能，并支持watch到scss的依赖文件(import)

全局安装

```bash
npm install fis-parser-node-sass-imweb -g
```

使用

```scss
@import 'lego_modules/ui/a.scss'; // 等同 lego_modules/ui/0.0.1/a.scss ，默认使用ui目录的最新版本。
@import 'lego_modules/ui@0.0.2/a.scss'; // 等同 lego_modules/ui/0.0.2/a.scss
@import 'lego_modules/ui/0.0.3/a.scss'; // 等同 lego_modules/ui/0.0.3/a.scss
```

规范

* 当引用路径包含lego_modules时，将路径转换为包含版本号的路径。


# 以下为官方README内容


## 安装与使用 

全局安装

```bash
npm install fis-parser-node-sass -g
```

## FIS2
开启插件

```javascript
fis.config.merge('modules.parser', {
    sass : 'node-sass',
    scss: 'node-sass'
});

fis.config.merge('roadmap.ext', {
    sass: 'css',
    scss: 'css'
});
```

插件配置

```javascript
fis.config.set('settings.parser.sass', {
    // 加入文件查找目录
    include_paths: []
});
```

## FIS3

```js
fis.match('*.scss', {
  rExt: '.css',
  parser: fis.plugin('node-sass', {
    // options...
  })
})
```


