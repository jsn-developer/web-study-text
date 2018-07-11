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
任意のブラウザを起動し、上記URLを入力してください。
<br>
今回はMicrosoft Edgeを使用しています。
<br>
下記のページが表示されます。
<br>
ページ上段のメニューに表示されている「Download」をクリックしてください。

<img src="./shots/database/db_1.png" width="550px">

下記のページが表示されます。
<br>
ページ中央「Download」をクリックしてください。

<img src="./shots/database/db_2.png" width="550px">

下記のページが表示されます。
<br>
ページ中央「Download 10.3.7 Stable Now!」をクリックしてください。

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
ブラウザによってはファイルに対する操作を要求されるので「保存」を選択してください

<img src="./shots/database/db_5.png" width="550px">

ダウンロードしたファイルを実行し、インストール作業を行ってください。
### インストール
それでは、インストーラを実行し、インストール作業を行います。
実行すると初期画面が表示されます。
「Next」をクリックしてください。

<img src="./shots/database/db_6.png" width="550px">

利用規約の画面が表示されます。
<br>
I accept the terms in the License Agreementにチェックをいれます。
<br>
「Next」をクリックしてください。

<img src="./shots/database/db_7.png" width="550px">

インストールするモジュール選択の画面が表示されます。
<br>
今回はこのままインストールを続けます。
<br>
「Next」をクリックしてください。

<img src="./shots/database/db_8.png" width="550px">

<br>
設定を行う画面が表示されます。
<br>
rootユーザーに任意のパスワードを入力してください。
<br>
確認用にもう一度パスワードを入力してください。
<br>
また、Use UTF8 as default server's character setにチェックを入れてください。
<br>
「Next」をクリックしてください。

<img src="./shots/database/db_9.png" width="550px">

利用するサービスの設定画面が表示されます。
<br>
今回はこのまま続けます。
「Next」をクリックしてください。

<img src="./shots/database/db_10.png" width="550px">

フィードバックプラグインの有効化の確認画面が表示されます。
<br>
今回はこのままで続けます。
<br>
「Next」をクリックしてください。

<img src="./shots/database/db_11.png" width="550px">

インストール開始の確認画面が表示されます。
<br>
「Install」をクリックしてください。

<img src="./shots/database/db_12.png" width="550px">

インストール中の画面が表示されます。
<br>
インストール状況を確認できます。

<img src="./shots/database/db_13.png" width="550px">

インストール完了画面が表示されます。
<br>
「Finish」をクリックしてインストーラを終了してください。

<img src="./shots/database/db_14.png" width="550px">

以上で、インストール作業が完了します。

### 接続方法

## データベースの用語を整理する

### データベース

### テーブル

### レコード

### カラム

## データベースを操作する

### データベースの作成

### データベースの一覧

### データベースの削除

### データベースの切り替え

## 作業を行うユーザを設定する

### create user

### grant

## テーブルを操作する

### テーブル作成

### テーブル一覧

### 構造の確認

## 様々なデータ型

このセクションでは、テーブルに登録できる型を紹介します。

### 数値

#### INTEGER

#### NUMERIC

### 文字列

#### CHAR

#### VARCHAR

#### CHARとVARCHARの使い分け

#### 日本語(マルチバイト文字)の取り扱い

### 日時

### 真偽値
