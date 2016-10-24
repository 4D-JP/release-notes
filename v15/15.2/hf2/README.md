4D v15.2 Hotfix 2
---

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0095187 Windows版のみ。日本語入力ソフトウェア[Japanist](http://www.fujitsu.com/jp/products/software/applications/applications/japanist/)を使用してリストボックスのセルにテキストを入力すると，特定のキー（a, e, i, o, u）でアプリケーションがクラッシュしました。

* ACI0095427 日本語に続けてスペース（空白）文字を入力した場合，点滅カーソルが消えました。また，入力した空白文字も表示されませんでした。「ワードラップ」プロパティが「あり」または「自動」に設定されたテキスト入力（変数・フィールド）全般およびリストボックスで問題が再現します。

**注記**: 「ワードラップ」は「複数行」が「あり」に設定されたオブジェクトに対して有効です。

[デザインリファレンス > アクティブオブジェクトのプロパティ> 複数行](http://doc.4d.com/4Dv15R5/4D/15-R5/Multiline.300-2964180.ja.html)

[デザインリファレンス > リストボックス > リストボックス列特有のプロパティ](http://doc.4d.com/4Dv15R5/4D/15-R5/List-box-column-specific-properties.300-2964161.ja.html)

* ACI0066193 ``LOG EVENT``に``Into 4D Commands Log``オプションを渡してコメントをシステムログに書き込んだ場合，日本語が化けました。
 
* ACI0095313 シンタックスチェックを実行すると，日本語のフォーム名が文字化け表示されました。

* ACI0095283 Windows版のみ。``Plain form window``タイプのウインドウを表示した場合，一般的なアプリケーションのアイコンがタイトルバーに表示されました。以前のバージョンでは，アプリケーションのアイコン（たとえば4Dのアイコン）が表示されていました。
 
* ACI0095167 クエリエディターから表示された選択リストダイアログをキャンセルすると，フォーカスがクエリエディターに戻りませんでした。

* ACI0095596 Mac版のみ。4D Remoteがサーバーに接続中のときに表示されるダイアログは，メッセージが複数行に及ぶと，上下の端が切れて文字が読めませんでした。

---

* ACI0095294 "Microsoft Generic/Text Only"プリンタードライバーに対して印刷ジョブを送信すると，空の文書が出力されました。

**注記**: 参考までに，当該ドライバーは``Carriage Return``コードを追加することがあり，そのために文書フォーマットが崩れてしまうことがあります。"Text Only"ドライバーで印刷するときには，行の位置を揃えるため，``Courrier New``のような固定長フォントを使用したほうが良いでしょう。

* ACI0095644 ``OPEN PRINTING JOB``の後，何も印刷せずに``CLOSE PRINTING JOB``を実行すると，空の文書が出力されました。
 
* ACI0095621 フォームエディター上の操作でマーカーを追加した場合，プロパティリストに新しいマーカーの項目が追加されませんでした。

* ACI0090525 プライマリーキーが複合フィールドで設定されている場合，トランザクション中であれば重複する値を登録することができてしまいました。一応，エラーダイアログは表示されますが，それでもトランザクションを確定すればレコードが作成できました。

* ACI0088141 ストラクチャエディターのインデックスエクスプローラー画面で，矢印キーを使用してフィールドの順番を変更すると，エラー``-20001``（配列の範囲チェック）が返されました。

* ACI0095653 4D Viewエリアのプロパティリストに[詳細設定](http://doc.4d.com/4Dv15R4/4D/15-R4/Plug-in-areas.300-2880332.ja.html)ボタンが表示されませんでした。
 
* ACI0095603 読み書きモードでロードされているレコードに``On Backup Shutdown``でアクセスした場合，バックアップの完了後，デッドロック状態に陥ることがありました。

* ACI0091264 ``String``で``ISO Date GMT``フォーマットに日付と時間を変換した場合，夏時間（フランスでは3月29日の早朝3時から実施）を反映しませんでした。以前のプラグイン``AP Timestamp to GMT``では問題ありませんでした。

* ACI0095545 Windows版のみ。ドロップダウンメニューの項目をマウスホイールで変更した場合，``On Clicked``イベントだけが発生しました。``On Data Change``も発生するべきです。

* ACI0095546 Windows版のみ。ドロップダウンメニューが表示されている間にキーボートで文字をタイプ入力した場合，すでに選択されている項目で続けて入力した文字が合致したとしても，次の項目にハイライトが移動しました。

* ACI0095487 v13で作成したラベルをv15で出力すると，フィールドやスタティックテキストの位置が左上にずれました。

* ACI0091810 フォームエディターでリストボックスの列を複製し，``command+Z``で取り消した直後の再描画が崩れていました。

* ACI0094251 スプラッシュウインドウ（メインプロセス）を閉じてデザインモードに切り替え，テーブルリストだけが表示された状態にした場合，Macでは99%，Windowsでは30%程度CPUがビジーになるケースがありました。テーブルを選択し，ユーザーモードのウインドウが表示されるようにすると，0%に戻りました。

原因は，ユーザーモードが非表示の場合，``On Load``は実行されても，``On Timer``が実行されなかったことにありました。そのため，``On Load``の``SET TIMER(-1)``で開始したタイマーが``On Timer``で停止されずいつまでも走り続けました。そのようなフォームメソッドがデフォルトリストフォームに記述されていなければ，問題ありません。

* ACI0095042 ``Dec``から正しい値が返されないケースありました。

```
Dec( (1/105000)*105000) // 0ではなく1が返される
```

**注記**: 修正により，``Dec``は限りなく``+/-1``に近い値の整数部を返すようになりました。


* ACI0094901 16桁の数値に対して``Mod``でモジューロを求めると，負の値が返されました。PHPであれば問題ありません。

```
nb:="0429429886111400"
ALERT(String(Mod(Num(nb);97)))
// BUG => -41

$result:=PHP Execute("";"bcmod";$T_Resultat;nb;"97")
ALERT($T_Resultat)
// OK => 56
```

**注記**: [ドキュメント](http://doc.4d.com/4Dv15/4D/15.1/Mod.301-2685791.ja.html)に述べられているように，(2^31を超える) おおきな実数に対してModを使用する場合には注意が必要です。

* ACI0095271 Mac版のみ。リストボックスの行が選択された状態でフォーカスを移動すると，テキストの色が白のまま，背景色だけがグレーに変化しました。

* ACI0095354 フォームウィザートを使用して印刷用リストフォームを作成すると，ストラクチャに問題が発生しました。MSCの検査ではオブジェクト名の重複が報告され，``METHOD GET PATH``は``-9802``エラーを返します。

* ACI0095468 Windows版のみ。MacでコンパイルしたストラクチャをWindowsで実行すると，``Character code(Folder separator)``のようなコードが``:``記号に固定されました。``Character code``に定数が渡されているようなコードをコンパイルした場合にだけ問題が発生します。

* ACI0094275 ツールボックスの「フィルター」ページで時間の表示フォーマットのドキュメントを選択すると，日付の表示フォーマットが定義エリアに転写されました。ダブルクリックで選択すると，範囲チェックエラーが表示される項目もあります。

* ACI0094978 サポートされないSQL（CASE...WHEN...）でビューを作成しようとすると，アプリケーションがクラッシュしました。

* ACI0095358 特定のデータベースでは，MSCが出力する検査ログを開くことができませんでした。XML解析エラーが返されました。

* ACI0093468 Windows版のみ。``GET SERIAL PORT MAPPING``は，4Dがすでに使用しているシリアルポートを返しませんでした。

```
ARRAY LONGINT($num;0)
ARRAY TEXT($name;0)
GET SERIAL PORT MAPPING($num;$name)
If (Size of array($num)<1)
        TRACE // アダプターが接続されていません
Else
        $port:=1  // ポートを開きます
        SET CHANNEL($num{$port}+100;Data bits 8+Parity none+Speed
9600)
        GET SERIAL PORT MAPPING($num;$name)
        TRACE // 開いたポートが含まれません
Windows
        SET CHANNEL(11)
end if
```

* ACI0094700 エクスプローラーの「ホーム」タブでメソッドをわずかでもドラッグすると，階層のトップレベルに移動しました。軽くクリックしただけのつもりでも，マウスポインターが少しでも移動しれば，メソッドが移動してしまいました。

* ACI0095265 ``DESCRIBE QUERY EXECUTION``を宣言してから，複数のクエリを実行した場合，``Get last query plan``と``Get last query path``は最初に実行したクエリに関する情報を返しました。コマンドは最後に実行したクエリに関する情報を返すはずです。

* ACI0095562 Mac版のみ。4DがへルプTipsを表示している間に別のウインドウを最前面に移動した場合，Tipsがすぐに消えませんでした。

*ACI0094436 他のサイトからジャンプした場合，``On Web Authentication``データベースメソッドにユーザー名とパスワードが渡されませんでした。直接，ブラウザにアドレスを入力した場合は問題ありません。HTTPヘッダーの``Referrerer``フィールドが存在する場合，まず``On Web Authentication``が実行され，認証が求められます。この時点で，存在するべきではない自動セッション管理のクッキーが確認できます。また，このステップに10~15秒ほど要することがあります。ブラウザからユーザー名とパスワードを送信すると，``On Web Authentication``が再び実行されますが，``$5``および``$6``が空です。

* ACI0087565 Mac版のみ。無効なコマンド名が``LAUNCH EXTERNAL PROCESS``に渡された場合，``OK``システム変数が``0``にセットされませんでした。

* ACI0090171 Mac版のみ。変換されたデータベースの環境設定「ショートカット」ページで``command``と右矢印キーを環境設定のショートカットに設定した後，そのショートカットを入力すると，エラー``-9935``が返されました。問題を解消するためには，``4D Shortcuts v15.xml``ファイルを作成するしかありませんでした。

* ACI0095329 64ビット版のみ。「開く > メソッド」メニューでメソッドを開くことができませんでした。ショートカットの``command+K``を入力しても駄目でした。

* ACI0095503 Mac/32ビット版のみ。フォームエディターのプロパティリストでフォント名のコンボボックスを上下矢印キーで操作した後，``enter``キーで確定すると，アプリケーションがクラッシュしました。新規オブジェクトでは問題ありません。既存のオブジェクトだけで問題が再現します。

* ACI0094500 Windows版のみ。ツールバーウインドウ上では，ヘルプTipsが表示されませんでした。また，3Dボタンの「ロールオーバー」効果が起きませんでした。

**注記**: ツールバーの管理方法はv15で刷新されました。新しいメカニズムでは，[Open form window](http://doc.4d.com/4Dv15/4D/15.1/Open-form-window.301-2686139.ja.html)の``Toolbar form window``定数と[SHOW TOOL BAR](http://doc.4d.com/4Dv15/4D/15.1/SHOW-TOOL-BAR.301-2686156.ja.html)を組み合わせて管理します。

http://doc.4d.com/4Dv15/4D/15/Toolbar-form-windows.300-2044334.ja.html

* ACI0095250 トランザクション中，保存場所が「データファイルの外」に設定されているピクチャーフィールドに画像を代入して新規レコードを保存し，トランザクション中にアンロード/ロードした場合，画像がロードされませんでした。トランザクションを確定した後でなければ，画像をロードすることができませんでした。

* ACI0095359 ラジオボタンをクリックすると，イベントが発生しませんでした。チェックボックスでは問題ありません。

* ACI0095374 ``GET BACKUP INFORMATION(Next backup date)``をクライアント側で実行すると，常にカレント日付とカレント時間が返されました。 

* ACI0095505 Windows版のみ。リストフォームに表示されたフィールドの整列を「右揃え」に設定した場合，幅に収まりきらないテキストが切り捨てられる代わりに，エリアの外に表示されました。

* ACI0094551 フランス語版のみ。日付フォーマットの``Internal date long (5)``および``Internal date abbreviated (6)``番は，月名の冒頭が大文字でした。フランス語では，月名をすべて小文字で表記するべきです。

* ACI0095063 Mac版のみ。``option``キーを押しながら``delete``を入力すると，ワードが削除されるはずですが，4D（フォームエディターおよびメソッドエディター）ではこのショートカットが認識されませんでした。

**注記**: Macの標準キーボードショートカットは下記のURLに列挙されています。

https://support.apple.com/en-us/HT201236

* ACI0095321 [MODIFY SELECTION](http://doc.4d.com/4Dv15/4D/15.1/MODIFY-SELECTION.301-2684948.ja.html)で実行されたフォームが表示されている間は，ヘルプメニューが動きませんでした。

* ACI0093999 Mac版のみ。4D Writeにテキストを入力すると，カーソルが消えました。マウスを動かすと再びカーソルが表示されました。

* ACI0094484 テキスト入力エリアのボーダースタイルが標準（``Plain (1)``）に設定されていた場合，ボーダーの色はフォントカラーを踏襲せず，常にブラックでした。フォームエディター上は問題ありません。ランタイムの問題です。

* ACI0095085 4D Serverのシャットダウン画面で「キャンセル」ボタンをクリックすると，サーバーは動き続きますが，接続中のクライアントは接続が切断され，新規接続はできなくなりました。

* ACI0095446 ユーザー設定が無効にされた状態で``OPEN SETTINGS WINDOW("/Database";True;User settings)``を実行すると，シンタックスエラーが返されました。しかし，エラーメッセージがありません。「ユーザーデータベース設定が有効化されていません。」というエラーメッセージが表示されるべきでした。

* ACI0095305 Windows版のみ。別々のフォームページに4D Writeと4D Webエリアをそれぞれ配置し，ページを切り替えると，4D Writeにテキストを入力することができなくなりました。

* ACI0095364 4D Write Pro文書に画像を挿入した後，削除し，元の画像ファイルを画像編集ソフトなどで加工してからもう一度挿入すると，加工前の古い画像が挿入されました。

* ACI0095383 4D Write Pro文書（72DPI）にコンテキストメニューから画像を追加し，マウス操作でその画像をリサイズすると，画像がぼやけて表示されました。

* ACI0095384 4D Write Pro文書の段落にマージンが設定されている場合，テキストの高さだけがハイライト表示されました。上下マージンもハイライト表示されるべきです。

* ACI0095211 コンボボックスにタイプ入力中，完全に一致するアイテムがない限り，項目が選択されませんでした。以前のバージョンでは，前方一致した最初のアイテムが選択され，途中でEnterキーを入力すれば入力中のテキストが補完されました。

* ACI0093728 コンボボックスのポップアップメニューが表示されているときに``escape``キーを入力した場合，メニューが閉じられる代わりに，Macでは，項目の選択が解除され，テキスト入力エリアがクリアされました。Windowsでは，ダイアログが閉じられました。

* ACI0093858 リストフォームに複数のブレークが設定されている場合，「ブレーク1，ブレーク2，ブレーク3，ブレーク」のような順序でプロパティリストに表示されました。ヘッダーの順序は問題ありません。

* ACI0094716 メソッドエディターで``Shift``+クリック操作で番号付きペーストボードにコードをコピーした場合，メソッドの「未保存」ステータスは「保存」に変化しますが，実際には保存されておらず，メソッドを閉じてから開き直すと，保存前の状態になりました。

**注記**: メソッドの「保存」ステータスは，Windowsの場合，ウインドウタイトルに``*``（アスタリスク）が表示されることで確認できます。Macの場合，ウインドウの閉じるボタン（赤）に中央部分が暗くなっているのが「未保存」のメソッドです。

* ACI0095574 Mac版のみ。ドラッグ＆ドロップ操作でピクチャを入力した場合，PICT形式で画像が保存されました。画像ファイルではなく，たとえばWebブラウザなどから画像を直接のドラッグ＆ドロップした場合に問題が再現します。

**注記**: PICT形式のサポートは廃止予定です。Cocoa（64ビット）版の4Dや「プレビュー」アプリケーションは，PICT形式の画像を表示することができません。

* ACI0095790 MacOS 10.11のみ。アプリケーションプロセスから起動したクイックレポートの出力先をHTMLまたはテキストファイルに設定した場合，クイックレポートのウインドウを閉じた後もグレーアウトされたウインドウが画面上に残されました。

* ACI0088557 4D Viewや4D Writeのツールバーを独立したパレットとしてドラッグアウトした場合，空のパレットウインドウが表示されました。

**注記**: この機能は，v14以降のアーキテクチャーと互換性がありません。修正により，4D Viewや4D Writeのツールバーを独立したパレットとしてドラッグアウトすることはできなくなりました。

* ACI0091212 [QUERY SELECTION](http://doc.4d.com/4dv15r/help/command/ja/page341.html)でクエリエディターを表示した場合，絞り込みではない，通常のクエリも実行できました。「クエリ」関係のオプションはクリック不可になるべきです。

* ACI0094154 [Select folder](http://doc.4d.com/4dv15r/help/command/ja/page670.html)は，指定されたフォルダーを選択するコマンドですが，階層に多数のフォルダーが存在する場合，目的のフォルダーまでリストをスクロールしませんでした。v2004以来の不具合です。

**注記**: これは[Windows](https://connect.microsoft.com/VisualStudio/feedback/details/518103/bffm-setselection-does-not-work-with-shbrowseforfolder-on-windows-7)の不具合です。回避策として，必要であれば，目的のフォルダーまでスクロールするようコマンドが改修されました。

* ACI0095525 検索ワードの途中にワイルドカード記号が使用された場合，キーワード検索で合致するのは，単語レベルで条件に合致するレコードではなく，テキスト全体で条件に合致するレコードでした。たとえば，``name%"B@que"``のようなクエリを実行した場合，"Banque Cantonale Vaudoise"や"Union de Banque Suisse"だけでなく，"Bureau Informatique"もヒットしました。

**注記**: 修正により，検索ワードの途中にワイルドカード記号が使用された場合，キーワードインデックスに基づいたシーケンシャルクエリが実行されるようになりました。

* ACI0095286 クイックレポートの列フィールドに``###,###,###,##0.00``のようなフォーマットを設定した場合，HTML出力でフィールドの値ではなく，タイトルにフォーマットが適用されました。

* ACI0095645 クイックレポートの小計エリアは，日付のフォーマットが正しくありませんでした。日月年（フランスでは一般的）の代わりに年月日フォーマットで日付が表示されました。HTML出力では問題ありません。

* ACI0095463 オブジェクト型のフォールド（データの保存オプションは「データファイルの中」）をテキスト型に途中で変更することができませんでした。フィールドのタイプは，テキストではなく，文字列になるため，レコードの再保存でデータが失われる恐れがありました。文字列からテキストに変更することはできません。データの保存オプションが「レコードと一緒」であれば問題ありません。

**注記**: 修正により，ストラクチャエディターがデータの保存オプションを内部的に切り替えるようになりました。フィールドのタイプをオブジェクトからテキストに変更するためには，オプションを「レコードと一緒」に変更する必要があります。

* ACI0095156 v13以前に作成されたPICT画像を[CONVERT PICTURE](http://doc.4d.com/4dv15r/help/command/ja/page1002.html)で拡大した後，[TRANSFORM PICTURE](http://doc.4d.com/4dv15r/help/command/ja/page988.html)または[WRITE PICTURE FILE](http://doc.4d.com/4dv15r/help/command/ja/page680.html)で変換しようとすると，アプリケーションがクラッシュしました。

* ACI0095624 Windows版のみ。サードパーティ社製プラグインエリア（例: [Print List Pro](http://www.e-node.net/redir/EN/produit_id_21/printlist-pro.html)）を印刷すると，最終ページにレコードが出力されないことがありました。ページの残りが印刷したいオブジェクトに対して不足している場合，4Dがプラグインからの改ページ要求を無視しました。

* ACI0094904 [SVG_New_textArea](http://doc.4d.com/4Dv15R5/4D/15-R5/SVG-New-textArea.301-3014996.ja.html)は，スペースなどの文字が含まれるフォント名に対応していませんでした。[SVG_SET_FONT_FAMILY](http://doc.4d.com/4Dv15R5/4D/15-R5/SVG-SET-FONT-FAMILY.301-3014993.ja.html)を使用する必要がありました。

* ACI0095575 クライアント/サーバーモードでは，別のデベロッパーが開いているフォームがロックされています。そのようなフォームをエディターで開くと，警告のダイアログが表示されますが，それを閉じた後は，たとえフォームがロックされていても，フォーム上のオブジェクトを選択して削除することができました。その後，フォームを閉じると，フォームオブジェクトは存在するのにオブジェクトメソッドが存在しない状態になってしまい，ストラクチャーが破損しました。

* ACI0095627  標準テキスト入力からコピーしたテキストをスタイル付きテキスト入力にペーストすると，標準テキストのスタイルで文字列が挿入されました。期待されるのは，ペースト先のスタイルが継承されることです。

* ACI0095673 15.2 Hotfix 1以降，クイックレポート内でクエリを実行しても，レコードがみつかりませんでした。

* ACI0095695 既存のフォームと同じ名前でフォームを作成しようとしたときに表示されるエラーメッセージの内容が間違っていました。

* ACI0094833 ツールボックスのリソースページで項目を名前順で並び替えようとしても，何も起きませんでした。

* ACI0094916 Windows版のみ。.NET ODBCプロバイダー経由で4D ODBCドライバーにアクセスした場合，クエリの結果が完全に返されませんでした。Microsoft Excel，WinSQL，PHPでは問題ありません。C#/.Netアプリケーションからのアクセスは``SQLGetData``のチャンク処理に問題がありました。

* ACI0095129 非常に負荷がかかった状態では，稀に[New log file](http://doc.4d.com/4dv15r/help/command/ja/page926.html)の実行中にレコード作成のオペレーションがログファイルに記録されないことがありました。

* ACI0095724 リストボックスの``'On Column Resize'``イベントは，リストボックスのヘッダー上でマウスボタンをリリースしなければ発生しませんでした。

* ACI0092571 [ユーザー設定](http://doc.4d.com/4Dv15R5/4D/15-R5/Using-user-settings.300-2964123.ja.html)が使用されている場合，アップグレード後に互換性オプションの「旧ネットワークレイヤーを使用する」が解除されました。

* ACI0095266 フォームにスタイル付きテキストが存在し，テキストにアンパーサンド記号（``&``）が含まれている場合，[Print form ](http://doc.4d.com/4dv15r/help/command/ja/page5.html)で空のオブジェクトが印刷されました。

* ACI0095726 Webサービスウィザードが生成するコードは，廃止予定コマンドである``_o_C_STRING``を含んでいました。

* ACI0095711 Mac版のみ。リストフォームに長いテキスト（700KB程度）を表示しようとすると，アプリケーションの振る舞いが非常に遅くなりました。

* ACI0091205 ``MAXINT``を超える行番号で[SAX Get XML node](http://doc.4d.com/4dv15r/help/command/ja/page860.html)のエラーが発生した場合，[GET LAST ERROR STACK](http://doc.4d.com/4dv15r/help/command/ja/page1015.html)に負の行番号が返されました。

* ACI0092274 [ON EVENT CALL](http://doc.4d.com/4dv15r/help/command/ja/page190.html)を中止する（イベントマネージャープロセスを通常にプロセスに切り替える）ためのキーコンビネーション（Windows版は``Control``+``Shift``+``Backspace`` Mac版は``command``+``shift``+``control``+``backspace``）が効きませんでした。