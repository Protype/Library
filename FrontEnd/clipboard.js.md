# 剪貼簿複製 clipboard.js

###### tags: `FrontEnd` `JavaScript` `Clipboard`

![](https://hackmd.io/_uploads/BkOP76W7U.png)

### ⚖️ `MIT License`

- Document: https://clipboardjs.com
- Github: https://github.com/zenorocha/clipboard.js/
- Official Site: https://clipboardjs.com

## Quick Start

#### Use NPM

```shell
npm install clipboard
```

#### Use CDN

```htmlmixed
<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.4/clipboard.min.js"></script>
```

快速相容式寫法，用 prompt 的巧思是參考 [#1]

```javascript
// Clipboard
new ClipboardJS ('[data-ui="clipboard"]')
  .on ('success', function (e) {
    alert ('已複製');
  }).on ('error', function(e) {
    prompt ('請使用 Ctrl + C 或 Cmd + C, 並按下 Enter 以複製', 'copy-me-content');
  });
```

## Usage

初始化，支援 DOM selector、HTML element(s)

```javascript
new ClipboardJS ('data-ui=["clipboard"]');
```

透過 `data-clipboard-text` 抓取文字

```htmlmixed
<a href="javascript:void(0)" data-ui="clipboard" data-clipboard-text="copy me !"></a>
```

透過 `data-clipboard-target` 從目標抓取

```htmlmixed
<input id="name" value="My name">

<a href="javascript:void(0)" data-ui="clipboard" data-clipboard-target="#name"></a>
```

事件

```javascript
var clipboard = new ClipboardJS('.btn');

clipboard.on('success', function(e) {
    console.info('Action:', e.action);
    console.info('Text:', e.text);
    console.info('Trigger:', e.trigger);

    e.clearSelection();
});

clipboard.on('error', function(e) {
    console.error('Action:', e.action);
    console.error('Trigger:', e.trigger);
});
```


其他更多請見 [Document](https://clipboardjs.com)

## Note & Experience

## Used by

- 2020 可澄音樂 PureStage

## Reference

- [#1 - How would I implement 'copy url to clipboard' from a link or button using javascript or dojo without flash](https://stackoverflow.com/questions/16526814/how-would-i-implement-copy-url-to-clipboard-from-a-link-or-button-using-javasc)