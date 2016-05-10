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

[PA_SEJOUR] 1<-N [PA_MVT] 1<-N [MVT_ACTES]

運用ではセレクションのサイズがあるので，ユーザーが苛立ちを感じるほどに時間がかかります。クエリパスを比較すると，明らかにv12とv15では違う処理がなされており，v15では途中でおおきな結果セットが作られていることがわかります。

```
//v12
AND
Join on Table : PA_SEJOUR , PA_MVT.Num_Admission = PA_SEJOUR.Num_admission , MVT_ACTES.Cle_MVT = PA_MVT.Cle_MVT
OR
[index : PA_SEJOUR.Num_admission ] = 160201001 (1 record found in 0 ms)
[index : PA_SEJOUR.Num_Admission1 ] = 160201001 (0 record found in 0 ms)
--> 1 record found in 0 ms
[index : PA_MVT.Num_Admission ] = <Array of Values> (1 record found in 0 ms)
--> 6 records found in 0 ms
AND
[index : MVT_ACTES.Type ] = BIOLOGIE (4 records found in 0 ms)
MVT_ACTES.Supprime LIKE false (4 records found in 0 ms)
MVT_ACTES.DeSortie LIKE false (4 records found in 0 ms)
MVT_ACTES.Signe_dte NOT LIKE 00/00/0 00:00:00 Or 4D Script (4 records found in 0 ms)
MVT_ACTES.Executant_type = INFIRMIERE Or MVT_ACTES.Executant_type = (4 records found in 0 ms)
MVT_ACTES.Date_debut <= 06/04/2016 00:00:00 Or 4D Script Or 4D Script (4 records found in 0 ms)
MVT_ACTES.Charge_dte LIKE 00/00/0 00:00:00 Or (4D Script And MVT_ACTES.Arret_dte LIKE 06/04/2016 00:00:00 And 4D Script) (0 record found in 0 ms)
--> 0 record found in 0 ms
--> 0 record found in 0 ms
```

```
//v15
AND
AND
[index : MVT_ACTES.Type ] = BIOLOGIE (14043 records found in 0 ms)
MVT_ACTES.Supprime == false (13259 records found in 21 ms)
MVT_ACTES.DeSortie == false (13198 records found in 12 ms)
MVT_ACTES.Signe_dte != 00/00/0 00:00 Or Vrai=Faux (11629 records found in 36 ms)
MVT_ACTES.Executant_type === INFIRMIERE Or MVT_ACTES.Executant_type === (11629 records found in 11 ms)
MVT_ACTES.Date_debut <= 06/04/2016 00:00 Or Non(Faux) Or "BIOLOGIE"#"DI" (11629 records found in 70 ms)
MVT_ACTES.Charge_dte == 00/00/0 00:00 Or ("BIOLOGIE"="BIOLOGIE" And MVT_ACTES.Arret_dte == 06/04/2016 00:00 And [MVT_ACTES]Arret_dte#[MVT_ACTES]Date_debut) (34 records found in 84 ms)
--> 34 records found in 234 ms
Join on Table : PA_MVT : MVT_ACTES.Cle_MVT = PA_MVT.Cle_MVT
Join on Table : PA_SEJOUR : PA_MVT.Num_Admission = PA_SEJOUR.Num_admission
OR
[index : PA_SEJOUR.Num_admission ] = 160201001 (1 record found in 0 ms)
[index : PA_SEJOUR.Num_Admission1 ] = 160201001 (0 record found in 0 ms)
--> 1 record found in 0 ms
--> 1 record found in 0 ms
--> 0 record found in 0 ms
--> 0 record found in 234 ms
```

* ACI0094401  クロスタブ型クイックレポート内の時間フィールドは，[Sum](http://doc.4d.com/4Dv15/4D/15.1/Sum.301-2686264.ja.html)の計算値が正しくありませんでした。小計値は秒単位，合計値は時間単位で値が表示されました。

* ACI0094120 ``$0``に値を返すようなメソッドが式ウォッチに登録されている状況で，[TRACE](http://doc.4d.com/4Dv15/4D/15.1/TRACE.301-2684990.ja.html)が使用されているメソッドを実行した場合，3回目のトレース以降はデバッガが使用できなくなりました。

* ACI0094029 [SET DATABASE PARAMETER](http://doc.4d.com/4Dv15/4D/15.1/SET-DATABASE-PARAMETER.301-2686308.ja.html)で``Circular log limitation``を指定すれば，ログファイルの数が最新のn個に制限されるはずですが，クライアント側では設定が無視され，延々とファイルが増えてゆきました。ターミナルクライアントはディスク容量が限られているため，このコマンドが特に必要です。

* ACI0091689 Windows版のみ。マーカーをcontrolクリックで削除することができませんでした。

* ACI0092682 メソッド内に変数名がいくつも含まれる場合，日本語入力中に表示されるガイドラインの位置が左にずれて表示されました。
