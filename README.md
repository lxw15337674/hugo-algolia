# hugo-lovelt-algolia

因为[hugo-algolia](https://github.com/replicatedhq/hugo-algolia)生成的索引文件uri是相对路径，会导致搜索结果的url出问题。（具体在这个[issues](https://github.com/dillonzq/LoveIt/issues/421)里。）。网上的教程都不正确，都会出现这个问题。为了解决这个问题，我修改了[hugo-algolia](https://github.com/replicatedhq/hugo-algolia)源码，加上了`baseURL`（ 如果没有设置默认为相对路径）,作为路径前缀配置，解决这个问题。

正确的配置：

```yaml
---
baseURL: '/'
algolia:
  index: "index-name"
  key: "[your API key]"
  appID: "[your app id]"
--- 
```



其他的命令和[hugo-algolia](https://github.com/replicatedhq/hugo-algolia)一致，但是包名要换成`hugo-lovelt-algolia`，这里只列出常用命令

### 安装

```
npm install hugo-lovelt-algolia
```

or

```bash
yarn add hugo-lovelt-algolia
```



### 生成索引

```bash
hugo-lovelt-algolia
```



### 生成并上传索引

```
hugo-algolia -s
```