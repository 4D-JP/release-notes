4D v14.5 Hotfix 1
---
* ACI0093268 Mac版のみ。4D Viewのスクロール速度に問題がありました。Macのトラックパッドやマウスでエリアを上下にスクロールした場合，エリアが2本指スワイプ操作にほとんどついてこられませんでした。スクロール速度が非常にゆっくりで，移動の開始も遅れがちでした。今回の修正で下記の動作が改良されました。

4D Write　
4D View　
プロパティリスト
クリックレポート

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

* ACI0089399 コンポーネントメソッドを[4DACTION](http://doc.4d.com/4Dv15/4D/15.1/URLs-and-Form-Actions.300-2685147.ja.html)URLで呼び出すことができませんでした。

* ACI0092682 メソッド内に変数名がいくつも含まれる場合，日本語入力中に表示されるガイドラインの位置が左にずれて表示されました。

* ACI0094451 SQL ``INTO``でBLOBフィールドをBLOB配列にコピーしようとしても，配列にデータが転写されませんでした。

* ACI0094502 Mac版のみ。iMacテンキーの``clear``を入力した場合，何もテキストが選択されていなければ，何も起きず，テキストが選択されていれば，制御文字が挿入されました。v13以前は，いずれの場合も制御文字が挿入されました。正しい動作は，選択されたテキストを削除することです。

* ACI0065508 リストボックスの``On Display Detail``イベントが``On Load``よりも先に実行されました。

* ACI0093215 新ネットワークレイヤー使用時に多数（例: 75）のクライアントから同時にシーケンシャルクエリにリクエストが送られた場合，SOAPリクエストの処理でアプリケーションがフリーズ（デッドロック）に陥ることがありました。

* ACI0094909 Mac版のみ。OS X 10.11 "El Capitan"では4D for OCIプラグインが使用できませんでした。OCIライブラリを``/usr/lib``にインストールすることができなくなったためです。

参考: OCIライブラリのインストール方法

* ダウンロード (http://www.oracle.com/technetwork/topics/intel-macsoft-096467.html)
* ``instantclient-basic-macos.x32-11.2.0.4.0.zip``または``instantclient-basic-macos.x64-11.2.0.4.0.zip``を入手
* ``/usr/local/lib``にライブラリをインストール
- libclntsh.dylib.11.1
- libnnz11.dylib
- libocci.dylib.11.1
- libociei.dylib
- libocijdbc11.dylib
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
