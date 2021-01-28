## はじめてのマークアップ

文字を表示することはできましたが、
世の中のWebサイトはもっと華やかだったり別なページに移動できたりしますよね。  
これを実現する為に利用するのが「マークアップ」です。
次は、マークアップによる装飾を行います。

以下のようなコードを書いて、同様にブラウザで実行してみましょう。

```html:bold.html
Hello, <b>BOLD</b> World!
```

![](./shots/html/shot_1_2.png)

「BOLD」の文字だけが太く表示されましたでしょうか？
この「\<b \>」が「太くする」マークアップ記号となります。

このマークアップ記号を一般的に「タグ」と呼びます。
例えば、この記号は一般的に「brタグ」と呼ばれることが多いです。

タグ(マークアップ記号)は、基本的に  

```html
<開始タグ>～</終了タグ>
```

の形で記載し、その囲った中に影響を及ぼします。
この囲った部分を「要素」と呼びます。

開始タグにはそのタグ名を、
終了タグには"/"(スラッシュ)とタグ名を記載します。  
特に終了タグの"/"を忘れないようにしてください。