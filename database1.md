# データベース基礎(準備編)

## MariaDBを使ってみよう

### MariaDBとは
MariaDB(マリアディービー)とはMySQLから派生したオープンソースの関係データベース管理システム（RDBMS)です。
<br>
MySQLと互換性があり、Googleにも採用されています。
<br>
また、多くのストレージエンジンを採用していることやスレッドプールが標準で利用できることも魅力の1つです。

### 公式サイトからダウンロード
公式サイト(https://mariadb.org/)からダウンロードできます。
<br>
任意のブラウザを起動し、上記URLを入力します。
<br>
今回はMicrosoft Edgeを使用しています。
<br>
下記のページが表示されます。
<br>
ページ上段のメニューに表示されている「Download」をクリックします。

<img src="./shots/database/db_1.png" width="550px">

下記のページが表示されます。
<br>
ページ中央「Download」をクリックします。

<img src="./shots/database/db_2.png" width="550px">

下記のページが表示されます。
<br>
ページ中央「Download 10.3.7 Stable Now!」をクリックします。

<img src="./shots/database/db_3.png" width="550px">

下記のページが表示されます。
<br>
このページでは「OS/CPU」からインストールしたいOSのMariaDBを選び、
<br>
「File Name」をクリックして実行ファイルをダウンロードします。
<br>
今回は「Windows x64」、msiのインストーラをダウンロードします。

<img src="./shots/database/db_4.png" width="550px">

下記のページが表示されます。
<br>
ブラウザによってはファイルに対する操作を要求されるので「保存」を選択します

<img src="./shots/database/db_5.png" width="550px">

ダウンロードしたファイルを実行し、インストール作業を行います。
### インストール
それでは、インストーラを実行し、インストール作業を行います。
実行すると初期画面が表示されます。
「Next」をクリックします。

<img src="./shots/database/db_6.png" width="550px">

利用規約の画面が表示されます。
<br>
I accept the terms in the License Agreementにチェックをいれます。
<br>
「Next」をクリックします。

<img src="./shots/database/db_7.png" width="550px">

インストールするモジュール選択の画面が表示されます。
<br>
今回はこのままインストールを続けます。
<br>
「Next」をクリックします。

<img src="./shots/database/db_8.png" width="550px">

<br>
設定を行う画面が表示されます。
<br>
rootユーザーに任意のパスワードを入力します。
<br>
確認用にもう一度パスワードを入力します。
<br>
また、Use UTF8 as default server's character setにチェックを入れます。
<br>
「Next」をクリックします。

<img src="./shots/database/db_9.png" width="550px">

利用するサービスの設定画面が表示されます。
<br>
今回はこのまま続けます。
「Next」をクリックします。

<img src="./shots/database/db_10.png" width="550px">

フィードバックプラグインの有効化の確認画面が表示されます。
<br>
今回はこのままで続けます。
<br>
「Next」をクリックします。

<img src="./shots/database/db_11.png" width="550px">

インストール開始の確認画面が表示されます。
<br>
「Install」をクリックします。

<img src="./shots/database/db_12.png" width="550px">

インストール中の画面が表示されます。
<br>
インストール状況を確認できます。

<img src="./shots/database/db_13.png" width="550px">

インストール完了画面が表示されます。
<br>
「Finish」をクリックしてインストーラを終了します。

<img src="./shots/database/db_14.png" width="550px">

以上で、インストール作業が完了します。

### 接続方法
本項では、データベースへ接続する方法について説明します。
<br>
まず、スタートメニューから「HeidiSQL」をクリックします。

<img src="./shots/database/db_15.png" width="550px">

セッションを作成する画面が表示されます。
<br>
「新規」をクリックします。

<img src="./shots/database/db_16.png" width="550px">

ネットワーク識別項目にMySQLを選択します。
<br>
パスワード項目にインストール時に設定したパスワードを入力します。
<br>
「開く」をクリックします。

<img src="./shots/database/db_17.png" width="550px">

接続に成功すれば、下記の画面が表示されます。

<img src="./shots/database/db_18.png" width="550px">

以上で、データベースとの接続が完了します。
## データベースの用語を整理する
この項目では、データベースの基本的用語を下記の画像と合わせて紹介します。

<img src="./shots/database/database.png" width="550px">

### データベース
データを管理するための入れ物のことを「データベース」と呼びます。
### テーブル
データベースに作成できる入れ物のことで、データを実際に格納する場所です。
<br>
また、表のような構造になっています。
### レコード
テーブルの行のことです。ロウとも呼びます。
### カラム
レコードを構成する属性のことです。フィールドとも呼びます。
### データベースの作成
データベースへの接続完了後の画面から説明します。

<img src="./shots/database/db_19.png" width="550px">

画面左側で右クリックし、新規作成を選択します。
<br>
新規作成欄の「データベース」をクリックします。

<img src="./shots/database/db_20.png" width="550px">

作成するデータベース名を入力するポップアップが表示されます。
<br>
今回は、「testdb」というデータベースを作成します。
<br>
名前を入力し、「OK」をクリックします。

<img src="./shots/database/db_21.png" width="550px">

作成されたデータベースは画面左側で確認できます。

<img src="./shots/database/db_22.png" width="550px">

### データベースの削除
 画面左側のデータベースを右クリックし、ドロップをクリックします。
 <br>
 今回は、「test」を削除します。
 削除確認のポップアップが表示されます。
 
 <img src="./shots/database/db_23.png" width="550px">

 OKをクリックします。

 <img src="./shots/database/db_24.png" width="550px">
 
 画面左側に削除されたデータベースが表示されていないことを確認します。

 <img src="./shots/database/db_25.png" width="550px">

### データベースの切り替え
操作対象のデータベースを指定するときは、
<br>
画面左側のデータベース名をクリックします。
<br>
また、現在操作対象のデータベースには緑色のチェックが表示されています。

<img src="./shots/database/db_26.png" width="550px">

## 作業を行うユーザを設定する
ルートユーザでは扱える権限が広く、誤った操作をしてしまうと影響が大きいため、
<br>
データベースごとに作業用ユーザを作成することが一般的です。

<br>
ここでは、作業用ユーザの作成方法を説明します。
<br>
まず、画面上段のメニューユーザ認証と特権の管理と表示されるアイコンをクリックします。
<br>
ユーザーマネージャーが表示されます。

<img src="./shots/database/db_27.png" width="550px">

この画面ではユーザーの作成及び権限を与えることができます。
<br>
まず、左側の追加ボタンをクリックします。

<img src="./shots/database/db_28.png" width="550px">

右側に名称未定のアカウント情報入力画面が表示されます。

<img src="./shots/database/db_29.png" width="550px">

今回は、「testuser」というユーザ名で作成します。
<br>
ホストはデフォルトの状態で続けます。
<br>
パスワードは任意のものを入力し、確認用にもう一度入力します。

<img src="./shots/database/db_30.png" width="550px">

次に、このユーザに権限を与えます。
<br>

アクセス許可項目にグローバル特権にチェックを入れます。
<br>
グローバル特権によってこのユーザはすべてのデータベースに対する操作が可能になりました。
<br>
保存ボタンをクリックします。

<img src="./shots/database/db_31.png" width="550px">

画面左に「testuser」が作成されたことを確認します。

<img src="./shots/database/db_32.png" width="550px">

## テーブル作成
それでは、実際にテーブルの作成を行いましょう。
<br>
画面左のデータベースを右クリックし、新規作成項目からテーブルをクリックします。

<img src="./shots/database/db_33.png" width="550px">

作成するテーブルの内容を入力する画面が表示されます。
<br>
まず、右画面に表示された基本タブにある名前項目にテーブルの名前を入力しましょう。
<br>
今回は、「book」と入力します。

<img src="./shots/database/db_34.png" width="550px">

次に、テーブルに行を追加しましょう。
<br>
画面中央のカラムという項目の「追加」をクリックします。

<img src="./shots/database/db_34_2.png" width="550px">

「カラム１」という名前の行が表示されます。

<img src="./shots/database/db_35.png" width="550px">

この行を編集し、データ型や長さ、NOT NULL制約や初期値の設定を行います。
<br>
今回は、「id」と入力し、データ型をINTにします。長さは10と入力します。
<br>
その他の項目はデフォルトの状態で続けます。

<img src="./shots/database/db_36.png" width="550px">

同様にして、行の追加を行います。
<br>
下記の画面のように行を追加します。

<img src="./shots/database/db_37.png" width="550px">

作成したテーブルは、画面右のデータベースタブをクリックするとテーブル一覧を見ることができます。

### テーブルを操作する
それでは、作成したテーブルの操作を行いましょう。
<br>
この項目では、以下の操作について紹介します。
<br>
操作を行うためには、画面右側のクエリータブをクリックします。
<br>
クエリータブにテーブルを作成するクエリーが残っていた場合は削除します。

<img src="./shots/database/db_38.png" width="550px">

<li>データの挿入  (INSERT INTO文)</li>

データの挿入にはINSERT INTO文を実行します。
<br>
構文は INSERT INTO テーブル名(テーブルのカラム名)
<br> 
VALUES(カラムごとに挿入するデータ)となります。(行番号1)
<br>
また、テーブルのすべてのカラムに値を挿入するときは
<br>
テーブル名の後に記述するテーブルのカラム名を省略することができます。(行番号2)
<br>
今回は、
``` sql
Insert into book('id','book_num','author_name','title','price')
  Values('1','2','夏目漱石','吾輩は猫である','1200');
```
このように入力しましょう。
<br>
同様にして、
``` sql
Insert into book('id','book_num','author_name','title','price')
  Values('2','3','太宰治','走れメロス','800');
```
さらにデータを挿入します。
<br>

このようなデータを操作する文をクエリーと呼びます。
<br>
クエリーを入力するときはカラム名をシングルコーテーションで囲みます。
<br>
これはすべてのクエリーで共通の条件となります。
<br>
また、構文では大文字で表記していますが、MySQLでは大文字と小文字の区別はないため
<br>
画像のように小文字で入力しても実行可能です。
<br>
クエリーの実行は画面上段のSQLを実行と表示されるアイコンをクリックします。

<img src="./shots/database/db_39.png" width="550px">

挿入したデータはデータタブをクリックして確認することができます。

<img src="./shots/database/db_40.png" width="550px">

<li>データの抽出  (SELECT文)</li>
 データの挿入にはSELECT文を実行します。
 
 抽出したいデータに条件を付けるときはテーブル名を記述した後にWhere句をつけて
 <br>
 条件を指定することができます。
 <br>
 今回は、
 ``` sql
Select title From book Where id = 1;
```
と入力します。
 <br>
 SELECT文の実行結果クエリータブの下に表示されます。

 <img src="./shots/database/db_41.png" width="550px">

<li>データの更新  (UPDATE文)</li>
データの更新にはUPDATE文を実行します。
<br>
構文は UPDATE テーブル名　SET カラム名 = 更新後の値 WHERE 条件

<img src="./shots/database/db_42.png" width="550px">

今回は、
``` sql
 Update book Set price = 1300 Where id = 1;
```
<br>
と入力します。
<br>
実行結果はデータタブから確認できます。

<img src="./shots/database/db_43.png" width="550px">

<li>データの削除  (DELETE文)</li>
データの削除にはDELETE文を実行します。
<br>
構文は DELETE FROM テーブル名 WHERE 条件 となります。
<br>
今回は、

```sql
 Delete * From book Where id = 2;
```
と入力します。

<img src="./shots/database/db_45.png" width="550px">

データが削除されているか、データタブを表示して確認します。

<img src="./shots/database/db_46.png" width="550px">

### テーブル一覧

作成したテーブルは画面右側のデータベースタブをクリックします。
<br>
また、各テーブルの構造はデータベースタブに表示されたテーブル名をクリックし、確認します。

## 様々なデータ型

このセクションでは、テーブルに登録できる型を紹介します。

### 数値
データベースに登録できる数値の型は次の２種類が代表的に挙げられます。
#### INTEGER
INTEGER型は整数型とよばれるものです。
<br>
表現できる数値の範囲は、最小値-2,147,483,648から最大値+2,147,483,647までです。

#### NUMERIC
NUMERIC型は固定小数点型とよばれるものです。
<br>
表現できる数値の範囲は精度とスケールによって変化します。
<br>
例：精度 = 5,スケール=2 の場合
<br>
   DECIMAL(5,2) と表現され、-999.99 から+999.99までの表現が可能です
### 文字列
文字列を表現するデータ型は以下２種類が挙げられます。
#### CHAR
固定長の文字列型です。値の範囲は0から256までです。
<br>
長さを固定するために、文字数が長さに満たない場合は空白スペースで長さを満たします。
<br>
以上のことから、文字列としての長さが一定である型となります。
#### VARCHAR
可変長の文字列型です。値の範囲は0から65536までです。
<br>
データのサイズが255より小さい場合は1バイトプレフィクスとして格納され
<br>
より大きい場合は2バイトプレフィクスとして格納されます。
#### CHARとVARCHARの使い分け
文字列として、空白を用いる場合はVARCHARを推奨します。
<br>
理由としては、CHARが文字列の長さを満たすために空白を文字列に追加するからです。
<br>
逆に格納する文字列が一定であるならばCHAR型が推奨されます。
<br>
必要十分な長さを用意できることや、長さより大きい値を格納する心配がありません。
#### 日本語(マルチバイト文字)の取り扱い
### 日時
DATE型は日付を表現できるデータ型です。
TIME型は時間を表現できるデータ型です。
DATETIME型は日付と時間を表現できるデータ型です。
TIMESTANP型は現在の日付・時間を表現できるデータ型です。
YEAR型は年を表現できるデータ型です。

### 真偽値
TINYINT型で表現することができます。
値を1に設定するとtrueと等しくなります。
値を0に設定するとfalseと等しくなります。
ただし、それ以外の値はtrueともfalseとも等しくなくなります。