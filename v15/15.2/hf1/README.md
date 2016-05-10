4D v15.2 Hotfix 1
---
* ACI0093268 Mac版のみ。4D Viewのスクロール速度に問題がありました。Macのトラックパッドやマウスでエリアを上下にスクロールした場合，エリアが2本指スワイプ操作にほとんどついてこられませんでした。スクロール速度が非常にゆっくりで，移動の開始も遅れがちでした。今回の修正で4D Write, 4D View, プロパティリスト，クイックレポートの動作が改良されました。

* ACI0094561 サイズの小さなBLOBに対して[EXPAND BLOB](http://doc.4d.com/4Dv15/4D/15.1/EXPAND-BLOB.301-2686170.ja.html)のgzip圧縮を使用すると，エラーメッセージが表示されました。

```
C_BLOB($blbContent)
C_LONGINT($lngIsCompressed)

CONVERT FROM TEXT("test";"UTF-8";$blbContent)
COMPRESS BLOB($blbContent;GZIP best compression mode)

BLOB PROPERTIES($blbContent;$lngIsCompressed)
If ($lngIsCompressed#0)
  EXPAND BLOB($blbContent)
End if
```

* ACI0094933 メソッドエディターに[REDRAW WINDOW](http://doc.4d.com/4Dv15/4D/15.1/REDRAW-WINDOW.301-2686137.ja.html)と入力した後，コマンド名の上にマウスポインターを置くとシンタックスが表示されますが，その内容に誤記がありました。

* 誤 ``REDRAW WINDOW( windows )} ``

* 正 ``REDRAW WINDOW{( windows )} ``
  
* ACI0094740 [SELECTION RANGE TO ARRAY](http://doc.4d.com/4Dv15/4D/15.1/SELECTION-RANGE-TO-ARRAY.301-2685271.ja.html)で不正なセレクション範囲を指定した場合，アプリケーションがクラッシュしました。

```
//テーブルにレコードは1件のみ
ALL RECORDS([Table_1])
SELECTION RANGE TO ARRAY(3;2;[Table_1];$a)
```

* ACI0094964 [QUERY BY FORMULA](http://doc.4d.com/4Dv15/4D/15.1/QUERY-BY-FORMULA.301-2685583.ja.html)の動作がv13とv15では違いました。たとえば，下記のようなリレーションが3テーブル間に設定されている場合，v13で瞬時だったクエリがv15では0.2秒ほどになりました。

```
[PA_SEJOUR] 1<-N [PA_MVT] 1<-N [MVT_ACTES]
```

運用ではセレクションのサイズがあるので，ユーザーが苛立ちを感じるほどに時間がかかります。クエリパスを比較すると，明らかにv12とv15では違う処理がなされており，v15では途中でおおきな結果セットが作られていることがわかります。

* ACI0094401  クロスタブ型クイックレポート内の時間フィールドは，[Sum](http://doc.4d.com/4Dv15/4D/15.1/Sum.301-2686264.ja.html)の計算値が正しくありませんでした。小計値は秒単位，合計値は時間単位で値が表示されました。

* ACI0094120 ``$0``に値を返すようなメソッドが式ウォッチに登録されている状況で，[TRACE](http://doc.4d.com/4Dv15/4D/15.1/TRACE.301-2684990.ja.html)が使用されているメソッドを実行した場合，3回目のトレース以降はデバッガが使用できなくなりました。

* ACI0094029 [SET DATABASE PARAMETER](http://doc.4d.com/4Dv15/4D/15.1/SET-DATABASE-PARAMETER.301-2686308.ja.html)で``Circular log limitation``を指定すれば，ログファイルの数が最新のn個に制限されるはずですが，クライアント側では設定が無視され，延々とファイルが増えてゆきました。ターミナルクライアントはディスク容量が限られているため，このコマンドが特に必要です。

* ACI0091689 Windows版のみ。マーカーをcontrolクリックで削除することができませんでした。

* ACI0092682 メソッド内に変数名がいくつも含まれる場合，日本語入力中に表示されるガイドラインの位置が左にずれて表示されました。

* ACI0094028 Mac版のみ。おおきな外部モニターをメイン画面として使用した場合，内部モニター（サブ画面）でクリックしたポップアップメニューの表示される位置が正しくありませんでした。 

* ACI0094194 Windows版のみ。ドロップダウンリストを矢印キーでスクロールし，Enterキーで選択および確定すると，アプリケーションがクラッシュしました。

* ACI0094314 Mac版のみ。[SET PRINT PREVIEW](http://doc.4d.com/4Dv15/4D/15.1/SET-PRINT-PREVIEW.301-2685618.ja.html)を実行すると，それまでに設定した用紙の向きがリセットされました。本来，コマンドの実行順序は関係ないはずです。

* ACI0094435 Mac版のみ。OS X 10.11 El Capitanでは，既定サイズよりも背の高いコンボボックスは正しく表示されませんでした。

* ACI0094454 リストフォームをダブルクリックしても，[FILTER EVENT](http://doc.4d.com/4Dv15/4D/15.1/FILTER-EVENT.301-2685822.ja.html)で画面の遷移を抑制することができます。ダブルクリックをフィルターして表示したダイアログから表示したダイアログを続けてキャンセルした場合，最初のリスト画面に復帰する代わりにフィルターしたはずの入力画面が表示されました。つまり，ダイアログを続けたことにより，フィルターが無効になりました。

* ACI0094739 Windows版のみ。終了処理中にメニューバークリックするとアプリケーションがクラッシュしました。

* ACI0094773 Mac版のみ。Retinaディスプレイに表示された4D Writeエリアに対して何かをドロップすると，画面の表示が乱れました。

* ACI0094861 [PRINTERS LIST](http://doc.4d.com/4Dv15/4D/15.1/PRINTERS-LIST.301-2685608.ja.html)が原因でクラッシュすることがありました。極めて特殊な状況でなければ再現しません。

* ACI0083980 データベース設定でメッセージフォントをクリックし，フォントピッカーをキャンセルしても，ピッカーで選択されていたフォントが採用されました。

* ACI0089399 コンポーネントメソッドを[4DACTION](http://doc.4d.com/4Dv15/4D/15.1/URLs-and-Form-Actions.300-2685147.ja.html)で呼び出すことができませんでした。

* ACI0093962 Mac版のみ。テキスト終わりにある空白をダブルクリックした場合，本来であれば最後のワードまたは空白が選択されるはずですが，何も起きませんでした。

* ACI0094045 [WR SAVE DOCUMENT](http://doc.4d.com/4Dv15/4D-Write/15/WR-SAVE-DOCUMENT.301-2398576.ja.html)でドキュメントをUTF-8形式で保存した場合，拡張子``txt``が省略されました。

```
$vl_Template:=WR New offscreen area 
$vt_Document:=System folder(Desktop)+"test.txt"
WR INSERT TEXT ($vl_Template;"4D is the best!!!")
WR SAVE DOCUMENT ($vl_Template;$vt_Document;wr unicode document UTF8)
WR DELETE OFFSCREEN AREA ($vl_Template)
```

* ACI0094410 バーコードフォントなど，一部のフォント名がラベルエディターのフォントリストに表示されませんでした。

注記: 表示されないフォント名は，現行のAPIではサポートされていないものです。（旧式のAPIを使用している）ラベルエディターのリストは修正されましたが，プロパティリストおよび[FONT LIST](http://doc.4d.com/4Dv15R3/4D/15-R3/FONT-LIST.301-2695248.ja.html)は，引き続き現行のフォント名だけが列挙されます。

* ACI0094451 SQL ``INTO``でBLOBフィールドをBLOB配列にコピーしようとしても，配列にデータが転写されませんでした。

* ACI0094502 Mac版のみ。iMacテンキーの``clear``を入力した場合，何もテキストが選択されていなければ，何も起きず，テキストが選択されていれば，制御文字が挿入されました。v13以前は，いずれの場合も制御文字が挿入されました。正しい動作は，選択されたテキストを削除するというものです。
