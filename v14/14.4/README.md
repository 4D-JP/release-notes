4D v14.4
---
* ACI0070568 ランタイムエラー画面の詳細ボタンをクリックしたときに表示されるプロセス番号が正しくありませんでした。

* ACI0071389 Plugin APIの```PA_ExecuteCommandByID```に配列を渡すことができませんでした。たとえば，```SELECTION TO ARRAY```のようなコマンドをプラグインからコールすることができませんでした。修正されたファイルは，Plugin APIの[リポジトリ](http://sources.4d.com/trac/4d_4dpluginapi/changeset/31)から入手することができます。配列に対するポインタを```PA_GetPointerParameter```で取得し，```PA_SetVariableOrFieldReference```でパラメーターにバインドしてください。
