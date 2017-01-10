4D v15.4 
---

``Nightly Build (207499)``

[4D v15.3 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v15/15.3/hf1)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0096166 遅いネットワークでは，HTTPクライアント（``WEB SERVICE CALL``，``HTTP Get``, ``HTTP request``）が途中で制御を返しました（``200 OK``）。

**注記**: macOSでは，[Network Link Conditioner](https://developer.apple.com/download/more/)をインストールすることにより，遅いネットワークのシミュレーションをすることができます。

* ACI0095550 メソッドエディター内で取り消し/やり直し（``command+Z`` / ``command+Shift+Z``）操作をした場合，変換候補ひとつずつが入力の履歴として扱われました。

---

* ACI0096063 [PRINT LABEL](http://doc.4d.com/4dv15r/help/command/ja/page39.html)でフォームを印刷した場合，テキストの水平整列が常に「左揃え」になりました。

* ACI0096167 Mac版のみ。メイン画面以外のディスプレイにフォームを表示した場合，コンボボックスをクリックしてもドロップダウンメニューが表示されませんでした。``ACI0096062``が修正されたことの副作用でした。

* ACI0095994 [GOTO OBJECT](http://doc.4d.com/4dv15r/help/command/ja/page206.html)の速度がv13と比較してずっと遅くなりました。

**注記**: このコマンドは，イベントサイクルの終わりに実行されていました。そのため，``On Losing Focus``イベント中に使用された場合，次のイベントサイクルが処理されるタイミングまで遅延されることがありました。
