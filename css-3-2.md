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
