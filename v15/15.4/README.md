4D v15.4 
---

[4D v15.3 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v15/15.3/hf1)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0096078 ポップアップメニューの項目に空の文字列が存在する場合，0番項目の代わりにその項目が選択されました。

* ACI0096166 遅いネットワークでは，HTTPクライアント（``WEB SERVICE CALL``，``HTTP Get``, ``HTTP request``）が途中で制御を返しました（``200 OK``）。

**注記**: macOSでは，[Network Link Conditioner](https://developer.apple.com/download/more/)をインストールすることにより，遅いネットワークのシミュレーションをすることができます。

* ACI0095550 メソッドエディター内で取り消し/やり直し（``command+Z`` / ``command+Shift+Z``）操作をした場合，変換候補ひとつずつが入力の履歴として扱われました。

---

* ACI0096063 [PRINT LABEL](http://doc.4d.com/4dv15r/help/command/ja/page39.html)でフォームを印刷した場合，テキストの水平整列が常に「左揃え」になりました。

* ACI0096167 Mac版のみ。メイン画面以外のディスプレイにフォームを表示した場合，コンボボックスをクリックしてもドロップダウンメニューが表示されませんでした。``ACI0096062``が修正されたことの副作用でした。

* ACI0095994 [GOTO OBJECT](http://doc.4d.com/4dv15r/help/command/ja/page206.html)の速度がv13と比較してずっと遅くなりました。

**注記**: このコマンドは，イベントサイクルの終わりに実行されていました。そのため，``On Losing Focus``イベント中に使用された場合，次のイベントサイクルが処理されるタイミングまで遅延されることがありました。

* ACI0096138 Windows版のみ。リストボックスのセル内で``Tab``文字が表示されませんでした。

* ACI0096157 リストボックスのセルに文字列をペーストした場合，``On After Edit``イベントが発生しませんでした。

* ACI0095216 ``command``+``option``+右クリック（Mac）または``Shift``+``Alt``+右クリック（Windows）でプロセスメニューを表示し，プロセスに割り込んだ場合，間違ったプロセスのデバッガが表示されたり，デバッガがまったく表示されないことがありました。

* ACI0085050 Bootcampで起動したWindowsをMacのRetinaディスプレイに表示した場合，デバッガのツールバーが表示されませんでした。通常のWindowsでは問題ありません。

* ACI0096177 プレビュー部分が非表示にされた状態でエクスプローラーを閉じ，ショートカット（``Control``+``Shift``+``Alt``+``E``）で再表示させた場合，プレビュー部分を表示させるためのボタンアイコンが間違っていました。その状態でテーブルのフィールドを選択すると，アプリケーションがクラッシュしました。

**注記**: 下記のファイルを削除することにより，エクスプローラーのフォーム設定を初期化することができます。

- Windows: ``C:\Users\<ユーザー名>\AppData\Roaming\4D\``
- Mac: ``/Users/<ユーザー名>/Library/Application Support/4D/``

* ACI0092113 Windows版のみ。フォームにリサイズハンドルがあり，ウインドウの右下いっぱいにリストボックスが配置されていた場合，リストボックスのスクロールバーとフォームにリサイズハンドルが同じ位置に表示されました。そのため，クリックで下方スクロール操作をすることができませんでした。

**注記**: 修正により，「グローボックスを隠す」プロパティが有効にされていれば，スクロールバーのほうが表示され，クリックで下方スクロール操作をすることができるようになりました。プロパティが有効にされていない場合，リサイズハンドルのほうが表示され，クリックで下方スクロール操作をすることはできません。

* ACI0095137 フォームエディターで複数のテキスト入力オブジェクトを水平方向に均等配置した場合，オブジェクトのサイズが変化することがありました。

* ACI0095947 クイックレポートの出力先をテキストまたはHTMLファイルに指定した場合，時間フィールドの値が秒数に換算されて出力されました。通常の印刷では問題ありません。

* ACI0096183 ユーザーフォームエディターにスタティックテキストオブジェクトを追加し，テキストが編集中の状態でエディターの左上にある「以前のバージョンに戻す」ボタンをクリックすると，アプリケーションがクラッシュしました。

* ACI0096235 フォームエディターのツールボタンでオブジェクトの入力順だけを変更した場合，変更内容が保存されませんでした。

* ACI0094987 ``LISTBOX SELECT BREAK``コマンドをメソッドエディターに入力した場合，第3引数に渡すことができる定数の候補が提案されませんでした。 

* ACI0096029 ``tab``キーでフィールドに移動した直後，カーソルの点滅が表示されない状態から開始しました。素早く``tab``キーで移動した場合，1秒間待たなければ，どこにカーソルが置かれているのか，わかりませんでした。

* ACI0096284 Windows版のみ。サービス起動した4D Serverで自動アップデートを実行した場合，タイミングの関係（フォルダーがロックされている）でアプリケーションの入れ替えに失敗することがありました。

* ACI0094989 テーブルにタイトル名を設定した場合，インポート画面にはテーブル名ではなくタイトル名でソートされたテーブルリストが表示されますが，そのような状態でインポートを実行すると，間違ったテーブルにデータが追加されました。

* ACI0096242 Windows版のみ。Access 2013からODBC経由でUUIDフィールドにアクセスするとエラーが返されました。Windows 10のExcel 2013からMS Queryの64ビット版でアクセスした場合は問題ありません。

* ACI0094528 Windows版のみ。マトリクスプリンター「Dascom 2600」に搭載されているプリンターフォントはプロパティリストに表示されませんでした。ツールボックス > スタイルシートには表示されます。

**注記**: 64ビット版では，印刷にデフォルトでDirect2Dテクノロジーが使用されます。画面には，Direct2Dに対応したフォントしか表示できないため，その大半がTrueTypeまたはOpenTypeであるプリンターフォントはフォームエディターのプロパティリストに含まれていませんでした。64ビット版でDirect2Dに対応していないフォントをフォームに使用することもできますが，画面と印刷の出力を一致させるためには，旧式のGDI印刷を有効にすることが勧められています。

```
SET PRINT OPTION(Legacy printing layer option;1)
```

* ACI0094537 ``FTP_GetDirList``は，6ヶ月以上前に更新されたファイルの更新時間を正しく返しませんでした。

* ACI0095712 リストボックスの自動アクションに「ページ移動」を設定した場合，クリックイベントでしかアクションが実行されませんでした。オブジェクトがフォーカス可であれば，上下矢印キーでも操作できるはずです。

**注記**: ページ移動後，リストボックスにフォーカスがとどまるようにするためには，下記のようなコードが必要です。

```
If (Form event=On Page Change)
	GOTO OBJECT(*;"List Box")
End if 
```

* ACI0095871 Mac版のみ。リストボックスのセルは，内容を編集している間だけ右揃えが左揃えになりました。

* ACI0095899 Mac版のみ。配列型リストボックスのヘッダータイトルは，ソートされているカラムだけ垂直揃えが上揃えになりました。
