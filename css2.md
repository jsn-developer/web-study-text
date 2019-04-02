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

こうすることで、全てのaタグに対して要素が適用されます。

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

### フォントを指定する

### Font-family

### font-weight

## 上下左右に寄せる

### 左右に寄せる - text-align

### 上下に寄せる - vertical-align

## 枠をつける - border

## 余白

### margin

### padding

### marginの相殺について

## 右並びの要素

### float

### flexbox

## さらにカッコイイスタイルを目指す

### shadow

### border-radius