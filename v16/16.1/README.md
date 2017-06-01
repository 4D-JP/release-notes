## 4D v16.1 

[4D v16.0 Hotfix 2](https://github.com/4D-JP/release-notes/blob/master/v16/16.0/hf2/)および[4D v16.0 Hotfix 1](https://github.com/4D-JP/release-notes/blob/master/v16/16.0/hf1/)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0096189 ``SQL LOGIN``に空の文字列を渡して接続ダイアログを表示した場合，認証情報が正しくても必ずログインに失敗しました。同じ情報をコマンドに引数で渡せばログインに成功します。

---

* ACI0095370 Mac版のみ。``On Column Resize``イベントが有効にされたリストボックスのリサイズイベントにブレークポイントを設定してトレースしようとすると，アプリケーションがハングしました。

* ACI0095842 ライセンス管理画面には，「4D Write」「4D View」とではなく，「4D Write | 4D Write Pro」「4D View | 4D View Pro」と表示されるべきでした。

* ACI0096074 64ビット版のみ。シートウィンドウの背景色は，親ウィンドウのものと同じカラーで表示されました。

* ACI0096142 クエリ定義ファイル (``.4DF``) をクエリエディターで読み込み，論理演算子を変更して再保存した場合，論理演算子が保存されませんでした。

* ACI0096144 オブジェクト型フィールドに対して中``QUERY BY ATTRIBUTE``でクエリを実行した場合，クライアント/サーバー版では，日付属性の値が``null``または存在しないレコードはヒットしませんでした。

* ACI0096194 ``LISTBOX SET ROW HEIGHT``で特定行の高さを変更した後，``LISTBOX SET ROWS HEIGHT``で全体の行高さを変更すると，縦スクロールできる距離の計算が狂ってしまい，最終行まで表示することができませんでした。
