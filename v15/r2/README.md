4D v15 R2
---
Fixed bugs build 191870 v15 R2 beta (Released on 2015-10-15)
--------------------------------------------------------------------------------
* ACI0093901 : Very little memory available in Mac 32 bits on El Capitan.

Fixed bugs build 191698 v15 R2 beta (Released on 2015-10-13)
--------------------------------------------------------------------------------
* ACI0093775 ビルドされたサーバー/クライアントアプリケーションでバージョン管理を有効にしておき，古いクライアントを新しいサーバーに接続したときに表示される画面を確定せずに，サーバー側の管理画面に表示されているユーザー名を確認します。ひとりだけ名前のないクライアントがいるはずです。そのまま20秒以上，待ちます。待った後，タスクマネージャーでクライアントを強制的に終了します。サーバー側には終了したクライアントのユーザーが残ります。このユーザーを管理画面のドロップボタンでドロップすることはできませんが，ライセンス数には影響がないようです。新ネットワークレイヤーでなければ起きません。

Fixed bugs build 191105 v15 R2 beta (Released on 2015-09-30)
--------------------------------------------------------------------------------
* ACI0093549 : Wrong list of plugins included in 4D/Plugins folder for 64-bit Win installer
* ACI0093550 : Wrong list of plugins included in 4D/Plugins folder for 64-bit Mac installer
* ACI0093593 : [131792] Modifier key missing from pop-up menu.

Fixed bugs build 190908 v15 R2 beta (Released on 2015-09-25)
--------------------------------------------------------------------------------
* ACI0093480 : Can not restart in compiled or in interpreted for C/S databases running with new network layer.
* ACI0093593 : [131792] Modifier key missing from pop-up menu.

Fixed bugs build 190540 v15 R2 beta (Released on 2015-09-17)
--------------------------------------------------------------------------------
* ACI0093072 : Service isn't relaunch after update 4D server v14  32bits with 4D server v15 32bits
* ACI0093073 : Update 4D server 64 bits doesn't work in service
* ACI0093214 : 4D crashs when we use the command DISPLAY RECORD 
* ACI0093630 : String(-0.99999999999999534) produces "1" instead of "-1"

Fixed bugs build 190266 v15 R2 beta (Released on 2015-09-10)
--------------------------------------------------------------------------------
* ACI0093225 特定の条件で[QUERY SELECTION](http://doc.4d.com/4Dv14/4D/14.4/QUERY-SELECTION.301-2511501.ja.html)を実行すると，キャッシュにパージできないオブジェクトが残ってしまい，次第にキャッシュが断片化して，データベースが遅くなったり，不可解なシンタックスエラーが発生するようになりました。たとえば，20,000件のテーブルでカレントセレクションが50件，130,000件のテーブルでカレントセレクションが600件，といった比率で問題は発生します。

Fixed bugs build 190005 v15 R2 beta (Released on 2015-09-08)
--------------------------------------------------------------------------------
* ACI0093580 Windows版のみ。チェコ語版のインストーラーを実行すると，エラーは発生しました。

Fixed bugs build 189629 v15 R2 beta (Released on 2015-08-31)
--------------------------------------------------------------------------------
* ACI0069136 Impossible to select an RTF file to create a hyperlink in 4D Write
* ACI0074490 クイックレポートで[Sum](http://doc.4d.com/4Dv14/4D/14.4/Sum.301-2510947.ja.html)を使用すると，アプリケーションがクラッシュしました。内部的に64ビット整数が返される関数のコールバックに問題ありました。
* ACI0079626 The command 'OBJECT GET BEST SIZE' used with a listbox returns wrong value
* ACI0081512 ラベルエディターでオブジェクトを水平に連結した場合，フィールド間に空白が自動的に挿入されるはずですが，そうはなりませんでした。
* ACI0082110 SQL: instability with the REPLICATE command when used with an SQL "WHERE" clause
* ACI0082461 Inconsistent sorting: Tables are not sorted the same way between Explorer and Method editor
* ACI0086721 "On Data Change" event doesn't always fire when change is done also programmatically
* ACI0087028 Some cells are not printed with 4D View plugin when using the 'repeated row' option
* ACI0087191 'OB Get' command: Type ahead of types is incorrect.
* ACI0087289 There is a problem with the generation of a 4D View sheet from the quick report which is positioned behind the window of the quick report
* ACI0088208 The command "SVG_New_embedded_image" could return a wrong picture reference
* ACI0088210 クイックレポートエディターの水平スクロールバーは，ウインドウを少しリサイズするまで動作しませんでした。
* ACI0088541 The focus circle around an object is too thin on Mac OS X
* ACI0089032 Problem of the candidate list for type ahead in the code editor.
* ACI0089072 In the Structure editor, Japanese character is incorrectly received by 4D.
* ACI0089325 Very slow scroll with a subform with lots of fields
* ACI0089568 プロパティリストでオブジェクトのフォント名が『ヒラギノ角ゴ ProN W6』などに設定されたストラクチャをv14にアップグレードすると，フォント名が『ヒラギノ角ゴ ProN』になってしまい，『W6』の情報が失われました。
* ACI0089658 Problem to manage groups name in Toolbox dialog
* ACI0089701 v14.2以降，[Menu selected](http://doc.4d.com/4Dv14/4D/14.4/Menu-selected.301-2511250.ja.html)から返されるメニュー番号違いました（フォームに関連付けられたメニュー）。また，その番号を[APPEND MENU ITEM](http://doc.4d.com/4Dv14/4D/14.4/APPEND-MENU-ITEM.301-2511241.ja.html)や[Get menu title](http://doc.4d.com/4Dv14/4D/14.4/Get-menu-title.301-2511262.ja.html)に渡しても駄目で，以前のバージョンで返された番号を渡さなければなりませんでした。
* ACI0089715 [SORT ARRAY](http://doc.4d.com/4Dv14/4D/14.4/SORT-ARRAY.301-2511942.ja.html)や[MULTI SORT ARRAY ](http://doc.4d.com/4Dv14/4D/14.4/MULTI-SORT-ARRAY.301-2511923.ja.html)でBLOB配列がソートされませんでした。
* ACI0089728 リストボックスのセルを編集中にマウスのロールボタンでスクロールすると，アプリケーションがクラッシュする場合がありました。
* ACI0089782 Since Mac OS X 10.10.x, the font color of a button text when clicking on it should be white ; instead, it is black with 4D
* ACI0089966 [PLATFORM PROPERTIES](http://doc.4d.com/4Dv14/4D/14.4/PLATFORM-PROPERTIES.301-2511885.ja.html)でWindows 8.1を検出することができませんでした。
* ACI0090102 並び替えダイアログの『削除』ボタンでフィールドをリストから取り除くことができませんでした。
* ACI0090149 Wrong text color display on cell if 'pv style automatic word wrap' property is set
* ACI0090157 Double click in a named selection in a listbox always shows the first record
* ACI0090165 Rearrange menu items doesn't save the change
* ACI0090277 Since 4D v14.3, a pop-up/dropdown object can't highlight an already selected item when open it out by clicking on it
* ACI0090491 Unable to update the title of the Application window
* ACI0090668 [FORM SCREENSHOT](http://doc.4d.com/4Dv14/4D/14.4/FORM-SCREENSHOT.301-2511088.ja.html)を（フォーム名を省略することによって）実行中のフォームに使用した場合，Webエリアの配置された領域が黒く塗りつぶされて出力されました。
* ACI0090743 Importing data exported in SHIFT-JIS turns unreadable.
* ACI0090817 [Num](http://doc.4d.com/4Dv14/4D/14.4/Num.301-2511786.ja.html)は，ハイフンまたはマイナス記号に続く文字列を無視しませんでした。たとえば，『123-45』が渡された場合，『123』が返されるべきですが，『12345』が間違って返されました。
* ACI0090825 Windows版のみ。[String](http://doc.4d.com/4Dv14/4D/14.4/String.301-2511773.ja.html)の16進数フォーマットは負の値が正しくありませんでした。
 
```
$result=String(-1;"&x")
 //期待値: "0xFFFFFFFF" 
 //結果値: "0x0000" 

$result=String(-1;"&$")
 //期待値: "$FFFFFFFF"
 //結果値: "$0" 
```
* ACI0090838 'CHANGE CURRENT USER' command does not change current user
* ACI0091051 After clicking on a combo box, closing the form window end the process but the window may leave open
* ACI0091193 [IMPORT DATA](http://doc.4d.com/4Dv14/4D/14.4/IMPORT-DATA.301-2511134.ja.html)にプロジェクトXMLを渡してデータをインポートした場合，文字コードの指定が無視されました。ダイアログから設定ファイルを選択した場合は問題ありません。
* ACI0091207 Problem when executing LEFT JOIN combined with WHERE and OR
* ACI0091274 フォームの2個の4D Writeエリアが表示されているとき，日本語変換の編集ウインドウが間違った場所に表示されることがありました。あるいは，間違ったほうのエリアに確定されたテキストが入力されました。
* ACI0091299 4D Viewのセルにテンキー側のピリオドキーを入力した場合，言語設定に従った小数点（ピリオドまたはカンマ）が入力されず，入力フィルターも正しく働きませんでした。
* ACI0091341 With 'OPEN FORM WINDOW', the size may be wrong after a conversion to v14
* ACI0091379 Focus ring becomes thick when hovering over 3D button
* ACI0091392 Focus issue for a PDF in Web Area using Acrobat
* ACI0091393 When you click in a numerical text area (variable or field, long integer or real), 4D does not automatically made the selection of the data already entered
* ACI0091484 4D Writeでスペルチェックを実行しても，ドキュメントが更新されませんでした。
* ACI0091525 4D stops responding on validating a form with an empty mandatory field.
* ACI0091528 Stylesheets with bold shown as italics as well on Listboxes headers
* ACI0091541 Calling a new process during an "On resize" event can freeze 4D
* ACI0091546 Memory leak while converting QuickTime picture with 'CONVERT PICTURE'
* ACI0091573 Printing from a JavaScript command is inoperative from a web area
* ACI0091616 [HTTP Request](http://doc.4d.com/4Dv14/4D/14.4/HTTP-Request.301-2510925.ja.html)に```PROFIND```のような（定数が定義されていない）HTTPメソッドを文字列で渡した場合，代わりに```GET```リクエストが送信されました。
* ACI0091637 'On data change' form event is unexpectedly triggered in a Combo box object.
* ACI0091687 In a LEFT OUTER JOIN, only the first criterion is taken into account
* ACI0091707 4D View may crash 4D when entering in a very large text in a cell edited
* ACI0091727 Auto Update regression - Administrator privileges are requested after Restart 4D command during the 4D server update (Windows only)
* ACI0091737 Mac版のみ。リストボックスのカラムに半角の円マークが含まれる表示フォーマットを適用した場合，半角のバックスラッシュが表示されました。
* ACI0091745 Since 4D v14 R4, pictures are badly drawn with 4D Write.
* ACI0091756 Restoring a v13 backup with 4D v14 Rx can lead to a crash.
* ACI0091817 Depending the font used, character downstroke is truncated on Mac OS X 10.10.x
* ACI0091866 Tool tip is missing to explain the need to restart database when index is missing for a primary key
* ACI0091868 Mac版のみ。Yosemiteで，ストラクチャをドラッグ＆ドロップで開き，メソッドエディターの点滅カーソルが1回目の点滅を完了する前に入力を開始した場合，日本語入力ができない状態になりました。ファイルメニューからストラクチャを開いた場合，あるいは少しの『間』を置いてからタイプ入力を始めた場合は問題ありません。

**参考**: [Yosemite日本語入力の対応を改善](http://www.4d.com/jp/blog/yosemite-japanese-input.html)
* ACI0091889 Non-enterable variables with automatic font colour are always black.
* ACI0091907  When creating a database to replace an existing one, the database is not replaced but created into the package of the preexisting database.
* ACI0091918 4D stops responding with a specific proxy configuration
* ACI0091928 There is a runtime syntax error with the Query Editor when a table has no fields.
* ACI0091933 No timeout when a web services is called
* ACI0091934 The value of "Soap Service Name" is always empty for the command "SOAP Get Info"
* ACI0091940 サーバーがMacでクライアントがWindowsの場合，WindowsクライアントでMacのスタイルシートを変更しても，更新が反映されませんでした。サーバーとクライアントのプラットフォームが逆であっても同じことでした。
* ACI0091941 Query editor does not allow numbers with decimal separator for FLOAT fields
* ACI0091967 Since v14 R4, a secured connection to a server from a client from another machine can lead to an unexpected error #1024 that prevent the connection.
* ACI0091988 Blocking of opening an already opened method in client/server.
* ACI0092000 クエリエディターで日付フィールドの『~日以内の過去/未来』を選択した場合，ダイアログに入力された数値ではなく，最後に表示された数値またはデフォルト値でクエリが実行されました。
* ACI0092011 Opening and closing the Explorer with "Esc" key may lead to a crash
* ACI0092057 Weak MD5 encryption for 'GENERATE CERTIFICATE REQUEST'
* ACI0092061 issue with GET PRINT OPTION(Destination option;val1;val2) and pdf file path
* ACI0092062 The Query editor displays a wrong format for suggested value when field type is time.
* ACI0092071 Cursor in 4D Write area disappears if an entry of combo-box or drop-down is selected
* ACI0092073 On Mac OS, when trying to make non-sizable a sizable object area that has the focus, you can have a bad redraw of the object focus area.
* ACI0092077 'LOG EVENT' command does not send text to Mac console using the constant "Into 4D debug message".
* ACI0092079 4D Remoteのみ。日付をオブジェクト変数に代入した場合，常にローカルタイムゾーンが使用されました。本来は，データベース設定の```JSON use local time```が反映されるべきです。もっとも，取り出した値は，元の（正しい）日付になります。

```
SET DATABASE PARAMETER(JSON use local time;0) 
C_OBJECT($oTest) 
C_DATE($testDate) 
$testDate:=!1965/2/12! 
OB SET($oTest;"Date1";$testDate) 
 //期待値: "1965-02-12T00:00:00Z" 
 //結果値: "1965-02-11T15:00:00Z" 
```

* ACI0092080 New constant 'BIND_IO' implemented in 4D for OCI
* ACI0092081 カレントセレクション型リストボックスにインデックスフィールドを追加し，フッターに自動計算を設定して```READ ONLY```モードで表示した場合，セレクションが空でない限りアプリケーションがクラッシュしました。
* ACI0092118 Plugin area in Design mode on Mac OS X.
* ACI0092127 Mac版のみ。Yosemiteでフルスクリーンモードから復帰した場合，デザインモードツールバーが本来の位置（メニューバーのすぐ下）に表示されませんでした。
* ACI0092174 Windows版のみ。デフォルトプリンターが設定されていない環境で[PRINTERS LIST ](http://doc.4d.com/4Dv14/4D/14.4/PRINTERS-LIST.301-2511456.ja.html)を使用した場合，空の配列が返されました。

**参考**: デフォルトプリンターが設定されていない環境では，下記のレジストリキーで```Device```が空です。

```
HKEYCU\Software\Microsoft\WindowsNT\CurrentVersion\Windows
```
* ACI0092203 The "ClientCertificatesFolder" folder is not set as the default folder for client's certificates
* ACI0092218 PICT形式の画像がフォームに配置されている場合，[PAGE SETUP](http://doc.4d.com/4Dv14/4D/14.4/PAGE-SETUP.301-2511442.ja.html)と[Print form](http://doc.4d.com/4Dv14/4D/14.4/Print-form.301-2511448.ja.html)でフォームをプリントアウトすると[PAGE BREAK](http://doc.4d.com/4Dv14/4D/14.4/PAGE-BREAK.301-2511449.ja.html)でアプリケーションがクラッシュしました。PDF印刷でも同じことがでした。画像が非表示でありました。
* ACI0092244 Windows版のみ。システム言語が『ルクセンブルグ』に設定されていた場合，アプリケーションを起動することができませんでした。
* ACI0092270 In compiled mode when calling ABORT from an error handling method, it does not abort the calling method as it is supposed to do
* ACI0092309 It happens that before displaying the wanted tab, the first tab displays shortly first
* ACI0092390 Since R5, the display position of placeholders on Mac OS X is shifted if text is Japanese.
* ACI0092402 アプリケーションビルドで『クライアント/サーバーアプリケーションをビルド』の『クライアントアプリケーションをビルド』をチェックせずに『MacOS/Windowsクライアントアプリケーションの自動更新を有効にする』をチェックしてビルドを進めた場合，エラーが返されたり，クラッシュしたりしました。
* ACI0092413 [DELETE MENU ITEM](http://doc.4d.com/4Dv14/4D/14.4/DELETE-MENU-ITEM.301-2511270.ja.html)に```-1```を渡しても，最後に追加された項目が削除されませんでした。
* ACI0092439 Slowness of 'UNREGISTRED CLIENT' command
* ACI0092446 『レコードを完全に削除』が有効にされていないテーブルのデータが含まれるデータファイルに対して『レコードヘッダーによる修復』を実行した場合，修復後にMSCのデータファイル検査でエラーがレポートされるようになりました。
* ACI0092454 Since v14 Rx version, the input text blinking cursor can just disappear.
* ACI0092460 『データファイルが更新された場合のみバックアップを行う』の動作に問題がありました。データファイルが更新されていない場合にバックアップが実行されないのは良いのですが，その後，新規レコードを追加した途端，スケジュールにないバックアップが開始されました。
* ACI0092485 『ユーザー更新可』プロパティを解除し，プロパティリストを閉じてから再表示させた場合，プロパティが選択されたままでした。
* ACI0092539 4D Remoteのみ。SQLの```INTO LISTBOX```は，何も結果が返されなかった場合，スタンドアロンではリストボックスをクリアしますが，4D Remoteでは何もしませんでした。
* ACI0092545 'QUERY BY FORMULA' issue with pointer
* ACI0092551[Print object](http://doc.4d.com/4Dv14/4D/14.4/Print-object.301-2511458.ja.html)でリストボックスをプリントアウトした場合，スタイル付きではないカラムが正しく印刷されませんでした。余計な改行コードが出力されました。
* ACI0092564 データファイルの名前にピリオドが含まれている場合，バックアップファイル（4BK）に連番が付けられず，常に最新のバックアップで上書きされてしまいました。
* ACI0092593 Since v14 R5, information returned by "GET WINDOW RECT" can be wrong if menu bar has been hidden.
* ACI0092616 リストボックスに複数行のテキストを表示し，文章がセルに収まらない長さで，折り返し（ワードワップ）が『自動』に設定されていた場合，水平揃え（右または中央）が反映されませんでした。
* ACI0092631  Edit action (cut, copy, paste, etc.) does not work using Japanese KANA keyboard layout.
* ACI0092651 Via the CSM during restore with integration of log file, if we click the finder, the selected log file window becomes inactive.  you need to force quite 4D, because none of the UI is responsive.
* ACI0092652 webサーバーにHTTPの```TRACE```命令を送信した場合，[RFC2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.8)で規定されているようにボディが返されず，ヘッダーだけが返されました。
* ACI0092679 SVGで『4State』バーコードフォントが使用できませんでした。
* ACI0092724 Changes in a stylesheet through the toolbox dialog are not always saved
* ACI0092735 Mac版のみ。[READ ONLY](http://doc.4d.com/--14.4/-/READ-ONLY.301-2511556.ja.html)で表示されたフォーム上の数値フィールドは，編集ができるような印象を与えました。数字部分をクリックすれば問題ありませんが，空白部分をクリックすると，フィールドが編集できそうな表示になりました。
* ACI0092736 14.4以降，フォームエディターから起動したフォームのメソッドをデバッガまたはエラーダイアログの『アボート』ボタンで中止した場合，再度，そのフォームを実行しても，アプリケーションを再起動するまでは，フォームイベントが発生しなくなりました。
* ACI0092741 メソッドエディターにSQLを記述し，[EXTRACT](http://doc.4d.com/4Dv14/4D/14/EXTRACT.300-1198478.ja.html)条件に続けて開く括弧を入力すると，アプリケーションがクラッシュしました。
* ACI0092764 ストラクチャエディターのインスペクターでフィールド名を『あああ』から『ｱｱｱ』に変更した場合，つまり，文字種だけを変更した場合，書き換えが無視されました。
* ACI0092810 Windows版のみ。Windows 7で日本語の入力中にアンダーライン（点線）が表示されませんでした。
* ACI0092858 ツールボックスのリソースページで，ファイルを選択して『名称変更』を選択した場合，現在のファイル名が表示されませんでした。また，『ディスク上に表示する』を選択しても，何も起きませんでした。
* ACI0092859 Mac版のみ。PDF文書を[READ PICTURE FILE](http://doc.4d.com/4Dv14/4D/14.4/READ-PICTURE-FILE.301-2511425.ja.html)で読み込んで[TRANSFORM PICTURE](http://doc.4d.com/4Dv14/4D/14.4/TRANSFORM-PICTURE.301-2511407.ja.html)で左右を反転した場合，[WRITE PICTURE FILE](http://doc.4d.com/4Dv14/4D/14.4/WRITE-PICTURE-FILE.301-2511426.ja.html)で書き出すと空のPDFになりました。
* ACI0092921 Drawing problem on a report after using the 4D command 'QR SET SORTS'
* ACI0092966 Problem when using the 'SVG_GET_ATTRIBUTES' command that returning single quotes instead of double quote when applied on tspan font families
* ACI0093003 Style text making the text invisible on a text menu item of a dynamic pop-up when there is an icon in this item
* ACI0093130 [SVG_SET_SHAPE_RENDERING](http://doc.4d.com/4Dv14/4D/14/SVG-SET-SHAPE-RENDERING.301-1382636.ja.html)に```optimizeSpeed```を渡すとエラーが返されました。
* ACI0093164 PA_Tokenize() leads 4D to quit
* ACI0093288 一部のSVG画像要素（matrix scalingがゼロかつshearがゼロではない）はピクチャエリアに表示されませんでした。Webエリアでは問題ありません。
