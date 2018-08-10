# Nunjucks-cst

[Nunjucks](https://mozilla.github.io/nunjucks/) is a full featured
templating engine for javascript. It is heavily inspired by
[jinja2](http://jinja.pocoo.org/). View the docs
[here](https://mozilla.github.io/nunjucks/).

# 重要说明

由于`nunjucks`模板引擎不兼容emberjs的`{{}}`标签，所以修改了`nunjucks`模板引擎的标签占位符。

| nunjucks默认占位符 | 修改后的占位符 |
| ---------------- | ------------- |
|       `{{`        |      `{$`      |
|        `}}`        |     `$}`      |
|        `{#`        |      `{@`     |
|        `#}`        |      `@}`     |


修改后使用`nunjucks`模板引擎解析的hexo插件会解析失败，所以需要同步修改依赖`nunjucks`模板引擎的hexo插件。

之所以这么做是因为[hexo](http://hexo.io)使用`nunjucks`解析生成静态HTML。然后我的主站[xcoding](http://xcoding.tech)使用了GitHub+hexo搭建。然后博客主要用于记录[EmberJS](http://emberjs.com)相关文章，EmberJS很多标签都是使用`{{}}`，与模板引擎的占位符冲突。

冲突出现的问题如下：
```js
http://hexo.io/docs/troubleshooting.html
Template render error: (unknown path) [Line 37, Column 81]
  expected variable end


Unhandled rejection Template render error: (unknown path) [Line 10, Column 95]
  unexpected token: #
```

当然也有其他解决方案，但是自定义模板占位符是比较好的方法，详细可以看如下博客：
[如何从根本解决hexo不兼容{{}}标签问题](http://xcoding.tech/2018/08/08/hexo/%E5%A6%82%E4%BD%95%E4%BB%8E%E6%A0%B9%E6%9C%AC%E8%A7%A3%E5%86%B3hexo%E4%B8%8D%E5%85%BC%E5%AE%B9%7B%7B%7D%7D%E6%A0%87%E7%AD%BE%E9%97%AE%E9%A2%98/)


## Installation

`npm install nunjucks-cst`

(View the [CHANGELOG](https://github.com/mozilla/nunjucks/releases))

## Documentation

See [here](https://mozilla.github.io/nunjucks/).

## Browser Support

Supported in all modern browsers. For IE8 support, use [es5-shim](https://github.com/es-shims/es5-shim).

## Tests

Run the tests with `npm test`.

Watch `master` branch's [tests running in the browser](https://mozilla.github.io/nunjucks/files/tests/browser/).

## Mailing List

Join our mailing list and get help with and issues you have:
https://groups.google.com/forum/?fromgroups#!forum/nunjucks

## Want to help?

Contributions are always welcome! Before you submit an issue or pull request, please read our [contribution guidelines](CONTRIBUTING.md).

[Contributors](https://github.com/mozilla/nunjucks/graphs/contributors)
