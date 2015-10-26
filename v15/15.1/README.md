4D v15.1
---
Fixed bugs v15.1 build 192035 (Released on 2015-10-20)
--------------------------------------------------------------------------------
* ACI0093698 : [131869] Buttons appear to be disabled
* ACI0093918 : [10.11]List box choice list icon is displayed too high on El Capitan
* ACI0093937 : Click on the combobox causes problem.

Fixed bugs v15.1 build 191892 (Released on 2015-10-16)
--------------------------------------------------------------------------------
* ACI0090006 シートウインドウで表示されたフォームにコンボボックスの動きに問題がありました。コンボボックスのポップアップをクリックした後（テキスト入力では問題ありません）ウインドウをクリックすると，コンボボックスのポップアップが隠れてしまいました。ただし，引き続き入力はでき，またアプリケーションを最前面に移動した後などに一瞬だけ表示されたりします。

Fixed bugs v15.1 build 191792 (Released on 2015-10-14)
--------------------------------------------------------------------------------
* ACI0093593 : [131792] Modifier key missing from pop-up menu
* ACI0093687 日本語入力中の『取り消し（Control+Z）』と『やり直し（Control+Shift+Z）』の動きが正しくありませんでした。**ACI0091505**とは違う問題です（詳細は以下のとおり）。

Fixed bugs v15.1 build 191739 (Released on 2015-10-13)
--------------------------------------------------------------------------------
* ACI0093762 プライマリーキーの無いv13データファイルを自動UUIDプライマリーキーが設定されたv15ストラクチャファイルで開いた場合，変換時にプライマリーキーのNULLがUUIDで満たされませんでした。そのため，ビルドされたアプリケーションでは，プライマリーキーの問題が検出された，というエラーが表示されてアプリケーションが終了します。MSCなどを使用しても，プライマリーキーの問題を解決することはできません。Nightly Build (14.191146, 15.190879) で発生した不具合です。ACI0093556（下記）の修正による副作用と思われます。
* ACI0093775 ビルドされたサーバー/クライアントアプリケーションでバージョン管理を有効にしておき，古いクライアントを新しいサーバーに接続したときに表示される画面を確定せずに，サーバー側の管理画面に表示されているユーザー名を確認します。ひとりだけ名前のないクライアントがいるはずです。そのまま20秒以上，待ちます。待った後，タスクマネージャーでクライアントを強制的に終了します。サーバー側には終了したクライアントのユーザーが残ります。このユーザーを管理画面のドロップボタンでドロップすることはできませんが，ライセンス数には影響がないようです。新ネットワークレイヤーでなければ起きません。
* ACI0093820 : Memory leaks and crash with MSC when switch between tab 'data' and 'structure'
* ACI0093901 : Very little memory available in Mac 32 bits on El Capitan.

Fixed bugs v15.0 build 191674 (Released on 2015-10-11)
--------------------------------------------------------------------------------
* ACI0093831 : [131929] Tab and return works wrong under certain conditions.

Fixed bugs v15.0 build 191432 (Released on 2015-10-07)
--------------------------------------------------------------------------------
* ACI0092047 : [131090] Variable is unenterable if web area on the same form (with PDF or website loaded)
* ACI0092680 Windows版のみ。[LAUNCH EXTERNAL PROCESS](http://doc.4d.com/4Dv14/4D/14.4/LAUNCH-EXTERNAL-PROCESS.301-2511896.ja.html)をブロッキングモードで実行した場合，外部プロセスから制御が返されるまで，CPUコア1個が100%のアクティビティを示しました。たとえば，8コアのWindowsであれば，12.5%のアクティビティがタスクマネージャーに表示されます。CPUがビジー状態になるため，外部アプリケーションのパフォーマンスも著しく低下します。v12以前のバージョンでは，外部プロセスから制御が返されるまで，4Dのユーザーインタフェースが完全にフリーズしたようになりましたが，CPU使用率が100%になることはありませんでした。
* ACI0093821 : Crash in (old) Quick report with Cross table preview

Fixed bugs v15.0 build 191390 (Released on 2015-10-06)
--------------------------------------------------------------------------------
* ACI0085368 SQLビューからリストボックスのSELECT INTOを何回も実行すると，次第にズレが発生し，ヘッダーの内容が更新されなかったり，必要な列が作成されないようになります。SQLビュー（```_USER_VIEW_COLUMNS```）というよりは，リストボックスの問題です。実際，SQLビューを使用しなくても，同じ問題が発生します。後続のSELECTを実行する前にリストボックスをクリア（LISTBOX DELETE COLUMN）すれば問題を回避することができます。
* ACI0085575 : [129623] Combo box and sheet window
* ACI0089241 Mac版のみ。Webサーバーがリクエストを処理している最中にWebサーバーを終了すると，以後，Webサーバーを起動しようとしても『データベースが公開できません』エラーが返されました。ポート番号が1024以上のときに問題が発生します。ポート番号が1023以下（[HelperTool](http://doc.4d.com/4Dv15/4D/15/Web-server-configuration-and-connection-management.300-2006437.ja.html)でWebサーバーを公開）であれば，問題ありません。
* ACI0089938 レコードが作成され，他のプロセスで更新されている間に再びレコードが作成された場合，自動インクリメントまたは[Sequence number](http://doc.4d.com/4Dv14/4D/14.4/Sequence-number.301-2511571.ja.html)で発行されるシーケンス番号が連番になりませんでした。たとえば，3件のレコードを作成して3個のプロセスで更新した場合，それぞれのシーケンス番号は1, 3, 5になりました。レコードをアンロードすれば，1, 2, 3が発行されます。レコードの作成時だけでなく，更新時にも新しいシーケンス番号が発行・予約されていました。修正により，新しいシーケンス番号はレコードの作成時にだけ発行されるようになりました。
* ACI0091164 Mac版のみ。デザインモードでリストボックスの列を選択し，イベントのチェックボックスをCommand+クリックしても，すべてのイベントをまとめて選択あるいは解除することができませんでした。
* ACI0092729 : Window position not saved.
* ACI0093598 : Listbox: In some cases, make a boolean column enterable  has no effect.
* ACI0093625 : [131810] Text in listbox cells shifted to the bottom so that characters are cut off.

Fixed bugs v15.0 build 191293 (Released on 2015-10-03)
--------------------------------------------------------------------------------
* ACI0090771 4D Remoteのストラクチャエディターからプライマリーキーアシスタントを起動し，閉じた後，クライアント側の実行メニュー『インタープリター再起動』を選択してサーバーを再起動すると，READ ONLYモードでストラクチャファイルが開かれるという警告が表示され，続けてサーバーがクラッシュしました。
* ACI0092821 アプリケーションビルドXMLプロジェクトファイルの[DataPathFile](http://doc.4d.com/4Dv15/4D/15/DataFilePath.300-2400037.ja.html)キーに相対パスを指定した場合に問題がありました。たとえば，ストラクチャファイルの名前が"application.4DC"でデータファイルの名前が"data.4DD"だった場合，データファイルがストラクチャと同じフォルダーに存在するのであれば，プロジェクトファイルは下記のようになるはずです。

```xml
<DataFilePath>data.4DD</DataFilePath>
```

しかし，実際には，初回の起動で『データファイルを作成または選択』ダイアログが表示されました。

**注記**: v11/12のドキュメントでは，POSIX相対パス，つまり"data.4DD"でストラクチャの隣にあるデータファイルが指定できる，と記述されていました。しかし，v13以降，ドキュメントはプラットフォーム特有の絶対または相対パスを指定するようにと改定されました。相対パスはWindowsが"\data.4DD"，Macが":data.4DD"と記述しなければなりません。問題は，この相対パスがアプリケーションに対して相対的だったことにあります。修正により，相対パスはストラクチャファイルに対して相対的（つまりドキュメントどおり）になりました。
* ACI0092875 SQLのDROP TABLEを短期間に連続して実行すると，データテーブルが削除されている，というランタイムエラーがランダムに発生しました。
* ACI0093766 : It is not possible to shutdown and restart the application server with ServerNet.
* ACI0093834 : OBJECT MOVE crash 4D with 4D server 64 bit on MAC.

Fixed bugs v15.0 build 191233 (Released on 2015-10-02)
--------------------------------------------------------------------------------
* ACI0092223 [OPEN SETTINGS WINDOW](http://doc.4d.com/4Dv14/4D/14.4/OPEN-SETTINGS-WINDOW.301-2510974.ja.html)で互換性ページを開くことができませんでした。
* ACI0093105 [ST Get text](http://doc.4d.com/4Dv14/4D/14.4/ST-Get-text.301-2510891.ja.html)に渡された標準テキストにXMLでエスケープされるべき文字（```&<>```など）が含まれていた場合，空の文字列が返されました。このコマンドには，スタイル付きテキスト（spanタグ/XML）と標準テキストのどちらも渡すことができ，無効なXMLであれば，標準テキストとして処理されます。
* ACI0093556 v12データファイルをテーブルが追加されたv15ストラクチャファイルで開いた場合，変換の直後に新規レコードを追加すると，データファイルが壊れました。ジャーナリングの有無は関係ありません。変換した直後にデータベースを再起動すれば，問題を回避することができます。
* ACI0093675 新規テーブルを作成し，レコードを追加した後，インデックス付きの日付フィールドを追加し，フォームにもそのフィールドを増設して既存レコードの日付フィールドを更新すると，MSCのデータファイル検証でB-Treeインデックスのエラー（キーが重複するレコード番号を参照している）がレポートされました。追加したフィールドが日付型でなければ問題ありません。
* ACI0093786 : Dropdown list : mousewheel could be inoperative (this bug appears because of ACI0093729 fix)

Fixed bugs v15.0 build 191177 (Released on 2015-10-01)
--------------------------------------------------------------------------------
* ACI0089836 : Memorization of window geometry not working
* ACI0093592 : Wrong information about current system in server administration window
* ACI0093670 : 4D Client IP Address does not appear in 4DRequestLog_ProcessInfo log
* ACI0093729 :[131883] issue with dropdown list displays in modal windows

Fixed bugs v15.0 build 191084 (Released on 2015-09-30)
--------------------------------------------------------------------------------
* ACI0093752 : Error with SVG_Validate_file

Fixed bugs v15.0 build 191063 (Released on 2015-09-29)
--------------------------------------------------------------------------------
* ACI0093641 : Form Editor - shift - new line drag
* ACI0093600 : The menu "File/Import ODBC..." displays an error alert
* ACI0093759 重複不可でインデックスが設定されているフィールドに何らかの理由で重複するレコードが登録されている場合，そのフィールドのインデックスを削除した後，[CREATE INDEX](http://doc.4d.com/4Dv14/4D/14.4/CREATE-INDEX.301-2511803.ja.html)または[SET INDEX](http://doc.4d.com/4Dv14/4D/14.4/SET-INDEX.301-2511800.ja.html)コマンドでインデックスを再作成すると，重複不可属性が解除されました。修正により，インデックス構築中に重複不可属性の違反が検出されても，属性は解除されないようになりました。
* ACI0093752 : Error with SVG_Validate_file
* ACI0093746 : Error -9930 with SVG command SVG_SET_STROKE_MITERLIMIT and parameter 0

Fixed bugs v15.0 build 191000 (Released on 2015-09-26)
--------------------------------------------------------------------------------
* ACI0088416 ビルドされたデスクトップ版アプリケーションの『[ユーザー認証](http://doc.4d.com/4Dv14/4D/14.4/Access-system-overview.300-2604083.ja.html)』ダイアログで『パスワードを保存』オプションを有効にしても，次回の起動で再び『ユーザー認証』ダイアログが表示されました。
* ACI0091789 Windows版のみ。フランス語版の4D Viewまたは4D Writeプラグインの著作権情報が英語でエクスプローラーに表示されました。
* ACI0093412 [PV Copy to blob](http://doc.4d.com/4Dv14/4D-View/14/PV-Copy-to-blob.301-1377956.ja.html)および[PV PASTE FROM BLOB](http://doc.4d.com/4Dv14/4D-View/14/PV-PASTE-FROM-BLOB.301-1377955.ja.html)で背面に配置された画像が処理されませんでした。
* ACI0093587 [ユーザー設定](http://doc.4d.com/4Dv15/4D/15/Using-user-settings.300-2045482.ja.html)を使用したときに表示されるサブメニューが英語でした。

Fixed bugs v15.0 build 190946 (Released on 2015-09-25)
--------------------------------------------------------------------------------
ACI0088897 : [131734 ] The command "PV Get Picture"  causes 4D to crash if it throws an error.
ACI0092449 : [131233] Since v14, it is impossible to send email in an encoding other than UTF-8
ACI0092629 : 4D issue when creating a form using the Form Wizard.
ACI0092788 : Issu with underline style in listbox
ACI0093419 : [131703] USE REMOTE DATABASE in C/S in Transaction fail
ACI0093480 : Can not restart in compiled or in interpreted for C/S databases running with new network layer.
ACI0093593 : [131792] Modifier key missing from pop-up menu
ACI0093608 : [131799] Right click on Splitter kills it
ACI0093633 : Lose focus with Modal Form dialog after display alert
ACI0093648 : [131830] Converted subtables cause problems if used in the query editor.

Fixed bugs v15.0 build 190774 (Released on 2015-09-23)
--------------------------------------------------------------------------------
ACI0088808 : [129686][131437] Incorrect OK value of SQL Login.
ACI0093075 : [131493] Memory leak using SVG SET ATTRIBUTE with a pointer as pictureObject

Fixed bugs v15.0 build 190695 (Released on 2015-09-21)
--------------------------------------------------------------------------------
ACI0078353 : [126275] FORM GET OBJECTS returns wrong variable pointer for listbox in edit mode.
ACI0090464 : Menus and plugins localization problem with Portuguese version.
ACI0093032 : [131463] Incorrect display of the listbox contents.
ACI0093368 : IMAP_GetMessage command returns error code on Mac 64 bits.
ACI0093389 : [131836] Dialog on Quit Merged.
ACI0093533 : [131707] Export editor has memory leak if called in a loop without table selected.
ACI0093621 : [131834][Build App v15] xliff not resolved (was: crash at startup.

Fixed bugs v15.0 build 190555 (Released on 2015-09-18)
--------------------------------------------------------------------------------
ACI0093191 : [131434] "Unique" property lost after repairing data.

Fixed bugs v15.0 build 190539 (Released on 2015-09-17)
--------------------------------------------------------------------------------
ACI0091977 : [131064] Issue with SET TABLE TITLES. 
ACI0092751 : [Query Editor]Popup menu is too small on Windows
ACI0093352 : [131529] Failed to execute INSERT command in External Database
ACI0093546 : Option "do not create log" is ignored in compact date file command
ACI0093630 : String( -0.99999999999999534) produces "1" instead of "-1"

Fixed bugs v15.0 build 190428 (Released on 2015-09-16)
--------------------------------------------------------------------------------
ACI0088819 : Location problem when duplicating a form.

Fixed bugs v15.0 build 190414 (Released on 2015-09-15)
--------------------------------------------------------------------------------
ACI0085614 : Internet Commands work wrong with relative path
ACI0087196 : 4D Stops Responding on Mac with "Picture Properties" When File is Corrupted
ACI0091224 : Transfer Time in web log shows confusing values
ACI0093442 : 4D Documentation Links

Fixed bugs v15.0 build 190312 (Released on 2015-09-11)
--------------------------------------------------------------------------------
ACI0093121 : Mistake in Japanese localisation of form editor; vertical instead horizontal
ACI0093462 : [131718] Export a report to 4D View does not work anymore.
ACI0093586 : List Box not scrolling to offscreen area when dragging column (user mod)

Fixed bugs v15.0 build 190179 (Released on 2015-09-10)
--------------------------------------------------------------------------------
ACI0088594 : Changing form name without validation. 

Fixed bugs v15.0 build 190137 (Released on 2015-09-09)
--------------------------------------------------------------------------------
ACI0089641 : [130456] Breakpoint in a "On display detail" list form event freezes.
ACI0092734 : Resizing width of listbox array
ACI0092779 : [131359] Xliff in a listbox
ACI0092792 : Style of units button or lllipsis is modify when enter in edit mode.
ACI0092980 : Scrolling is very slow in Hierarchical Lists.
ACI0093008 : [131627] The subform window content disappears.
ACI0093336 : Issu when move locked column
ACI0093339 : Listbox footer ignores font colour settings
ACI0093594 : Spelling error in french on information pop-up.

Fixed bugs v15.0 build 190021 (Released on 2015-09-08)
--------------------------------------------------------------------------------
ACI0092137 : Export data editor - double click adds field twice
ACI0092560 : [131063] AJAX requests with 'Reuse Temporary Contexts' Can Crash 4D Remote
ACI0093044 : Missing plugins icon in the explorer
ACI0093396 : [131690] Listbox, Data Source Undefined leads the crash of 4D
ACI0093415 : [131705] 404 Status persistent due to an error in the 4D code
ACI0093459 : No SVG created if only a part of styled text is styled by context menu
ACI0093546 : Option "do not create log" is ignored in compact date file command
ACI0093580 : 4D installation issue on the Czech Windows OS.

Fixed bugs v15.0 build 189972 (Released on 2015-09-05)
--------------------------------------------------------------------------------
ACI0093297 : [131641] generating the typing does not consider the listbox headers. 
ACI0093459 : No SVG created if only a part of styled text is styled by context menu
ACI0093504 : Context-click radio buttons and check boxes

Fixed bugs v15.0 build 189937 (Released on 2015-09-04)
--------------------------------------------------------------------------------
ACI0087170 : [131228] Option AUTO_GENERATE makes select count(*) from ... is null" fail
ACI0090953 : [130601] Large Transaction will Not Complete with 4D Server v14.3HF1 64-Bit
ACI0091497 : [130861] Change current user blocks plugin licenses
ACI0092116 : [130949] Navigation slowness when editing a 4D view document
ACI0093072 : Service isn't relaunch after update 4D server v14  32bits with 4D server v15 32bits
ACI0093073 : Update 4D server 64 bits doesn't work in service
ACI0093467 : QR Execute Command can return error No 9852 in 4D v15

Fixed bugs v15.0 build 189829 (Released on 2015-09-03)
--------------------------------------------------------------------------------
ACI0081921 : [127310] Web area problem : the web area scrollbars become inaccessible.
ACI0093196 : In a built Client/Server application the Server is not being populated with a version number
ACI0093073 : Update 4D server 64 bits doesn't work in service

Fixed bugs v15.0 build 189717 (Released on 2015-09-01)
--------------------------------------------------------------------------------
ACI0075500 : Quick Report Breaks Subsequent Order By
ACI0076615 : Quick report and deleted field
ACI0082378 : [130361] List Box not scrolling to offscreen area when dragging column
ACI0087268 : [128955] Freeze of 4D with incorrect formula in the Quick Report
ACI0092786 : [131295] Use of shortcuts in a pop up drop down list
ACI0092994 : The current value is not selected in the pop-up 
ACI0093044 : Missing plugins icon in the explorer
ACI0093281 : Crash after drag & drop of a picture in a form on Design mode
ACI0093470 : Explorer Menu not working
ACI0093510 : MSC - Verify structure crash in Volume Desktop

Fixed bugs v15.0 build 189616 (Released on 2015-08-28)
--------------------------------------------------------------------------------
ACI0068730 : SQL Month and Year functions give incorrect results
ACI0084755 : "Current method path" does no more return object path Compiled
ACI0090862 : System_Table: count for _User_Columns returns 0
ACI0090925 : SQL Month and Year functions can return incorrect results
ACI0092691 : Connection is broken when using new network layer with On Server Close Connection
ACI0092692 : [Servernet] On Server Close Connection reports network error
ACI0093361 : Copy/Paste with empty selection while KANA input is active.   

Fixed bugs v15.0 build 189460 (Released on 2015-08-26)
--------------------------------------------------------------------------------
ACI0093237 : [131602] BASIC web authentication takes 15 seconds using Safari or FireFox

Fixed bugs v15.0 build 189423 (Released on 2015-08-25)
--------------------------------------------------------------------------------
ACI0093225 : [131600] QUERY SELECTION produces locked objects that lead to fragmented cache

Fixed bugs v15.0 build 189396 (Released on 2015-08-22)
--------------------------------------------------------------------------------
ACI0092892 : [131408] HTTP Get - Digest Auth - bad/uncomplete opaque header

Fixed bugs v15.0 build 189364 (Released on 2015-08-21)
--------------------------------------------------------------------------------
ACI0091083 : LISTBOX SET LOCKED COLUMNS ( {* ;} object ; -10 ) and move column
ACI0093359 : Dereferenced field pointer from method fails  

Fixed bugs v15.0 build 189325 (Released on 2015-08-20)
--------------------------------------------------------------------------------
ACI0089383 : The expiration date of the license is always 00.00.0000 in the MCS Information window.
ACI0092583 : [Forum 4D] Data damaged after a Compact
ACI0093245 : [131609] MSC crashes while repairing structure

Fixed bugs v15.0 build 189261 (Released on 2015-08-19)
--------------------------------------------------------------------------------
ACI0093195 : 4D Mac 64-bits Memory leak with SQL statement

Fixed bugs v15.0 build 189224 (Released on 2015-08-18)
--------------------------------------------------------------------------------
ACI0092533 : [131302] Http SET OPTION on setting HTTP timeout does not change
ACI0093137 : [131560] [v15 regression] Constants with umlauts cannot be compiled
ACI0093138 : Custom Constants, Method Editor: 'resname xxxx not found'
ACI0093288 : [131637] Incomplete display in SVG files.

Fixed bugs v15.0 build 189179 (Released on 2015-08-15)
--------------------------------------------------------------------------------
ACI0092803 : [131380] Edit history (control+Z) is not cleared after current record change
ACI0093076 : Text Fields in Quick Reports Are Cut Off
ACI0093129 : OK variable is not set to 0 after an incorrect execution of "XML GET ERROR"
ACI0093248 : ST GET ATTRIBUTES - Attribute text color

Fixed bugs v15.0 build 188995 (Released on 2015-08-11)
--------------------------------------------------------------------------------
ACI0093042 : Malfunction in the menu editor
ACI0093093 : [131517] Close box of a palette does not work anymore under certain conditions
ACI0093130 : Error with SVG_SET_SHAPE_RENDERING with parameter "optimizeSpeed"
ACI0093341 : 4DIC Mac64 failures

Fixed bugs v15.0 build 188938 (Released on 2015-08-08)
--------------------------------------------------------------------------------
ACI0081512 : [130550] Label Editor: problem with the horizontal concatenation
ACI0093318 : Memory leak for new cooperative processes with a window

Fixed bugs v15.0 build 188914 (Released on 2015-08-07)
--------------------------------------------------------------------------------
ACI0090169 : Scope of local Object variables.

Fixed bugs v15.0 build 188707 (Released on 2015-08-04)
--------------------------------------------------------------------------------
ACI0074490 : Using the "Sum" function in a Quick Report causes 4D to crash
ACI0083311 : [127619][130393] DHtml document and accented characters
ACI0089701 : [131194][131378] Menu selected returns 2052 instead of 2049
ACI0089966 : PLATFORM PROPERTIES and Windows 8.1
ACI0091274 : [130770] Japanese shown in wrong area when there is 2 4D Write areas in a form
ACI0091299 : [130750] Window Resizing
ACI0091504 : [130869] Behavior change in handling of Build App Keys on Mac as of 13.5HF1
ACI0091505 : [131379] Behavior of Ctrl+Z and Shift+Ctrl+Z is wrong when using Japanese in 4D
ACI0091590 : [130900] ERASE WINDOW will unexpectedly make background grey
ACI0091608 : [130913] 4D crashes when opening HTML file with 4D Write
ACI0091772 : [131003] Window Resizing
ACI0091904 : Print listbox dropdown list and checkbox
ACI0091906 : Print listbox elipsis button and unit button are not print
ACI0091907 : Create and replacing a database
ACI0091920 : Since R5, it is impossible to select a size-zero object in the Form Editor
ACI0091942 : Issu for scrolling when move row in listbox
ACI0092047 : [131090] Variable is unenterable if web area on the same form (with PDF or website loaded)
ACI0092071 : [131101] Cursor in 4D Write disappears
ACI0092251 : [131154] Keyboard shortcuts with no modifiers don't work if Japanese Input (Alphabet-mode) is used
ACI0092402 : Build archive without build client crash 4D
ACI0092446 : [131231] Issues with MSC Verify and Repair by Headers
ACI0092460 : [131245] "Backup only if the data file has been modified"
ACI0092515 : [131262] error 3146 from Access when using AND or OR in WHERE statement
ACI0092564 : The 4BK backup file is systematically overwritten
ACI0092631 : [131298] Edit action (cut, copy, paste, etc) does not work using Japanese KANA keyboard layout since v14
ACI0092643 : [131266] MS Access crashing with CDate query to 4D
ACI0092651 : MSC restore displays "file select" dialog in wrong window type, user must force quit 4D.
ACI0092679 : [131619] 4D SVG does not render Text properly in certain fonts
ACI0092681 : [131371] VARIABLE TO BLOB et ARRAY BLOB
ACI0092709 : SET EXTERNAL DATA PATH issue with relative path "../"
ACI0092735 : [131350] READ ONLY records may look like editable in v14
ACI0092764 : [129787][131374] Japanese received incorrectly in structure editor (2)
ACI0092858 : Contextual menu in Toolbox/Resources doesn't work
ACI0092859 : Modifying pdf file with Transform Picture
ACI0092871 : [131383] Webservice et retour xml vide
ACI0092914 : [131422] new domains to use in the E-Mail registration
ACI0092922 : Closing a WebSession already used cause a DeadLock in 4D WebSession Manager
ACI0092944 : Web variables not reinitialized on SOAP calls
ACI0092954 : [131446] 4D Mobile OEM licenses are not copied during build process
ACI0092956 : [131426] OBJECT SET TITLE not working if object is using Object name XLIFF syntax
ACI0092962 : Disabled default button is blue if window is inactive on Mac
ACI0092966 : SVG_GET_ATTRIBUTES : tspan font-family, simple quote-> double quote
ACI0092969 : An error is displayed when trying to reconnect to 4D server.
ACI0092990 : QUERY BY ATTRIBUTE with null value as parameter does'nt return the same think in sequential or indexed
ACI0092991 : Engined OEM Server : License or privilege error.
ACI0093006 : QUERY BY ATTRIBUTE, bad results when using the operator # in Client/Server
ACI0093010 : Difference in behavior on QUERY BY ATTRIBUTE with and without index, in one case it is not diacritical in the other it is.
ACI0093013 : OEM Application with Mobile Expansions can use unlimited mobile connexions
ACI0093030 : Action not dispay in "Action" column of Moving dialogue
ACI0093031 : Instability in menus management, in design mode
ACI0093063 : "Clear" button to clear menu background image does nothing
ACI0093069 : QUERY BY ATTRIBUTE doesn't work in indexed with array object
ACI0093072 : Service isn't relaunch after update 4D server v14  32bits with 4D server v15 32bits
ACI0093127 : checkbox/radio button labels don't print if platform is not "print" on windows 8.1 
ACI0093128 : [131546] Unnecessary word-wrap is performed on radio button/check box labels in printing 
ACI0093151 : Default button higher than 22 pixels bad display
ACI0093164 : PA_Tokenize() crashes 4Dv15
ACI0093170 : [131464]  MSC does not detect duplicate resources in the structure.
ACI0093201 : Event "on selection change" raises too much for 4D Write Pro object
ACI0093215 : 4D Server freezes under heavy load
ACI0093221 : Deadlock on web server
ACI0093250 : 4D Server freezes when sending messages to an unresponsive client
ACI0093257 : 4D Server stops accepting new connections
