# 概要

textareaで入力した文字列をファイルで保存するための最低限のサンプルです。

# 実行環境

* Node.js - 10.x
* Yarn - 1.12.x
* lite-server - 2.5.x

# 動作確認

## 1. サンプルのダウンロード

```
git clone git@github.com:yasu-s/blob-dl-js-sample.git
```

## 2. パッケージインストール  

```
cd blob-dl-js-sample
yarn
```

## 3. サンプルの起動  

```
yarn start
```

## 4. 実行結果

http://localhost:3000/

![blob_dl](https://user-images.githubusercontent.com/2668146/63091929-fce14000-bf9a-11e9-95d2-8c678ad7cb2d.gif)

# サンプルソース  

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>Blob Sample</title>
  <script>
    function save() {
      // テキストエリアより文字列を取得
      const txt = document.getElementById('txt').value;
      if (!txt) { return; }

      // 文字列をBlob化
      const blob = new Blob([txt], { type: 'text/plain' });

      // ダウンロード用のAタグ生成
      const a = document.createElement('a');
      a.href =  URL.createObjectURL(blob);
      a.download = 'sample.txt';
      a.click();
    };
  </script>
</head>
<body>
  <button onclick="save();">Save Text</button>
  <br />
  <textarea id="txt" cols="50" rows="5"></textarea>
</body>
</html>
```
