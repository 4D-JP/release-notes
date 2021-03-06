4D v16 R6
---

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0097948 ``OBJECT DUPLICATE``でラジオボタンをグループ化することができませんでした。複製元のオブジェクトがすでにグループ化されている場合は問題ありません。

* ACI0097497 Windows版のみ。ビルドしたSDIモードのアプリケーションの場合，複数のインスタンスが同時に起動できてしまいました。MDIモードであれば問題ありません。デザインモードとは違い，ビルドしたアプリケーションは，二重に起動できないようになっているべきです。

* ACI0093293 Mac版のみ。メソッドエディターのツールバーに統合されている検索フィールドの履歴ボタンをクリックしても，過去の実行した検索のポップアップメニューが表示されませんでした。

* ACI0094424 メソッド名の30文字目が日本語だった場合，そのメソッドを複製すると同じ名前のメソッドが作成されました。

* ACI0095659 Mac版のみ。アプリケーション名にシングルクオート（アポストロフィ）記号が含まれている場合，``SET UPDATE FOLDER``および``RESTART 4D``による自動アップグレードが完了できませんでした。ログファイルを確認すると，更新されたアプリケーションの起動（``open -a``コマンド）に失敗していることがわかります。

* ACI0096996 管理画面を表示するためのキーボードショートカット（``Control``/``command``+``U``）が効きませんでした。

* ACI0097124 4D Server Windows 64ビット版のみ。新規データベースを作成すると，エラー``1010``が返されました。``MECAB.DLL``がインストールされていないためです。

* ACI0097129 Mac 64ビット版のみ。「終了」メニューのタイトルが日本語として不自然（「終了 4D」）でした。「4D を終了」と表示されるべきです。

* ACI0097246 Google日本語入力などのサードパーティ社製日本語入力メソッド（IME）がインストールされている環境で，特定のフィールドにフォーカスを移動すると，システム標準の日本語入力に切り替わりました。

* ACI0097247 Windows版のみ。日本語入力（IME）が有効な状態でダイアログを表示し，ボタンなどのオブジェクトがフォーカスを得ている状態でそのフォームを閉じた場合，日本語入力（IME）ができなくなりました。

* ACI0097262 テキストフィールドの保存オプションを「データファイルの外」に設定した場合，マルチバイト文字がテキストの259バイト目に出現すると，後続の文字列がレコード保存時に失われました。

* ACI0097341 クライアント側でユーザー認証ダイアログ（ログイン画面）をキャンセルすると，サーバー側のユーザーリストに無名の接続が残され，接続ライセンス数が消費されたままになりました。

* ACI0097352 Windows版のみ。ペーストボード内にSVGピクチャーがセットされている場合，終了時にアプリケーションがクラッシュしました。SVG以外の画像フォーマットであれば問題ありません。終了前にペーストボードをクリアすれば，クラッシュしません。

* ACI0097448 ``On After Edit``および``On Data Change``イベントが有効にされたフォームにコンボボックスが存在する場合，``On After Edit``イベントでコンボボックスの自由入力アイテム（0番要素）に新しい値を代入しても，確定時に``On Data Change``イベントが発生しませんでした。``On After Edit``イベントが併用されていなければ，つまり，通常のタイプ入力で更新したのであれば，コンボボックスの入力確定時に``On Data Change``イベントが発生します。

* ACI0097457 Mac版のみ。アプリケーション名にアポストロフィ記号が含まれている場合，クライアント自動アップグレードが成功しませんでした。

* ACI0097496 Mac 64ビット版のみ。日本語変換中に文字列を削除しようとした場合，確定された文字列と未確定の文字列の間で余計に``delete``キーを入力する必要がありました。

* ACI0097572 メソッドの途中にカーソル位置が存在する場合，キーストローク毎にカーソルの位置がずれてゆきました。

* ACI0097478 Windows版のみ。階層リストに「Yu Gothic/遊ゴシック」フォントのイタリック文字を表示した場合，文字列の一番右が少しだけ欠けて表示されました。

* ACI0097778 ``BASE64 ENCODE``から返される文字列は，``40,000``文字ごとに改行コード``CR`` ``LF``が挿入されました。

* ACI0097787 v15で作成したリストボックスをv16に変換した場合，フッター変数の「型」が正しくありませんでした。数値型に設定されていたものがテキスト型になりました。

**注記**: v15では「変数タイプ」メニューの末尾に表示された「なし」が，v16ではメニューの冒頭に表示されるようになったことが原因でした。そのため，変換されたストラクチャでは，ポップアップメニューの位置番号と保存されたプロパティ値のマッピングに食い違いが発生していました。この問題は，下記のように是正されています：

1. v15から変換されたフッターの「変数タイプ」には，実際のプロパティ値が表示されます。

1. 修正前のv16で作成されたフッターの「変数タイプ」メニューをクリックすると，実際のプロパティとは違う項目が選択された状態でリストが表示されます。したがって，本来の値を改めて選択しなければなりません。

1. フッターの水平揃えは，変数タイプに応じたものが適用され，変数も正しい型で初期化されます。修正前はそうではありませんでした。

---

* ACI0097784 フォーム入力の確定イベントで``REJECT``コマンドを実行しても，入力が拒否されませんでした。

* ACI0097693 ``APPEND TO ARRAY``に直接``OB Get``を渡した場合，シンタックスエラーが返されました。

**注記**: ``OB Get``の返り値を指定する定数が省略されたときの振る舞い改善されました。オブジェクト記法が有効にされている場合，``Null``または未定義のプロパティは空の文字列が返されます（互換モード）。オブジェクト記法が有効にされていない場合，``Null``または未定義のプロパティが変換されずにそのまま返されます。16 R5では，標準の``String`` ``Num`` ``Date`` ``Time``関数で未定義の値が変換できる点に留意してください。 

* ACI0097740 無効な``HTTP Request``をコールがステータスコード``200``を返しました。``0``が返されるべきです。

* ACI0097730 ``«wr_number :###.##0,00»``または``«wr_number :###,##0.00»``のようにフォーマットされた数値が含まれた4D Write文書が正しく4D Write Pro文書に変換することができませんでした。``String(wr_number ;"###.##0.00"``のように，ヨーロッパ式の小数点（カンマ）がピリオドに変換され，桁区切りと小数点が同じ記号になりました。

* ACI0096868 64ビット版のみ。ラベルエディターで設定ファイルを書き出した場合，システム変数``DOCUMENT``が更新されませんでした。

* ACI0097707 macOS High Sierraのみ。言語と地域の設定に複数の言語がリストアップされている場合，英語のシステム日付フォーマットが採用されました。英語がリストに含まれていなければ，問題ありません。

* ACI0096779 ローカルパスに拡張文字が含まれている場合，``FTP_Send``がエラー``-43``を返しました。Mac版では，ファイルが送信されません。Windows版では，転送が成功しますが，指定したファイル名がサーバー側で文字化けしました。

* ACI0097701 macOS 10.13 High Sierraのみ。メソッドのコードをコマンドまたはメニューを実行して書き出すと，一時ファイル（``{UUID}.temp``）がデスクトップに作成されました。新しいファイルシステム（APFS）特有の問題です。

* ACI0097641 表示されていないページのリストボックスに対して``LISTBOX SET COLUMN WIDTH``を使用することができませんでした。たとえば，``On Load``イベントやページ移動と同時に列の幅を設定することができませんでした。

* ACI0097658 新ネットワークレイヤーのみ。多数クライアントが同時に接続を開始し，ユーザー認証プロセスに負荷がかかった場合，サーバーの反応が待ちきれずにクライアントが認証の途中で接続を断念することがあります。そうなると，以降，新規のクライアント接続ができなくなってしまいました。

* ACI0097649 幅が``1``ポイントのタブコントロールがフォームに存在する場合，そのフォームを表示しようとするとアプリケーションがクラッシュしました。

* ACI0097642 特定のSQL文を実行すると，アプリケーションがクラッシュしました。

```sql
Begin SQL
SELECT R.[Code], R.[Intitule], R.[Couleur_Planning], R.[Externe], E.[Ordre_Affichage], F.[Ordre_Affichage]
FROM [Element_Liste_Ressource] E
INNER JOIN [Famille_Ressource] F
ON E.[Famille] = F.[Famille]
INNER JOIN [Materiel] R
ON F.[Code_Materiel] = R.[Code]
WHERE E.[Code_Liste] = 73
AND E.[Portee_Element] = 2
AND E.[Type_Ressource] = 2
AND R.[Abandonne] = false
AND R.[Hors_Planning] = false
AND R.[Code] NOT IN (
SELECT PR.[Code_Materiel]
FROM [Protection_Ressource] PR
WHERE PR.[Type_Ressource] = 2
AND PR.[Code_Groupe] = 3
AND PR.[Protection_Lecture] = TRUE )
AND R.[Societe] IN ('Eclair Cinéma', 'Eclair Group', '', 'Eclair MEDIA')
End SQL
```

* ACI0097635 macOS 10.13 High Sierraのみ。``Get file from pasteboard``コマンドの実行に長い時間（1分ほど）を要しました。``Pasteboard data size``でも同じ問題が発生します。

* ACI0097630 「4D Serverに接続」ダイアログの「カスタム」ページに情報を入力してから，「利用可」ページに移動し，「カスタム」ページに戻ると，入力した情報がクリアされました。

* ACI0097623 ブール型フィールドの表示フォーマットを``STR#``リソース（例：``:16001,1``）で設定している場合，ラジオボタンではなくチェックボックスが表示され，フォーマット定義が（例：``jpg;png``）そのままボタンタイトルとして表示されました。

* ACI0097621 64ビット版のみ。ビルドしたサーバーアプリケーションの「データベース設定」メニューでは，ユーザー設定とストラクチャ設定を切り替えるための階層メニュー項目が表示されませんでした。ストラクチャファイルとデータファイルが同じフォルダー内になければ問題ありません。

* ACI0097613 アプリケーションを再起動したり，デザインモードとアプリケーションモードを切り替えたりすると，「レコード > 最後に使用したテーブル」の並び順が変わりました。

* ACI0097564 バックアップ実行中に内部ランタイムエラー``22``（無効な引数）が返されることがありました。内部エラーが検出されたとしても，ダイアログを表示するべきではありません。

* ACI0097537 ホストよりも新しいバージョンの4Dでコンパイルされたコンポーネントメソッドを実行すると，アプリケーションが終了することがありました。

* ACI0097521 macOS 10.13 High Sierraのみ。リストボックスのセルにマウスポインターを重ねると，ポップアップメニューが関連づけられていることを示す矢印アイコンが消えました。

* ACI0097520 フィールドのSQLエイリアスが別テーブルの名前と同じ場合，メソッドエディターのコード補完でアプリケーションがクラッシュしました。

* ACI0097519 Mac版のみ。``SVG Find element ID by coordinates``コマンドで塗りつぶし（``fill``）色が黒（``black``）のオブジェクトを検出することができませんでした。

* ACI0097508 環境設定ダイアログの「メソッド」ページで，「カラー」設定タブから「スタイル」または「オプション」設定タブに切り替えてから「カラー」の戻ると，一番下のチェックボックス2個が表示されませんでした。

* ACI0097495 メソッドエディターの階層を展開・収縮するノードアイコンを非表示に設定した場合，アイコンにマウスポインターを重ねて``option``キーを押すとアプリケーションがクラッシュしました。

* ACI0097488 Mac版のみ。バックアップ処理によってシステムに搭載されたメモリの80%以上のサイズに相当するファイルが作成されると，利用できるメモリが極端に少なくなりました。Webブラウザなど，他のアプリケーションを操作すれば，キャッシュされたファイルが解放されることにより，状況が改善されることがあります。しかし，何もしなければ，あるいは``sudo purge``などの管理コマンドを実行しなければ，メモリが非常に乏しい状態で動作を強いられることになります。

* ACI0097482 新ネットワークレイヤーのみ。スリープ中のクライアントをサーバー管理ウィンドウからドロップすることができませんでした。

* ACI0097462 デバッガ使用中にメソッドのコールチェーンをダブルクリックして表示させた呼び出し元のメソッド上で変数名にマウスポインターを重ねると``undefined = undefined``というヘルプTipsが表示されました。

* ACI0097460 複数のビルドされたクライアントアプリケーションが同じフォルダーに存在する場合，一方の自動アップグレードが進行している間に他方のアプリケーションが自動アップグレードを開始すると，両方のアプリケーションがクラッシュしました。自動アップグレードの一時ファイルに共通の名前「``$Tempo4DClient``」が使用されているためです。

* ACI0097458 64ビット版のみ。フォームエディター上で複数のリストボックス列が選択されている場合，カラーピッカーを使用して背景色を設定することができませんでした。

* ACI0097439 Mac版のみ。画像が含まれる4D Write Pro文書を表示したフォームを閉じた後，別のストラクチャを開いたり，``CLEAR VARIABLE``を実行すると，約10分後にアプリケーションがクラッシュしました。

* ACI0097413 ``Request``ダイアログをキャンセルした場合，空の文字列ではなく，デフォルト入力値が返されました。

* ACI0097411 4D Writeから変換した4D Write Pro文書は「スモールキャピタル（小文字と同じ高さの大文字）」スタイル指定が継承されませんでした。

* ACI0097409 「4D Web Application Server」ライセンスでアプリケーションを起動した場合，``4DC``ファイルを開こうとすると，エラー``10507``が返され，コンパイルされたデータベースを開くことができませんでした。

* ACI0097408 Mac版のみ。AreaList Proプラグインエリアがフォーカスされている状況で，同にフォームに存在するテキスト入力オブジェクトをクリックしても，フォーカスが移動しませんでした。もう1回，そのオブジェクトをクリックすることが必要です。

* ACI0097400 Mac 64ビット版のみ。環境設定や終了など，システム系の標準アクションがメニューバー項目に設定されている場合，そのメニュー項目を選択すると，別のメニュー項目に設定されたプロジェクトメソッドが実行されました。メニュー参照が1個ずれているかのようです。

* ACI0097399 ``WEB SERVICE CALL``を連続して使用すると，2度目の実行でエラー``9911``が返されました。

* ACI0097392 フィールドのタイプが途中で変更されたために，異なるタイプの値がレコードに保存されている場合，SQLの``OUTER JOIN``と``ORDER BY``を実行すると，アプリケーションがクラッシュしました。すべてのレコードを保存し直すか，MSCでレコードの強制更新（圧縮 > 特殊）を実行すれば，問題は解消されます。

* ACI0097386 Apache2をプロキシサーバーとしてセットアップしている場合，POSTされたHTTPボディの最初の2バイトがたまに欠落することがありました。直接リクエストを受信した場合は問題ありません。NGINXでも問題はないようです。

* ACI0097383 変数に対する参照をSQLの``INSERT``文で使用した場合，その変数のいずれかに空の文字列が含まれていると，Microsoft SQL Serverに値を送信することができませんでした。エラーメッセージが表示されることも，エラーハンドリングメソッドが実行されることもありません。

* ACI0097380 64ビット版クライアントのみ。サーバーに接続しているユーザーの数が多いと，ラベル印刷に時間がかかりました。たとえば，1ユーザーであれば約1秒，10ユーザーであれば同じラベルの印刷に4=5秒ほど要しました。

* ACI0097370 新ネットワークレイヤーのみ。イーサネットケーブルが引き抜かれるなど，クライアント接続が不意に失われた場合， ``On Server Close Connection``データベースメソッドが実行されませんでした。

* ACI0097369 デフォルト名前空間のURIが含まれるXML文書を``DOM Parse XML Source``で解析しようとすると，エラー`` -9935``が返されました。

* ACI0097359 クエリエディターに16個以上のフィールドが表示されている場合，擬似ポップアップメニューに表示されるフィールドリストを矢印キーで操作することができませんでした。キー入力すると，ポップアップメニューが閉じられ，最後に選ばれていたフィールドが選択されました。

* ACI0097357 ツールボックスのリソースタブ上でSVG画像が正常にレンダリングされないことがありました。一部のプロパティが無視されているためです。

* ACI0097354 Windows版のみ。ディスプレイ解像度が異なる環境でストラクチャを開閉した場合，ウィンドウ位置を記録したJSONファイルに範囲外の座標（たとえば負の値）が書き込まれ，結果的に4DのMDIウィンドウにアクセスできなくなることがありました。

* ACI0097353 クライアント側でレコードを開いた状態で，サーバー側のネットワークケーブルを外し，ユーザーリストからクライアントが消えるまで待ってからケーブルを再接続し，クライアント側で別のレコードをロードしようとすると，アプリケーションがフリーズしました。

* ACI0097338 Windows版のみ。32ビット版のサーバーに接続した直後にクエリを実行すると，アプリケーションがクラッシュしました。

* ACI0097321 セレクション型のリストボックスをストラクチャ間でコピーした場合，コピー先でフィールド参照が失われました。テーブル数が1個であり，リストボックスの列に設定されているのがそのテーブルであれば，フィールドの参照もコピーすることができます。しかし，テーブル数が2個以上であり，2個目のテーブルがリストボックスの列に設定されている場合，フィールドの参照が列と一緒にコピーされません。

* ACI0097316 Windows 10のみ。ネットワークドライブ上にインストールされた4Dを起動すると，アプリケーションがクラッシュしました。

* ACI0097314 Windows版のみ。Microsoft XPS Writerプリンターで印刷中にキャンセルボタンをクリックすると，プリントジョブを開始できない，というダイアログが表示されますが，そのダイアログを閉じても印刷の進捗が表示され，中止ボタンをクリックしても，印刷を止めることができませんでした。印刷を中止するためには，アプリケーションを強制的に中止しなければなりません。

* ACI0097312 Mac 64ビット版のみ。高速でWebエリアを何度も開閉していると，アプリケーションがクラッシュしました。

* ACI0097311 継承されたフォームのオブジェクトを複製した場合，元のオブジェクトのプロパティ設定がどうであっても，複製されたオブジェクトにはタブ移動ができませんでした。

* ACI0097303 クライアントサーバーモードでメソッドにブレークポイントを追加しても，ランタイムエクスプローラーに表示されないことがありました。その場合，別のブレークポイントを追加すると，先のものが消え，新しいほうがメソッドエディターに残りました。

* ACI0097302 64ビット版のみ。``MSG_GetBody``および``MSG_Extract``は，メールの解析に32ビット版よりもずっと長い処理時間を要しました。

* ACI0097297 コンパイルモードでは，変数名にフィールドが設定されているポップアップメニューやコンボボックスのオブジェクトメソッドが実行されませんでした。単純な変数名では問題ありません。

* ACI0097282 SQLの``SELECT``文で時間型フィールドをテキストに``CAST``すると，該当する時間がミリ秒で返されました。たとえば，午前1時（``01:00``）に対し，``3600000``	が返されました。期待されるのは，以前のバージョンのように，``0:1:0:0``が返されることです。

* ACI0097278 Mac版のみ。選択リストが関連づけられたリストボックス列にタブ移動して上矢印キーでポップアップメニューを表示し，``return``キーでリスト項目を確定した場合，以後，その項目が変更できなくなりました。下矢印キーでは問題ありません。

* ACI0097264 ``On Outside Call``イベントで``ACCEPT``コマンドを使用した場合，すぐにはフォームが閉じられず，次に発生したイベントで閉じられませんでした。

* ACI0097257 ユーザー/グループ認証システムが設定されているアプリケーションで，ユーザー名とパスワードの入力画面でログイン操作を完了せずにネットワークから離れた場合，無名のユーザープロセスがサーバー側に残されました。たとえば，ログイン画面を表示したまま，ノートパソコンを閉じて別の場所に移動し，操作を再開した場合に問題が発生します。そのままログインした場合，サーバー側に無名のユーザーと有効なユーザーの両方が存在することになり，余分にクライアント接続ライセンスが消費されました。新旧どちらのネットワークレイヤーでも問題が発生しますが，旧ネットワークレイヤーであれば，クライアント/サーバー接続タイムアウトまで待てば無名のユーザーが消滅します。新ネットワークレイヤーでは，無名のユーザーはドロップすることができず，状況を是正するためにはサーバーを再起動するしかありません。

* ACI0097254 ``IMAP_SetPrefs``で設定したパス名にウムラウト記号が含まれている場合，``IMAP_MsgLst``を実行するとエラー``-120``が返されました。

* ACI0097241 32ビット版のみ。``WA Evaluate javascript``で``JQuery``コマンドを実行すると，コールスタックの最大数に達した，というエラーメッセージが返されました。

* ACI0097233 Windows版のシステムWebエリアのみ。``On URL Filtering``イベント内で``WA EXECUTE JAVASCRIPT FUNCTION``コマンドを使用し，``window.location.href="http://..."``のようなJavaScriptを実行した場合，2回目の``On URL Filtering``イベントが発生しませんでした。

* ACI0097210 Mac 32ビット版のみ。旧式ネットワークレイヤーでサーバーに接続した場合，4D RemoteのPU使用率がすぐに100%に達し，その後，常時80%前後をキープしました。サーバー側でもかなり高い数値がみられます。新ネットワークレイヤー，または64ビット版クライアントであれば問題ありません。

* ACI0097208 Mac 32ビット版のみ。クライアント側でデザインモードにアクセスし，エクスプローラーのホームタブでサブフォルダーを作成すると，アプリケーションがクラッシュしました。最上位のフォルダーを作成した場合は問題ありません。また，シングルユーザー版でも発生しません。

* ACI0097207 Windows版のみ。``RESTORE``コマンドに引数を渡して復元をすぐに開始した場合「停止」ボタンのタイトルには「復元」と表示されました。 

* ACI0097197 4D Write Proエリアをフォームに配置した場合，フォームの右および下側に数ピクセルのマージンが加算されました。

* ACI0097193 クロスタブモードでクイックレポートをテキストまたはHTMLファイルに出力した場合，値が空のレポートが作成されました。プレビューだけならうまく表示できることもあれば，HTMLが大丈夫でテキストファイルが出力できないこともありました。プレビューを実行するとエラーが返されることもありました。

* ACI0097184 64ビット版のみ。``GRAPH``コマンドで作成した円グラフが32ビット版とは値の表示がおおきく違いました。32ビット版は0°（12時）から時計回りに値が描画されますが，64ビット版は90°（3時）から反時計回りに値が描画されました。

* ACI0097176 並び替えダイアログの右側フィールド順序のドラッグ＆ドロップによる変更ができませんでした。

* ACI0097135 特定の条件下では，``SVG Find element IDs by rect``がSVG要素IDの配列を返しませんでした。

* ACI0097120 64ビット版のみ。クイックレポートで日付フィールドに対して``Min``または``Max``関数を使用した場合，日付ではな数値が返されました。

* ACI0097119 Mac 64ビット版のみ。ストラクチャエディター上でリレーションを設定する場合，描画中に水平スクロールが発生すると，アプリケーションがクラッシュしました。

* ACI0097055 ビルドされたサーバーアプリケーションのデータファイルと同じ階層（``Server Database``フォルダー）にユーザー設定を置いた場合，キャッシュサイズの設定を変更しても，再起動後にカスタム設定が反映されませんでした。

* ACI0097045 4D Write Proウィジェットの「幅」入力エリアに間違っておおきな値を入力した場合，エラーが表示されました。その後，修正するために文字を削除しようとしても，キーストローク毎にエラーが表示されました。

* ACI0097021 ラジオボタンのプロパティで表示オプションにインタープロセス変数を使用（例：``:<>RessFormulaire,1``）すると，フォームを実行したときにボタンがチェックボックスとして表示されました。``:16000,1``のような指定であれば問題ありません。リソースは``.lproj``フォルダー内のXLIFFファイルに保存されています。

* ACI0097005 ツールボックス「リソース」ページのリストビューで2個以上のアイテムが選択されている場合，削除ボタンをクリックしてもアイテムが削除されませんでした。また，右クリック操作をしても，コンテキストメニューが表示されませんでした。

* ACI0096911 Mac版のみ。「サーバーに接続中」ウィンドウの「停止」ボタンをクリックしても，処理が中断されずにタイムアウトまで続きました。たとえば，入力したIPアドレスでサーバーが公開されていないような場合，接続の試みをすぐに停止することができませんでした。

* ACI0096870 64ビット版のみ。クイックレポートエディター（``QR REPORT``）でレポートを出力した場合，作成した文書のパスがシステム変数``Document``に代入されませんでした。

* ACI0096801 サブフォームウィジェットの水平リサイズオプションが「拡大」に設定されている場合，``On Load``イベント中にウィジェット内のオブジェクトを移動すると，``OBJECT SET COORDINATES``から返される位置情報が正しくありませんでした。実際の位置にフォームのリサイズされた幅を加算した値が返されました。``On Timer``イベントであれば問題ありません。

* ACI0096795 ``SQL LOGIN("4D:[データベース名]...")``シンタックスに対してエラー``9918``が返されました。

* ACI0096775 ``On Exit``データベースメソッドの中で``TRACE``が使用された場合，``On Exit``が実行されませんでした。

* ACI0096695 Mac 64ビット版のみ。``On Load``イベントで``DIALOG``コマンドを使用すると，画面が再描画でちらつきました。

* ACI0096654 64ビット版のみ。データ書き出しダイアログのキャンセルボタンをクリックすると，「ファイルが作成できません」というエラー``-1``が返されました。

* ACI0096646 HTTPサーバーとHTTPクライアントを併用した場合，HTTPクライアントの速度が遅くなりました。

* ACI0096615 トランザクション中にインデックスの削除や作成を実行すると，データ書き込みのタイミングでアプリケーションがクラッシュしました。

* ACI0096573 Windows版のみ。水平スクロール操作をして表示されたリストボックス列のヘッダーおよびフッターにはヘルプTipsが表示されませんでした。

* ACI0096533 4D Viewのセルに新規カスタムフォーマット（例：``£###.###.##0,00``）を設定することができませんでした。

* ACI0096532 4D Viewのセルにカスタム通過フォーマット（例：``£ ###.###.##0,00``）を設定することができませんでした。ツールバーの「フォーマット」ドロップダウンメニューに追加したフォーマットが表示されないためです。

* ACI0096165 Windows版のみ。英語版のオペレーションシステムで地域と言語を「トルコ語」に設定した場合，サーバー管理画面のボタンがクリックに反応しませんでした。

* ACI0096025 階層リストボックスが表示されているフォームのページから別のページに移動し，``LISTBOX SELECT ROW``を実行した場合，意図したのとは違う行にコマンドが適用されました。その後，`LISTBOX Get number of rows``を使用した場合，実際の行数に階層のノード行を加えた数が返されました。どちらのページでコマンドを実行しても，動作は同じであるべきです。

* ACI0095763 ``SUSPEND TRANSACTION``でトランザクションを一時的している間にレコードを保存したことによってトリガが実行された場合，``RESUME TRANSACTION``で「トランザクションは停止されていないので再開できません」というエラーが表示されました。

* ACI0095626 BLOB配列に対するポインターを使用し，``$ptr->{$row}{$offset}``のようなコードを実行した場合，インタープリターモードでは問題ありませんが，コンパイルモードでは範囲チェックエラーが返されました。

* ACI0095585 すでに配列が表示されているリストボックスを``LISTBOX SET HIERARCHY``で階層表示に切り替えた場合，キーボードの上下矢印キーに対して垂直スクロールが正しく働きませんでした。

* ACI0095136 メソッドエディターで``Case of``構文の``Else``や``:``などの中間ブロックにコードをタイプ入力しようとすると，アプリケーションがクラッシュしました。挿入位置直前（上部）の条件ブロックが畳まれている場合に問題が発生します。``If``構文の条件が畳まれた状態で``Else``ブロックを編集しようとした場合にも同じ問題が発生します。

* ACI0094994 SQLのサブクエリを実行すると，サーバーがしばらく応答しませんでした。

* ACI0094836 日付型の変数を日付入力ウィジェットに関連付けた場合，フォームを開く前にセットされていた変数の値がフォームを実行すると初期化されました。

* ACI0094675 3Dボタン・3Dラジオボタン・3Dチェックボックスをストラクチャ間でコピーした場合，オブジェクトは複製されますが，アイコンのリソース画像は複製されませんでした。

* ACI0094242 ``alter table CLIENTS_CYCLES add primary key (champ1, champ2)``のようにコードで複合プライマリーキーを設定した場合，重複する値の組み合わせをデータベースに登録してもエラーが返されませんでした。

* ACI0097289 Webプロセスが自動的に閉じられた場合，``On Web Close Process``データベースメソッドが実行されませんでした。たとえば，最大Webプロセス数を設定し，その数を超えてセッション管理されたリクエストを受け付けた場合，[もっとも古いプロセスが自動的に破棄される](http://doc.4d.com/4Dv16/4D/16.3/On-Web-Close-Process-database-method.300-3652272.ja.html)はずですが，このタイミングでデータベースイベントが実行されませんでした。

* ACI0097288 ``While``および``Repeat``の終了条件は真偽値であるべきですが，コンパイラーはこの式をチェックしませんでした。``If``および``Case``の場合と同じように，条件式の型をチェックするべきです。

* ACI0097286 ``LISTBOX DELETE ROWS``で配列型リストボックスの行を削除した場合，行高さの配列が正しく更新されませんでした。削除した行ではなく，最後の行に対応する要素が削除されました。``LISTBOX INSERT ROWS``も同様です。

* ACI0097157 新ネットワークレイヤーのみ。クライアント/サーバーの接続タイムアウトを「無制限」に設定した場合，2時間ほどでクライアント接続が切断されました。

* ACI0097036 オブジェクト記法で未定義のプロパティにアクセスするとシンタックスエラーが返されました。

**注記**: 16R4と16R5では，未定義プロパティの振る舞いが違います。

https://blog.4d.com/object-notation-improvement-after-customer-feedback/

* ACI0097019 Mac版のみ。64ビット版の4D ServerからODBC経由でMySQLに文字列を``INSERT``した場合，``aaaa\0``のように終末文字コードが挿入されました。

* ACI0095145 シンボルファイルにオブジェクト型の変数が出力されませんでした。

* ACI0097512 オブジェクト記法が有効にされていない場合，ストラクチャエディターで数字から始まるフィールド名を入力することができました。

* ACI0097479 DTDが設定されたXML文書を``DOM Parse XML source``で解析しようとすると，エラー``-9935``が返されました。

* ACI0097465 配列型のリストボックスで行の高さがコントロール配列あるいは自動設定で制御されている場合，``OBJECT SET SCROLL POSITION``でスクロールした後に``OBJECT GET SCROLL POSITION``を実行すると，ひとつ前に行番号が返されました。

* ACI0097429 ``QR EXECUTE COMMAND``で``qr cmd presentation``を実行しようとすると，アプリケーションがクラッシュしました。

* ACI0097390 ``On Web Connection``データベースメソッドで``WEB SEND TEXT``の後に``QUERY SELECTION``がコールされた場合，アプリケーションがクラッシュしました。

* ACI0097373 64ビット版のみ。新クイックレポートエディターの「新規作成」ボタンに問題がありました。ツールモードでエディターを開いた場合，ボタンをクリックしても何も起きません。ウィジェットモードでエディターを開いた場合，ボタンをクリックするとシンタックスエラーが返されました。

**注記**: サブフォームとして``NQR``が選択できたことに問題がありました。ウィジェットモードでエディターを使用する場合のサブフォームは``%Report``です。

* ACI0097323 Windows版のみ。SDIモードで起動されたクライアントアプリケーション（スプラッシュウィンドウは「非表示」に設定）のウィンドウをすべて閉じた場合，アプリケーションは自動的に終了するはずですが，バックグラウンドでプロセスが動作を続けました。タスクマネージャーで確認することができます。デスクトップ版のアプリケーションでは問題ありません。

* ACI0097639 Mac版のみ。フォームエディターでリソースフォルダーからピクチャボタンに画像をドロップした場合，アプリケーションがクラッシュすることがありました。

* ACI0097586 ``SPELL GET DICTIONARY LIST``から返される言語名が正しくありませんでした。``English (United States)``が3個，``Portuguese (Brazil)``が2個，``unknown``が1個，リストに含まれました。

* ACI0097533 オブジェクト記法を使用してオブジェクトの内部オブジェクトに新しい値を代入した場合，オブジェクトの更新が認識されませんでした。明示的に親オブジェクトを更新する必要がありました。

* ACI0097517 ポインター変数に``Null``を代入した場合，そのポインターをデバッガーに表示させるとアプリケーションがクラッシュしました。

* ACI0093494 [``ARRAY TO SELECTION``](http://doc.4d.com/4Dv16/4D/16.3/ARRAY-TO-SELECTION.301-3652156.ja.html)または[``SELECTION TO ARRAY``](http://doc.4d.com/4Dv16/4D/16.3/SELECTION-TO-ARRAY.301-3652157.ja.html)の中間命令をループ文で構築した場合，実行は問題なく成功しますが，シンタックスチェックでエラーが返されました。

* ACI0097723 4D Write Pro文書に2個以上の表が組まれている場合，``ST INSERT TEXT``でセルにテキストを挿入すると，その行の高さ計算が正しくありませんでした。

* ACI0097696 Windows版のみ。リストフォームのスクロールがぎこちない感じです。

* ACI0097738 PICT形式など，プラットフォームでサポートされていないフォーマットの画像が4D Write Pro文書に挿入されている場合，表示ができないことを知らせるアイコンではなく，空の画像が表示されました。

* ACI0097167 デザインモード検索で更新日が「昨日以降」のオブジェクトを検索した場合の結果が正しくありませんでした。指定とは逆の条件でオブジェクトが返されました。

* ACI0097654 Windows版のみ。``On Startup``データベースメソッドで``SHOW MENU BAR``あるいは``HIDE MENU BAR``を使用することができませんでした。

* ACI0097798 オブジェクト記法を有効にした場合，一部のコードがコンパイルできなくなりました。下記はコンパイルができないコードの例です。

```
ALL RECORDS([Table_1]) 
APPLY TO SELECTION([Table_1];[Table_1]Field_2:="123")
```

```
QUERY([Table_1];[Table_1]Field_2="111";*)
QUERY([Table_1]; | [Table_1]Field_2="222") //セミコロンが抜けている
```

```
Case of 
Else $toto:=1 
End case
```

* ACI0097872 ``APPEND TO LIST``コマンドのコード補完に表示される候補文字列が正しくありませんでした。``($P_pop_individu_payeur->``と入力すると``length``というプロパティ名が間違って表示されました。

* ACI0097868 スペイン語・チェコ語版のみ。デザインモードで4D Write Proコマンド名にマウスポインターを重ねると，説明文の代わりに``XLIFF``参照が表示されました。

* ACI0097539 大量のSOAPリクエストを処理すると，サーバーが突然に終了することがありました。サーバー側で管理画面を表示していると，さらに問題が起こりやすくなるようです。

* ACI0097859 Windows版のみ。リストボックスの行の高さを「行」単位で指定し，サイズ``12``または``18``の``MS Sans Serif``フォントを設定した場合，``p``, ``q``, ``g``のような文字の「ぶらさがり」が途切れて表示されました。サイズ``14``では問題ありません。リストボックスのテキストレンダリングが「DirectWrite」の場合に問題が発生します。「GDI」であれば問題ありません。

**注記**: レンダリングの違いによって発生する「ずれ」の度合いは，使用するフォントによって異なりますが，ほとんどの場合，それは1ピクセル程度の違いです。しかし，GDIだけでサポートされているフォントの場合，DirectWriteでは代替フォントが使用されるため，かなりの違いが発生することがあります。TrueTypeでもOpenTypeでもない，``Terminal``や``Roman``のようなビットマップフォントがこれに相当します。なお，リストボックスのレンダリングモードは，データベースパラメーター``107``で変更することができます。

0: バージョン15以前に作成されたリストボックスであればGDI，16以降で作成されたリストボックスであればDirectWriteを使用します。（デフォルト）

1: 常にDirectWriteを使用します。

2: 常にGDIを使用します。

* ACI0097909 Windows版のみ。オブジェクト記法が有効にされている場合，変換されたアプリケーションのシンタックスチェックがメソッドの解析でクラッシュすることがありました。

* ACI0097860 リストボックス行の高さを「自動」に設定し，縦スクロールバーの表示を「自動」または「はい」に設定した場合，表示されている行の高さの合計がリストボックスの高さを超えない限り，垂直スクロールバーは表示されませんが，その状態で``LISTBOX INSERT ROWS``でリストボックスの高さを超えるまで行を追加しても，垂直スクロールバーが表示されませんでした。また，クリック操作で正しく行を選択することもできません。リストボックス行の高さを「自動」に設定されていなければ問題ありません。

* ACI0097832 配列型のリストボックスで一部の行を非表示に設定している場合，垂直スクロールバーおよび行の高さが「自動」に設定されていると，垂直スクロールバーが正しく描画されませんでした。

* ACI0097722 64ビット版のみ。クイックレポートエリアをフォームに組み込んだ場合，4D Viewのライセンスが必要になりました。

* ACI0097904 サーバーに接続した後，ファイルメニューからデータベースを閉じ，「最近使用したデータベース」メニューから同じサーバーに接続すると，アプリケーションがクラッシュしました。

* ACI0097791 ``WEB SERVICE GET RESULT``で問題が発生した場合，4D View Proライセンスがない，というエラーメッセージが表示されました。エラーメッセージのXLIFFリソースが同じ``94``という``id``を使用しているためです。

* ACI0097933 Windows 64ビット版のみ。ようこそ画面（CEF版Webエリアを使用している）からデータベースを開いた場合，一部のプラグインが読み込めませんでした。直接，ドラッグ＆ドロップ等でストラクチャファイルを開いた場合は問題が発生しません。CEF版のWebエリアが内部的にDLLの検索パスを追加する``SetDllDirectory``を使用しているためです。

* ACI0097931 オブジェクト記法が有効にされている場合，SQLに長文を記述するとシンタックスチェックがエラーを返しました。

* ACI0097924 新ネットワークレイヤーのみ。リストフォームのクリックイベントなどで``ON EVENT CALL``が使用された場合，ネットワークの品質や状態により，「ヌル終点」エラーが発生することがありました。サーバーがバーチャルマシン上で運用されていたり，サーバーがWindowsでクライアントがMacの場合，ネットワークのデータ転送遅延（リクエストの対する反応時間）が長くなるため，容易に発生します。

* ACI0097557 Mac 32ビット版のみ。デザインモードのメソッドエディターまたはフォームエディターのウィンドウが開かれた状態でアプリケーションを終了した場合，再開時にそれらrのウィンドウが以前の位置に表示されませんでした。

**注記**: 32ビット版のアプリケーションはCarbonですが，ウィンドウの一覧を取得するためにCocoaのAPIが使用されていたことが原因でした。

* ACI0097953 Windows 64ビット版のみ。特定のプラグインコマンドを実行しようとすると「指定されたモジュールがロードできませんでした」エラーが返されました。4D for OCI, XL Plugin, ToBitPro XLなどの64ビット版プラグインです。

* ACI0097946 コンボボックスに入力されたテキスト選択してペーストボードにコピーすることができませんでした。カット操作であれば問題ありません。

* ACI0097957 リストボックスの列がピクチャ型に設定されている場合，プロパティリストに時間型のプロパティが表示されました。``ACI0097787``が修正されたビルド``220165``以降に特有の問題です。

* ACI0097989 サーバーに接続したクライアントのプロセスステータスが「延期」になった後，クライアント側でメニューあるいはツールバーの「最近使用したデータベース」から同じサーバーに再接続しようとした場合，別のクライアントが再接続した直後の20秒間は接続することができませんでした。

* ACI0097891 Mac 64ビット版のみ。ヘルプメニューからサーバー管理画面を表示することができませんでした。日本語版特有の問題です。``OPEN ADMIN WINDOW``あるいはツールバーのアイコンを使用すれば表示することができます。

* ACI0097998 クライアント側のファイルメニューからデータベースを閉じ，同じサーバーアプリケーションに接続した後，クライアントをスリープさせた場合，スリープから復帰するとクライアントがフリーズしました。
