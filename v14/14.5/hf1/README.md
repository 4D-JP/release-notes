4D v14.5 Hotfix 1
---

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0094250 Mac 64bits版（日本語）のみ。新規データベースを作成した直後にエラーメッセージが表示されました。

* ACI0092650 メソッドエディターに改行コード（バックスラッシュ記号）が使用されている場合，日本語変換中のガイドラインが2行目以降は左にずれて表示されました。

* ACI0092682 メソッド内に変数名がいくつも含まれる場合，日本語入力中に表示されるガイドラインの位置が左にずれて表示されました。

---

* ACI0095255 セレクション型（命名セレクションも含む）リストボックスのヘッダーをクリックして並び替えを実行した後，1行目に表示されたレコードを編集して``tab``キーで入力を確定すると，別のレコードが更新される可能性がありました。

**注記**: 並び替えの直後，``On After Sort``イベントで[UNLOAD RECORD](http://doc.4d.com/4Dv15/4D/15.1/UNLOAD-RECORD.301-2686061.ja.html)を実行すれば，問題を回避することができます。

* ACI0095184 「プリント時可変」プロパティが有効にされたフィールドをプリントアウトした場合，間違った位置にオブジェクトが印刷されることがありました。

* ACI0091711 クエリ定義ファイルをロードすると空のエラーダイアログが表示されることがありました。

* ACI0091247 Mac版のみ。階層リストに``Carriage return``が含まれるテキストを表示した場合，2行にわたってテキストが表示されました。

``注記:** 修正により，改行コード以降のテキストは切り捨てられるようになりました。

* ACI0094947 階層リストボックスをセットアップ（作成およびデータ挿入）したのと同じメソッド内でコールされた場合，[LISTBOX SELECT BREAK](http://doc.4d.com/4Dv15/4D/15.1/LISTBOX-SELECT-BREAK.301-2686094.ja.html)は何もしませんでした。階層リストボックスでなければ問題ありません。

* ACI0094837 [OBJECT SET FONT](http://doc.4d.com/4Dv15/4D/15.1/OBJECT-SET-FONT.301-2685674.ja.html)でリストボックスのフォントを``%password``に設定することができませんでした。

* ACI0095091 サブフォームから表示された入力フォームでは，階層ポップアップメニューをクリックしても，2度目以降はポップアップメニューが表示されませんでした。

* ACI0094670 [MODIFY SELECTION](http://doc.4d.com/4Dv15/4D/15.1/MODIFY-SELECTION.301-2684948.ja.html)を実行している値，ヘルプメニューの項目を選択することができませんでした。

* ACI0092893 スタンドアロン版で「最近使用したデータベース」メニューからアプリケーションを再起動した場合，デザインモード「ツール」メニューに「4D View」（あるいは何であれ最初に表示されるべきプラグインツール）が表示されませんでした。

* ACI0093949 階層ポップアップメニューに項目を追加すると，別の階層ポップアップメニューの選択された項目が変化することがありました。

* ACI0094651 配列型リストボックスを印刷した場合，ピクチャーの透明な背景が黒く出力されました。

* ACI0094988 階層リストボックスをセットアップ（作成およびデータ挿入）したのと同じメソッド内でコールされた場合，[LISTBOX SELECT ROW ](http://doc.4d.com/4Dv15/4D/15.1/LISTBOX-SELECT-ROW.301-2686109.ja.html)は何もしませんでした。階層リストボックスでなければ問題ありません。

* ACI0095118 リストボックスに同じ配列が2個以上表示されている場合，ヘッダークリックによる並び替えが正しく働きませんでした。

* ACI0093268 Mac版のみ。4D Viewのスクロール速度に問題がありました。Macのトラックパッドやマウスでエリアを上下にスクロールした場合，エリアが2本指スワイプ操作にほとんどついてこられませんでした。スクロール速度が非常にゆっくりで，移動の開始も遅れがちでした。今回の修正で4D Write, 4D View, プロパティリスト，クイックレポートの動作が改良されました。

* ACI0094561 サイズの小さなBLOBに対して[EXPAND BLOB](http://doc.4d.com/4Dv15/4D/15.1/EXPAND-BLOB.301-2686170.ja.html)のgzip圧縮を使用すると，エラーメッセージが表示されました。

```
C_BLOB($blbContent)
C_LONGINT($lngIsCompressed)

CONVERT FROM TEXT("test";"UTF-8";$blbContent)
COMPRESS BLOB($blbContent;GZIP best compression mode)

BLOB PROPERTIES($blbContent;$lngIsCompressed)
If ($lngIsCompressed#0)
  EXPAND BLOB($blbContent)
End if
```

* ACI0089399 コンポーネントメソッドを[4DACTION](http://doc.4d.com/4Dv15/4D/15.1/URLs-and-Form-Actions.300-2685147.ja.html)で呼び出すことができませんでした。

* ACI0094451 SQL ``INTO``でBLOBフィールドをBLOB配列にコピーしようとしても，配列にデータが転写されませんでした。

* ACI0094502 Mac版のみ。iMacテンキーの``clear``を入力した場合，何もテキストが選択されていなければ，何も起きず，テキストが選択されていれば，制御文字が挿入されました。v13以前は，いずれの場合も制御文字が挿入されました。正しい動作は，選択されたテキストを削除するというものです。

* ACI0065508 リストボックスの``On Display Detail``イベントが``On Load``よりも先に実行されました。

* ACI0093215 新ネットワークレイヤー使用時に多数（例: 75）のクライアントから同時にシーケンシャルクエリにリクエストが送られた場合，SOAPリクエストの処理でアプリケーションがフリーズ（デッドロック）に陥ることがありました。

* ACI0094909 Mac版のみ。OS X 10.11 El Capitanでは4D for OCIプラグインが使用できませんでした。OCIライブラリを``/usr/lib``にインストールすることができなくなったためです。

参考: OCIライブラリのインストール方法

* ダウンロード http://www.oracle.com/technetwork/topics/intel-macsoft-096467.html
* ``instantclient-basic-macos.x32-11.2.0.4.0.zip``または``instantclient-basic-macos.x64-11.2.0.4.0.zip``を入手
* ``/usr/local/lib``にライブラリをインストール
```
libclntsh.dylib.11.1
libnnz11.dylib
libocci.dylib.11.1
libociei.dylib
libocijdbc11.dylib
```
* ``libclntsh.dylib.11.1``に対するシンボリックリンク``libclntsh.dylib``を作成
* ``/private/etc``に``TNSNAMES.ORA``設定ファイルを追加

```
  oracle4D =
    (DESCRIPTION =
      (ADDRESS = (PROTOCOL = TCP)(HOST = 192.168.1.2)(PORT = 1521))
    (CONNECT_DATA =
      (SERVICE_NAME = XE)
    )
  )
```
