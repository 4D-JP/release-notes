[4D v13.5 Hotfix 4](http://forums.4d.fr/Post/JP/16253595/1/16253596)
---
* ACI0091573 WebエリアにJavaScriptをインジェクションしてページをプリントすることができませんでした。

```
$error:=WA Evaluate javascript(*;"Area";"window.print()")
```

**注記**: OS X 10.10 Yosemiteでは，[WA SET PAGE CONTENT](http://doc.4d.com/4Dv13/4D/13.5/WA-SET-PAGE-CONTENT.301-1457208.ja.html)の後に```On End URL loading```イベントが発生しないため，[DELAY PROCESS](http://doc.4d.com/4Dv13/4D/13.5/DELAY-PROCESS.301-1457966.ja.html)でタイミングを調節する必要があるかもしれません。

```
WA SET PAGE CONTENT(*;"Area";"<html><body>Test</body></html>";"")
DELAY PROCESS(Current process;30)
$error:=WA Evaluate javascript(*;"Area";"window.print()")
```

Windows版では，ネイティブWebエリアを使用してください。**Windows版のWebKitは印刷をサポートしていません**。

* ACI0087977 リストボックスがページ2以降に配置されていた場合，[LISTBOX INSERT ROW](http://doc.4d.com/4Dv13/4D/13.5/LISTBOX-INSERT-ROWS.301-1458211.ja.html)で間違った位置に行が挿入されました。

* ACI0082461 エクスプローラーに表示されるテーブルの並び順とメソッドエディターのタイプアヘッド候補ウィンドウに表示されるテーブルの並び順に一貫性がありませんでした。

* ACI0091546 [PV Get picture ](http://doc.4d.com/4Dv13/4D/13/PV-Get-picture.301-916124.ja.html)にメモリーリークがありました。たとえば，4D Viewに挿入されたQuickTime画像を標準的なフォーマットに変換している途中でメモリが不足してしまい，処理が継続できなくなることがありました。

* ACI0091458 リストフォームに配置された3Dボタンは，レコードを編集している時など，表示されないことがありました。標準ボタンでは問題ありません。

* ACI0091425 リストボックス上で左マウスボタンのダブルクリックが検出されませんでした。

* ACI0091413 複数行のテキストフィールドをクリックレポートで参照し，4D Viewに出力した場合，テキストフィールドは最初の行しか表示されませんでした。

* ACI0090149 Mac版のみ，4D Viewセルのテキスト自動折り返しが有効に設定されている場合，テキストのカラーが適用されませんでした。（文字色がブラックになりました）

* ACI0087028 4D Viewの印刷オブションで行の繰り返しが有効に設定されている場合，セルの内容が印刷されませんでした。

* ACI0091787 Windows版のみ，階層リストのアイテム数が多い場合，リサイズやスクロールの処理にとても時間がかかりました。

* ACI0091706 Windows版のみ，Webエリアに[TinyMCE](http://www.tinymce.com/)のようなエディターを表示し，同じフォームに表示された普通のテキスト入力エリアがフォーカスを得ている状態で文字列を入力した場合，両方のエリアに文字列が表示されました。いずれかのオブジェクトをクリックしてから入力を始めれば，問題ありません。

* ACI0091348 Windows版のみ，タブコントロールの最後の項目が選択された状態でその項目を[DELETE FROM ARRAY](http://doc.4d.com/4Dv13/4D/13.5/DELETE-FROM-ARRAY.301-1457526.ja.html)で削除すると，アプリケーションがクラッシュしました。

* ACI0091314 クライアント/サーバー版で特定のクエリ（インデックスが設定されたフィールドと設定されていないフィールドの組み合わせでリレートフィールドを検索）を実行すると，アプリケーションがフリーズすることがありました。関係するフィールドにインデックスが設定されていれば，問題ありません。

* ACI0091271 Windows版のみ，13.5 Hotfix 2のODBCドライバーで4D Serverに接続すると，一部のテーブルがみつからない，というエラーが返されました。以前のバージョンでは，問題ありません。

* ACI0090951 Mac版のみ，一部のSVGオブジェクトはプリントアウトまたはPDF出力で黒く印刷されました。

* ACI0090575 UTF-8エンコーディングでファイル名が渡された場合，[MSG_EXTRACT](http://doc.4d.com/4Dv13/4D/13.2/MSG-Extract.301-1086702.ja.html)で一部の文字が```?```に変換されてしまいました。

```
filename*=utf-8''U%CC%88berarbeitete%20Offerte.pdf
```

Unicodeが内部的に[正規化](http://ja.wikipedia.org/wiki/Unicode%E6%AD%A3%E8%A6%8F%E5%8C%96)されていなかったことが原因でした。

* ACI0090125 2003以前に作成されたアプリケーションのリストフォームで[システムハイライトカラー](http://doc.4d.com/4Dv12/4D/12.4/Output-forms.300-1015998.ja.html)プロパティが有効にされていない場合，レコードが選択された状態でリストを上下にスクロールすることができませんでした。13.4以降で問題が発生しました。

* ACI0089465 Windows版のみ，リスト型サブフォームの表示にとても時間がかかることがありました。

* ACI0089181 表示フォーマット```## ####```が設定されているテキスト入力エリアには，最後の桁が表示されませんでした。

* ACI0086794 4D Writeのズーム率を200%に変更した場合，カーソルが間違った位置に表示されました。

* ACI0082110 クライアント/サーバー版でSQL [REPLICATE](http://doc.4d.com/4Dv13/4D/13.4/REPLICATE.300-1225617.ja.html)のWHERE句にプロセス変数を使用した場合，アプリケーションがクラッシュしました。リテラル値であれば，問題ありません。

* ACI0086913 クイックレポートの計算カラムに表示フォーマットを適用することができませんでした。

* ACI0087122 ```DOCUMENT LIST```をWindowsからMavericks上のSMB共有ネットワークボリュームに対して実行した場合，ファイル数が正確に返されませんでした（99個を超える場合）。問題は修正されましたが，正常な動作にはWindows 7またはWindows Server 2008 R2以降が必要です。