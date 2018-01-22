## 4D v16.3 Hotfix 1

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0097496 Mac 64ビット版のみ。日本語変換中に文字列を削除しようとした場合，確定された文字列と未確定の文字列の間で余計に``delete``キーを入力する必要がありました。

* ACI0096911 Mac版のみ。「サーバーに接続中」ウィンドウの「停止」ボタンをクリックしても，処理が中断されずにタイムアウトまで続きました。たとえば，入力したIPアドレスでサーバーが公開されていないような場合，接続の試みをすぐに停止することができませんでした。

**注記**: 64ビット版だけが修正されました。

* ACI0097129 Mac 64ビット版のみ。「終了」メニューのタイトルが日本語として不自然（「終了 4D」）でした。「4D を終了」と表示されるべきです。

* ACI0096996 管理画面を表示するためのキーボードショートカット（``Control``/``command``+``U``）が効きませんでした。

* ACI0097478 Windows版のみ。階層リストに「Yu Gothic/遊ゴシック」フォントのイタリック文字を表示した場合，文字列の一番右が少しだけ欠けて表示されました。

---

* ACI0096779 ローカルパスに拡張文字が含まれている場合，``FTP_Send``がエラー``-43``を返しました。Mac版では，ファイルが送信されません。Windows版では，転送が成功しますが，指定したファイル名がサーバー側で文字化けしました。

* ACI0097623 ブール型フィールドの表示フォーマットを``STR#``リソース（例：``:16001,1``）で設定している場合，ラジオボタンではなくチェックボックスが表示され，フォーマット定義が（例：``jpg;png``）そのままボタンタイトルとして表示されました。

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

* ACI0097630 「4D Serverに接続」ダイアログの「カスタム」ページに情報を入力してから，「利用可」ページに移動し，「カスタム」ページに戻ると，入力した情報がクリアされました。

* ACI0097613 アプリケーションを再起動したり，デザインモードとアプリケーションモードを切り替えたりすると，「レコード > 最後に使用したテーブル」の並び順が変わりました。

**注記**: テーブル数が``15``を超過する場合に問題が発生します。

* ACI0097520 フィールドのSQLエイリアスが別テーブルの名前と同じ場合，メソッドエディターのコード補完でアプリケーションがクラッシュしました。

* ACI0097458 64ビット版のみ。フォームエディター上で複数のリストボックス列が選択されている場合，カラーピッカーを使用して背景色を設定することができませんでした。

* ACI0097409 「4D Web Application Server」ライセンスでアプリケーションを起動した場合，``4DC``ファイルを開こうとすると，エラー``10507``が返され，コンパイルされたデータベースを開くことができませんでした。

* ACI0097392 フィールドのタイプが途中で変更されたために，異なるタイプの値がレコードに保存されている場合，SQLの``OUTER JOIN``と``ORDER BY``を実行すると，アプリケーションがクラッシュしました。すべてのレコードを保存し直すか，MSCでレコードの強制更新（圧縮 > 特殊）を実行すれば，問題は解消されます。

* ACI0097303 クライアントサーバーモードでメソッドにブレークポイントを追加しても，ランタイムエクスプローラーに表示されないことがありました。その場合，別のブレークポイントを追加すると，先のものが消え，新しいほうがメソッドエディターに残りました。

* ACI0097207 Windows版のみ。``RESTORE``コマンドに引数を渡して復元をすぐに開始した場合「停止」ボタンのタイトルには「復元」と表示されました。 

* ACI0097173 Windows版のみ。4D Write Proエリアから複数行のテキストをコピーして一般的なテキストエディターに標準テキスト形式でペーストした場合，同じ文章が2回挿入されました。

* ACI0096654 64ビット版のみ。データ書き出しダイアログのキャンセルボタンをクリックすると，「ファイルが作成できません」というエラー``-1``が返されました。

* ACI0096573 Windows版のみ。水平スクロール操作をして表示されたリストボックス列のヘッダーおよびフッターにはヘルプTipsが表示されませんでした。

* ACI0094242 ``alter table CLIENTS_CYCLES add primary key (champ1, champ2)``のようにコードで複合プライマリーキーを設定した場合，重複する値の組み合わせをデータベースに登録してもエラーが返されませんでした。

* ACI0097386 Apache2をプロキシサーバーとしてセットアップしている場合，POSTされたHTTPボディの最初の2バイトがたまに欠落することがありました。直接リクエストを受信した場合は問題ありません。NGINXでも問題はないようです。

**注記**: 4DのフロントエンドにApacheをセットアップする方法は下記の記事で詳しく説明されています。

http://kb.4d.com/assetid=75920

* ACI0097193 クロスタブモードでクイックレポートをテキストまたはHTMLファイルに出力した場合，値が空のレポートが作成されました。プレビューだけならうまく表示できることもあれば，HTMLが大丈夫でテキストファイルが出力できないこともありました。プレビューを実行するとエラーが返されることもありました。

**注記**: 64ビット版のクイックレポートが修正されました。

* ACI0095763 ``SUSPEND TRANSACTION``でトランザクションを一時的している間にレコードを保存したことによってトリガが実行された場合，``RESUME TRANSACTION``で「トランザクションは停止されていないので再開できません」というエラーが表示されました。

* ACI0097184 64ビット版のみ。``GRAPH``コマンドで作成した円グラフが32ビット版とは値の表示がおおきく違いました。32ビット版は0°（12時）から時計回りに値が描画されますが，64ビット版は90°（3時）から反時計回りに値が描画されました。


* ACI0097045 4D Write Proウィジェットの「幅」入力エリアに間違っておおきな値を入力した場合，エラーが表示されました。その後，修正するために文字を削除しようとしても，キーストローク毎にエラーが表示されました。

* ACI0095626 BLOB配列に対するポインターを使用し，``$ptr->{$row}{$offset}``のようなコードを実行した場合，インタープリターモードでは問題ありませんが，コンパイルモードでは範囲チェックエラーが返されました。

* ACI0097658 新ネットワークレイヤーのみ。多数クライアントが同時に接続を開始し，ユーザー認証プロセスに負荷がかかった場合，サーバーの反応が待ちきれずにクライアントが認証の途中で接続を断念することがあります。そうなると，以降，新規のクライアント接続ができなくなってしまいました。

* ACI0097649 幅が``1``ポイントのタブコントロールがフォームに存在する場合，そのフォームを表示しようとするとアプリケーションがクラッシュしました。

* ACI0097426 ``Alt``キーを押しながらビルドしたクライアントアプリケーションを起動し，表示させたログインダイアログの「このダイアログを次回起動時に表示」を有効にした場合，クライアントを再起動してもログインダイアログが表示されませんでした。

* ACI0097701 macOS 10.13 High Sierraのみ。メソッドのコードをコマンドまたはメニューを実行して書き出すと，一時ファイル（``{UUID}.temp``）がデスクトップに作成されました。新しいファイルシステム（APFS）特有の問題です。

* ACI0097697 Mac版のみ。指定リストが関連づけられたリストボックス列は，ポップアップメニューをクリックし，上下矢印キーで値を決定すると，それ以降，上下矢印キーで内容が変更できなくなりました。

* ACI0097707 macOS High Sierraのみ。言語と地域の設定に複数の言語がリストアップされている場合，英語のシステム日付フォーマットが採用されました。英語がリストに含まれていなければ，問題ありません。

* ACI0097575 クライアント側のメソッドエディターで設定したブレークポイントがランタイムエクスプローラーに反映されないことがありました。

* ACI0097346 フォームにロードされた直後にクリックした場合，あるいは直接キーボードで値を入力した場合， 日付ピッカーウィジェットの表示が正しくありませんでした。

* ACI0097760 プロセスが延期ステータスに置かれている場合，``UNREGISTER CLIENT``を実行すると接続が切断されました。

* ACI0097700 時間ピッカーウィジェットが配置されたフォームを表示すると，``On Bound Varible Change``イベントに関連したメッセージが表示されました。デバッグ目的のコードが残されているようです。

* ACI0097488 Mac版のみ。バックアップ処理によってシステムに搭載されたメモリの80%以上のサイズに相当するファイルが作成されると，利用できるメモリが極端に少なくなりました。Webブラウザなど，他のアプリケーションを操作すれば，キャッシュされたファイルが解放されることにより，状況が改善されることがあります。しかし，何もしなければ，あるいは``sudo purge``などの管理コマンドを実行しなければ，メモリが非常に乏しい状態で動作を強いられることになります。

* ACI0097788 新ネットワークレイヤーのみ。接続中のクライアントがスリープモードのタイムアウトに到達した場合，サーバーがデッドロック状態に陥り，クライアントの新規接続ができなくなりました。また，スリープ中のクライアントがドロップされませんでした。

* ACI0097779 新ネットワークレイヤーのみ。接続中のクライアントがスリープモードのタイムアウトに到達した場合，サーバーがデッドロック状態に陥り，クライアントの新規接続ができなくなりました。また，スリープ中のクライアントがドロップされませんでした。

**注記**: スリープモードのタイムアウトは``48``時間です。スリープ状態クライアントこの時間に到達した場合，ロックされたオブジェクトを解放するため，そのクライアントは強制的にドロップされます。振る舞いを検証するために``SET DATABASE PARAMTER``のセレクター``98``（非公開）で一時的に設定することができます。デフォルト値は``172800``です。

* ACI0097730 ``«wr_number :###.##0,00»``または``«wr_number :###,##0.00»``のようにフォーマットされた数値が含まれた4D Write文書が正しく4D Write Pro文書に変換することができませんでした。``String(wr_number ;"###.##0.00"``のように，ヨーロッパ式の小数点（カンマ）がピリオドに変換され，桁区切りと小数点が同じ記号になりました。

* ACI0097740 無効な``HTTP Request``をコールがステータスコード``200``を返しました。``0``が返されるべきです。

* ACI0096868 64ビット版のみ。ラベルエディターで設定ファイルを書き出した場合，システム変数``DOCUMENT``が更新されませんでした。

* ACI0097683 Windows版のみ。システムのアピアランスを「クラシック」テーマに設定した場合，サーモメーターの目盛りが部分的にしかフォームエディターに表示されませんでした。

* ACI0097656 素早く続けてボタンまたはサブフォームを（ダブル）クリックした場合，最初のイベントメソッドが完了するよりも先に次のイベントメソッドが実行されることがありました。たとえば，クリックイベントで``ALERT``コマンドなどを実行してモーダルダイアログを表示した場合，フォームを閉じることができなくなり，アプリケーションを強制的に終了するしかありませんでした。

* ACI0097373 64ビット版のみ。新クイックレポートエディターの「新規作成」ボタンに問題がありました。ツールモードでエディターを開いた場合，ボタンをクリックしても何も起きません。ウィジェットモードでエディターを開いた場合，ボタンをクリックするとシンタックスエラーが返されました。