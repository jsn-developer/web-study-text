
## 色を変更する

色を指定するためには、``color:``という項目名を利用するという説明をしました。

本項では、複数ある色の指定方法について学習します。

### 色名指定

CSSでは色名指定で表示できる色が用意されており、色の名称を指定することでその色を表示します。

以下に基本色となる16色を示します。

| |色名|RGB値|
|:--|--|--|
| \color[HTML]{00FFFF} ■ |aqua|#00FFFF|
| \color[HTML]{000000} ■ |black|#000000|
| \color[HTML]{0000FF} ■ |blue|#0000FF|
| \color[HTML]{FF00FF} ■ |fuchsia|#FF00FF|
| \color[HTML]{808080} ■ |gray|#808080|
| \color[HTML]{008000} ■ |green|#008000|
| \color[HTML]{00FF00} ■ |lime|#00FF00|
| \color[HTML]{800000} ■ |maroon|#800000|
| \color[HTML]{000080} ■ |navy|#000080|
| \color[HTML]{808000} ■ |olive|#808000|
| \color[HTML]{800080} ■ |purple|#800080|
| \color[HTML]{FF0000} ■ |red|#FF0000|
| \color[HTML]{C0C0C0} ■ |silver|#C0C0C0|
| \color[HTML]{008080} ■ |teal|#008080|
| \color[HTML]{FFFFFF} ■ |white|#FFFFFF|
| \color[HTML]{FFFF00} ■ |yellow|#FFFF00|

他にも、「拡張された色名」が124色存在しますが、ここでは説明を省略します。

### 16進数による指定

16進数を用いて、RGBの各値を0~FF(255)の範囲で表現することで、色の指定を行うことができます。

### rgb() / rbga()による指定

RGB値を10進数で指定したい場合には、rgb()関数を使用します。

```css
selector {
    color: rgb(255,0,0);
}
```

また、rgbaという関数を使用することで透明度（アルファ値）を指定できます。
透明度は第4引数で指定し、0 ~ 1の間で指定し、値が小さいほど透明度が高くなります。

```css
selector {
  color: rgba(255, 0, 0, 0.6);
}
```
