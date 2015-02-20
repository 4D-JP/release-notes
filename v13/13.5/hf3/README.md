* ACI0091096 Windows版のみ，**13.5 HF1以降**，『[プリント時可変](http://doc.4d.com/4Dv13/4D/13.4/Printing-areas-of-variable-size.300-1226584.ja.html)』が設定された変数またはフィールドを印刷した場合のオブジェクトの高さが間違っていました。

* ACI0090847 Windows版のみ，[タブコントロール](http://doc.4d.com/4Dv13/4D/13.4/Tab-Controls.300-1226566.ja.html)は必要に応じてタブがスクロールするようになっていますが，v13以降，表示されていないタブをコマンドで選択した場合，v11のようにタブコントロールが自動的にスクロールしませんでした。

* ACI0090844 フォント名（font-family属性）が小文字だけで指定（例: Arialではなくarial）されたSVGを印刷した場合，あるいは[WRITE PICTURE FILE](http://doc.4d.com/4Dv13/4D/13.5/WRITE-PICTURE-FILE.301-1458028.ja.html)でイメージをPNGやBMPに変換した場合，結果が正しくありませんでした。フォーム表示は問題ありません。【参考】[Highcharts](http://www.highcharts.com/) v4はそのようなSVGを出力するようです。
