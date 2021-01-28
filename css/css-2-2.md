## フォントを指定する

本項では、表示する文字に関する指定を学習します。

### font-family

フォント名を指定することで、
そのフォントで文字を表示させることができます。

フォント名を指定することでそのフォントに変更できますが、
<u>ブラウザがインストールされた**OSに存在しないフォント**を指定した場合には変更されません。</u>

とくに、MS〇〇やメイリオはWindows用のフォントです。
そのため、各OSに合わせて複数のフォントを指定するのが一般的です。

フォントの指定は以下のように複数個列挙できます。
以下の例では、MSゴシックがインストールされたWindowsPCではMSゴシックが、
それ以外のOSではsans-serifというフォントが適用されます。

```css
style {
  font-family: "MS ゴシック",sans-serif;
}
```

### font-weight

フォントの太さを指定できます。

100〜900の100刻み、もしくは以下の文字列で表現できます。

- normal（通常、400相当）
- bold（太め、700相当）
- lighter（親要素の指定より1段階太い）
- bolder（親要素の指定より一段階細い）

```css
style {
  font-weight: bold;
}
```

実際に数値を使用する際、100〜900の数値指定をしてもあまり太さに変化のない場合があります。
これは、フォントがすべての太さに対応していないためです。

100~1000のすべてに対応したフォントは珍しく、normal,boldにのみ対応したフォントがほとんどです。

### font-style

フォントのスタイルを指定できます。

スタイルは以下の中から指定できます。

- normal（通常）
- italic（イタリック体）
- oblique（斜体）

```css
style {
  font-style: italic;
}
```

イタリック体は筆記体調に変形したもの、斜体はそのまま斜めに傾けたものを指します。

ほとんどの場合、normalまたはitalicを使用します。

イタリック体も斜体も対応しているかどうかはフォント次第ですので、指定しても変形されない場合があります。
とくに日本語フォントの場合イタリック体は用意されていない場合が多く、
イタリックを指定しても斜体と同じ文字が表示されます。

そのため、とくに日本ではイタリック体＝斜体として扱われる場合もあります。