\newpage
\part{JavaScript基礎}

# JavaScript基礎学習

## JavaScriptとは

JavaScriptは、主にWebブラウザ上で動作するスクリプト言語です。

なお、"Java"の名を冠してはいますが、
サン・マイクロシステム社(現在はOracle社）が開発したJavaとの互換性等はありません。

## JavaScriptにできること

JavaScriptは、主にブラウザ上で表示されるHTML要素の操作に使用されます。

以下に、サンプルとして幾つかの使用例を紹介します。

# JavaScriptの基本構文

本章では、JavaScriptの基本的な構文を学びます。

## 変数と定数の定義

変数は、varで定義することができます。

```javascript
var a = 5;
console.log(a);
```

## JavaScriptのコードを書く準備

まずは、以下のようなhtmlファイルを作成します。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <title>JavaScript</title>
</head>
<body>
<script>

</script>
</body>
</html>
```

HTML内にJavaScriptを宣言する場合、
"<script>〜</script>"内で囲んで記載したコードがJavaScriptとして認識されます。

```javascript
<script>
  〜ここに処理を書く〜
</script>

```

## 変数と定数

まずは、変数を用意して表示してみましょう。

```javascript
var number = 5;
var char = "hello";

// 文字列の表示
console.log(number);
console.log(char);
```

console.logは、コンソール出力を表します。
ブラウザでこのログを表示するためには、開発者コンソールを開きます。

WindowsでIE/Edge/Chromeを使用している場合、
F12キーを推すと開発者コンソールを開くことができます。

コンソールを開くと、以下のように出力されているかと思います。

![](./shots/javascript/js_0_1.png)

## コメントの書き方

コメントは、// または /* ～ */ を使用して記載することができます。

```javascript
var number = 5; // 数値の宣言
var char = /* 文字列の宣言 */ "hello";
```

// を使用した場合にはその行のそれ以降の文字がすべてコメントとして認識されます。  
一方、/* ～ */は囲った部分のみをコメントとして認識します。

### JavaScriptで扱える変数型

JavaScriptで使用できる型について学びます。

#### 数値型

整数または実数で指定することができます。
数値を代入することで、その変数は数値として扱われます。

```javascript
var a = 4;   // 整数
var b = 5.0; // 実数
```

#### 文字列

文字列の宣言を行う場合には、"(ダブルクォート)または'(シングルクォート)で囲んで宣言します。

```javascript
var a = "abc";
var b = 'abc';
```

#### 配列

JavaScriptで配列を宣言するには、下記の2種類の方法があります。

```javascript
// Array型で宣言
var a = new Array(1, 2, 3);
// [] で囲って宣言
var b = [1, 2, 3];
```

上記の例では、どちらも同じ内容の配列が宣言されます。

どちらを使用しても構いませんが、Arrayを使用する場合には注意が必要です。  

```javascript
var c = new Array(3);
var d = [3];
```

この場合、変数cには、「サイズが3の配列(中身は空)」が代入されます。  
一方、変数dには「サイズが1の配列(値が3)」が代入されます。

#### 連想配列

JavaScriptでは、key-value型の連想配列も簡単に宣言することができます。

```javascript
var map = {
    "key1": "value1",
    "key2": 54.3,
    "key3": [1, 3, 5, 7],
    "key4": {
        "child1": "childValue1"
    }
}
```

配列は[] で囲むのに対し、連想配列は { } で囲んで宣言します。

値は key: valueの形で記載を行います。  
keyは文字列で指定しますが、valueには数値や文字列だけでなく、
配列や連想配列を代入することができます。

なお、値を取得する場合には、配列も連想配列も[]を使用して値を取り出します。

```javascript

// 配列の宣言
var list = ["1", "2", "3"];
// 連想配列の宣言
var map = {
    "key1": "value1",
    "key2": "value2"
}

// 配列の値取得は格納場所の指定で取得。
var listElem = list[0];

// 連想配列の値取得はキーとなる文字列を指定して取得
var mapElem = map["key1"];
```

## JavaScriptの基本構文を学ぶ

本章では、JavaScriptの基本的な構文を学習します。

### 条件分岐

#### if文

if文の書き方は以下のようになります。

```javascript
var x = 1;

if (x === 0) {
    // xが0の場合
    console.log("xは0。")
} else if (x > 0) {
    // xが0ではなく、かつxが0より大きい場合
    console.log("xは0より大きい。");
} else {
    // 上記の条件のいずれにも合致しない場合
    console.log("xば0より小さい。");
}
```

この時、気を付けなければならないのは、「===」で比較を行っている点です。
JavaScriptの比較は数値に変換して実施するため、文字列の比較も内部的には数値に変換しようとします。

そのため、以下のような比較をしようとすると同じ値とされてしまいます。

```javascript
let a = 5;
let b = "5";

if (a == b) {
    console.log("aとbは同じ。");
}
```

そのため、型も含めて比較を行いたい場合には、イコールを3つ並べて比較を行います。

リクエストパラメータの処理などで、あえて数値と文字を同じとするような手法もありますが、
誤ったコーディングを防止する目的でも、なるべく「===」による比較を行いましょう。

### switch文

一つの変数の値に応じた条件を指定する場合にはswitch文が便利です。
基本的には以下のような書き方をします。

```javascript
var weather = "晴れ";

switch(weather) {
    case "晴れ":
        console.log("いい天気ですね");
        break;
    case "曇り":
        console.log("雨が降らないといいですね");
        break;
    case "小雨":
        console.log("傘の準備を忘れないようにしてください。");
    case "大雨":
    case "台風":
        console.log("外出を控えることも検討してください。")
        break;
    default:
        console.log("外の天気に気を付けましょう。");
}
```

switch文を使用することで、if文を用いるよりも簡素に記載することができます。
defaultに記載した内容は、if文でのelseに相当します。

なお、コーディングの際にはbreakの存在を忘れないようにしましょう。  
breakを指定しない場合、次のcase文の内容も実行されます。

上記の例の場合、「小雨」の場合には、

- 傘の準備を忘れないようにしてください。
- 外出を控えることも検討してください。

の2つのメッセージが表示されます。

うまく活用することですっきりとしたコードとすることができますが、
とても便利な反面予期しないバグの原因になることもあります。

## ループ

### for文

回数を指定したループにはforを使用します。

```javascript
for (var i = 1: i <= 10: i++) {
    console.log(i + "番目です。");
}
```

このようにすることで、10回の処理を行うことができます。

for文の中の基本的な書き方は以下の通りです。

```javascript
for (初期値; 継続条件; 加算条件)
```

上記の例では、

1. 初期値として変数"i"に 1を代入
1. { } で囲まれた中の処理を実施
1. iをインクリメント(1を加算)する
1. i が 10以下の場合には処理を続行(1から繰り返し)

というような流れとなります。

### while文

一定の条件下で処理を続行する場合には、while文を使用します。

```javascript
i = 1;

while(i <= 10) {
    console.log(i + "番目です。");
    i++;
}
```

実行してみると、前項のfor文と同じ結果が出力されるかと思います。  
このように、forとwhileの書き方には互換を持たせることができます。

「○回実行する」場合にはforを、
「●●の間実行する」場合にはwhileを使うようにするとよいでしょう。

### for in文

配列の中身をループして参照する場合にはfor-in文を使用します。

```javascript
let array = ["a", "b", "c"];

for (let i in array) {
    console.log(array[i]);
}
```

この際、iに対して配列のインデックスが渡されますので注意が必要です。
配列内の値を取得するためには、インデックスを用いた指定をする必要があります。

なお、同様に連想配列に対しても同じような使い方ができます。

```javascript
let map = {
    "key1": "a",
    "key2": "b",
    "key3": "c"
};

for (let key in map) {
    console.log(map[key]);
}
```

### 配列のforEach関数

配列の値を取得して処理を行う場合があります。
その場合には、forEachを使用することで、簡単に配列の値を取得することができます。

```javascript
let array = ["a", "b", "c"];

array.forEach(function(elem, i){
    console.log(i + ":" + elem);
});
```

以下の情報がコンソールに出力されましたか？

```javascript
0:a
1:b
2:c
```

JavaScriptでは配列に対してforEachが定義されています。  

ループ内で実行したい処理を関数として定義し、引数として渡します。
この関数を「コールバック関数」と呼びます。

forEachに対するコールバック関数の引数は以下のようになります。

```javascript
function(対象の要素, 要素のインデックス, 配列) {}
```

第一引数は必須ですが、インデックスや配列全体を取りたい場合には、
それぞれ第二引数と第三引数を指定することでコールバック関数に値を渡すことができます。

なお、このコードは下記のコードと同等になります。

```javascript
let array = ["a", "b", "c"];

for(var i in array) {
    console.log(i + ":" + array[i]);
}
```

この書き方でも動きますので、あまり使い道はないかもしれません。
状況に応じて使い分けをしましょう。

## 配列を使いこなす

配列には、forEachの他にも様々な関数が用意されています。
本項では、配列の操作を行う関数を紹介します。

### filter

配列の条件に合うものを抽出します。

```javascript
var array = [1, 3, 6, 3, 2, 7, 10];

var filtered = array.filter(function(elem, i, array) {
    // 条件を返却
    return elem > 5;
});

console.log(filtered); // -> [6, 7, 10]
```

### find

配列から特定の要素を検索して取得する場合にはfindが使用できます。

filterと似た使い方になりますが、
filterは配列が返却されるのに対し、findは値が返却されます。

```javascript
var array = [1, 3, 6, 3, 2, 7, 10];

var found = array.find(function(elem, i, array) {
    return elem === 3;
});

console.log(found); // -> 3
```

### map

既存の配列を処理し、新しい配列を作成する場合にはmapを使用します。

例として、配列内の数値すべてに10%を加算する場合を考えます。

```javascript
var array = [100, 300, 400, 500];

var newList = array.map(function(elem, i, array) {
    return elem * 1.1;
});

console.log(newList); // -> [110, 330, 440, 550];
```

### reduce / reduceRight

配列を捜査して統計を取得するような場合にはreduceまたはreduceRightを使用します。

例として、配列内の合計値を取得する場合を考えます。

```javascript
var array = [98, 67, 80, 74, 90];

var total = array.reduce(function(val, elem, i, array) {
    return val + elem;
});

console.log(total); // -> 409
```

reduceは0番目から、reduceRightは最後から処理を繰り返していきます。
