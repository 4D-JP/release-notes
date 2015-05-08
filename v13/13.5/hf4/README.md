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
