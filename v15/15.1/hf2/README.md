4D v15.1 Hotfix 2
---

* ACI0094492 引数の関節参照に値を代入することができませんでした。ビルド196080以降の問題です。コンパイラー/シンタックスチェックが『無効な定数型です』エラーを出力します。ACI0094499（下記）と関連があります。問題が発生するコードの例:

```
C_LONGINT(${1})
${1}:=3
```

* ACI0094499 引数の関節参照に対して比較演算子を使用することができませんでした。ビルド196129以降の問題です。コンパイラー/シンタックスチェックが『無効な定数型です』エラーを出力します。問題が発生するコードの例:

```
For ($i;1;Count parameters)
  If (${$i}#"")
  //何かの処理
  End if 
End for 
```

**注記**: 回避策として余分のカッコを使用することができます。例: ``If((${$i})#"")``

* ACI0094515 引数の関節参照を変数に代入することができませんでした。ビルド194900以降の問題です。コンパイラー/シンタックスチェックで『変数の型を倍長整数からタイプ19に変更しようとしています。』というエラーが返されました。問題が発生するコードの例:

```
C_LONGINT(${1})
C_LONGINT($minimum)

$minimum:=$1
For ($param;2;Count parameters)
  If (${$param}<$minimum)
    $minimum:=${$param}
  End if
End for 
```

* ACI0068985 メソッドエディターのオートコンプリート機能は，候補が多数（たとえば3万件以上）存在する場合，動作がとても遅くなりました。

* ACI0093488 [SQL LOGIN](http://doc.4d.com/4Dv15/4D/15.1/SQL-LOGIN.301-2686188.ja.html)コマンドで4Dから別の4D Serverにログインする場合，"4D:{データベース名}"記法を使用すると，エラー9918が返されました。v15同士の問題です。v14からv15に接続する場合は問題ありません。また，第1引数に空の文字列を渡してサーバーを選択する場合も問題ありません。

* ACI0094433 セレクション型のリストボックスに対して[LISTBOX DUPLICATE COLUMN](http://doc.4d.com/4Dv15/4D/15.1/LISTBOX-DUPLICATE-COLUMN.301-2686079.ja.html)を実行してデータソースが未定義のカラムを複製すると，アプリケーションがクラッシュしました。ビルド195696以降の問題です。

* ACI0089945 Windows版のみ。フィールドの名前が8文字以下の場合，アラビア文字の値が表示されませんでした。v13では問題ありません。

* ACI0094007 Mac版のみ。[SVG_New_text]のフォント名"Arial"とスタイル定数``Bold``を渡した場合，ボールド体のテキストが表示されませんでした。"Times New Roman"フォントであれば，問題ありません。

* ACI0094430 ツールメニューから4D Viewエリアを表示し，文書を開いてスクロールすると，アプリケーションがクラッシュすることがありました。プラグインが負の列番号に対応していなかったことが原因でした。

* ACI0094497 [ピクチャボタン](http://doc.4d.com/4Dv15/4D/15.1/Picture-Buttons.300-2679559.ja.html)の『マウスアップで戻る』プロパティが有効にされている場合，『ボタン押下中は自動更新』の値に関係なく，ボタン押下中は自動更新されました。

* ACI0094547 Mac版のみ。メソッドエディターの展開/収縮アイコン（三角形）とブロックの終端を結ぶ縦ラインの位置が揃っていませんでした。

* ACI0092351 オブジェクト型フィールドのレコード保存場所を『レコードと一緒』に変更してからストラクチャエディターを閉じた場合，開きなおしてみると，以前のプロパティ値に戻っていました。つまり，変更が保存されませんでした。データベースではなく，ストラクチャエディターの問題でした。[オブジェクト型フィールド](http://doc.4d.com/4Dv15/4D/15.1/External-data-storage.300-2679440.ja.html)はこの保存方式をサポートしています。

* ACI0093311 [131762] Windows版のみ。別アプリケーションがフォーカスを得ると，非モーダルダイアログの``On Deactivate``イベントが実行されました。v14以前のバージョンでは，同イベントが発生しませんでした。そのため，ダイアログの``On Deactivate``イベントで``BRING TO FRONT(Current process)``が実行されるようにコーディングされていた場合，4D以外のアプリケーションが最前面にある間，ずっとイベントが発生し，ダイアログが点滅し続けました。

v14と比較して，[EXECUTE FORMULA](http://doc.4d.com/4Dv15/4D/15.1/EXECUTE-FORMULA.301-2685876.ja.html)および[PROCESS 4D TAGS](http://doc.4d.com/4Dv15/4D/15.1/PROCESS-4D-TAGS.301-2684931.ja.html)のループ実行にかかる時間が長くなりました（コンパイルモード）。前者は，2倍以上，後者は4倍以上，遅くなりました。

***注記**: 修正により，一定数のフォーミュラーがキャッシュに保持されるようになりました。この値は，[SET DATABASE PARAMETER](http://doc.4d.com/4Dv15/4D/15.1/SET-DATABASE-PARAMETER.301-2686308.ja.html)のセレクター``92``で有効にすることができます。

**参考**: [フォーミュラの書き方](http://www.4d.com/jp/blog/formula-execution.html)

* ACI0094438 リストボックスのダブルクリック時アクション『レコード編集』で入力フォームを開いた場合，そのフォームに4D Writeエリアが存在すると，そのエリアにはカーソルが表示されませんでした。

* ACI0094485 ビルドしたアプリケーションの動作が不安定でした。ビルド194902以降の問題です。[ACI0089829](https://github.com/4D-JP/release-notes/tree/master/v15/15.1/hf1)修正の副作用でした。

* ACI0091544 [132257] WR PICTURE TO AREA does not work when running it on the server.
* ACI0094399 [132124] Problem when sorting ListBox.
* ACI0094431 [132408] 4D IC do no more send german diacritical chars like äöüß.
* ACI0094478 [132454] Disabled highlight buttons are badly rendered on a list form.
* ACI0094479 [132453] Listbox not enterable if "On Getting Focus" AND invisble Array assigned.
* ACI0094416 [132395] Quick Report file destination and 4Dpop.
* ACI0089253 Save all & star.
* ACI0092139 [131127] [4D View] Numeric formats do not work in certain regions.
* ACI0090701 [130821] 4D issues when running compiler tools such as check syntax and compile.
* ACI0093505 [132287] Check box: the state of the space key change issues.
* ACI0094332 [132362] Japanese corrupted in QR when converting from v14 to v15.
* ACI0094346 [132352] 4D lets C_OBJECT field hold wrong value {"":""}, then crashes accessing it.
* ACI0091101 [4D Write Pro] properties background color exceeds a radius border at corners.
* ACI0093422 [4D Write Pro] Bad behaviour of underline when text is subscript or superscript.
* ACI0093761 Expression that evaluates as a function (obj.func) does not work on windows native web area.
* ACI0093783 4D Write Pro: Select style without selection.
* ACI0094063 Non roman text Navigation direction is inversed in 4D Write Pro.
* ACI0094095 [132299] open form windows: "*" option and the full-screen problem.
* ACI0094333 [132356] 4D v15 copy&paste incompatible with MS Word 2016.
* ACI0094363 [4DWP] Adverse and inexplicable events.

* ACI0094274 Mac版のみ。変数のプロパティで『ドラッグ可』が有効にされている場合，``On Clicked``イベントが発生しませんでした。ダブルクリックが必要でした。

* ACI0094302 ビルドしたアプリケーションで[EDIT FORM](http://doc.4d.com/4Dv15/4D/15.1/EDIT-FORM.301-2685255.ja.html)を実行すると，少し間を置いてからアプリケーションがクラッシュしました。

* ACI0094402 Mac版のみ。[Open window](http://doc.4d.com/4Dv15/4D/15.1/Open-window.301-2686131.ja.html)にウインドウタイプ``2``を渡し，クローズボックスメソッドを設定すると，ウインドウ参照番号に``0``が返されました。問題が発生するコードの例:

```
$win:=Open window(300;300;600;600;Plain dialog box;"TITLE";"CLOSE_BOX")
```

