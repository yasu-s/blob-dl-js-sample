# Overview

This is a minimum sample to save the text entered in textarea as a file.

# System requirements

* Node.js - 10.x
* Yarn - 1.12.x
* lite-server - 2.5.x

# Operation check

## 1. Download Sample

```
git clone git@github.com:yasu-s/blob-dl-js-sample.git
```

## 2. Installing packages  

```
cd blob-dl-js-sample
yarn
```

## 3. Launch sample application  

```
yarn start
```

## 4. Execution result

http://localhost:3000/

![blob_dl](https://user-images.githubusercontent.com/2668146/63091929-fce14000-bf9a-11e9-95d2-8c678ad7cb2d.gif)

# Sample source  

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>Blob Sample</title>
  <script>
    function save() {
      // get string from text area
      const txt = document.getElementById('txt').value;
      if (!txt) { return; }

      // convert string to Blob
      const blob = new Blob([txt], { type: 'text/plain' });

      // a tag generation for download
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
