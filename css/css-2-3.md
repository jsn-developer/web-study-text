## テキストの位置指定

CSSを用いて、子要素を位置を上下左右に寄せることができます。

### 左右に寄せる - text-align

テキストの左右位置を調整するには、text-alignを使用します。

よく使用される値は以下の通りです。

|値| 説明|
|--|--|
|left | 左端に揃える |
| right | 右端に揃える |
| center | 中央に配置 |

### 上下に寄せる - vertical-align

テキストの上下一を調整するには、vertical-alignを使用します。  
ただし、vertical-alignを適用できるのは、インライン要素とテーブルセルのみで、ブロックレベル要素には適用できませんので注意が必要です。

よく使用される値は以下の通りです。

|値| 説明|
|--|--|
| top | 上端に揃える |
| middle | 下端に揃える |
| bottom | 中央に配置 |

たとえば、divの中にあるspanを中央に配置するには次のコードを使用します。

```html
<div>
  <span>TEST</span>
</div>
```

```css
div {
  height: 4em;
  width: 10em;
  display: table-cell;
  text-align: center;
  vertical-align: middle;
  border: solid 1px red;
}
```

``vertical-align``を適用するため、div要素に``display: table-cell``を適用しています。
