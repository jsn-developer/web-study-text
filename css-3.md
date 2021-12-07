# 要素の位置関係をマスターする

## 要素の余白

要素に対して余白を付与するためには、2つの方法があります。

- margin
- padding

marginは、「要素の外部」に対する余白、
paddingは、「要素の内部」に対する余白となります。

図にすると以下のようになります。

![marginとpadding](./shots/css/css2-6.png){width=300px}

例として、以下のようなcssを考えます。

```css
div {
  background-color: blue;
  display: inline-block;
}
p {
  padding: 8px;
  margin: 8px;
  background-color: gray;
}
span {
    background-color: red;
}
```

```html
<html>
  <body>
    <div>
      <p>
        <span>inner</span>
      </p>
    </div>
  </body>
</html>
```

この場合、以下のように表示されます。

![inner](./shots/css/css-2-1.png)

p要素（灰色の背景部分）に対して設定したmarginおよびpaddingが反映されることで、
div要素（青い背景）、およびspan要素（赤い背景）の部分に対しての空白部分が生成されます。

### marginの相殺

marginで空白を指定した要素が並んだ場合に、それぞれで指定したmarginの値が相殺される場合があります。

例として、下記のようなスタイルを考えます。

```css
p{
  float: left;
  border: solid 1px gray;
  margin-left: 10px;
  margin-right: 20px;
}
```

```html
<html>
  <body>
    <div>
      <p>first</p>
      <p>second</p>
    </div>
  </body>
</html>
```

その際、以下のように表示されます。

![相殺](./shots/css/css-2-2.png)

この時、2つの要素の間には20pxの間隔が指定されています。
スタイルだけを見ると、left要素に10px、right要素に20pxをmarginを指定しているため合わせて30pxの間隔になるように思えます。
しかし、この場合にはmargin同士は相殺されるため、大きい値である20pxが適用されることになります。

## 要素の配置と位置関係

### position

positionを指定することで、要素の位置を親からみてどう配置するのかを設定することができます。
指定できるものとしては、以下のものがあります。

- absolute
- relative
- fixed
- static（標準、指定なしと同義）

試しに、それぞれの動きを見てみましょう。

```css
.box{
  position: absolute;
  top: 30px;
  left: 30px;
  width: 100px;
  height: 100px;
  background-color: gray;
}

p {
  margin: 0px;
}

.absolute {
  top: 10px;
  left: 10px;
  position: absolute;
  background-color: red;
}
.relative {
  top:30px;
  left:30px;
  position: relative;
  background-color: blue;
  color: white;
}
.fixed {
  top:20px;
  left: 20px;
  position: fixed;
  background-color: yellow;
}
```

```html
<html>
  <body>
    <div class="box">
      <p class="absolute">absolute</p>
      <p class="relative">relative1</p>
      <p class="relative">relative2</p>
      <p class="fixed">fixed</p>
    </div>
  </body>
</html>
```

実行すると、以下のようになります。

![](./shots/css/css-2-3.png)

特徴をまとめると、以下のようになります。

#### relative

relativeは、「元々表示する位置からの相対距離」を指定することで表示位置をずらす事ができます。
そのため、例のように２つのrelativeを指定した場合、二つの要素が並んで(+30,+30)された場所に表示されます。

#### absolute

absoluteは「親要素を起点とした絶対位置」を指定します。
例の場合、親の左上を起点として(10, 10)の位置に表示しています。

#### fixed

relativeは、absoluteと同様に絶対位置を指定して配置しますが、
「親要素に関係なく、画面に対する絶対位置」で表示されます。

そのため、親要素の場所に関係のない配置がされますので構成に気をつける必要があります。

### float

通常、ブロック要素を複数個定義した場合には改行されるため縦並びに表示されます。
floatプロパティを使用することで、綺麗な横並びを実現できます。

```css
p {
  float: left;
  margin-left: 10px;
}
```

```html
<html>
  <body>
    <div class="container">
      <p>Item1</p>
      <p>Item2</p>
      <p>Item3</p>
    </div>
  </body>
</html>
```

実行すると、以下のように表示されます。

![](./shots/css/css-2-4.png)

このように、floatを使用することで綺麗な横並びを実現できます。
なお、float:right;を指定することで、右を基準とした並びをすることもできます。

#### floatのクリア

floatを解除する場合、以下のような記載をすることで解除する事ができます。

```css
p {
  float: left;
  margin-left: 10px;
}

p:last-child {
  clear: left;
}
```

```html
<html>
  <body>
    <div class="container">
      <p>Item1</p>
      <p>Item2</p>
      <p>Item3</p>
      <p>Item4</p>
    </div>
  </body>
</html>
```

実行すると以下のように表示されます。

![float](./shots/css/css-2-5.png)

cssにて「p:last-child」に対してclear:leftを指定していますが、
この「last-child」は、「pの中の最後の要素」を表しています。

つまり、「最後のp要素のみfloatを解除する」ことになります。

この「:last-child」を「擬似クラス」と呼びます。
次回は、この擬似要素について解説します。
