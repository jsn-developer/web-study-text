# CSSとは

CSSとは、"Cascading Style Sheets"（カスケードスタイルシート）の略で、
HTMLと組み合わせることでページの見た目を装飾できます。

## ボックスとブロック

ページにデザインを適用する場合は、ボックス（ブロック、かたまり）という単位で考えるとよいでしょう。

ある範囲にボックスを作りたい場合は、次のように``<div>``タグを使います。

```html:block.html
<div>
    <h2>見出しのボックス</h2>
    <p>
        文章の
        <b>
           ボックス
        </b>
    </p>
</div>
```

![BOX](./shots/css/shot_c1_1.png)