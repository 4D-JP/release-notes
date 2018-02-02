## 4D v16.4
[4D v16.3 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf1/)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0097778 ``BASE64 ENCODE``から返される文字列は，``40,000``文字ごとに改行コード``CR`` ``LF``が挿入されました。

---

* ACI0097715 64ビット版のみ。テーブルに非表示フィールドが存在する場合，そのフィールド以降のフィールドタイトルがクイックレポートエディターに正しく表示されませんでした。

* ACI0097390 ``On Web Connection``データベースメソッドで``WEB SEND TEXT``の後に``QUERY SELECTION``がコールされた場合，アプリケーションがクラッシュしました。

* ACI0097838 オブジェクト型フィールドのスカラー属性に対する4D Mobileクエリの結果が正しくありませんでした。
