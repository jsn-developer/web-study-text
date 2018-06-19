# MemberLogic.java

## クラス概要

メンバー情報を取得するクラス

## メソッド一覧

- getAllList
- searchList
- registerd

## getAllList

### 概要

全てのメンバー情報を取得する。

### 引数

なし

### 戻り値

- List\<MemberDto\>

    メンバー情報のリスト

### 処理内容

データベースを初期化する。

返却用のリストを初期化する。

tryブロックを開始する。

- データベースのSelectAllメソッドを呼び出す。 
- 呼び出した結果を返却用のリストに代入数する。

エラーが発生した場合

- エラー情報をスローする。

返却用リストを返却する。

<div style="page-break-before:always"></div>

## searchList
-----

### 概要

メンバー情報の検索を実施する。

### 引数

- 検索メンバー名: name (String)

    検索するメンバーの名前を渡す

### 戻り値

- List\<MemberDto\>

    検索結果

### 処理内容

引数のnameが空またはnullの場合

> getAllList を呼び出し、戻り値を返却する。

返却用のリストを初期化する。

tryブロックを開始する

> PreparedStatement型でパラメータを初期化する。
>
> パラメータのsetStringメソッドを呼び出し、以下の引数を設定する。
>
> - parameterIndex : 1
> - x : 検索メンバー名
>
> 以下のSQLを実行する。
> 
> ```sql
> select * from member where name like '%@name%'
> ```
> 実行結果を返却用リストに代入する。

エラーが発生した場合

> エラー情報をスローする。

<div style="page-break-before:always"></div>

## searchList
-----

### 概要

メンバー情報の検索を実施する。

### 引数

- 検索メンバー名: name (String)

    検索するメンバーの名前を渡す

### 戻り値

- List\<MemberDto\>

    検索結果

### 処理内容

引数のnameが空またはnullの場合

- getAllList を呼び出し、戻り値を返却する。

返却用のリストを初期化する。

tryブロックを開始する

- PreparedStatement型でパラメータを初期化する。

- パラメータのsetStringメソッドを呼び出し、以下の引数を設定する。

     - parameterIndex : 1
     - x : 検索メンバー名
- 以下のSQLを実行する。

    ```sql
     select * from member where name like '%@name%'
    ```
- 実行結果を返却用リストに代入する。

エラーが発生した場合

- エラー情報をスローする。


<div style="page-break-before:always"></div>

## register

### 概要

メンバー情報を登録する。

### 引数

- 登録情報: data (ModelData)

    登録するモデル情報

### 戻り値

なし

### 処理内容

データベースを初期化する

データベースのトランザクションを開始する。

tryブロックを開始する。

- データベースの登録メソッドを呼び出し、登録処理を行う。

- データベースをコミットする。

エラーが発生した場合

- データベースをロールバックする。
- エラー情報をスローする。
