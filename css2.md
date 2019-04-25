# 様々なスタイルを使ってみよう

## 基本となるスタイル

```css
セレクタ {
    設定名: 値;
}

```

### セレクタの種類

#### 要素名セレクタ

pタグやaタグなど、タグの要素名から指定することができます。

例として、aタグの要素を変更します。

```css
a {
    color: red;
    font-size: large;
}
```

こうすることで、全てのa要素に対して上記のスタイルが適用されます。

#### クラス名を指定しての指定

特定の要素にのみ指定を行いたい場合、クラス名を指定してスタイルを記載します。

```css:style.css
.red {
    color: red;
}

.green{
    color: green;
}
```

```html:index.html
<html>
<body>
    <div class="red">Red</div>
    <p class="green">Green</p>
</body>
</html>
```

クラス指定する場合には、要素に関わらず指定することができますが、  
例えば非インライン要素に対するvertical-alignなど、
要素によっては適用されない場合があります。

#### 複数の要素からセレクタを構成する

##### 複数の条件から指定

セレクタを指定する際に、複数の条件を使用してセレクタとすることができます。

例として、「文字を赤くする」ための記載をします。

```css
div.red {
    color: red;
    font-weight: bold;
}

a.red {
    color: red;
    font-size: large;
}
```

```html:index.html
<html>
<body>
    <div class="red">Red</div>
    <br/>
    <a class="green">Green</a>
</body>
</html>
```

この場合、同じclass="red"を指定した場合でも、
divタグは文字が太くなり、aタグは文字が大きくなります。

このように、同じクラス名を使用する場合でも、
要素ごとに違った挙動をさせることができます。

### 色を変更しよう

ここでは、色の変更を行います。

#### 色名指定

CSSでは色名指定で表示できる色が用意されており、色の名称を指定することでその色を表示することができます。

以下に基本色となる16色を示します。

| |色名|RGB値|
|:--|--|--|
| <span style="color:#00FFFF;">■</span> |aqua|#00FFFF|
| <span style="color:#000000;">■</span> |black|#000000|
| <span style="color:#0000FF;">■</span> |blue|#0000FF|
| <span style="color:#FF00FF;">■</span> |fuchsia|#FF00FF|
| <span style="color:#808080;">■</span> |gray|#808080|
| <span style="color:#008000;">■</span> |green|#008000|
| <span style="color:#00FF00;">■</span> |lime|#00FF00|
| <span style="color:#800000;">■</span> |maroon|#800000|
| <span style="color:#000080;">■</span> |navy|#000080|
| <span style="color:#808000;">■</span> |olive|#808000|
| <span style="color:#800080;">■</span> |purple|#800080|
| <span style="color:#FF0000;">■</span> |red|#FF0000|
| <span style="color:#C0C0C0;">■</span> |silver|#C0C0C0|
| <span style="color:#008080;">■</span> |teal|#008080|
| <span style="color:#FFFFFF;">■</span> |white|#FFFFFF|
| <span style="color:#FFFF00;">■</span> |yellow|#FFFF00|

他にも、「拡張された色名」が124色存在しますが、ここでは説明を省略します。

#### 16進数による指定

16進数を用いて、RGBの各値を0~FF(255)の範囲で表現することで色の指定を行うことができます。



#### rgb()による指定

RGB値を10進数で指定したい場合には、rgb()関数を使用します。

```css
selector {
    color: rgb(255,0,0);
}
```

### フォントを指定する

表示する文字に関する指定を行います。

### font-family

フォント名を指定することで、
そのフォントで文字を表示させることができます。

### font-weight

フォントの太さを指定できます。

## 上下左右に寄せる

### 左右に寄せる - text-align

### 上下に寄せる - vertical-align

## 枠をつける - border

## 余白

要素に対して余白を付与するためには、二つの方法があります。

- margin
- padding

marginは、「要素の外部」に対する余白、
paddingは、「要素の内部」に対する余白となります。

図にすると以下のようになります。

<img src="./shots/css/css2-6.png" style="width:300px">

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

<img src="./shots/css/css-2-1.png" >

p要素(灰色の背景部分)に対して設定したmarginおよびpaddingが反映されることで、
div要素(青い背景)、およびspan要素(赤い背景)の部分に対しての空白部分が生成されます。

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

<img src="./shots/css/css-2-2.png" >

この時、二つの要素の間には20pxの間隔が指定されています。
スタイルだけを見ると、left要素に10px、right要素に20pxをmarginを指定しているため、
合わせて30pxの間隔になるように思えますが、
margin同士は相殺されるため、大きい値である20pxが適用されることになります。

## 位置の指定方法

### position

positionを指定することで、要素の位置を親からみてどう配置するのかを設定することができます。
指定できるものとしては、以下のものがあります。

- absolute
- relative
- fixed
- static(標準、指定なしと同義)

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

<img src="./shots/css/css-2-3.png">

特徴をまとめると、以下のようになります。

**relative**  
relativeは、「元々表示する位置からの相対距離」を指定することで表示位置をずらす事ができます。
そのため、例のように２つのrelativeを指定した場合、二つの要素が並んで(+30,+30)された場所に表示されます。

**absolute**
absoluteは「親要素を起点とした絶対位置」を指定します。
例の場合、親の左上を起点として(10, 10)の位置に表示しています。

**fixed**
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

<img src="./shots/css/css-2-4.png">

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

<img src="./shots/css/css-2-5.png">

cssにて「p:last-child」に対してclear:leftを指定していますが、
この「last-child」は、「pの中の最後の要素」を表しています。

つまり、「最後のp要素のみfloatを解除する」ことになります。
