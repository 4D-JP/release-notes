## 4D v16.4
[4D v16.3 Hotfix 2](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf2/)および[4D v16.3 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf1/)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0097834 64ビット版のみ。サーバー管理画面を閉じた後，メニューから再表示させることができませんでした。

---

* ACI0097381 Mac 32ビット版のみ。``SET CURRENT PRINTER``が初回は効きませんでした（「すべてのプリンター」の設定が有効になりました）。2回目以降の印刷は問題ありません。

* ACI0097932 Mac版のみ。``OPEN PRINTING JOB``および``CLOSE PRINTING JOB``コマンドでメモリーリークが発生しました。プリントジョブを終了しても，プロセスを終了するまでは印刷で使用したメモリが解放されないため，同一プロセス内で大量のページ数を印刷した場合，アプリケーションがクラッシュする恐れがありました。

* ACI0098002 Windows版のみ。フォームを何度も開いたり，閉じたりしていると，メニューバーが解放されるタイミングでアプリケーションがクラッシュする場合がありました。
