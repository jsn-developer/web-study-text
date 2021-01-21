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
