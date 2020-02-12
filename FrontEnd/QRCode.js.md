# QRCode 產生套件 QRCode.js

###### tags: `FrontEnd` `QRCode` `JavaScript`

### ⚖️ `MIT License`

- Document: https://github.com/davidshimjs/qrcodejs
- Github: https://github.com/davidshimjs/qrcodejs
- Official Site: https://github.com/davidshimjs/qrcodejs


在 Github 上從 JavaScript 產生 QRCode 的相關工具裡，星星數最多的一個套件，但從 2015 年就停止了維護，並且似乎有不少 bug。


## Quick Start

#### Use NPM

這是由 llyys 所包裝的版本

```shell
npm install qrcodejs
```

#### Fetch file

```htmlmixed
wget https://raw.githubusercontent.com/davidshimjs/qrcodejs/master/qrcode.min.js -o qrcode.min.js
```

## Usage

:::danger
🧨 已遇過自動產生失敗的問題，可透過循環檢查來確保，其他可參考 [#1]
:::

#### HTML

```htmlmixed
<div id="qrcode"></div>
```

#### JavaScript

:::warning
👉 如果要用 jQuery 的話記得要用 `$()[0]` 取得 node，否則會出現 `'appendChild' of null` 錯誤。
:::


直接呼叫

```javascript
new QRCode (document.getElementById ("qrcode"), "text-or-url");
```

多參數呼叫

```javascript
var qrcode = new QRCode (document.getElementById ("qrcode"), {
  text: "http://jindo.dev.naver.com/collie",
  width: 128,
  height: 128,
  colorDark : "#000000",
  colorLight : "#ffffff",
  correctLevel : QRCode.CorrectLevel.H
});
```

其他函式

```javascript
qrcode.clear(); // clear the code.
qrcode.makeCode("http://naver.com"); // make another code.
```

針對自動產生 QRCode 失敗的處理方式

```javascript

// QRCode
var qr
  , qrnode = $('#qrcode')
  , imgnode = null
  , qrurl = 'url'
  , qrtimer = null
  , qrcounter = 0
  ;

// Enable interval
qrtimer = setInterval (qrcodeGenerator, 400);

// QRCode generator
function qrcodeGenerator () {

  // 找看看 img node
  if (! imgnode || imgnode.length <= 0)
    imgnode = qrnode.find ('img');

  // 最多等 10 次，或 img 確實產生了（src 不為空），結束 interval
  if (++qrcounter > 10 || (imgnode && imgnode.length > 0 && imgnode.attr ('src') != '')) {
    clearInterval (qrtimer);
    return;
  }

  // 還沒產生 QRCode 的話，先產生
  if (! qr) {
    qr = new QRCode (qrnode[0], {
      text: qrurl,
      width: 200,
      height: 200,
      colorDark : "#000000",
      colorLight : "#ffffff",
      correctLevel : QRCode.CorrectLevel.H
    });
  }

  // 每次都要求產生 qrcode
  qr.makeCode (qrurl);
}
```

## Note & Experience

1. 如果用 jQuery 記得要取到 node 本身
2. 自動產生失敗有人提到可透過 `MutationObserver` 解決，但我還是偏好 interval - [#1]

## Used by

- 2020 可澄音樂 PureStage

## Reference

- [#1 - 使用 qrcodejs 生成二維碼的幾個問題](https://www.twblogs.net/a/5bf7fb16bd9eee18cf8aa268)

