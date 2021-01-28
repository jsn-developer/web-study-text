# クラス名によるスタイルの適用

前項では、すべてのdiv要素に対するスタイル指定を紹介しましたが、
一部のdiv要素にのみ適用したい場合があります。

その場合には、要素の他にクラスを指定することで、
特定の要素に対してのみ適用できます。

```html:class.html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="site.css">
    <style type="text/css">
        .red {
            color:red;
        }

        .blue {
            color:blue;
        }
    </style>
</head>
<body>
    <div class="red">
        色が赤くなります。
    </div>
    <div class="blue">
        色が青くなります。
    </div>
</body>
</html>
```

実際に上記コードを実行すると、以下のようになります。

![赤と青](./shots/css/shot_c1_2.png)

正常に赤と青が表示されましたでしょうか？

このように、クラス指定を組み合わせることで
より簡単にスタイルの指定ができます。
