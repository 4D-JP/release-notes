4D v13.6
---

* ACI0092648 4D Volume Deskopのビルド番号を特定することができませんでした。

**注記**: 通常，ビルド番号は，[Application version](http://doc.4d.com/4Dv13/4D/13.5/Application-version.301-1458428.ja.html)で特定することができますが，ビルドされたアプリケーションでは，Info.plistに記述された情報 (```CFBundleShortVersionString, CFBundleVersion```) を参照する必要があるかもしれません。今回の修正により，Info.plistファイルにビルド番号が反映されるようになりました。

* ACI0092730 Windows版のみ，[IT_Version](http://doc.4d.com/4Dv13/4D/13.2/IT-Version.301-1086826.ja.html)から返されるバージョン番号が正確ではありませんでした。

* ACI0092713 統合WebKit版，およびMac版システムWebエリアで[WA EXECUTE JAVASCRIPT FUNCTION](http://doc.4d.com/4Dv13/4D/13.5/WA-EXECUTE-JAVASCRIPT-FUNCTION.301-1457214.ja.html)または[WA Execute JavaScript](http://doc.4d.com/4Dv13/4D/13.5/WA-Execute-JavaScript.301-1457215.ja.html)でJavaScriptを実行することができませんでした。13.5では問題ありません。13.5HF1以降の問題です。
 
* ACI0091680 [XSLT GET ERROR](http://doc.4d.com/4Dv13/4D/13.5/XSLT-GET-ERROR.301-1457286.ja.html)を実行した後，```OK```変数に```1```が代入されませんでした。

* ACI0091616 ```PROFIND```など，非標準のHTTPメソッドを[HTTP Request](http://doc.4d.com/4Dv13/4D/13.5/HTTP-Request.301-1458478.ja.html)に渡した場合，```GET```が送信されました。

* ACI0092244 Windows版で地域と言語が『ルクセンブルグ』に設定されている場合，4Dが起動直後にクラッシュしました。

**注記**: 4D Writeと4D Viewのバージョンも13.6に上げる必要があります。

* ACI0091207 ```LEFT JOIN```の```WHERE```句に2個目の条件が```OR```または```IN```で渡され，それが存在しないレコードを指している場合，結果が正しくありませんでした。その場合，返されるはずのレコードも返されませんでした。

```sql
SELECT OrderDetails.OrderDetailID, Orders.CustomerID
FROM OrderDetails 
LEFT JOIN Orders ON (OrderDetails.OrderID = Orders.OrderID) 
WHERE ((Orders.CustomerID = 1) OR (Orders.CustomerID = 9))
INTO :OrderLinesID_al, :OrdersCustomerID_al
```

* ACI0087028 4D Viewの印刷オブションで行の繰り返しが有効に設定されている場合，セルの内容が印刷されませんでした。

* ACI0069136 4D Writeエリア上でコンテキストメニューを表示し，『ハイパーリンクを挿入』ダイアログで『ドキュメントを開く』で文書タイプを『RTF』に変更しても，ファイル選択画面でRTFファイルを選択することができませんでした。
 
**注記**: 4Dとプラグイン，両方のバージョンを13.6に上げる必要があります。

* ACI0092077 Mac版で，[LOG EVENT](http://doc.4d.com/4Dv13/4D/13.5/LOG-EVENT.301-1457583.ja.html)の```Into 4D Debug Message```を使用しても，コンソールにメッセージが書き込まれませんでした。 

* ACI0090668 [FORM SCREENSHOT](http://doc.4d.com/4Dv13/4D/13.5/FORM-SCREENSHOT.301-1458325.ja.html)を使用した場合，Webエリアの配置された領域が黒く塗りつぶされて出力されました。

**注記**: 修正されたのは，Windows版だけです。Mac版は，v14以降で修正されました。いずれにしても，Webエリアのオフスクリーンレンダリングはサポートされていません。修正とは，Webエリアの配置された領域が黒く塗りつぶされない，ということであり，ビットマップ画像が出力されるように改良された，ということではありません。

* ACI0091271 Windows版のみ，13.5 Hotfix 2のODBCドライバーで4D Serverに接続すると，一部のテーブルがみつからない，というエラーが返されました。以前のバージョンでは，問題ありません。

* ACI0086794 4D Writeのズーム率を200%に変更した場合，カーソルが間違った位置に表示されました。

* ACI0085460 **13.4以降**，HTML式が埋め込まれた4D Write文書をHTML4形式で出力した場合，HTMLの開始タグと終了タグが誤ってエスケープされました。

* ACI0087028 4D Viewの印刷オブションで行の繰り返しが有効に設定されている場合，セルの内容が印刷されませんでした。

* ACI0057942 アプリケーションビルドのダイアログ画面でUnlimited Desktopのライセンス（.licence4D）を追加した場合，MasterとExpansionに同一のライセンス番号が表示されました。

* ACI0080677 Mac版のみ，コードエディターにいくらかの日本語を入力した後，それ以上は戻れなくなるところまで『取り消し』（command+Z）した後に『やり直し』（command+shift+Z）した場合，元のテキストが複製されました。

* ACI0082110 クライアント/サーバー版でSQL [REPLICATE](http://doc.4d.com/4Dv13/4D/13.4/REPLICATE.300-1225617.ja.html)のWHERE句にプロセス変数を使用した場合，アプリケーションがクラッシュしました。リテラル値であれば，問題ありません。

* ACI0082461 エクスプローラーに表示されるテーブルの並び順とメソッドエディターのタイプアヘッド候補ウィンドウに表示されるテーブルの並び順に一貫性がありませんでした。

* ACI0087122 ```DOCUMENT LIST```をWindowsからMavericks上のSMB共有ネットワークボリュームに対して実行した場合，ファイル数が正確に返されませんでした（99個を超える場合）。問題は修正されましたが，正常な動作にはWindows 7またはWindows Server 2008 R2以降が必要です。

* ACI0087370 [13.5 Hotfix 2](http://www.4d.com/jp/blog/about-13-5-2.html)で改善された問題がさらに修正されました。
 
* ACI0087679 リストボックスに非表示の列が含まれている場合，その列よりも右側の列をドラッグしたときに表示される列の挿入ポイントが間違っていました。

* ACI0087977 リストボックスがページ2以降に配置されていた場合，[LISTBOX INSERT ROW](http://doc.4d.com/4Dv13/4D/13.5/LISTBOX-INSERT-ROWS.301-1458211.ja.html)で間違った位置に行が挿入されました。

