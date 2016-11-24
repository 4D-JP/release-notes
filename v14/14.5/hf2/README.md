4D v14.5 Hotfix 2
---

[4D v14.5 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v14/14.5/hf1)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0095632 日本語版のみ。Windows 7では，ストラチャエディターのインスペクターは入力エリアの高さが不足しているため，日本語変換中のガイドラインが表示されませんでした。Windows 10では問題ありません。

* ACI0095089 Windows日本語版のみ。ファイル > 書き出し > ストラクチャ定義をHTMLに書き出し...を選択しても，エクスポートされるのはXMLファイルのほうでした。

---

* ACI0094194 Windows版のみ。ポップアップメニューアイテムをキーボートで確定した直後に[CONFIRM](http://doc.4d.com/4Dv15R5/4D/15-R5/CONFIRM.301-2936614.ja.html)コマンドを実行すると，アプリケーションがクラッシュしました。

* ACI0095018 [外部ファイルのユーザー設定を有効にする](http://doc.4d.com/4Dv15R5/4D/15-R5/Using-user-settings.300-2964123.ja.html)がチェックされていないまま下記のコードを実行すると，アプリケーションがクラッシュしました。

```
OPEN SETTINGS WINDOW("/Database";True;User settings)
```

* ACI0095163 フランス語版のみ。``ST FIXER TEXTE BRUT``のヘルプTipsが英語でした。

* ACI0091205 [SAX Get XML node](http://doc.4d.com/4dv15r/help/command/ja/page860.html)コマンドは，32,768行目以降で発生したエラーの行番号がエラースタックに返されませんでした。

* ACI0095446 ユーザー設定が無効にされた状態で``OPEN SETTINGS WINDOW("/Database";True;User settings)``を実行すると，シンタックスエラーが返されました。しかし，エラーメッセージがありません。「ユーザーデータベース設定が有効化されていません。」というエラーメッセージが表示されるべきでした。

* ACI0090910 新ネットワークレイヤーが有効にされた64ビット版サーバーにMacまたはWindowsのクライアントから接続しようとすると，エラー``-19191``が返されました。それ自体は正しいことなのですが，エラーメッセージが空でした。

**注記**: 修正により「使用しているネットワークレイヤーが異なるのでサーバーに接続できません。クライアントアプリケーションをアップグレードして下さい。」というメッセージが表示されるようになりました。

* ACI0095177 Windows版のみ。フルスクリーンモードの4D Viewは，テキストに続けてタブまたは改行を入力すると，テキストが消えました。

* ACI0088141 ストラクチャエディターのインデックスエクスプローラー画面で，矢印キーを使用してフィールドの順番を変更すると，エラー``-20001``（配列の範囲チェック）が返されました。

* ACI0095653 4D Viewエリアのプロパティリストに[詳細設定](http://doc.4d.com/4Dv15R4/4D/15-R4/Plug-in-areas.300-2880332.ja.html)ボタンが表示されませんでした。

* ACI0091264 ``String``で``ISO Date GMT``フォーマットに日付と時間を変換した場合，夏時間（フランスでは3月29日の早朝3時から実施）を反映しませんでした。以前のプラグイン``AP Timestamp to GMT``では問題ありませんでした。

* ACI0091810 フォームエディターでリストボックスの列を複製し，``command+Z``で取り消した直後の再描画が崩れていました。