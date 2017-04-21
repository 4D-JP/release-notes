## 4D v16.1 

``210503``

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0096548 Mac版のみ。ファイルサイズが0のドキュメントを``Document to text``で読み込もうとすると，``utf-8``エンコーディングを指定しない限り，error in user parameter list (paramErr) というエラーが返されました。

---

* ACI0096314 何もエラーが発生していない状況で``XML GET ERROR``を実行すると，アプリケーションが終了しました。

```
C_TEXT($Ref;$Error)
$Ref:=DOM Create XML Ref("my_root")
TRACE
XML GET ERROR($Ref;$Error)
DOM CLOSE XML($Ref)
```

* ACI0096589 ``LISTBOX SET HIERARCHY``でページ2以降に配置された階層リストボックスの階層を操作した後，`` FORM GOTO PAGE``でそのページに移動しようとすると，アプリケーションが終了しました。

* ACI0094940 クイックレポートエディターを起動した後，プリントプレビューを実行すると，エディター上のラベル「レコード/セレクション」および「レコード/テーブル」が消え，それぞれ数だけが画面上に表示されました。

* ACI0096560 階層リストボックスのたたまれた行に対して``EDIT ITEM``を実行した場合，その階層が表示されるようになりますが，その後，出現した分の行数だけ移動できる距離が下方向に延長されておらず，最後までスクロールすることができませんでした。

* ACI0096595 デザインモード・ツールバーの「新規」ボタンは，メソッドエディターやフォームエディターを使用しているときでも，常に新規データベースの作成ダイアログを表示しました。エディターが開かれているときは，状況に応じ，新規テーブル・メソッド・フォームの作成ダイアログが表示されるべきです。

* ACI0096600 Windows 32ビット版のみ。リストフォームを印刷（``XPS``プレビューを含む）すると，背景色の設定されたスタイル付きテキストの位置がずれました。

* ACI0096464 Windows版のみ。``OB GET``コマンドは，16進数表記の整数を変換しませんでした。たとえば，``0x00FFFFFF``を取り出そうとした場合，``16777215``ではなく，``0``が返されました。

```
C_OBJECT($obj)
C_LONGINT($decimal)
C_TEXT($hex)

OB SET($obj;"hex";"0x00FFFFFF")
$decimal:=OB Get($obj;"hex";Is longint) 
```

* ACI0096386 4D Server上でWebサーバーを起動した後に管理者（``Administrator``）のパスワードを変更した場合，``On Web Authentication``データベースメソッドが実行されると，以前のパスワードに戻ってしまいました。デスクトップ版では問題ありません。また，``Designer``や一般ユーザーアカウントも問題ありません。