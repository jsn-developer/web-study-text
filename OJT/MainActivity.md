# MainActivity.java

## クラス概要

メイン画面の処理を行うActivityクラス。

## メソッド一覧

- onCreate
- onRestart

<div style="page-break-before:always"></div>

## onCreate

### 概要

画面生成時に呼び出されるメソッド。
<br>
画面の初期化を行う。

### 引数

#### savedInstanceState

バンドル情報

### 戻り値

なし

### 処理内容

スーパークラスのメソッド呼び出しを行う。

Viewの生成を行う。

フルスクリーンモードの設定をセットする。
- "SYSTEM_UI_FLAG_HIDE_NAVIGATION"をセット
- "SYSTEM_UI_FLAG_FULLSCREEN"をセット
- "SYSTEM_UI_FLAG_IMMERSIVE_STICKEY"をセット

レイアウトから　WebViewを取得する。

WebViewの設定を取得し、以下の情報をセットする。
- JavaScriptの使用を許可する
- ページ全体を表示する
- ViewPortを有効化する

WebViewClientを初期化しWebViewにセットする。

WebChromeClientを初期化しWebViewにセットする。

WebViewに以下のURLをロードする。

- http://js-lens-sv2/LENS/ 

<div style="page-break-before:always"></div>

## onRestart

### 概要

画面の再描画時に呼び出されるメソッド。

### 引数

なし

### 戻り値

なし

### 処理内容

スーパークラスのメソッド呼び出しを行う。

フルスクリーンモードの設定をセットする。

- "SYSTEM_UI_FLAG_HIDE_NAVIGATION"をセット
- "SYSTEM_UI_FLAG_FULLSCREEN"をセット
- "SYSTEM_UI_FLAG_IMMERSIVE_STICKEY"をセット
