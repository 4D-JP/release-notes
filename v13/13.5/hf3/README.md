* ACI0090575 [MSG_Extract](http://doc.4d.com/4Dv13/4D/13.2/MSG-Extract.301-1086702.ja.html)は，RFCエンコード（例: U%CC%88berarbeitete%20Offerte.pdf）されたUnicodeファイル名を正しく展開しませんでした。

* ACI0090444 ピクチャフィールドが『[プリント時可変](http://doc.4d.com/4Dv13/4D/13.4/Printing-areas-of-variable-size.300-1226584.ja.html)』に設定されていた場合，イメージが印刷されませんでした。

* ACI0090378 HTTPヘッダーの『accept』フィールドに『compress, gzip, identify』が含まれていた場合，[On Web Connection](http://doc.4d.com/4Dv13/4D/13.5/On-Web-Connection-Database-Method.300-1457408.ja.html)に制御が渡らず，406エラーが返されました。

* ACI0090363 Mac版のみ，fill属性が『none』に設定されているSVGイメージを印刷すると，その部分は黒く塗りつぶされたように出力されました。

* ACI0090343 Windows版のみ，サブレコード追加のキーボードショートカットを『control+<』に設定した場合，一度の入力でレコードが2件，追加されました。WM_KEYDOWNメッセージをWM_CHARに変換するための例外的な処理（control+<で必要だった）がいまでは必要ないようです。

* ACI0090259 Webサービスで公開されたメソッドの入力パラメーターにローカル変数が使用できませんでした。（コンパイルモードで『EXECUTEメソッドのパラメータが不正』ランタイムエラーが返されました。）プロセス変数（Compiler_WEBで宣言）であれば問題ありません。

* ACI0087679 リストボックスに非表示の列が含まれている場合，その列よりも右側の列をドラッグしたときに表示される列の挿入ポイントが間違っていました。

* ACI0091096 Windows版のみ，**13.5 HF1以降**，『[プリント時可変](http://doc.4d.com/4Dv13/4D/13.4/Printing-areas-of-variable-size.300-1226584.ja.html)』が設定された変数またはフィールドを印刷した場合のオブジェクトの高さが間違っていました。

* ACI0090847 Windows版のみ，[タブコントロール](http://doc.4d.com/4Dv13/4D/13.4/Tab-Controls.300-1226566.ja.html)は必要に応じてタブがスクロールするようになっていますが，v13以降，表示されていないタブをコマンドで選択した場合，v11のようにタブコントロールが自動的にスクロールしませんでした。

* ACI0090844 フォント名（font-family属性）が小文字だけで指定（例: Arialではなくarial）されたSVGを印刷した場合，あるいは[WRITE PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/WRITE-PICTURE-FILE.301-1458028.ja.html)でイメージをPNGやBMPに変換した場合，結果が正しくありませんでした。フォーム表示は問題ありません。

【参考】[Highcharts](http://www.highcharts.com/) v4はそのようなSVGを出力するようです。

* ACI0085460 **13.4以降**，HTML式が埋め込まれた4D Write文書をHTML4形式で出力した場合，HTMLの開始タグと終了タグが誤ってエスケープされました。

* ACI0080677 Mac版のみ，コードエディターにいくらかの日本語を入力した後，それ以上は戻れなくなるところまで『取り消し』（command+Z）した後に『やり直し』（command+shift+Z）した場合，元のテキストが複製されました。

* ACI0057942 アプリケーションビルドのダイアログ画面でUnlimited Desktopのライセンス（.licence4D）を追加した場合，MasterとExpansionに同一のライセンス番号が表示されました。

* ACI0087370 [13.5 Hotfix 2](http://www.4d.com/jp/blog/about-13-5-2.html)で改善された問題がさらに修正されました。
 
* ACI0090753 ピクチャオブジェクトのコンテキストメニューまたは[READ PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/READ-PICTURE-FILE.301-1458029.ja.html)でインポートしたイメージ，あるいは [SET PICTURE FILE NAME](http://doc.4d.com/4Dv13/4D/13.5/SET-PICTURE-FILE-NAME.301-1458048.ja.html)で名前を設定したイメージのファイル名を[Get picture file name](http://doc.4d.com/4Dv13/4D/13.5/Get-picture-file-name.301-1458051.ja.html)で参照した場合，最初は名前が返されますが，4D Remoteでレコードを再ロードした後は空の文字列が返されました。シングルユーザー版または4D Server（ストアドプロシージャー）では問題ありません。
