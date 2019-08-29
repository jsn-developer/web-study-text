
# ECMAScript 2015(ES2015) について学ぶ

ブラウザの進歩と同時に、JavaScript自体も様々な仕様が追加されています。

本章では、2015年に策定されたECMAScript2015(ES2015)で追加された、比較的新しい書き方について学習します。  
なお、ES2015はES6と記載している場合もあります。

古いブラウザでは正常に動作しないなどの問題がありますので、  
本書のサンプルでは同仕様を適用しないようになっています。

動作保証を行う環境に問題がなければ、積極的にES2015の書き方を採用していきましょう。

## 新しい変数の概念

varで宣言した変数は、他の言語とはスコープの概念が少し異なりました。

例として、以下のようなコードを考えます。

```javascript
var x = 1;

if (x === 1) {
    var x = 2;
    var y = 3;
}

console.log(x);
console.log(y);
```

C言語をはじめとするコンパイル言語では、
同名関数の定義でエラーになるか、スコープ内でのみ有効な変数が再生成されます。

しかしながら、JavaScriptのvarは再宣言が可能であり、定義が共有されるため、
このような書き方をしてもxは同じものとして扱われます。

その後、ES2015よりletとconstが登場し、
これにより、スコープごとに有効な変数と定数の定義が可能になりました。  
なお、IE9など古いブラウザでは動きませんので注意してください。

letはスコープ内の変数宣言に、constは定数宣言に使用することができます。

まとめると以下のようになります。

| 名称 | スコープ | 再宣言 | 再代入 |
|-----|----------|-------|--------|
| var   | グローバル | ○ | ○ |
| let   | ブロック   | × | ○ |
| const | ブロック   | × | × |

古いブラウザへの対応が必須なような特殊環境下でない限り、
letおよびconstを使用するようにしましょう。

## アロー関数による宣言

ES2015からは、アロー関数を用いてより簡略化した関数宣言ができるようになりました。

### 基本形

コールバック関数などで関数を宣言する場合、functionの記載を省略することができます。

```javascript

// 従来の書き方
var func = function(min, max) {
    for (var i = min; i <= max; i++) {
        console.log(i);
    }
}

// アロー関数を用いた書き方
const func = (min, max) => {
    for (let i = minl; i <= max; i++) {
        console.log(i)
    }
}
```

どちらも、同じ動きとなります。

### 省略形

#### 引数が1つの場合の省略

引数が一つしかない場合、引数の()も省略することができます。

```javascript
const func = n => {
    console.log(n);
}
```

ちなみに、引数がない場合には省略することができません。
引数のない()を記載する必要があります。

```javascript
const func = () => {
    console.log("呼ばれた。");
}
```

#### 処理内容が1行で書ける場合

処理内容がreturnで始まる1行の場合、さらに省略することができます。

```javascript
const func = n => n * n;
```

これは、以下の関数制限と同等になります。

```javascript
const func = function(n) {
    return n * n;
}
```

このように、うまく使い分けることでコードをより簡略化することができます。

## クラスの宣言

従来のJavaScriptでオブジェクト指向的なクラスを作成する場合には、
少しクセがありました。

ES2015からは簡単にクラスを宣言することができるようになりました。

従来のJavaScriptでは、prototypeという概念を用いて、
オブジェクトに対してメソッドを追加で宣言していました。

```javascript
/** Personオブジェクトの宣言*/
var Persion = function(name) {
    this.name = name;
}
Persion.prototype.say = function(){
    console.log("My name is " + this.name);
}

var p = new Person("太郎");
p.say(); // -> My name is 太郎

```

新しいクラス宣言では、以下のように記載することができます。

```javascript

class Person {
    /**
     * コンストラクタ
     * @param name 氏名
     */
    constructor(name) {
        this.mane = name;
    }

    say() {
        console.log("My name is " + this.name);
    }
}

const taro = new Person("太郎");
taro.say(); // -> My name is 太郎
```

これにより、より簡易的にクラスの宣言ができるようになりました。

## 関数のデフォルト値指定

ES2015以前でも、関数の呼び出しの際に引数を省略をすることができました。
その場合には、引数にnullが渡される挙動がとられていました。

ES2015では、省略された場合にデフォルト値を指定することができます。

```javascript
function add(a, b = 5) => a + b;

console.log(add(3,2)); // -> 5
console.log(add(3));   // -> 8
```

第二引数が指定された場合にはその値を、渡されない場合にはデフォルト値である5を加算します。

## テンプレート文字列

ES2015からは、文字列の結合にテンプレートを用いることができるようになりました。  
テンプレート文字列には`(バッククォート)を用います。シングルクォートではありませんので注意してください。

```javascript

// 従来の書き方
console.log("My name is " + name);

// テンプレート文字列を用いた書き方
console.log(`My name is ${name}`);
```

テンプレート文字列をうまく活用することで無用に長くなっていた文字列結合をより簡略化することができます。

## 可変長引数

関数の引数に ...　を指定することで、可変長の引数をとることができます。

```javascript
function show(...arr) {
    console.log(arr)
}

show(1, 2, 3, 4, 5) // -> [1, 2, 3, 4, 5]
```

```javascript
function show(a, ...arr) {
    arr.forEach(elem => {
        console.log(elem);
    })
}

show(1, 2, 3, 4, 5) // -> [2, 3, 4, 5]
                    // ※1は引数aに格納される
```

このように、呼び出し元では別の宣言として呼び出したものを、
呼び出し先では配列化して扱うことができます。

### for-ofによる反復

ES2015では、ArrayのforEachに対応する新しいループができるようになりました。

```javascript
const arr = [1, 2, 3, 4, 5];

for(let elem of arr) {
    console.log(elem);
}
```

インデックスの使用が不要な場合には、for-ofの使用をすることで、
値の取得間違いを防ぐことができます。
