## 4D v15.5

[4D v15.4 Hotfix 1](https://github.com/4D-JP/release-notes/blob/master/v15/15.4/hf1/), [4D v15.4 Hotfix 2](https://github.com/4D-JP/release-notes/blob/master/v15/15.4/hf2/)および[4D v15.4 Hotfix 3](https://github.com/4D-JP/release-notes/blob/master/v15/15.4/hf3/)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

---

* ACI0096974 ツールボックスのリソースページで複数の項目をまとめて削除しようとすると，空の確認ダイアログが表示されました。

* ACI0096237 メソッドエディターのツールバーに表示されている番号付きクリップボードのヘルプTips正しくありませんでした。Macの場合，``command``+``shift``+``1``などと表示されますが，実際のショートカットは``command``+``option``+``1``です。Windowsの場合，``command``+``shift``+``1``などと表示されますが，実際のショートカットは``Control``+``Alt``+``1``です。

* ACI0096722 4D Write Proエリアを作成した直後，デフォルトで設定されたオブジェクト名がエディター上に表示されませんでした。4D View ProエリアやWebエリアのように，オブジェクト名または変数名（あれば）が表示されるべきです。

* ACI0096937 Windows版のみ。リストフォーム内で``On Display Detail``イベントが処理されている場合，マウスのロールボタンによるスクロールが少し遅くなります。その状態でスクロール中に右クリックイベントを処理し，``Pop up menu``でポップアップメニューを表示すると，アプリケーションが終了しました。
