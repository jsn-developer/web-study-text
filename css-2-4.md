## 要素に枠をつける

要素に枠を付けるには、borderを使用します。

### borderの基本形

borderの基本系は以下の通りです。

```css:border.css
.border {
    border: solid 1px black;
}
```

3つの値を指定することができ、それぞれ

1. ボーダースタイル
1. 太さ
1. 色

を指定できます。

スタイルの一例は以下の通りです。

| 値 | 説明 |
|--|--|
| none | 線なし |
| solid | 1本線 |
| double | 2本線 |
| dashed | 破線 |
| dotted | 点線 |

### 個別の指定

borderは上下左右それぞれで指定することもできます。

```css:border.css
.border {
    border-top: solid 1px black;
    border-left: double 2px red;
    border-right: dashed 1px blue;
    border-bottom: dotted 1px green;
}
```

表示すると以下のようになります。

![](./shots/css/css-2-7.png)

### 各項目の個別指定

borderに関する設定は、スタイル、太さ、色をそれぞれ別で設定もできます。

```css
.border {
    border-style: solid; /** スタイル */
    border-color: red;   /** 色 */
    border-width: 2px;   /** 太さ */
}
```

上下左右の個別指定についても同様です。
top/left/right/bottomを入れることで個別に指定することができます。

```css
.border-top {
    border-top-style: solid;
    border-top-color: red;
    border-top-width: 2px;
}
```
