4D v17.0 Hotfix 2
---

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

---

* ACI0098518 ``FORM LOAD``コマンドでメモリにロードした4D Write Proエリアに対して``OBJECT Get font``を使用した場合，アプリケーションがクラッシュしました。

* ACI0098409 Windows 10 1803のみ。Acrobat Reader DC・ Office 365・Kyoceraのプリンタードライバをインストールし，デフォルトプリンターに設定した後，オペレーションシステムを再起動して，Microsoft Wordに続けて4Dを起動して``FONT STYLE LIST``を実行すると，しばらく後にアプリケーションがクラッシュしました。

* ACI0098547 クライアントサーバー版のみ。出力フォームにレコードを表示し，フォームをスクロールしたり，リサイズしたりするたびに，メモリーリークが発生しました。

* ACI0098506 VPN経由でサーバーに接続した状態で，30分間程度，クライアントを操作せずに放置すると，接続が失われることがありました。LANでは問題ありません。

* ACI0098515 4D Mobile/Wakanda 2.5.0のREST API経由で4Dのメソッドをコールした場合，空の戻り値が返されました。ビルド``223886``では問題ありません。ビルド``225801``の問題です。

* ACI0098481 クライアント/サーバー版のみ。``fromCollection()``でレコードを作成した場合，もしリレート先のデータクラスに外部キーが存在しないと，リレート先のエンティティが更新され，プライマリキー（``relatedEntity``リレーション属性）の値が``Null``にセットされました。

```
C_OBJECT($dataclass1;$result)
$dataclass1:=ds.IA_employee

$t1_Collection:=New collection
$t1_obj:=New object
$t1_obj.ID:=7
$t1_obj.employer:=New object()
$t1_obj.employer.ID:=10 //doesn't exist in the dataclass "IA_company"
$t1_obj.firstName:="Zoro"
$t1_Collection.push($t1_obj)
$result:=$dataclass1.fromCollection($t1_Collection)
ASSERT(Undefined($result[0].employer);"employer should not be created")
```

* ACI0098360 コレクション型のリストボックスにエンティティセレクションを表示した場合，1テーブルのリレーション属性のヘッダーをクリックすると『…属性は…データクラスに存在しません』というエラーが返され，並び替えができませんでした。``On header clicked``イベントで`` $0:=-1``を実行し，``Form.sel:=Form.sel.orderBy()``で並び替えを実行することはできますが，本来であれば，ヘッダーのクリックで自動的に実行されなければなりません。``ACI0098169``と同じ問題です。

* ACI0097954 Mac 64ビット版のみ。旧式ネットワークレイヤーでサーバーに負荷のかかる処理を続けていると，1時間ほどでアプリケーションがクラッシュしました。接続クライアント数が多ければ，それだけ短い時間で問題が発生します。

* ACI0098348 クライアント/サーバー版のみ。外部ユーザー設定ファイルが有効にされたアプリケーションで，SQLのTLSを有効にした場合，ダイアログには新しい設定が正しく表示されますが，再起動後，SQLを実行すると，接続エラーが返されました。SQLのTLSモードは，ストラクチャ設定でなければ，有効にすることができませんでした。

* ACI0098500 ランタイムエクスプローラーのプロセスリストにWebサービス（SOAP）プロセスが表示されませんでした。『一時的なコンテキストを再利用する』が有効にされていると，新規プロセスを作成する代わりに4D Mobile（REST）プロセスが再利用されました。

* ACI0098565 未定義のオブジェクト型プロパティなど，``undefined``をコンパイルモードでテキスト型に代入した場合，何も代入されませんでした。インタープリターモードのように，空の文字列が代入されるべきです。