[4D v14.3 Hotfix 2](http://forums.4d.fr/Post/FR/15945962/1/15945963)
---
* ACI0091348 Windows版のみ，配列型のタブコントロールの最後の要素が選択されている場合，[DELETE FROM ARRAY](http://doc.4d.com/4Dv14/4D/14.3/DELETE-FROM-ARRAY.301-1697569.ja.html)でそのタブを削除するとアプリケーションがクラッシュしました。

* ACI0091172 [QUERY SELECTION](http://doc.4d.com/4Dv14/4D/14.3/QUERY-SELECTION.301-1697129.ja.html)で表示したクエリエディターのクエリタイプメニューは，デフォルトで「絞り込み」にセットされていませんでした。

* ACI0091143 コンポーネントメソッドSVG_SET_FONT_FAMILYを使用した場合，SVG_CLEARでメモリーが完全に解放されませんでした（メモリーリーク）がありました。

【参考】メモリーリークは[GET MEMORY STATISTICS](http://doc.4d.com/4Dv14/4D/14.3/GET-MEMORY-STATISTICS.301-1696594.ja.html)で確認することができます。

* ACI0091090 『プリント時可変』オブジェクトが設定されたテキストを印刷した場合，0による除算が発生することにより，アプリケーションがクラッシュすることがありました。

* ACI0091086 Mac版のみ，OS X 10.10でPRINT SELECTIONを実行すると，入力可フィールドの背景色がランダムにグレーでプリントアウトされました。

* ACI0091082 Mac版のみ，リストボックスに[スクロールしない列](http://doc.4d.com/4Dv14/4D/14.3/List-box-specific-properties.300-1705526.ja.html)が設定されており，そのリストボックスがサブフォームに含まれている場合，デザインモードでそのフォームを開くとアプリケーションがクラッシュしました。

* ACI0090990 [クイックレポートエディター](http://doc.4d.com/4Dv14/4D/14.3/Sorting-report-records.300-1705505.ja.html)で追加したフィールドの並び替え条件を設定することができますが，昇順/降順を示す三角形のアイコンが表示されませんでした。

* ACI0090951 Mac版のみ，3Dボタン・ラジオボタン・チェックボックス・ピクチャボタン・ピクチャポップアップメニューで参照されたSVG画像を印刷すると，真っ黒に出力されました。変数やフィールドでは問題ありません。

* ACI0090881 空のテキスト・BLOB・ピクチャフィールドに対して[Get External data path](http://doc.4d.com/4Dv14/4D/14.3/Get-external-data-path.301-1697422.ja.html)を発行すると，空の文字列を返す代わりに『ExternalData:Table-1 Field-1』といった無効なパスが返されました。

* ACI0090865 Windows版のみ，統合WebKit版の[Webエリア](http://doc.4d.com/4Dv14/4D/14.3/Web-areas.300-1705532.ja.html)は，コンテキストメニューに『LOCALIZED STRING NOT FOUND』と表示されました。

* ACI0090853 Windows版のみ，ポップアップメニューにスクロールバーが表示されるときのサイズが不十分でした。

* ACI0090847 Windows版のみ，タブコントロールは必要に応じてタブがスクロールするようになっていますが，v13以降，表示されていないタブをコマンドで選択した場合，v11のようにタブコントロールが自動的にスクロールしませんでした。

ACI0090847 In case of change of current tab, 4D does not always make it visible.
ACI0090828 Build Application very slow when copying files on mac
ACI0090753 'Get picture file name' fails under certain conditions
ACI0090654 Listbox: Default alignment is ignored when printing listbox for numeric column
ACI0090575 'MSG_EXTRACT' can't decode properly UTF8 encoded file names.
ACI0090567 Build Application: Master license column not updated when removing license
ACI0090556 Build Dialog: Master column is empty for expansion licences
ACI0090541 In client/server mode, "METHOD SET CODE" can unexpectedly quit 4D Server
ACI0090527 When editing form, 'undo' about font settings not working properly

* ACI0090448 Mac版のみ，フォームエディター上でボタンやテキスト入力オブジェクトを選択し，ペーストボードにコピーしたBLOBを後でペーストボードに再現しても，ペーストしたときにはスタティックピクチャーとして貼り付けられました。

【参考】Mac版のAPPEND DATA TO PASTEBOARDは，すでにペーストボードに存在するデータを追加（上書き）しようとした場合，ペーストボード全体の内容をクリアするようになっています。加えて，com.apple.pictをペーストボードに追加すると，自動的にpublic.jpegやpublic.pngも追加されます。そのため，ペーストボートにデータを追加する順序次第では，先に追加したフォームオブジェクトなどのデータが消去されてしまいます。すでに格納されているデータを消さずにペーストボードデータを追加するためには，そのタイプが存在するかどうかを確認しなければなりません。ペーストボードにデータが存在しなければ[Pasteboard data size](http://doc.4d.com/4Dv14/4D/14.3/Pasteboard-data-size.301-1697028.ja.html)が-102を返します。

* ACI0090378 HTTPヘッダーの『accept』フィールドに『compress, gzip, identify』が含まれていた場合，[On Web Connection](http://doc.4d.com/4Dv14/4D/14.3/On-Web-Connection-Database-Method.300-1697689.ja.html)に制御が渡らず，406エラーが返されました。

* ACI0090364 リストボックスの列を入力可に設定し，選択リストを設定した場合，セルの編集中に上下矢印キーを入力すると，アプリケーションがクラッシュしました。

* ACI0090319 Mac版のみ，リストフォームのOn Headerイベントでは[SET WINDOW TITLE](http://doc.4d.com/4Dv14/4D/14.3/SET-WINDOW-TITLE.301-1697737.ja.html)が効きませんでした。

ACI0090259 Runtime Error "Invalid parameters" in Web Service method
ACI0090258 Program hangs after using SMTP_SEND without optional parameter
ACI0090116 Updating an application by itself : deletion of application
ACI0090115 Incomplete printing of a styled text with variable frame on Windows
ACI0090094 'SET PRINT OPTION' to a PDF not working
ACI0089899 After a signed merged application updated, Gatekeeper it not triggered
ACI0089704 Web Area doesn't work correctly when displayed in a form page that is not page 1
ACI0089335 PK Wizard not loading in C/S mode
ACI0089184 4D Write menu not shown with 'Movable dialog box' window type
ACI0089145 Remote 4D link proposed in the submenu local databases.
ACI0089113 '.4DC' does not open the adjacent '.4DD' by default
ACI0088790 Some strings cut in label editor in spanish version
ACI0088470 Blinking cursor becomes invisible because of a right justification
ACI0088360 Entering decimal separator does not work in a listbox
ACI0088262 External data path damaged for picture field.
ACI0087679 Listbox: column insertion position marker is badly calculated
ACI0087370 Using 'WEB SEND RAW DATA(data;*)' on a very bad network can hang 4D
ACI0087352 PRINT LABEL (l([table];>) or PRINT LABEL (>) : Syntax error
ACI0087312 Synchronous sorting of arrays object
ACI0087252 In 4D View tabulating from cell to cell does not work
ACI0086913 Quick Report: No numeric format for calculated column

* ACI0082468 Windows版のみ，メソッドエディターの候補ウィンドウに不要な横スクロールバーが表示されるために高さが不十分になり，最後の補完候補が隠れてしまいました。

* ACI0080790 Windows版のみ，ペイント（mspaint.exe）から画像をピクチャエリアにコピー＆ペーストした場合，イメージが縮小されました。

* ACI0080677 Mac版のみ，コードエディターにいくらかの日本語を入力した後，それ以上は戻れなくなるところまで『取り消し』（command+Z）した後に『やり直し』（command+shift+Z）した場合，元のテキストが複製されました。

* ACI0072111 アプリケーションサーバーのポート番号を19813以外に設定してサーバー/クライアントアプリケーションをビルドした場合，ビルドしたクライアントの『サーバーに接続』ダイアログにはビルドしたサーバーの名前が表示されませんでした。
