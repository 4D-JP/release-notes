* ACI0091096 Windows版のみ，**13.5 HF1以降**，『[プリント時可変](http://doc.4d.com/4Dv13/4D/13.4/Printing-areas-of-variable-size.300-1226584.ja.html)』が設定された変数またはフィールドを印刷した場合のオブジェクトの高さが間違っていました。

* ACI0090847 Windows版のみ，[タブコントロール](http://doc.4d.com/4Dv13/4D/13.4/Tab-Controls.300-1226566.ja.html)は必要に応じてタブがスクロールするようになっていますが，v13以降，表示されていないタブをコマンドで選択した場合，v11のようにタブコントロールが自動的にスクロールしませんでした。

* ACI0090844 フォント名（font-family属性）が小文字だけで指定（例: Arialではなくarial）されたSVGを印刷した場合，あるいは[WRITE PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/WRITE-PICTURE-FILE.301-1458028.ja.html)でイメージをPNGやBMPに変換した場合，結果が正しくありませんでした。フォーム表示は問題ありません。【参考】[Highcharts](http://www.highcharts.com/) v4はそのようなSVGを出力するようです。

* ACI0085460 **13.4以降**，HTML式が埋め込まれた4D Write文書をHTML4形式で出力した場合，HTMLの開始タグと終了タグが誤ってエスケープされました。

* ACI0080677 Mac版のみ，コードエディターにいくらかの日本語を入力した後，それ以上は戻れなくなるところまで『取り消し』（command+Z）した後に『やり直し』（command+shift+Z）した場合，元のテキストが複製されました。

* ACI0057942 アプリケーションビルドのダイアログ画面でUnlimited Desktopのライセンス（.licence4D）を追加した場合，MasterとExpansionに同一のライセンス番号が表示されました。

* ACI0087370 [13.5 Hotfix 2](http://www.4d.com/jp/blog/about-13-5-2.html)で改善された問題がさらに修正されました。
 
* ACI0090753 ピクチャオブジェクトのコンテキストメニューまたは[READ PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/READ-PICTURE-FILE.301-1458029.ja.html)でインポートしたイメージ，あるいは [SET PICTURE FILE NAME](http://doc.4d.com/4Dv13/4D/13.5/SET-PICTURE-FILE-NAME.301-1458048.ja.html)で名前を設定したイメージのファイル名をGet picture file nameで参照した場合，最初は名前が返されますが，4D Remoteでレコードを再ロードした後は空の文字列が返されました。シングルユーザー版または4D Server（ストアドプロシージャー）では問題ありません。
