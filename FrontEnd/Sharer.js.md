# 社群分享套件 Sharer.js

###### tags: `FrontEnd` `JavaScript`

![](https://hackmd.io/_uploads/SJL60cWXI.png)

- Document: http://ellisonleao.github.io/sharer.js/
- Github: https://github.com/ellisonleao/sharer.js/
- Official Site: http://ellisonleao.github.io/sharer.js/

## Quick Start

#### Use NPM

```shell
npm install sharer.js
```

#### Use CDN

```htmlmixed
<script src="https://cdn.jsdelivr.net/npm/sharer.js@latest/sharer.min.js"></script>
```

## 常用 Code

:::info
💡Sharer.js 引入後會自動啟用對 **`data-sharer`** 作判斷，不需額外手動處理。
:::

#### Facebook

```htmlmixed
<button class="button" data-sharer="facebook" data-hashtag="hashtag" data-url="url">Share on Facebook</button>
```

#### Line

```htmlmixed
<button class="button" data-sharer="line" data-title="title" data-url="url">Share on Line</button>
```

其他更多請見 [Document](http://ellisonleao.github.io/sharer.js/#line)

## Note & Experience

1. 不支援 Instagram，ig 沒有提供 share API 或 endpoint
2. 不支援微信，微信分享需要註冊他的 SDK，一般做法是改為生成網址 QRCode - [#1]

## Used by

- 2020 可澄音樂平台 PureStage

## Reference

- [#1 - 微信分享填坑指南](https://segmentfault.com/a/1190000014461916)

