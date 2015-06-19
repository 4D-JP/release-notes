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

* ACI0057942 アプリケーションビルドのダイアログ画面でUnlimited Desktopのライセンス（.licence4D）を追加した場合，MasterとExpansionに同一のライセンス番号が表示されました。

* ACI0080677 Mac版のみ，コードエディターにいくらかの日本語を入力した後，それ以上は戻れなくなるところまで『取り消し』（command+Z）した後に『やり直し』（command+shift+Z）した場合，元のテキストが複製されました。

* ACI0082110 クライアント/サーバー版でSQL [REPLICATE](http://doc.4d.com/4Dv13/4D/13.4/REPLICATE.300-1225617.ja.html)のWHERE句にプロセス変数を使用した場合，アプリケーションがクラッシュしました。リテラル値であれば，問題ありません。

* ACI0082461 エクスプローラーに表示されるテーブルの並び順とメソッドエディターのタイプアヘッド候補ウィンドウに表示されるテーブルの並び順に一貫性がありませんでした。

* ACI0087122 ```DOCUMENT LIST```をWindowsからMavericks上のSMB共有ネットワークボリュームに対して実行した場合，ファイル数が正確に返されませんでした（99個を超える場合）。問題は修正されましたが，正常な動作にはWindows 7またはWindows Server 2008 R2以降が必要です。

* ACI0087370 [13.5 Hotfix 2](http://www.4d.com/jp/blog/about-13-5-2.html)で改善された問題がさらに修正されました。
 
* ACI0087679 リストボックスに非表示の列が含まれている場合，その列よりも右側の列をドラッグしたときに表示される列の挿入ポイントが間違っていました。

* ACI0087977 リストボックスがページ2以降に配置されていた場合，[LISTBOX INSERT ROW](http://doc.4d.com/4Dv13/4D/13.5/LISTBOX-INSERT-ROWS.301-1458211.ja.html)で間違った位置に行が挿入されました。

* ACI0089181 表示フォーマット```## ####```が設定されているテキスト入力エリアには，最後の桁が表示されませんでした。

* ACI0089465 Windows版のみ，リスト型サブフォームの表示にとても時間がかかることがありました。

* ACI0090125 2003以前に作成されたアプリケーションのリストフォームで[システムハイライトカラー](http://doc.4d.com/4Dv12/4D/12.4/Output-forms.300-1015998.ja.html)プロパティが有効にされていない場合，レコードが選択された状態でリストを上下にスクロールすることができませんでした。13.4以降で問題が発生しました。

* ACI0090259 Webサービスで公開されたメソッドの入力パラメーターにローカル変数が使用できませんでした。（コンパイルモードで『EXECUTEメソッドのパラメータが不正』ランタイムエラーが返されました。）プロセス変数（Compiler_WEBで宣言）であれば問題ありません。

* ACI0090343 Windows版のみ，サブレコード追加のキーボードショートカットを『control+<』に設定した場合，一度の入力でレコードが2件，追加されました。

* ACI0090363 Mac版のみ，fill属性が『none』に設定されているSVGイメージを印刷すると，その部分は黒く塗りつぶされたように出力されました。

* ACI0090378 HTTPヘッダーの『accept』フィールドに『compress, gzip, identify』が含まれていた場合，[On Web Connection](http://doc.4d.com/4Dv13/4D/13.5/On-Web-Connection-Database-Method.300-1457408.ja.html)に制御が渡らず，406エラーが返されました。

* ACI0090444 ピクチャフィールドが『[プリント時可変](http://doc.4d.com/4Dv13/4D/13.4/Printing-areas-of-variable-size.300-1226584.ja.html)』に設定されていた場合，イメージが印刷されませんでした。

* ACI0090753 ピクチャオブジェクトのコンテキストメニューまたは[READ PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/READ-PICTURE-FILE.301-1458029.ja.html)でインポートしたイメージ，あるいは [SET PICTURE FILE NAME](http://doc.4d.com/4Dv13/4D/13.5/SET-PICTURE-FILE-NAME.301-1458048.ja.html)で名前を設定したイメージのファイル名を[Get picture file name](http://doc.4d.com/4Dv13/4D/13.5/Get-picture-file-name.301-1458051.ja.html)で参照した場合，最初は名前が返されますが，4D Remoteでレコードを再ロードした後は空の文字列が返されました。シングルユーザー版または4D Server（ストアドプロシージャー）では問題ありません。

* ACI0090844 フォント名（font-family属性）が小文字だけで指定（例: Arialではなくarial）されたSVGを印刷した場合，あるいは[WRITE PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/WRITE-PICTURE-FILE.301-1458028.ja.html)でイメージをPNGやBMPに変換した場合，結果が正しくありませんでした。フォーム表示は問題ありません。

* ACI0090847 Windows版のみ，[タブコントロール](http://doc.4d.com/4Dv13/4D/13.4/Tab-Controls.300-1226566.ja.html)は必要に応じてタブがスクロールするようになっていますが，v13以降，表示されていないタブをコマンドで選択した場合，v11のようにタブコントロールが自動的にスクロールしませんでした。

* ACI0090951 Mac版のみ，一部のSVGオブジェクトはプリントアウトまたはPDF出力で黒く印刷されました。

* ACI0091314 クライアント/サーバー版で特定のクエリ（インデックスが設定されたフィールドと設定されていないフィールドの組み合わせでリレートフィールドを検索）を実行すると，アプリケーションがフリーズすることがありました。関係するフィールドにインデックスが設定されていれば，問題ありません。

* ACI0091348 Windows版のみ，タブコントロールの最後の項目が選択された状態でその項目を[DELETE FROM ARRAY](http://doc.4d.com/4Dv13/4D/13.5/DELETE-FROM-ARRAY.301-1457526.ja.html)で削除すると，アプリケーションがクラッシュしました。

* ACI0091413 複数行のテキストフィールドをクリックレポートで参照し，4D Viewに出力した場合，テキストフィールドは最初の行しか表示されませんでした。

* ACI0091425 リストボックス上で左マウスボタンのダブルクリックが検出されませんでした。

* ACI0091458 リストフォームに配置された3Dボタンは，レコードを編集している時など，表示されないことがありました。標準ボタンでは問題ありません。

* ACI0091546 [PV Get picture ](http://doc.4d.com/4Dv13/4D/13/PV-Get-picture.301-916124.ja.html)にメモリーリークがありました。たとえば，4D Viewに挿入されたQuickTime画像を標準的なフォーマットに変換している途中でメモリが不足してしまい，処理が継続できなくなることがありました。

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

* ACI0091706 Windows版のみ，Webエリアに[TinyMCE](http://www.tinymce.com/)のようなエディターを表示し，同じフォームに表示された普通のテキスト入力エリアがフォーカスを得ている状態で文字列を入力した場合，両方のエリアに文字列が表示されました。いずれかのオブジェクトをクリックしてから入力を始めれば，問題ありません。

* ACI0091787 Windows版のみ，階層リストのアイテム数が多い場合，リサイズやスクロールの処理にとても時間がかかりました。

* ACI0090575 UTF-8エンコーディングでファイル名が渡された場合，[MSG_EXTRACT](http://doc.4d.com/4Dv13/4D/13.2/MSG-Extract.301-1086702.ja.html)で一部の文字が```?```に変換されてしまいました。

```
filename*=utf-8''U%CC%88berarbeitete%20Offerte.pdf
```

Unicodeが内部的に[正規化](http://ja.wikipedia.org/wiki/Unicode%E6%AD%A3%E8%A6%8F%E5%8C%96)されていなかったことが原因でした。

* ACI0090149 Mac版のみ，4D Viewセルのテキスト自動折り返しが有効に設定されている場合，テキストのカラーが適用されませんでした。（文字色がブラックになりました）

* ACI0085460 **13.4以降**，HTML式が埋め込まれた4D Write文書をHTML4形式で出力した場合，HTMLの開始タグと終了タグが誤ってエスケープされました。

* ACI0086794 4D Writeのズーム率を200%に変更した場合，カーソルが間違った位置に表示されました。

* ACI0089727 トランザクション中に作成された『大文字』のインデックスフィールドをトランザクション中にクエリした場合，みつかりませんでした。

* ACI0089742 [DIALOG](http://doc.4d.com/4Dv13/4D/13.5/DIALOG.301-1457244.ja.html)コマンドで表示したフォームからDIALOGコマンドで同じフォームを表示した場合，最初に表示したほうのフォームには入力ができないはずですが，Mac版で日本語入力が有効にされていれば，テキストを入力することができました。

* ACI0089753 『プリント時可変』オプションが有効にされたマルチスタイルテキストのサイズがページ内に収まらない場合，Windows版ではプリントが無限に続き，アプリケーションをシャットダウンするしかありませんでした。

* ACI0089765 Windows版でSVGピクチャを印刷した場合，一部のフォント（例: Univers Condensed イタリック体）が印刷されませんでした。中には，[PAGE BREAK](http://doc.4d.com/4Dv13/4D/13.5/PAGE-BREAK.301-1458005.ja.html)でハングを引き起こすものもあります。表示は問題ありません。

* ACI0089799 Mac OS X 10.9プラットフォームでは，ダイアルオブジェクトの配色が正しくありませんでした。10.10 Yosemiteプラットフォームでは，オブジェクトをクリックすることができませんでした。

* ACI0090018 トランザクションの操作によっては，インデックスが無効になることがありました。たとえば，トランザクション中にレコードを作成して確定，新しいトランザクションを開始し，そのレコードを変更・保存した後にキャンセル，また新しいトランザクションを開始し，そのレコードを変更・保存した後に確定した場合，MSCにはインデックスの問題が報告され，実際，インデックスを使用する統計などが誤った値を返しました。

* ACI0090035 XMLスキーマ定義（XSD）の中には，```xsd:import```要素を使用し，他のXMLスキーマ定義を参照するようなものが少なくありません。4Dの[DOM Parse XML source](http://doc.4d.com/4Dv13/4D/13.5/DOM-Parse-XML-source.301-1457319.ja.html)は，そのようなスキーマ定義を使用してXMLを検証した場合，すべてのスキーマ定義の名前空間が同一であるとみなされ，エラーが返されました。```xsd:include```とは違い，```xsd:inport```は異なる名前空間のスキーマ定義が参照できるはずです。

**参考**: [http://msdn.microsoft.com/ja-jp/library/ms256237(v=vs.110).aspx](http://msdn.microsoft.com/ja-jp/library/ms256237(v=vs.110).aspx)

* ACI0090049 セレクション型のリストボックスが含まれるプロジェクトフォームをドラッグ＆ドロップ操作により他のストラクチャに移動した場合，テーブルが一緒にコピーされませんでした。テーブルが定義されていないリストボックス，あるいは間違ったテーブルに関連づけられたリストボックスが作成されました。

* ACI0090155 SVGコンポーネントのパレットから色をピクチャ変数にドラッグ＆ドロップした場合，OS X 10.10 Yosemiteではクラッシュしました。GIFファイルをデスクトップからピクチャ変数にドラッグ＆ドロップした場合も同様でした。

* ACI0090337 Webプロセスのユーザーが正しく設定されていない場合，Webプロセスでクラッシュすることがありました。

* ACI0087601 [Execute on server](http://doc.4d.com/4Dv13/4D/13.5/Execute-on-server.301-1457971.ja.html)でストアドプロシージャーを実行し，サーバー側で4D Viewのオフスクリーンエリアを作成した後，4D Remote側の小数点がピリオド，4D Server側の小数点がヴィルギュル（カンマ）の場合，クライアントから渡された数値型の変数が誤ったフォーマットで挿入されました。

* ACI0076706 4D Viewでピクチャを印刷した場合，位置が正しくないことがありました。具体的には，表示フォーマットが『バックグランド』に設定されているとき，繰り返し印刷で画像の位置が正しくありませんでした。

* ACI0088901 スケジュール設定されたバックアップをユーザーがキャンセルした場合，以後，スケジュールされたバックアップが実行されませんでした。スケジュールを設定した直後のバックアップは，『中止』ボタンをクリックしたとしても，すぐに再開されますが，スケジュールにより実行されたバップアップをユーザーが中止した場合，バックアップログには『 (1406) バックアップはユーザーによりキャンセルされました』という記録が追加され，『次回バックアップ予定』もスケジュールどおりに更新され続けますが，サーバーの再起動・BACKUPコマンドやマニュアルバックアップ実行・スケジュールの変更等をしない限り，スケジュールされたバックアップは実行されませんでした。

* ACI0088762 ビルドされたクライアントは，一般的なサーバーにも接続することができました，修正により，そのようなサーバーに対する接続を試みたビルドクライアントでは，『自動アップデート』画面ではなく，『バージョンが違います』エラーが表示されるようになりました。なお，同一マシンで複数のサーバーが起動しているような環境では，hardlinkキーを使用することが推奨されています。

* ACI0088645 Microsoft Accessから4Dの実数フィールドにODBC経由でアクセスした場合，指数表示となりますが，精度が足りませんでした。FLOATフィールドであれば問題ありません。実数フィールドはMicrosoft AccessのSINGLEに，FLOATはDOUBLEに変換されるためです。

**注記**: 修正されたODBCドライバーのDSN設定ページ『MSAccess』オプションを有効にする必要があります。

* ACI0089090 MS QueryでパラメーターのあるSQL文を実行すると，"Server rejected the connection:Failed to execute statement"というエラーが返されました。

エラーが返されるSQLの例

```
SELECT Contacts.CompanyID, Contacts.SurnameFROM Contacts ContactsWHERE (Contacts.CompanyID=[param])
```

* ACI0089105 MS SQL Serverのリンクサーバーから```OPENQUERY```ステートメントを実行すると，エラーが返されました。

エラーが返されるSQLの例

```
SELECT * FROM OPENQUERY(TAOW128909_Main, 'SELECT * from Table_1')
```

* ACI0041745 ODBC Proの```ODBC_SQLBindParameter```でOracleのストアドプロシージャーを実行した場合，戻り値が正しく返されないことがありました。

エラーが返されるSQLの例

```
$result:=ODBC_SQLBindParameter ($iCursorID;4;$iIO;SQL_INTEGER ;0;0;->myResult;- >vIndic)
```

* ACI0088718 Microsoft IIS7 FTPサーバーでMSDOSモードが有効にされている場合，```FTP_GetDirList```でディレクトリの一覧を取得することができませんでした。IIS7では，"200 MSDOS-like directory output is off/on"というメッセージが"200 MSDOS-like directory output is off/on."（ピリオドに注目）に変更されたためです。　

* ACI0078522 ```IT_GetPort```でSSL系の新しいプロトコル設定  (12=SMTP SSL; 13=POP3 SSL; 14=IMAP SSL) が指定できませんでした。

* ACI0071389 プラグインAPIの```PA_ExecuteCommandByID```に配列を渡すことができませんでした。

* ACI0091207 ```LEFT JOIN```の```WHERE```句に2個目の条件が```OR```または```IN```で渡され，それが存在しないレコードを指している場合，結果が正しくありませんでした。その場合，返されるはずのレコードも返されませんでした。

```
SELECT OrderDetails.OrderDetailID, Orders.CustomerID
FROM OrderDetails 
LEFT JOIN Orders ON (OrderDetails.OrderID = Orders.OrderID) 
WHERE ((Orders.CustomerID = 1) OR (Orders.CustomerID = 9))
INTO :OrderLinesID_al, :OrdersCustomerID_al
```

* ACI0092077 Mac版で，``` LOG EVENT```の```Into 4D Debug Message```を使用しても，コンソールにメッセージが書き込まれませんでした。
 
* ACI0069136 4D Writeエリア上でコンテキストメニューを表示し，『ハイパーリンクを挿入』ダイアログで『ドキュメントを開く』で文書タイプを『RTF』に変更しても，ファイル選択画面でRTFファイルを選択することができませんでした。***修正が有効になるためには，4Dとプラグイン，両方のバージョンを13.6に上げる必要があります。***
 
* ACI0087128 [LOG EVENT](http://doc.4d.com/4Dv14R5/4D/14-R5/LOG-EVENT.301-1851206.ja.html)で出力したメッセージがイベントビューアに表示されませんでした。

* ACI0087176 多数の4D Remoteが同時にサーバーに接続しようとすると，サーバーがフリーズしました。

* ACI0087260 v12以前で作成されたアプリケーションを変更した場合，自動Webセッション管理のオプションが最初から有効にされていました。互換性のため，変換されたデータベースでは無効にされているべきです。

* ACI0087293 ゼロによる除算で得た値```I```を渡した場合，[GRAPH](http://doc.4d.com/4Dv14R5/4D/14-R5/GRAPH.301-1851411.ja.html)でアプリケーションがクラっシュしました。

* ACI0087325 サブフォームの描画中に[REDRAW WINDOW](http://doc.4d.com/4Dv14R5/4D/14-R5/REDRAW-WINDOW.301-1852283.ja.html)を実行すると，正しく再描画されないことがありました。

**注記**: 修正が適用されるためには，システムハイライトカラーを有効にする必要があります。

* ACI0087347 Windows版のみ。```System time short```定数で時間を文字列に変換した場合，地域と言語の設定に反して秒数も返されました。

* ACI0087374 プロパティリストを操作してオブジェクトのタイプをフィールドから変数に変更した場合，オブジェクトメソッドが失われ，MSCでエラーが検出されました。
 


