## 4D v16.3 Hotfix 5
[4D v16.3 Hotfix 4](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf4/)および[4D v16.3 Hotfix 3](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf3/)および[4D v16.3 Hotfix 2](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf2/)および[4D v16.3 Hotfix 1](https://github.com/4D-JP/release-notes/tree/master/v16/16.3/hf1/)の修正事項もご覧ください。

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

* ACI0098025 クリックイベントでカレントウィンドウのフォームが切り替わった直後，フォーカス可かつタブ不可に設定されたボタンオブジェクトにフォーカスが移動した場合，日本語入力メソッドが利用不可になりました。新規ウィンドウでダイアログが表示されたのであれば，問題ありません。フォーカスをタブ移動すれば，再び日本語入力メソッドが利用できるようになりますが，そのためには，フォーカスを得たオブジェクトがタブ可に設定されていなければなりません。

* ACI0098157 データベース言語が「日本語」に設定されており「旧バージョン互換のテキスト比較」が有効（デフォルト）にされている場合，長音記号が単純な記号としてではなく，母音を引き延ばす発音記号として検索されました。たとえば，「あんがーるず」の「ア」を置換または検索しようとした場合，「がー」の「ー」も「ア」と同等であるとみなされました。

* ACI0098129 ``LOAD VARIABLES``でオブジェクト型変数をロードするとアプリケーションがクラッシュしました。

---

* ACI0094811 コマンドで作成したメニューバーに対して``RELEASE MENU``をコールしなかった場合，アプリケーションが終了時にクラッシュしました。

* ACI0098094 日付配列に対して``Min``や``Max``などの統計関数が使用されていた場合，コンパイラーからエラーが返されました。

* ACI0098098 フランス語版は定数``Web Client IP address to listen``がローカライズ（``Web client adresse IP d’écoute``）されていませんでした。

* ACI0094683 2個以上の要素を有する配列を使用し，インデックスが設定されたフィールドに対して``QUERY WITH ARRAY``を実行した場合，ワイルドカード文字（``@``）がヌルまたは空の文字列に対して効かず，該当する位置に少なくとも1個は文字がなければなりませんでした。インデックスが設定されていなければ問題ありません。

* ACI0098188 コンパイルモードで``Min``や``Max``などをレコードに対して使用して戻り値をポインターで逆参照された変数に代入した場合，ポインターによるタイプの再定義エラーが返されました。配列に対して統計関数を使用した場合には問題ありません。

* ACI0098107 4D Write Proでコンテキストメニューから用紙のサイズや方向を変更した場合，該当するコンテキストメニュー項目にチェックマークが表示されませんでした。

* ACI0097668 32ビット版のみ。空の``4LB``ファイルをラベルエディターで開いた場合，アプリケーションがクラッシュしました。

* ACI0098223 定数``OCI_STMT_DECLARE ``の値が正しくありませんでした。``39``ではなく``9``であるべきです。

* ACI0098165 16.3以前に作成したWrite Pro文書のレコードを16R6以降で開いた場合，オブジェクトの中に属性が2個ずつ作成されました。

* ACI0098178 64ビット版のみ。``IMPORT DATA``の第1引数に空の文字列（``""``）が渡した場合，ファイル選択ダイアログが表示されませんでした。

* ACI0098236 Windows版のみ。Microsoftの[自己署名証明書](https://msdn.microsoft.com/en-us/library/windows/desktop/jj835832.aspx)を発行して[署名ツール](https://msdn.microsoft.com/en-us/library/aa387764.aspx)で64ビット版のOEMサーバーアプリケーションを署名することができませんでした。

**注記**: 回避策として[``delcert``](https://github.com/MadhukarMoogala/delcert)などで証明書を取り除いてから改めてサーバーアプリケーションに署名することができます。

* ACI0098063 64ビット版クイックレートエディターのタイトルに``n``の文字をタイプ入力すると，「レポートを開く（ファイル選択）」ダイアログが表示されました。

* ACI0098253 ``&``の文字が含まれているSVG画像を``SVGTOOL_show_in_viewer``メソッドで開いた場合，エラー`` -20002``が返されました。

* ACI0097938 Windows Server 2008 R2，Windows Server 2012のみ。特定のマシンでは``Graphics.dll``が原因でアプリケーションがクラッシュしました。