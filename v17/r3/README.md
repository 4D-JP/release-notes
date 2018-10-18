4D v17 R3
---

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

---

* ACI0098769 オブジェクト型フィールドを``SET FIELD VALUE NULL``で``Null``に設定することができませんでした。

* ACI0098669 ``entity.clone()``でピクチャー型のフィールドがコピーされませんでした。

* ACI0098728 コレクション型のリストボックスで，カラムのデータソースにプライマリーキーではないフィールドにリンクしたリレーション属性を表示させた場合，最初の表示はできますが，ヘッダーをクリックして並び替えを試みると，アプリケーションがフリーズしました。間違ったリレーション属性が使用されているようです。

* ACI0098725 ``entity.lock()``でロックしたエンティティに対して再度``entity.lock()``を実行した場合，ローカルモードでは``{"success:true"}``が返されますが，リモートモードでは``{"success:false"}``が返されます。

* ACI0098555 クライアント/サーバー版のみ。ORDAで空の日付フィールドにアクセスした場合，``Null``が返されました。期待されるのは``00/00/00``が返されることです。

* ACI0098692 Mac版のみ。システムカラーパレットを使用して4D Write Pro文書のテキストカラーを変更し，他には何も変更しなかった場合，変更が保存されませんでした。フォントの色だけでなく，サイズやスタイルも変更すれば，変更が正しく保存されます。

* ACI0098673 Mac 32ビット版のみ。コードでビルドしたメニューバーをスタートアップでインストールした場合，アプリケーションモードに切り替わるタイミングでアプリケーションがクラッシュしました。

* ACI0098645 ``OBJECT Get style sheet``は，オブジェクトに設定されたスタイルシートではなく，スタイルシート0番を常に返しました。

* ACI0098642 ``IMPORT TEXT``コマンドでテキスト型のフィールドに値をインポートした場合，文字列の前後にあるスペース文字が切り捨てられました。

* ACI0098639 ``LOG FILE TO JSON``コマンドを実行すると，メモリーリークが発生しました。

* ACI0098626 リレートフィールドに対するインデックスORDAクエリを``IN``条件で実行した場合，結果が正しくありませんでした。``IN``条件を指定しなかった場合，あるいはインデックスを使用しなかった場合は問題ありません。

* ACI0098624 Write Pro文書のテーブル（表組み）レンジに対し，``wk font bold``のようなテキスト属性を設定した場合，``range.start``と``range.end``の間にある文字列だけに適用されました。テーブルレンジが指定されたのであれば，テーブル全体に対して属性が適用されるべきです。

* ACI0098599 ORDAクエリの照合文字列にシングルクオート記号が含まれている場合（例：``Levi's``），クライアント/サーバーモードでエラー``1806``「正しく整形されてないURLです」が返されました。シングルユーザーモードでは問題ありません。

* ACI0098580 Windows版のみ。連続してシーケンシャルクエリを実行した後，サーバーの管理画面やメニューの反応が悪くなりました。

* ACI0098579 コンパイルモードでピクチャに対する逆参照されたポインターに対して``Null``を代入することができませんでした。

* ACI0098569 フォームオブジェクトの『変数または式』に``TheString+":"``のようなフォーミュラが設定されている場合，`` OBJECT GET BEST SIZE``は評価されたテキストに基づいて正確な値を返しませんでした。``TheString``のような単純な変数であれば問題ありません。

* ACI0098568 背景色が透明に設定されているリストボックスの水平罫線を非表示に設定した場合，（透過プロパティによって無効化されている）リストボックスの背景色で水平罫線が描画されました。

* ACI0098567 エンティティセレクションに対して``count()``コレクションメソッドを使用すると，アプリケーションがクラッシュしました。確かにエンティティセレクションはオブジェクトであり，コレクションではありませんが，だとしても，クラッシュするのではなく，シンタックスエラーのダイアログを表示するべきです。

* ACI0098565 未定義のオブジェクト型プロパティなど，``undefined``をコンパイルモードでテキスト型に代入した場合，何も代入されませんでした。インタープリターモードのように，空の文字列が代入されるべきです。

* ACI0098564 クライアント/サーバー版のみ。無効なプライマリーキーをORDAの``dataClass.get()``に渡した場合，ローカルモードでは``null``が返されますが，クライアント/サーバーモードではエラー``1543``が返されます。

* ACI0098559 クライアント/サーバー版のみ。ORDAでWrite Proオブジェクトが保存されたフィールドにアクセスした場合，不完全なオブジェクトが返されました。シングルユーザー版では問題ありません。

* ACI0098558 Mac 64ビット版のみ。新規プロセスで開かれたウィンドウを``INVOKE ACTION``の標準アクションで閉じた場合，すぐにはウィンドウが閉じられませんでした。

* ACI0098547 クライアントサーバー版のみ。出力フォームにレコードを表示し，フォームをスクロールしたり，リサイズしたりするたびに，メモリーリークが発生しました。

* ACI0098538 クライアント/サーバー版のみ。``newEntity()``で作成したエンティティの属性は，すべて``Null``でした。タイプに応じたデフォルト値がセットされるべきです。

* ACI0098535 Write Proドキュメントの選択したフォントが極細・極太などのスタイルをサポートしている場合，『フォントスタイル』標準アクションをポップアップメニューに設定すると，選択した範囲に応じて正しいフォントスタイルが自動的に選択されませんでした。たとえば，フォントが14週類のスタイルをサポートしているとしても，し，標準・ボールド・イタリック・ボールドイタリックの4種類しかメニューにセットされませんでした。

* ACI0098530 サーバー管理画面の『新規接続を拒否・許可』ボタンをクリックして，新規クライアント接続を許可した後，サーバーが『利用可能なサーバー』リストに再表示されませんでした。また，サーバーを再起動するまで接続することができませんでした。

* ACI0098526 ORDAでNフィールドに相当するリレーション属性を更新しようとすると，指定した値ではなく，``Null``が代入されました。値を確認して，もう一度，同じ値を代入すれば，今度は成功します。あるいは，値を代入する代わりに，1レコードに相当するエンティティを代入すれば，問題を回避することができます。

* ACI0098522 標準アクションを使用してカレントレコードを移動すると，別ページに配置されたプラグインエリアに対してもレコードがロードされたというイベントが配信されました。カレントページのアクティブなエリアだけがイベントを受け取るべきです。

* ACI0098518 ``FORM LOAD``コマンドでメモリにロードした4D Write Proエリアに対して``OBJECT Get font``を使用した場合，アプリケーションがクラッシュしました。

* ACI0098515 4D Mobile/Wakanda 2.5.0のREST API経由で4Dのメソッドをコールした場合，空の戻り値が返されました。ビルド``223886``では問題ありません。ビルド``225801``の問題です。

* ACI0098511 クライアント/サーバー版のみ。コレクション型のリストボックスをダブルクリックし，切り替わった詳細フォームでレコードを編集して元のフォームに復帰した場合，更新された値がリストボックスに反映されませんでした。セレクション型のリストボックスでは問題ありません。

* ACI0098507 64ビット版のみ。サーバー側で``MSG_Charset``および``MSG_GetBody``を使用した場合，特定の組み合わせ（``1;1``, ``0;1``）でアプリケーションがクラッシュしました。``MSG_Charset``を使用しなければ問題ありません。

* ACI0098497 4D Serverのデータベース設定ダイアログに``2048 MB``以上のキャッシュサイズを入力して『適用』ボタンをクリックした場合，キャッシュサイズが正しく設定されませんでした。``SET CACHE SIZE``であれば問題ありません。

* ACI0098481 クライアント/サーバー版のみ。ORDAの``fromCollection()``に渡されたプライマリーキーが1フィールドに相当するデータクラスに存在しない場合，新規エンティティが作成され，そのプライマリーキーには``Null``が代入されました。この場合，新規エンティティは作成されるべきではありません。

* ACI0098480 ``QR RUN``コマンドでテキスト形式のクイックレポートを出力した場合，システム変数の``FldDelimit``および``RecDelimit``ではなく，既定の区切り文字（``Tab``および``Carriage return``/Windows版は``CR LF``）が使用されました。

* ACI0098476 4D Viewのセルに``=``記号を入力すると，マウス操作でセルを指定してフォーミュラを入力することができますが，Retinaディスプレイでは，正しい座標の範囲が選択されませんでした。

* ACI0098446 4D Write文書を4D Write Proに変換した後，そのレコードを開こうとすると，アプリケーションがクラッシュすることがありました。コマンドで変換するのではなく，4D Writeから4D Write Proにコピー＆ペーストすれば問題ありません。

* ACI0098443 リアルタイムモニターに時間がミリ秒単位で表示されませんでした。端数は切り捨てられ，値が1秒に満たない場合は何も表示されませんでした。

* ACI0098430 『デザインモードを検索』ダイアログの『タイプ』ポップアップメニューで『プラグインコマンド』を選択した後，『名前』を『等しい』から別の値に変更しようとすると，ダイアログが閉じられました。

* ACI0098409 Windows 10 1803のみ。Acrobat Reader DC・ Office 365・Kyoceraのプリンタードライバをインストールし，デフォルトプリンターに設定した後，オペレーションシステムを再起動して，Microsoft Wordに続けて4Dを起動して``FONT STYLE LIST``を実行すると，しばらく後にアプリケーションがクラッシュしました。

* ACI0098408 64ビット版のみ。ラベルエディターにピクチャーフィールドをドラッグ＆ドロップして追加した場合，初回の印刷プレビューでエラーが返されました。エディターを閉じて，同じ操作をもう一度繰り返した後，画像が表示されるようになります。

* ACI0098406 ``LISTBOX INSERT COLUMN``の実行速度がバージョン2004から16との比較でかなり落ちました（30倍）。フッターのオブジェクト名を明示的に指定すれば，問題が発生しません。

* ACI0098405 ``Open Window``あるいは``Open form window``で開いたウィンドウに表示された文字列を``MESSAGE``コマンドで更新することができませんでした。

* ACI0098401 リストボックス列の『自動行高』プロパティが有効にされている場合，``EDIT ITEM``や``OBJECT SET SCROLL POSITION``で目的の行まで正しくスクロールしませんでした。

* ACI0098400 Mac版のみ。ハイパーリンクが設定された文章をテキストエディットからコピー＆ペーストした場合，ハイパーリンクのURLとスタイルが継承されませんでした。

* ACI0098399 Mac 32ビット版のみ。大量（例：３時間で19万件）のSOAPリクエストを処理すると，サーバーがクラッシュすることがありました。ACI0097539とは別の問題です。管理画面を表示した状態で放置すれば，より短時間でアプリケーションがクラッシュします。

* ACI0098393 ``OB SET ARRAY``コマンドを4D Write Proオブジェクトに対して使用すると，アプリケーションがクラッシュすることがありました。

* ACI0098390 ``IMPORT TEXT``またはインポートダイアログを使用して実数またはFloat型フィールドにテキストデータを読み込んだ場合，スペース記号など，数字ではない文字がデータの前後に存在すると，``0``がインポートされました。整数・倍長整数・64ビット整数では問題ありません。

* ACI0098389 Word文書から4D Write Proにテキストをコピー＆ペーストした後，ウィジェットの『マージンとスタイル』タブをクリックすると，エラーが返されることがありました。

* ACI0098388 32ビット版のみ。旧バージョンでは問題なかった，サードパーティ社製のプラグインコマンドを使用すると，終了時にアプリケーションがクラッシュしました。

**注記**: 別スレッドからプラグインSDKをコールしてハンドルを作成していることが原因です。返されたエラーコードを無視して無効なハンドルを使用しているためにクラッシュしています。修正により，別スレッドでもプラグインSDKをコールしてハンドルを作成することができるようになりました。

* ACI0098386 日本語変換入力中に表示される下線の色がブラックに固定されていました。

* ACI0098384 配列型リストボックスの列に行の背景色配列が含まれている場合，``LISTBOX DELETE ROWS``コマンドで（最終行ではない）行を削除しようとすると，指定した行だけでなく，最終行も削除されました。

* ACI0098369 64ビット版のみ。``OCIAttrGetVal``に定数の``OCI_ATTR_IOMODE``を渡した場合，入出力パラメーターに対して``OCI_TYPEPARAM_INOUT (2)``ではなく``8``が返されました。

* ACI0098368 ``DELAY PROCESS``で遅延したプロセスを``PAUSE PROCESS``で停止した場合，1回の``RESUME PROCESS``では再開することができず，``RESUME PROCESS``または``DELAY PROCESS(...;0)``をもう一度コールする必要がありました。

* ACI0098363 デザインモードの『未使用のローカル変数を検索』メニューを実行した場合，コレクション型およびオブジェクト型の変数が検出されませんでした。

* ACI0098359 SSO（ドメインサーバー認証）とクライアント/サーバー通信の暗号化を両方とも有効にした場合，クライアントからサーバーに接続できませんでした。接続に失敗した後，サーバーに無名の接続中ユーザーが残されました。管理画面にユーザーが表示されるわけではなく，サーバーを終了しようとすると『接続中のユーザーがいます』というメッセージが表示されることにより，その存在と人数が確認できます。

* ACI0098356 4D Write文書をWrite Proに変換した場合，タブ処理が正しく変換されないことがありました。カスタマイズされたデフォルトのタプ位置や，リスト項目の絶対タブ位置のレンダリングが間違っていました。

* ACI0098348 クライアント/サーバー版のみ。外部ユーザー設定ファイルが有効にされたアプリケーションで，SQLのTLSを有効にした場合，ダイアログには新しい設定が正しく表示されますが，再起動後，SQLを実行すると，接続エラーが返されました。SQLのTLSモードは，ストラクチャ設定でなければ，有効にすることができませんでした。

* ACI0098343 Windows版のみ。添付ファイルの名前にウムラウトが含まれる場合，``MSG_Charset(1;1) ``設定の``MSG_Extract``で作成されるファイル名が正しくありませんでした。

* ACI0098331 別のインスタンスで開かれたデータベースを開こうとすると，『READ ONLYモードで開きますか』警告ダイアログが表示されますが，これをキャンセルすると，アプリケーションがクラッシュしました。

* ACI0098307 Windows 32ビット版のみ。実行中の印刷ジョブをキャンセルボタンで中止することができませんでした。

* ACI0098287 Windows 64ビット版のみ。メニューバーが関連付けられた標準ウィンドウからメニューバーが関連付けられていないモーダルダイアログを表示した場合，メニュー項目が``disabled``状態になります。そこまでは良いのですが，そこからさらにメニューバーが関連付けられていないモーダルダイアログを表示して閉じると，最初のモーダルダイアログが最前面にとどまらず，メニュー項目にアクセスできてしまいました。

* ACI0098277 環境設定でフォームエディターにデフォルトで表示されるバッジを変更した場合，エディターのツールバーに表示されるアイコンが選択されているバッジと合わないことがありました。たとえば『オブジェクトメソッド』のバッジが選択されているのに『標準アクション』のアイコンが表示されました。

* ACI0098261　``MODIFY SELECTION``で表示した出力フォームからダブルクリック操作で入力フォームに移行した場合，リストボックスのチェックボックスは（入力可であっても）入力不可であるかのように表示されました。

* ACI0098246 Mac 64ビット版およびWindows版のみ。ダイアログを表示中に``ADD RECORD``を実行し，切り替わった入力フォームでボタン（フォーカス可・タブ可）がフォーカスされた場合， ``GOTO OBJECT``を使用してテキスト入力エリアにフォーカスを移動しても，日本語入力メソッドがオフになったままでした。

* ACI0098213 Windows版のみ。``HTTP Get``コマンドで特定のURLにアクセスするとエラー#30（``HTTP Server unreachable``）が返されました。

* ACI0098208 文字列の位置を指定する添字``[[$index]]``を文字列定数に対して使用した場合，コンパイルでエラーが返されました。文字列定数の代わりに変数を使用すれば問題ありません。

* ACI0098179 64ビット版のみ。ファイルメニューの「データをファイルに書き出し」で表示されるダイアログは，自動リレーションに対応していませんでした。リレートテーブルを選択しても，マスターテーブルのフィールドが表示されました。

* ACI0098169 コレクション型のリストボックスにオブジェクト型フィールドの属性値を表示した場合，列ヘッダーをクリックすると，並び替えが実行される代わりにエラーが返されました。

* ACI0098163 セレクション型のリストボックスに『サブレコード追加』標準アクションでレコードを追加し，セルにタイプ入力したテキストが未確定の状態で再びレコード追加を実行すると，編集中だったセルの値が新規レコードのセルに引き継がれました。

* ACI0098117 ``IMAP_Search``でアプリケーションがクラッシュする場合がありました。ACI0096656修正の副作用です。リクエストが長すぎる場合，サーバーに拒否されることがあります。修正により，クラッシュする代わりに，エラーが返されるようになりました。

* ACI0098102 ``DIALOG``コマンドでWebエリアが配置されたフォームを別ウィンドウに表示した場合，そのフォームで``CANCEL``コマンドを使用すると，呼び出し元のダイアログが閉じられました。フォームメソッドでWebエリアのURL変数にアドレスを代入すれば問題ありません。また，別ウィンドウのダイアログを表示する直前にブレークポイントを挿入すれば，問題は再現しません。

* ACI0098097 4D Viewプラグインエリアのセルに対してコピー・カット操作あるいは``PV SPECIAL CUT``コマンドを実行すると，特定のセルでアプリケーションがクラッシュしました。スタイルシートをセルに対して設定した後，そのスタイルシートを削除した場合に問題が発生します。

* ACI0098054 共有コレクションに共有オブジェクトを追加し，``Use``/``End use``構文の中でその共有オブジェクトをロックした状態で``New process``を使用して起動したプロセスをデバッグしようとすると，デバッガウィンドウがフリーズしました。

* ACI0098035 Windows版のみ。リストボックスのプロパティで『行の移動』と『ドラッグ＆ドロップ』の両方が有効にされている場合，行の移動ができませんでした。

* ACI0097889 4D Writeプラグインで作成した文書（``4W7``）を4D Write Proで開いた場合，読み込みに時間がかかりました（``0.2``秒だったものが``0.4``秒に）。

* ACI0097842 オブジェクト記法と文字列の位置を指定する``[[``と``]``を併用した場合，コンパイルでエラーが返されました。

* ACI0097823 プリエンプティブモードで``RESOLVE POINTER``を実行すると，空の文字列が返されました。

* ACI0097596 Windows版のみ。Webエリアが表示されているフォームページから別にページに切り替えた場合，フォーム上のテキスト入力エリアに文字を入力することができませんでした。アプリケーションを最前面から外し，復帰した後であれば，再び入力ができるようになります。一部のWebページで問題が発生するようです。WebKit版のWebエリアでは問題が発生しません。

* ACI0097388 デザインモードの『未使用のローカル変数を検索』メニューを実行した場合，BLOB配列，オブジェクト配列，時間配列は検出されませんでした。

* ACI0097377 4D Viewに貼り付けられた画像をコンテキストメニューの『クリア』で消去し，入力を確定した後，同じレコードを開いてピクチャーの参照をダブルクリックし，ピクチャー属性の『縦横比を保持』を有効にすると，アプリケーションがクラッシュしました。

* ACI0090544 ``IMAP_Search``の第2パラメーターに空の文字列を渡すとアプリケーションがクラッシしました。

* ACI0098257 エンティティセレクションに対して``entitySelection.distinct()``を実行した場合，日付フィールドの値は文字列で返されました。

* ACI0098206 フォームスキーマ（``formsSchema.json``）にリスト項目のプロパティ（スタイル・アイコン・カラー・ダブルクリック・複数項目選択可）が存在しませんでした。

```json
"action": { // standard action name associated to the item
"type": "string"
},
"textDecoration": {
"enum": ["none", "underline"]
},
"fontWeight": {
"enum": ["normal", "bold"]
},
"fontStyle": {
"enum": ["normal", "italic"]
},
"stroke": { // text color
"$ref": "#/definitions/types/color"
},
"icon": { // path to the icon
"$ref": "#/definitions/types/picture"
}
```

* ACI0097769 サーバーの管理画面で新規接続を拒否に設定した場合，既存のクライアント接続が切断されました。

* ACI0097767 ``OBJECT DUPLICATE``でページ``0``に配置されたフォームオブジェクトを複製した場合，入力ができなくなりました。

* ACI0096700 アプリケーションを再起動した場合，フォームエディターのプロパティリストでヘルプTipsや入力フィルターのポップアップメニューが操作できなくなりました。

* ACI0096435 SQLで``JOIN``と``ORDER BY``を併用した場合，``DESC``を指定しても``ASC``で並び替えが実行されました。

```
ARRAY DATE($ad_Birth;0)

Begin SQL
SELECT P.Birth FROM Person P
JOIN Company C ON C.ID=P.Id_company
ORDER BY 1 DESC 
INTO :$ad_Birth;
End SQL
```

* ACI0090572 ``Components``フォルダーにインストールされたコンポーネントの公開メソッド名をメソッドエディターでなぞっても，ヘルプTipsが表示されませんでした。SVGコンポーネントなどのプリインストールされたコンポーネントでは問題ありません。

* ACI0098771 クライアント/サーバー版のみ。コレクション型のリストボックスのデータソースを``entity.RelatedTable``のように設定し，カラムのデータソースを``This.Field``に設定したリレート属性を表示させようとした場合，初回だけエラーが表示されました。

* ACI0098557 4D Write Proの表組みにピクチャーが表示されている場合，その表組みをコピーして別インスタンスの4D Write Proにペーストすると，表示が激しく崩れました。

* ACI0098734 クライアント/サーバー版で``entity.clone()``を実行した場合，フィールドの値が空でした。ローカルモードではコピー元のエンティティと同じ値が代入されています。プライマリーキーがUUIDの場合にだけ問題が発生します。 

* ACI0098814 SDIモードでクイックレポートエディターを使用した場合，印刷ダイアログが表示されませんでした。

* ACI0098531 17日以上前に起動したマシンで，プラグインSDKのイベント処理をすると，マウスダウンよおびマウスアップイベントの発生時間が正しく返されませんでした。キーダウンイベントは問題ありません。

* ACI0098517 4D for iOSのビルド＆実行メニューでエラーが返されることがありました。

* ACI0098464 ``CREATE THUMBNAIL``で作成したピクチャーをエンティティ属性に代入した場合，フィールドの値が空になりました。

* ACI0098463 ORDAクエリの検索条件に特定の文字列が含まれていた場合，アプリケーションがクラッシュしました。

```
$es:=ds.PEOPLE.query("Gender = True or Partner = NULL")
```

* ACI0098377 ヘッダーが表示されていないリストボックスに対して``LISTBOX SET PROPERTY(*;"Column1";lk column resizable;0)``を実行した場合，アプリケーションがクラッシュしました。

* ACI0098347 4D Write Proエリアで直前のテキストとは違うスタイルが設定された文字の直後にカーソルが置かれている場合，キーボードの左矢印キーでカーソルが２文字分移動しました。

* ACI0098342 ``WEB SET OPTION``でHTTPの圧縮モードで変更しても，サーバーに新しい設定が反映されませんでした。

* ACI0098333 コレクション型のリストボックスで``Tab``キーを入力して列を移動した場合，カレント項目およびカレント項目位置の式が更新されませんでした。

* ACI0098304 ``entitySelection.max()``で異なるデータ型が含まれるオブジェクト型フィールドを処理した場合，エラーが返されることがありました。

**注記**: 異なるデータ型の比較をする場合のプライオリティが見直されました。日付型が最高，ブール型が最低となります。

* ACI0098454 4D for iOSの専用URL``/mobileapp/``に無効なリクエストが送信された場合，アプリケーションがクラッシュしました。

* ACI0098419 環境設定ダイアログでメソッドのカラー設定ページには「初期設定」ボタンが表示されませんでした。

* ACI0098417 環境設定画面でカラーピッカーを表示した場合，ピッカーに表示されるデフォルトカラーは，設定されたカラーに関係なく，常にブラックでした。

* ACI0098378 ``WEB SET OPTION``でWebサーバーの設定を変更した後，別のアプリケーションを開いた場合，設定がリセットされませんでした。

* ACI0098719 ビルドされたアプリケーションを起動した環境に4Dフォルダーが存在しない場合，``4Dpeer.txt``ファイルが作成できない，というエラーが返されました。ビルドされたアプリケーションの場合，デフォルトの4Dフォルダーではなく，そのアプリケーションのカスタマイズされた設定フォルダーが使用されるべきです。