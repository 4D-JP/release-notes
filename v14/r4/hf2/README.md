[4D v14 R4 Hotfix 2](http://forums.4d.fr/Post/FR/15925866/1/15925867)
---

* ACI0091293 **R4以降**，コンボボックスにテキストを入力中，On After Edit, On Before Keystroke, On After Keystrokeイベントに続けて発生したOn Data Changeイベントをトレースした場合，デバッガが即座に閉じられるようになりました。（On Data Changeと前述したイベント群が両方とも設定されていなければ大丈夫です。）

* ACI0090646 [Resoucesフォルダー](http://doc.4d.com/4Dv14/4D/14/Managing-the-Resources-folder.300-1242116.ja.html)の内容は，変更がない限り，サーバーからクライアントに転送されないはずですが，**R4以降**，毎回の接続でフォルダーの同期が始まるようになりました。（互換性オプション『[旧式ネットワークレイヤーを使用する](http://doc.4d.com/4Dv14R4/4D/14-R4/Network-compatibility-option-important-note.300-1756365.ja.html)』が解除されていれば，問題ありませんが，このオプションを解除することは推奨されていません。）

* ACI0090520 **R4以降**，4D Viewコマンドにポインターを渡すことができなくなりました。例: ```$textPtr->:=PV Get cell text value ($areaPtr->;$colPtr->;$rowPtr->)```

* ACI0090496 **R4以降**，Windows版のみ，フォームに貼り付けられたスタティックイメージの表示される位置が，フォームエディターとフォーム実行時では少し違うようになりました。ペイントから直接ペーストしたものなど，直接フォームエディターに貼り付けたEMF形式の画像で問題が発生します。BMPやPNGでは問題ありません。

* ACI0089846 **R4以降**，Windows版のみ，プラグインがロードされたアプリケーションを終了すると，プラグインをアンロードするタイミングでクラッシュしました。
