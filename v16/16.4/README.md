## 4D v16.4
[4D v16.3 Hotfix 3](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf3/)および[4D v16.3 Hotfix 2](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf2/)および[4D v16.3 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf1/)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0098038 日本語変換中は矢印キーでカーソルの位置を移動することができませんでした。

---

* ACI0098245 Windows版のみ。フォームオブジェクトに``Tahoma``フォントが使用されている場合，``Wingdings``フォントが代わりに表示されました。Window 10 1803アップデート以降の問題です。問題はランタイムモードだけで発生し，フォームエディターで再保存すると解消されます。

**注記**: フォントを番号で参照する古い手法で作成されたフォームで問題が発生します。

* ACI0098184 4D Write文書に埋め込まれた``Num(...) * "..."``のような式は，4D Write Proに変換した後，正しく評価されませんでした。

* ACI0097912 クライアント/サーバー通信の暗号化が有効にされており，データベース設定でアプリケーション開始時にWebサーバーが自動的に起動するように設定されていた場合，中間証明書のチェーンが不完全となり，セキュリティ評価が下がりました。メニューやコマンドでWebサーバーを起動した場合には問題ありません。

* ACI0098278 4D Write文書を4D Write Proに変換した後，テキストが失われてしまい，空のページになってしまうことがありました。
