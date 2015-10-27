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
* ACI0088897 : [131734 ] The command "PV Get Picture"  causes 4D to crash if it throws an error.
* ACI0092449 4D Internet Commandは，UTF-8以外のエンコーディングで電子メールを送信することができませんでした。[SMTP_SetPrefs](http://doc.4d.com/4Dv14/4D-Internet-Commands/14/SMTP-SetPrefs.301-1237783.ja.html)や[SMTP_Charset](http://doc.4d.com/4Dv14/4D-Internet-Commands/14/SMTP-Charset.301-1237763.ja.html)は効力がありませんでした。
* ACI0092629 非常に古いバージョンから変換されたデータベースの場合，フォームウィザードで新規フォームを作成しようとすると，アプリケーションがクラッシュすることがありました。
* ACI0092788 : Issu with underline style in listbox
* ACI0093419 クライアント/サーバー版のみ。[エクスターナルデータベース](http://doc.4d.com/4Dv14/4D/14/USE-DATABASE.300-1198442.ja.html)から```SQL_INTERNAL```にスイッチした後，トランザクション内で実行されたSQLが失敗しました。トランザクションを開始しなければ問題ありません。
* ACI0093480 : Can not restart in compiled or in interpreted for C/S databases running with new network layer.
* ACI0093593 : [131792] Modifier key missing from pop-up menu
* ACI0093608 スプリッターを右クリックすると，以降，動かすことができなくなりました。
* ACI0093633 Windows版のみ。モーダルダイアログからアラートを表示した場合，アラートを閉じた後にオブジェクトのフォーカスが失われました。つまり，タブキーでフォーカスを移動することができなくなりました。標準ウインドウであれば問題ありません。
* ACI0093648 変換された[サブテーブル](http://doc.4d.com/4Dv14/4D/14.4/Subrecords.201-2510849.ja.html)を参照するとクエリエディターでエラーが発生しました。

Fixed bugs v15.0 build 190774 (Released on 2015-09-23)
--------------------------------------------------------------------------------
* ACI0088808 [SQL LOGIN](http://doc.4d.com/4Dv14/4D/14.4/SQL-LOGIN.301-2511762.ja.html)は接続が失敗してもシステム変数```OK```に```1```が代入されました。
* ACI0093075 [SVG SET ATTRIBUTE ](http://doc.4d.com/4Dv14/4D/14.4/SVG-SET-ATTRIBUTE.301-2512238.ja.html)に対してピクチャ変数をポインター経由で渡した場合，メモリーリークが発生しました。

Fixed bugs v15.0 build 190695 (Released on 2015-09-21)
--------------------------------------------------------------------------------
* ACI0078353 配列型リストボックスのセルが編集中のとき，[FORM GET OBJECTS](http://doc.4d.com/4Dv14/4D/14.4/FORM-GET-OBJECTS.301-2511080.ja.html)を使用すると，変数ポインターの配列に誤った値が返されました。つまり，リストボックス本体の配列ではなく，編集されている列の配列に対するポインターが返されました。
* ACI0090464 Mac版のみ。ポルトガル語版の4D Viewまたは4D Writeプラグインのメニューが正しくローカライズされていませんでした。"en"ローカライズが存在する場合，"pt-BR"はOSに認識されないようです。修正により，XLIFFファイルの言語識別子は"pt"に変更されました。Appleのドキュメントには，ポルトガル（ブラジル）語を"pt"，ポルトガル（ポルトガル）語を"pt-PT"で指定する，という記述があります。
* ACI0093032 Mac版のみ。リストボックスは，改行コードで区切られた2文字単語の表示が不自然でした。

**正**

```
ab
ab
```

**誤**

```
a...
b
```
* ACI0093368 : IMAP_GetMessage command returns error code on Mac 64 bits.
* ACI0093389 : [131836] Dialog on Quit Merged.
* ACI0093533 おおきなストラクチャで[EXPORT DATA](http://doc.4d.com/4Dv14/4D/14.4/EXPORT-DATA.301-2511133.ja.html)を繰り返し使用した場合，かなりのメモリーリークが発生しました。テーブルが指定されておらず，またエクスポート設定が再利用されない場合に問題が発生します。

```
//Method1
$ref:=""
EXPORT DATA("";$ref;*)

C_LONGINT($i) 
For ($i;1;100) 
  EXECUTE METHOD("Method1")
End for 
```

* ACI0093621 : [131834][Build App v15] xliff not resolved (was: crash at startup.

Fixed bugs v15.0 build 190555 (Released on 2015-09-18)
--------------------------------------------------------------------------------
* ACI0093191 『重複不可』属性が設定されたフィールドのデータに重複する値が保存されていた場合，MSCの標準データ修復を実行すると，該当するフィールドの『重複不可』属性が外されました。そのため，圧縮後の運用で重複チェックが実施されないようになりました。『レコードの強制更新』や『アドレステーブル圧縮』が適用されたデータ圧縮の場合，新しいインデックスは圧縮後の再起動時に作成されるため，重複不可違反の警告は特に表示されません。対照的に，標準の圧縮では既存のインデックスが圧縮されるだけなので，重複不可違反は再作成されたインデックスにも継承されることになり，そのために，重複不可チェックが実施されていました。修正により，重複不可チェックは，データベース起動後のインデックス再構築時にだけ実施され，MSCの標準データ修復では実行されないようになりました。

**注記**: データベース起動時後のインデックス再構築は，下記の場合に実行されます。

1. ストラクチャでインデックスが定義されているのにインデックスが存在しない
1. インデックスは存在するが別のアルゴリズム（異なるICUのバージョンまたはフラグ設定）で作成された

将来のバージョンでは，データベース起動後のインデックス再構築時に検出されたフィールド名および違反の内容が詳細にレポートされるようになる予定です。レコード更新時やインポート時にも詳細な違反情報が表示されるようになります。今回の修正　は，『重複不可』属性が不意に解除される問題に関するものです。

Fixed bugs v15.0 build 190539 (Released on 2015-09-17)
--------------------------------------------------------------------------------
* ACI0091977 [SET TABLE TITLES](http://doc.4d.com/4Dv14/4D/14.4/SET-TABLE-TITLES.301-2512001.ja.html)は，ユーザー/デザインモードの『書き出し』ダイアログにも作用しました。このコマンドは，アプリケーションモードだけに適用されるはずです。修正により，ユーザー/デザインモードの『書き出し』ダイアログはテーブルの実名を使用するようになりました。
* ACI0092751 : [Query Editor]Popup menu is too small on Windows
* ACI0093352 エクスターナルデータベースに[CREATE TABLE](http://doc.4d.com/4Dv14/4D/14/CREATE-TABLE.300-1198460.ja.html)でテーブルを作成した後，すぐに[USE DATABASE DATAFILE](http://doc.4d.com/4Dv14/4D/14/USE-DATABASE.300-1198442.ja.html)で参照し，[INSERT](http://doc.4d.com/4Dv14/4D/14/INSERT.300-1198463.ja.html)を実行しようとすると，エラーが返されました。作成したテーブルにアクセスするためには，データベースを再起動することが必要でした。

**注記**: 実際には，ローカルデータベースでも同じ問題が発生します。作成直後のINSERTコマンドで『インデックスが無効または未設定です』エラーが返されました。

```
Begin SQL
  CREATE TABLE IF NOT EXISTS T2
  (ID INT32 AUTO_INCREMENT, 
  name TEXT,
  PRIMARY KEY (ID));
End SQL

TRACE

Begin SQL
  INSERT INTO T2 (name) VALUES ('Henry');
End SQL
```
* ACI0093546 : Option "do not create log" is ignored in compact date file command
* ACI0093630 : String( -0.99999999999999534) produces "1" instead of "-1"

Fixed bugs v15.0 build 190428 (Released on 2015-09-16)
--------------------------------------------------------------------------------
* ACI0088819 エクスプローラーの『ホーム』タブで，メソッドを複製した場合，新しいメソッドは同じフォルダー内に作成されますが，フォームを複製した場合，新しいフォームはトップレベルに作成されました。

Fixed bugs v15.0 build 190414 (Released on 2015-09-15)
--------------------------------------------------------------------------------
* ACI0085614 : Internet Commands work wrong with relative path
* ACI0087196 Mac版のみ。[PICTURE PROPERTIES](http://doc.4d.com/4Dv14/4D/14.4/PICTURE-PROPERTIES.301-2511415.ja.html)に壊れたピクチャ（例: 高さと幅がゼロ）が渡された場合，アプリケーションがフリーズしました。
* ACI0091224 : Transfer Time in web log shows confusing values
* ACI0093442 : 4D Documentation Links

Fixed bugs v15.0 build 190312 (Released on 2015-09-11)
--------------------------------------------------------------------------------
* ACI0093121 日本語版のみ。フォームエディターの『オブジェクト』メニューの『縦中央揃え』と『横中央揃え』が逆でした。またコンテキストメニューの『縦均等配置』とあるべきところが『整列...』となっていました。
* ACI0093462 クイックレポートから4D Viewの出力に問題がありました。レコードの数が正しくありませんでした。HTML出力は問題ありません。
* ACI0093586 フォームエディター上でリストボックスのヘッダーをドラッグすると表示しきれていなかった列がスクロールするはずですが，v13以降，スクロールはせずに列だけが移動しました。

Fixed bugs v15.0 build 190179 (Released on 2015-09-10)
--------------------------------------------------------------------------------
* ACI0088594 エクスプローラーでフォームの名前を編集中，入力を確定せずにトリプルクリックすると，フォーム名が元に戻ってしまいました。

Fixed bugs v15.0 build 190137 (Released on 2015-09-09)
--------------------------------------------------------------------------------
* ACI0089641 : [130456] Breakpoint in a "On display detail" list form event freezes.
* ACI0092734 : Resizing width of listbox array
* ACI0092779 リストボックスのブール型カラム（チェックボックス）ラベルをXLIFFまたはリソースで定義することができませんでした。
* ACI0092792 : Style of units button or lllipsis is modify when enter in edit mode.
* ACI0092980 Mac版のみ。階層リストのスクロール速度が遅すぎました。
* ACI0093008 リスト型サブフォームが画面に表示できる行数またはそれよりも後の位置にレコードを追加した場合，サブフォームに表示されていたレコードの値が画面から消えました。
* ACI0093336 リストボックスのロックされたカラムを移動すると，ロックされていないカラムの水平スクロールが逆方向に動きました。
* ACI0093339 : Listbox footer ignores font colour settings
* ACI0093594 : Spelling error in french on information pop-up.

Fixed bugs v15.0 build 190021 (Released on 2015-09-08)
--------------------------------------------------------------------------------
* ACI0092137 : Export data editor - double click adds field twice
* ACI0092560 4D RemoteのWebサーバーで『[一時的なコンテキストを再利用する](http://doc.4d.com/4Dv15/4D/15/Web-Server-Settings.300-2006441.ja.html)』オプションが有効にされている場合，pendingステータスのAJAXリクエストで4D Remoteがクラッシュすることがありました。
* ACI0093044 : Missing plugins icon in the explorer
* ACI0093396 : [131690] Listbox, Data Source Undefined leads the crash of 4D
* ACI0093415 自動セッション管理が有効にされている場合，最後に返されたHTTPステータスコードが500（内部サーバーエラー）だったときは，次のリクエストでOn Web Connectionが実行されず，404が返されました。
* ACI0093459 : No SVG created if only a part of styled text is styled by context menu
* ACI0093546 : Option "do not create log" is ignored in compact date file command
* ACI0093580 Windows版のみ。チェコ語版のインストーラーを実行すると，エラーは発生しました。

Fixed bugs v15.0 build 189972 (Released on 2015-09-05)
--------------------------------------------------------------------------------
* ACI0093297 コンパイラー画面で『変数定義を生成』した場合，リストボックスのヘッダー変数がCompiler_Variablesに追加されませんでした。
* ACI0093459 : No SVG created if only a part of styled text is styled by context menu
* ACI0093504 ラジオボタンやチェックボックスを右クリックした場合，値は変わらないはずですが，通常のクリックと同じように値がトグルされました。

Fixed bugs v15.0 build 189937 (Released on 2015-09-04)
--------------------------------------------------------------------------------
* ACI0087170 AUTO_GENERATE属性が設定されているプライマリーキーではないフィールドは，既存のレコードであっても，```NULL```の代わりに新しい値が自動的に発行されてしまうため，[QUERY](http://doc.4d.com/4Dv14/4D/14.4/QUERY.301-2511498.ja.html)やSELECTで```NULL```を検索できませんでした。
* ACI0090953 巨大なトランザクション（1000万件のレコードを作成）を実行すると，-9999エラー（ディスクに空きスペースがない）が返されてしまい，処理を完了することができませんでした。キャッシュサイズが少なめに設定されているため，一時フォルダーにはxxxxx.transファイルが作成され，サイズがおおきくなりますが，ディスクサイズにはまだまだ余裕があります。トランザクションがキャッシュだけで完結すれば問題ありません。トランザクション中に作成されるテンポラリファイルの問題です。
* ACI0091497 [CHANGE CURRENT USER](http://doc.4d.com/4Dv14/4D/14.4/CHANGE-CURRENT-USER.301-2512039.ja.html)をOn Startupで実行すると，4D Write/4D Viewプラグインライセンスを占有しました。
* ACI0092116 スクロールバー・矢印キー・ クリックなどの操作に対する4D Viewの反応が以前のバージョンと比較して遅くなりました。
* ACI0093072 : Service isn't relaunch after update 4D server v14  32bits with 4D server v15 32bits
* ACI0093073 : Update 4D server 64 bits doesn't work in service
* ACI0093467 : QR Execute Command can return error No 9852 in 4D v15

Fixed bugs v15.0 build 189829 (Released on 2015-09-03)
--------------------------------------------------------------------------------
* ACI0081921 Mac版のみ。Webエリアが表示されているページに移動すると同時に[WA OPEN URL](http://doc.4d.com/4Dv14/4D/14.4/WA-OPEN-URL.301-2512246.ja.html)でページを読み込んだ場合，Webエリアの垂直スクロールバーが効きませんでした。
* ACI0093196 : In a built Client/Server application the Server is not being populated with a version number
* ACI0093073 : Update 4D server 64 bits doesn't work in service

Fixed bugs v15.0 build 189717 (Released on 2015-09-01)
--------------------------------------------------------------------------------
* ACI0075500 並び替えが定義されているクイックレポートを実行した場合，直後の[ORDER BY](http://doc.4d.com/4Dv14/4D/14.4/ORDER-BY.301-2511496.ja.html)が効きませんでした。
* ACI0076615 削除されたフィールドを含むクイックレポートは開くことができませんでした。
* ACI0082378 リストボックスのヘッダをドラッグすることにより，表示されていないカラムを引き出すことができませんでした。
* ACI0087268 : [128955] Freeze of 4D with incorrect formula in the Quick Report
* ACI0092786 リストフォーム上でポップアップドラップダウンリストを表示した場合，リストの項目をキーボード入力で選択することができませんでした。
* ACI0092994 Windows版のみ。ポップアップドラップダウンリストをクリックしたとき，カレント項目が選択された状態で表示されませんでした。14.2では問題ありませんでした。
* ACI0093044 : Missing plugins icon in the explorer
* ACI0093281 : Crash after drag & drop of a picture in a form on Design mode
* ACI0093470 : Explorer Menu not working
* ACI0093510 : MSC - Verify structure crash in Volume Desktop

Fixed bugs v15.0 build 189616 (Released on 2015-08-28)
--------------------------------------------------------------------------------
* ACI0068730 SQL関数の[MONTH](http://doc.4d.com/4Dv14/4D/14/MONTH.300-1198486.ja.html)と[YEAR](http://doc.4d.com/4Dv14/4D/14/YEAR.300-1198483.ja.html)を月の1日に対して使用した場合，コンピューターのシステム時間帯によっては，前月の値が返されました。
* ACI0084755 : "Current method path" does no more return object path Compiled
* ACI0090862 SQLで[CREATE TABLE](http://doc.4d.com/4Dv14/4D/14/CREATE-TABLE.300-1198460.ja.html)の直後に[_USER_COLUMNS](http://doc.4d.com/4Dv14/4D/14/System-Tables.300-1352230.ja.html)を[SELECT](http://doc.4d.com/4Dv14/4D/14/SELECT.300-1198464.ja.html)した場合，作成したばかりのテーブルに関する情報が返されませんでした。
* ACI0090925 : SQL Month and Year functions can return incorrect results
* ACI0092691 : Connection is broken when using new network layer with On Server Close Connection
* ACI0092692 : [Servernet] On Server Close Connection reports network error
* ACI0093361 Windows版のみ。かな入力（ローマ字ではない）モードが使用されており，クリップボードが空の場合，編集ショートカット（Control+X, C, V, etc.）を入力すると半角カナの ｻ, ｿ, ﾋといった文字が入力されました。

Fixed bugs v15.0 build 189460 (Released on 2015-08-26)
--------------------------------------------------------------------------------
* ACI0093237 : [131602] BASIC web authentication takes 15 seconds using Safari or FireFox

Fixed bugs v15.0 build 189423 (Released on 2015-08-25)
--------------------------------------------------------------------------------
* ACI0093225 特定の条件で[QUERY SELECTION](http://doc.4d.com/4Dv14/4D/14.4/QUERY-SELECTION.301-2511501.ja.html)を実行すると，キャッシュにパージできないオブジェクトが残ってしまい，次第にキャッシュが断片化して，データベースが遅くなったり，不可解なシンタックスエラーが発生するようになりました。たとえば，20,000件のテーブルでカレントセレクションが50件，130,000件のテーブルでカレントセレクションが600件，といった比率で問題は発生します。

Fixed bugs v15.0 build 189396 (Released on 2015-08-22)
--------------------------------------------------------------------------------
* ACI0092892 [HTTP Get](http://doc.4d.com/4Dv14/4D/14.4/HTTP-Get.301-2510926.ja.html)を[Digest認証](http://doc.4d.com/4Dv14/4D/14.4/HTTP-AUTHENTICATE.301-2510927.ja.html)で実行した場合，不正なopaqueヘッダー（閉じる二重引用符がない）が送信されました。

Fixed bugs v15.0 build 189364 (Released on 2015-08-21)
--------------------------------------------------------------------------------
* ACI0091083 ロックされたカラムのあるリストボックスに[LISTBOX SET LOCKED COLUMNS](http://doc.4d.com/4Dv14/4D/14.4/LISTBOX-SET-LOCKED-COLUMNS.301-2511191.ja.html)に負のカラム番号を渡すと，ロックされたカラムがなくなり，カラムを動かすとアプリケーションがクラッシュしました。
* ACI0093359 : Dereferenced field pointer from method fails  

Fixed bugs v15.0 build 189325 (Released on 2015-08-20)
--------------------------------------------------------------------------------
* ACI0089383 : The expiration date of the license is always 00.00.0000 in the MCS Information window.
* ACI0092583 レコードとインデックスを圧縮した後，データファイルが破損（圧縮前の検査ではレポートされなかったエラーが発生）するケースがありました。
* ACI0093245 : [131609] MSC crashes while repairing structure

Fixed bugs v15.0 build 189261 (Released on 2015-08-19)
--------------------------------------------------------------------------------
* ACI0093195 : 4D Mac 64-bits Memory leak with SQL statement

Fixed bugs v15.0 build 189224 (Released on 2015-08-18)
--------------------------------------------------------------------------------
* ACI0092533 : [131302] Http SET OPTION on setting HTTP timeout does not change
* ACI0093137 : [131560] [v15 regression] Constants with umlauts cannot be compiled
* ACI0093138 : Custom Constants, Method Editor: 'resname xxxx not found'
* ACI0093288 一部のSVG画像要素（matrix scalingがゼロかつshearがゼロではない）はピクチャエリアに表示されませんでした。Webエリアでは問題ありません。

Fixed bugs v15.0 build 189179 (Released on 2015-08-15)
--------------------------------------------------------------------------------
* ACI0092803 カレントレコードを変更した後，入力エリアの取り消し（Control+Z）履歴がクリアされませんでした。
* ACI0093076 : Text Fields in Quick Reports Are Cut Off
* ACI0093129 [XML GET ERROR](http://doc.4d.com/4Dv14/4D/14.4/XML-GET-ERROR.301-2512184.ja.html)に不正な引数を渡してもOKシステム変数に0が代入されませんでした。
* ACI0093248 スタイル付きテキスト全体の文字カラーを黒ではない値に変更した場合，[ST GET ATTRIBUTES](http://doc.4d.com/4Dv14/4D/14.4/ST-GET-ATTRIBUTES.301-2510888.ja.html)から0が返されました。テキストの一部だけを変更した場合は問題ありません。

Fixed bugs v15.0 build 188995 (Released on 2015-08-11)
--------------------------------------------------------------------------------
* ACI0093042 : Malfunction in the menu editor
* ACI0093093 [ADD RECORD](http://doc.4d.com/4Dv14/4D/14.4/ADD-RECORD.301-2512225.ja.html)または[MODIFY RECORD](http://doc.4d.com/4Dv14/4D/14.4/MODIFY-RECORD.301-2512226.ja.html)でパレットウインドウを表示した場合，閉じるボタンが動作しませんでした。
* ACI0093130 [SVG_SET_SHAPE_RENDERING](http://doc.4d.com/4Dv14/4D/14/SVG-SET-SHAPE-RENDERING.301-1382636.ja.html)に```optimizeSpeed```を渡すとエラーが返されました。
* ACI0093341 : 4DIC Mac64 failures

Fixed bugs v15.0 build 188938 (Released on 2015-08-08)
--------------------------------------------------------------------------------
* ACI0081512 ラベルエディターでオブジェクトを水平に連結した場合，フィールド間に空白が自動的に挿入されるはずですが，そうはなりませんでした。
* ACI0093318 : Memory leak for new cooperative processes with a window

Fixed bugs v15.0 build 188914 (Released on 2015-08-07)
--------------------------------------------------------------------------------
* ACI0090169 オブジェクト型のローカル変数を別プロセスに引数で渡した場合，相手プロセス側でその変数を更新すると，呼び出し側のローカル変数も更新されました。オブジェクト型は参照型なので，代入されたローカル変数が同じオブジェクトを参照するのは正常ですが，プロセスを超えてローカル変数が同じオブジェクトを参照するのは間違いでした。

例:

```
C_OBJECT($1)
C_OBJECT($object)
C_LONGINT($psn)

Case of 
: (Count parameters=0)
TRACE
$object:=JSON Parse("{}")
If (OB Is defined($object))
$psn:=New process(Current method name;0;Current method name;$object)
End if 

TRACE

: (Count parameters=1)

TRACE
$object:=$1

OB set($1;"test";"coucou")
  // 呼び出し元の$objectに注目。（本プロセスの$objectが更新されるのは正常）
TRACE

End case 
```

Fixed bugs v15.0 build 188707 (Released on 2015-08-04)
--------------------------------------------------------------------------------
* ACI0074490 クイックレポートで[Sum](http://doc.4d.com/4Dv14/4D/14.4/Sum.301-2510947.ja.html)を使用すると，アプリケーションがクラッシュしました。内部的に64ビット整数が返される関数のコールバックに問題ありました。
* ACI0083311 アクセント記号が含まれる 4D Write文書をHTML4形式でエクスポートした場合，拡張文字が正しく出力されませんでした。修正により，UTF-8エンコーデイングと16進数のエンティティ参照（&#x...;）がサポートされるようになりました。
* ACI0089701 v14.2以降，[Menu selected](http://doc.4d.com/4Dv14/4D/14.4/Menu-selected.301-2511250.ja.html)から返されるメニュー番号違いました（フォームに関連付けられたメニュー）。また，その番号を[APPEND MENU ITEM](http://doc.4d.com/4Dv14/4D/14.4/APPEND-MENU-ITEM.301-2511241.ja.html)や[Get menu title](http://doc.4d.com/4Dv14/4D/14.4/Get-menu-title.301-2511262.ja.html)に渡しても駄目で，以前のバージョンで返された番号を渡さなければなりませんでした。
* ACI0089966 [PLATFORM PROPERTIES](http://doc.4d.com/4Dv14/4D/14.4/PLATFORM-PROPERTIES.301-2511885.ja.html)でWindows 8.1を検出することができませんでした。
* ACI0091274 フォームの2個の4D Writeエリアが表示されているとき，日本語変換の編集ウインドウが間違った場所に表示されることがありました。あるいは，間違ったほうのエリアに確定されたテキストが入力されました。
* ACI0091299 4D Viewのセルにテンキー側のピリオドキーを入力した場合，言語設定に従った小数点（ピリオドまたはカンマ）が入力されず，入力フィルターも正しく働きませんでした。
* ACI0091504 Mac版のみ。アプリケーションビルドの```ClientWinIncludeIt```キーが有効で```ClientWinFolderToMac```のパスが無効な場合，アプリケーションビルドでエラー（Windows用の4D Volume Desktopがみつからない）が返されました。
* ACI0091505 日本語入力中の『取り消し』（Control+Z）と『やり直し』（Control+Shift+Z）の振る舞いが一般的なアプリケーションとは違い，変換中に表示された候補がすべて履歴に残りました。
* ACI0091590 [ERASE WINDOW](http://doc.4d.com/4Dv14/4D/14.4/ERASE-WINDOW.301-2512108.ja.html)を実行すると，ウインドウの背景カラーがグレーになることがありました。
* ACI0091608 : [130913] 4D crashes when opening HTML file with 4D Write
* ACI0091772 Windows版のみ。[Open form window](http://doc.4d.com/4Dv14/4D/14.4/Open-form-window.301-2512114.ja.html)で表示したウインドウを最大化してから閉じることを繰り返した場合，ウインドウ位置が少しずつ右下に移動してゆきました。
* ACI0091904 [Print object](http://doc.4d.com/4Dv14/4D/14.4/Print-object.301-2511458.ja.html)あるいは印刷メニューでリストボックスをプリントアウトした場合，チェックボックスまたはドロップダウンリストのあるセルには何も印刷されませんでした。
* ACI0091906 : Print listbox elipsis button and unit button are not print
* ACI0091907 : Create and replacing a database
* ACI0091920 : Since R5, it is impossible to select a size-zero object in the Form Editor
* ACI0091942 リストボックスの行を上または下にドラッグしても，自動的に垂直スクロールが働きませんでした。v15は，『ドロップ可』およびOn Dropイベントプロパティが有効にされていれば，スクロールが発生しました。
* ACI0092047 : [131090] Variable is unenterable if web area on the same form (with PDF or website loaded)
* ACI0092071 : [131101] Cursor in 4D Write disappears
* ACI0092251  Mac版のみ。日本語入力の『英字』モードが選択されている場合，CommandやControlなどのモディファイアの無いキーボードショートカットが効きませんでした。U.S.などの直接入力モードであれば，問題ありません。
* ACI0092402 アプリケーションビルドで『クライアント/サーバーアプリケーションをビルド』の『クライアントアプリケーションをビルド』をチェックせずに『MacOS/Windowsクライアントアプリケーションの自動更新を有効にする』をチェックしてビルドを進めた場合，エラーが返されたり，クラッシュしたりしました。
* ACI0092446 『レコードを完全に削除』が有効にされていないテーブルのデータが含まれるデータファイルに対して『レコードヘッダーによる修復』を実行した場合，修復後にMSCのデータファイル検査でエラーがレポートされるようになりました。
* ACI0092460 『データファイルが更新された場合のみバックアップを行う』の動作に問題がありました。データファイルが更新されていない場合にバックアップが実行されないのは良いのですが，その後，新規レコードを追加した途端，スケジュールにないバックアップが開始されました。
* ACI0092515 4D ServerにAccessからODBCで接続した場合，WHERE句にANDまたはOR述語が含まれていると，エラーが返されました。

**注記**: 4D ODBC Driverが修正されました。

```
Dim ws As Workspace
Dim db As Database
Set ws = DBEngine.Workspaces(0)
Set db = ws.OpenDatabase("stxtst", False, True, "ODBC;")

//NG
Select shrs.SHR_ValidTo, shrs.SHR_ValidFrom, shrs.Numberofshares 
Into OldShares
From [ODBC;DSN=stxtst;].[Shares] as shrs 
Where ((shrs.Numberofshares>=1000000) AND (shrs.Numberofshares<=9000000))

//OK
Select shrs.SHR_ValidTo, shrs.SHR_ValidFrom, shrs.Numberofshares 
Into OldShares
From [ODBC;DSN=stxtst;].[Shares] as shrs 
Where (shrs.Numberofshares>=1000000)
```

* ACI0092564 データファイルの名前にピリオドが含まれている場合，バックアップファイル（4BK）に連番が付けられず，常に最新のバックアップで上書きされてしまいました。
* ACI0092631 : [131298] Edit action (cut, copy, paste, etc) does not work using Japanese KANA keyboard layout since v14
* ACI0092643 4D ServerにAccessからODBCで接続した場合，CDate（日付の文字列）を使用するとAccessがクラッシュしました。
* ACI0092651 : MSC restore displays "file select" dialog in wrong window type, user must force quit 4D.
* ACI0092679 SVGで『4State』バーコードフォントが使用できませんでした。
* ACI0092681 BLOB配列に対して[VARIABLE TO BLOB](http://doc.4d.com/4Dv14/4D/14.4/VARIABLE-TO-BLOB.301-2511977.ja.html)が使用できませんでした。
* ACI0092709 : SET EXTERNAL DATA PATH issue with relative path "../"
* ACI0092735 Mac版のみ。[READ ONLY](http://doc.4d.com/--14.4/-/READ-ONLY.301-2511556.ja.html)で表示されたフォーム上の数値フィールドは，編集ができるような印象を与えました。数字部分をクリックすれば問題ありませんが，空白部分をクリックすると，フィールドが編集できそうな表示になりました。
* ACI0092764 ストラクチャエディターのインスペクターでフィールド名を『あああ』から『ｱｱｱ』に変更した場合，つまり，文字種だけを変更した場合，書き換えが無視されました。
* ACI0092858 ツールボックスのリソースページで，ファイルを選択して『名称変更』を選択した場合，現在のファイル名が表示されませんでした。また，『ディスク上に表示する』を選択しても，何も起きませんでした。
* ACI0092859 Mac版のみ。PDF文書を[READ PICTURE FILE](http://doc.4d.com/4Dv14/4D/14.4/READ-PICTURE-FILE.301-2511425.ja.html)で読み込んで[TRANSFORM PICTURE](http://doc.4d.com/4Dv14/4D/14.4/TRANSFORM-PICTURE.301-2511407.ja.html)で左右を反転した場合，[WRITE PICTURE FILE](http://doc.4d.com/4Dv14/4D/14.4/WRITE-PICTURE-FILE.301-2511426.ja.html)で書き出すと空のPDFになりました。
* ACI0092871 Webサービスの出力タイプがXML型で，そのXMLが空（```<root/>```）だった場合，不正なSOAPエンベロープが生成されました。
* ACI0092914 ライセンス登録画面のメールアドレス入力欄で『.website』『.berlin』といったドメイン名は無効であるとして，退けられました。
* ACI0092922 : Closing a WebSession already used cause a DeadLock in 4D WebSession Manager
* ACI0092944 : Web variables not reinitialized on SOAP calls
* ACI0092954 : [131446] 4D Mobile OEM licenses are not copied during build process
* ACI0092956 [OBJECT SET TITLE](http://doc.4d.com/4Dv14/4D/14.4/OBJECT-SET-TITLE.301-2511364.ja.html)で[XLIFF](http://doc.4d.com/4Dv15/4D/15/Appendix-C-XLIFF-architecture.300-2045562.ja.html)の『オブジェクト名』シンタックスで設定された3Dボタンのラベルを変更することができませんでした。 
* ACI0092962 Mac版のみ。Yosemiteプラットフォームで非アクティブウインドウのデフォルトボタンは，グレーに表示されるべきですが，ブルーに表示されました。
* ACI0092966 : SVG_GET_ATTRIBUTES : tspan font-family, simple quote-> double quote
* ACI0092969 : An error is displayed when trying to reconnect to 4D server.
* ACI0092990 : QUERY BY ATTRIBUTE with null value as parameter does'nt return the same think in sequential or indexed
* ACI0092991 : Engined OEM Server : License or privilege error.
* ACI0093006 : QUERY BY ATTRIBUTE, bad results when using the operator # in Client/Server
* ACI0093010 : Difference in behavior on QUERY BY ATTRIBUTE with and without index, in one case it is not diacritical in the other it is.
* ACI0093013 : OEM Application with Mobile Expansions can use unlimited mobile connexions
* ACI0093030 : Action not dispay in "Action" column of Moving dialogue
* ACI0093031 デザインモードのツールボックスでメニューバーを削除した後，別のメニューバーを『テスト』すると，アプリケーションがクラッシュしました。また，メニューバーを追加し，ツールボックスのページを切り替えて戻った後，メニューバーを削除し，ツールボックスのページを切り替えて戻ると，メニューのリストが空になりました。
* ACI0093063 : "Clear" button to clear menu background image does nothing
* ACI0093069 : QUERY BY ATTRIBUTE doesn't work in indexed with array object
* ACI0093072 : Service isn't relaunch after update 4D server v14  32bits with 4D server v15 32bits
* ACI0093127 Windows版のみ。Windows 8.1プラットフォームでフォームまたはオブジェクトのプラットフォームプロパティが『印刷』ではない場合，ラジオボタンやチェックボックスのラベルがプリントアウトされませんでした。Windows 7では問題ありません。
* ACI0093128 Windows版のみ。ラジオボタンやチェックボックスをプリントアウトした場合，ラベルテキストで不要な折り返し（ワードラップ）が発生しました。
* ACI0093151 Mac版のみ。Yosemiteプラットフォームで高さが22ポイントに満たないデフォルトボタンの表示が正しくありませんでした。
* ACI0093164 : PA_Tokenize() crashes 4Dv15
* ACI0093170 重複不可のストラクチャリソースに何らかの理由で重複が存在した場合，MSCのアプリケーション検査でインデックスのエラーがレポートされました。修正により，ストラクチャリソースの重複がレポートされるようになりました。
* ACI0093201 : Event "on selection change" raises too much for 4D Write Pro object
* ACI0093215 : 4D Server freezes under heavy load
* ACI0093221 : Deadlock on web server
* ACI0093250 : 4D Server freezes when sending messages to an unresponsive client
* ACI0093257 : 4D Server stops accepting new connections
