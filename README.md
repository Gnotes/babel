# babel

**Babel** 是一个 JavaScript 编译器,用于转换JS语法为其他规则的工具.  

## .babelrc

*类似其他可执行文件一样，`.babelrc`是babel编译的配置文件，在`babel6` 的配置中`必须存在`此文件，于项目`根目录`*  
- Json 格式，由于.babel将序列化为JSON5，因此此文件是Json格式书写

```json
{
  "presets":["es2015", "react", "stage-2"],
  "plugins":["transform-react-jsx"],
  "env": {
    "production": {
      "plugins": ["transform-react-constant-elements"]
    }
  }
}
```

## 可选参数

- [Options](https://babeljs.io/docs/usage/api/#options)  
- [Options](http://babeljs.cn/docs/usage/options/)  

| 名称 | 默认值 | 描述 |
| --- | --- | --- |
| `babelrc` | true | 指定是否需要使用`.babelrc` `.babelignore` 文件，在使用`CLI` 并指定 `--no-babelrc` 参数时这个选项将不可用 |
| `comments` | true | 是否输出注释 |
| `env` | **`{}`** | 指定babel环境参数，如：`{ env: { production: { ... } } }` ，在指定`BABEL_ENV`=`production` 时，将使用这个配置，如果没有将会查找`NODE_ENV`，否则该环境值为`development`|
| `plugins` | **`[]`** | 配置babel编译插件 |
| `presets` | **`[]`** | 配置babel预设转换规则 |
| `...` | *—* | 查看原文 |


## presets

预设你需要的编码规则(方法)，如你使用箭头函数(属于es6语法)，你就应该设置为`es2015` 

- env
- es2015
- es2016
- es2017
- latest (推荐使用env)
- react
- stage-0
- stage-1
- stage-2
- stage-3

**这些预设转换规则对应`babel-preset-xxx`，如：`env` -> `babel-preset-env`，这些包都需要`npm install`**  

### es2015 & es2016 & es2017 & latest & react ...

- es2015 也就是包含了 `ES6` 的方法
- es2016 也就是包含了 `ES7` 的方法
- es2017 也就是包含了 `ES8` 的方法
- latest 是一个特殊的presets，包括了es2015，es2016，es2017的插件（目前为止，以后有es2018也会包括进去）
- react 添加jsx,flow

### stage-x(stage-0/1/2/3/4)

*stage-x和上面的es2015,es2016等类似，只是还没有正式加入到babel release中，但是它是按照JavaScript的提案阶段区分的，一共有5个阶段。而数字越小，阶段越靠后，存在依赖关系。也就是说stage-0是包括stage-1的，以此类推*
 
## plugins

在presets中其实就是将插件添加到了对应的版本，如果我们不配置presets，而只针对某一个转码的话可以直接使用plugins进行配置，如上的箭头函数：`es2015-arrow-functions`，我们就可以使用箭头函数的方式进行书写了

```json
{
  "plugins": ["transform-es2015-arrow-functions"]
}
```

## 参考文档

- [babel 中文](http://babeljs.cn/)  
- [阮一峰 babel入门教程](http://www.ruanyifeng.com/blog/2016/01/babel.html)  
- [babel 英文](https://babeljs.io/)  
- [babel github](https://github.com/babel/babel)  
- [如何写好.babelrc？Babel的presets和plugins配置解析](https://zhuanlan.zhihu.com/p/24224107)  