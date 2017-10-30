## 4D v15.6

* ACI0097282 SQLの``SELECT``文で時間型フィールドをテキストに``CAST``すると，該当する時間がミリ秒で返されました。たとえば，午前1時（``01:00``）に対し，``3600000``	が返されました。期待されるのは，以前のバージョンのように，``0:1:0:0``が返されることです。

* ACI0097063 64ビット版のみ。JOINを活用した複雑なSQLを続けて実行していると，サーバーアプリケーションがクラッシュすることがありました。