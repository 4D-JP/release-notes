## 4D v16.4

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0096911 Mac版のみ。「サーバーに接続中」ウィンドウの「停止」ボタンをクリックしても，処理が中断されずにタイムアウトまで続きました。たとえば，入力したIPアドレスでサーバーが公開されていないような場合，接続の試みをすぐに停止することができませんでした。

**注記**: 64ビット版だけが修正されました。

* ACI0097129 Mac 64ビット版のみ。「終了」メニューのタイトルが日本語として不自然（「終了 4D」）でした。「4D を終了」と表示されるべきです。

* ACI0096996 管理画面を表示するためのキーボードショートカット（``Control``/``command``+``U``）が効きませんでした。

---

* ACI0097642 特定のSQL文を実行すると，アプリケーションがクラッシュしました。

```sql
Begin SQL
SELECT R.[Code], R.[Intitule], R.[Couleur_Planning], R.[Externe], E.[Ordre_Affichage], F.[Ordre_Affichage]
FROM [Element_Liste_Ressource] E
INNER JOIN [Famille_Ressource] F
ON E.[Famille] = F.[Famille]
INNER JOIN [Materiel] R
ON F.[Code_Materiel] = R.[Code]
WHERE E.[Code_Liste] = 73
AND E.[Portee_Element] = 2
AND E.[Type_Ressource] = 2
AND R.[Abandonne] = false
AND R.[Hors_Planning] = false
AND R.[Code] NOT IN (
SELECT PR.[Code_Materiel]
FROM [Protection_Ressource] PR
WHERE PR.[Type_Ressource] = 2
AND PR.[Code_Groupe] = 3
AND PR.[Protection_Lecture] = TRUE )
AND R.[Societe] IN ('Eclair Cinéma', 'Eclair Group', '', 'Eclair MEDIA')
End SQL
```

* ACI0097630 「4D Serverに接続」ダイアログの「カスタム」ページに情報を入力してから，「利用可」ページに移動し，「カスタム」ページに戻ると，入力した情報がクリアされました。

* ACI0097613 アプリケーションを再起動したり，デザインモードとアプリケーションモードを切り替えたりすると，「レコード > 最後に使用したテーブル」の並び順が変わりました。

**注記**: テーブル数が``15``を超過する場合に問題が発生します。

* ACI0097520 フィールドのSQLエイリアスが別テーブルの名前と同じ場合，メソッドエディターのコード補完でアプリケーションがクラッシュしました。

* ACI0097458 64ビット版のみ。フォームエディター上で複数のリストボックス列が選択されている場合，カラーピッカーを使用して背景色を設定することができませんでした。

* ACI0097409 「4D Web Application Server」ライセンスでアプリケーションを起動した場合，``4DC``ファイルを開こうとすると，エラー``10507``が返され，コンパイルされたデータベースを開くことができませんでした。

* ACI0097392 フィールドのタイプが途中で変更されたために，異なるタイプの値がレコードに保存されている場合，SQLの``OUTER JOIN``と``ORDER BY``を実行すると，アプリケーションがクラッシュしました。すべてのレコードを保存し直すか，MSCでレコードの強制更新（圧縮 > 特殊）を実行すれば，問題は解消されます。

* ACI0097303 クライアントサーバーモードでメソッドにブレークポイントを追加しても，ランタイムエクスプローラーに表示されないことがありました。その場合，別のブレークポイントを追加すると，先のものが消え，新しいほうがメソッドエディターに残りました。

* ACI0097207 Windows版のみ。``RESTORE``コマンドに引数を渡して復元をすぐに開始した場合「停止」ボタンのタイトルには「復元」と表示されました。 

* ACI0097173 Windows版のみ。4D Write Proエリアから複数行のテキストをコピーして一般的なテキストエディターに標準テキスト形式でペーストした場合，同じ文章が2回挿入されました。

* ACI0096654 64ビット版のみ。データ書き出しダイアログのキャンセルボタンをクリックすると，「ファイルが作成できません」というエラー``-1``が返されました。

* ACI0096573 Windows版のみ。水平スクロール操作をして表示されたリストボックス列のヘッダーおよびフッターにはヘルプTipsが表示されませんでした。

* ACI0094242 ``alter table CLIENTS_CYCLES add primary key (champ1, champ2)``のようにコードで複合プライマリーキーを設定した場合，重複する値の組み合わせをデータベースに登録してもエラーが返されませんでした。
