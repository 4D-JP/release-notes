4D v15.2
---

[4D v15.1 Hotfix 2](https://github.com/4D-JP/release-notes/blob/master/v15/15.1/hf2/README.md)および[Hotfix 1](https://github.com/4D-JP/release-notes/blob/master/v15/15.1/hf1/README.md)の修正事項は，それぞれのページに掲載されています。

* ACI0094644 クイックレポートエディターにフォーミュラーを入力しようとすると，キーストロークが二重に処理されました。たとえば，``substring``とタイプ入力した場合，``ssuubbssttrriinngg``というフォーミュラーになりました。通常のフォーミュラーエディターでは問題ありません。15.1には存在しなかった不具合です。

* ACI0093985 サーバー選択ダイアログには，日本語のコンピューター名が``?``という文字で表示されました。新しいネットワークレイヤー特有の問題です。

* ACI0094548 Windows版のみ。``AP FULL SCREEN``または``AP NORMAL SCREEN``どちらかのコマンドを繰り返し使用していると，アプリケーションがクラッシュしました。不具合はプラグイン側で修正されています。確認するために4Dのバージョンを入れ替える必要はありません。

* ACI0094196 Windows版のみ。``Pop up form window``および`` Toolbar form window``タイプのウインドウ上では，``On Mouse Move``イベントが発生しませんでした。 ACI0094688と同じ問題です。

* ACI0094734 Mac版のクライアントで，ようこそ画面を閉じることによってデザインモードに切り替えた後，終了メニューを選択すると，クライアントがフリーズしました。

* ACI0093455 Mac版の4D Viewの[PV SET CELL PROPERTY](http://doc.4d.com/4Dv15/4D-View/15/PV-SET-CELL-PROPERTY.301-2061444.ja.html)コマンドに``pv style color text odd``を指定した場合，実際には``pv style automatic word wrap``が変化しました。16進数で表現したRGB値の赤と緑が入れ替わっているような振る舞いでした。

* ACI0093887 Mac版の4D Viewに追加したテキストの色が正しくありませんでした。

* ACI0094208 クリックレポートエディターのカラムヘッダーをトリプルクリックすると，起動したフォーミュラーエディターがクリックレポートエディターの背後に移動してしまい，画面を閉じることができなくなりました。

* ACI0094557 OS X El Capitanのみ。フルスクリーンモードでウインドウが表示されているときに``Escape``キーを入力すると，アプリケーションがクラッシュしました。

* ACI0094501 Windows版のみ。階層リストボックスに入力できる通常の列とチェックボックス型の列が表示されているときに，``Tab``キーでチェックボックス型の列にフォーカスを移動すると，アプリケーションがクラッシュしました。

* ACI0094491 [SMTP_SetPrefs](http://doc.4d.com/4Dv15/4D-Internet-Commands/15/SMTP-SetPrefs.301-2397898.ja.html)でエンコーディングを設定した後，[SMTP_Charset](http://doc.4d.com/4Dv15/4D-Internet-Commands/15/SMTP-Charset.301-2397916.ja.html)でメールの件名だけにエンコーディングが適用されるように指定 (``$Error:=SMTP_Charset (1;0)``) した場合，メールの本文にもエンコーディングが適用されました。
