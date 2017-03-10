4D v16.0 Hotfix 2
---

Nightly Build ``209433``

[4D v16.0 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v16/16.0/hf1)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0096406 文字列フィールドに日本語を入力している間，そのフィールドの文字数を超える変換候補は画面上に表示されませんでした。たとえば，2文字まで入力できるフィールドに『ほうりゅう』と入力した場合，変換を確定するまでは『ほう』の2文字しか表示されませんでした。

---

* ACI0096485 ``TRACE``コマンドやブレークポイントが設定されていても，サーバー側ではデバッガが表示されませんでした。

* ACI0089884 ``ST SET PLAIN TEXT``コマンドは，``&``, ``<``, ``>``のような文字をHTMLに変換しませんでした。

**注記**: 実際には，挿入ではなく，出力の問題でした。スタイル付きテキストの内容が``<span>``タグに囲われていないテキストであり，かつ，そのテキストが``&``, ``<``, ``>``のような文字を含んでいる場合，内容がHTMLとして出力されませんでした。

* ACI0096447 ビルドしたクライアントアプリケーションで管理画面を表示した場合，一部のXLIFF参照が欠落していました。Volume Desktopに``monitor.xlf``ファイルが含まれていないことが原因です。

* ACI0096461 ``ALERT``のダイアログが表示されている間，``Alt``+``Shift``+右クリックまたは``control``+``option``+右クリックでプロセスポップアップメニューを呼び出してデバッグすることができませんでした。

* ACI0096493 Mac版のみ。4D Mobileの接続数が限られているサーバーに対し，管理ウインドウを表示したまま，大量のREST接続を試みると，サーバーがクラッシュしました。ACI0096100とは別の問題です。

* ACI0096496 トランザクション中に``SET QUERY AND LOCK``を使用し，インデックスが設定されていないフィールドに対してクエリを実行した後，``SET QUERY AND LOCK``を解除してから絞り込みクエリを実行した場合，最初のクエリでみつかったレコードがロックされませんでした。

* ACI0096425 特定のオブジェクト変数をデバッガに表示しようとしたり，``JSON Stringify``で書きだそうとすると，アプリケーションがクラッシュしました。

**注記**: すでに値が存在する属性を未定義のオブジェクト変数で置き換えた場合に問題が発生します。

例：

```
C_OBJECT($obj)
C_OBJECT($empty)

$obj:=JSON Parse("{\"attribut1\":\"Hello\",\"attribut2\":\"2\"}"))
TRACE
  //$empty:=JSON Parse("{\"att1\":\"toto\"}")	// $emptyが定義済みであれば問題なし
OB SET($obj;"attribut1";$empty)
$json:=JSON Stringify($obj)
```

* ACI0096507 Windows版のみ。Direct2Dモードでないときに``ALERT``のようなコマンドを使用すると，別のウィンドウを最前面に移動したタイミングでアプリケーションがクラッシュしました。

**注記**: Direct2Dモードは，``SET DATABASE PARAMETER``で制御することができます。

```
SET DATABASE PARAMETER(Direct2D status;Direct2D disabled)
ALERT("...")
```

* ACI0096434 複雑なSQLコードをメソッドエディターにペーストすると，アプリケーションがクラッシュすることがありました。

例：

```
Begin SQL
 SeLeCT nom, adresse, adresse2, code_postal, commune
 FROM SQL_tiers,SQL_TYPe_TIeRS,SQL_APPARTeNANCe_TYPe_TIeRS
 WHeRe (SQL_APPARTeNANCe_TYPe_TIeRS.IDTIeRS=SQL_TIeRS.IDTIeRS)
 AND (SQL_APPARTeNANCe_TYPe_TIeRS.IDTYPe_TIeRS=SQL_TYPe_TIeRS.IDTYPe_TIeRS)
 AND(type_tiers = 'GDS')
 AND (SQL_APPARTeNANCe_TYPe_TIeRS.Date_fin_appartenance<>'')
 AND  (SQL_TIeRS.Code_postal LIKe <<$departement%>>)
 INTO :$nom_exp, :vAdresse_1, :vAdresse_2, :vCode_Postal, :vCommune;
End SQL
```

* ACI0096481 Windows版のみ。ビルドしたアプリケーションは，メインプロセスのスプラッシュウィンドウ以外のウィンドウにカスタマイズしたアイコンではなく4Dのアイコンが表示されました。 
