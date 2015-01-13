4D v14 R4 Hotfix 1
---

* ACI0090599 [Popup menu](http://doc.4d.com/4Dv14R4/4D/14-R4/Pop-up-menu.301-1708614.ja.html)は，何も項目が選択されなかった場合，0が返されるはずですが，R4以降，**-1が返される**という問題がありました。

* ACI0090677 [LISTBOX GET ARRAYS](http://doc.4d.com/4Dv14R4/4D/14-R4/LISTBOX-GET-ARRAYS.301-1707554.ja.html)は，```arrStyles```にスタイル・カラー・背景色・非表示を制御するための配列に対するポインター，または未定義であれば```NUL```が返されるはずですが，R4以降，スタイル配列だけが設定されていた場合，```NUL```ではなく，スタイル配列に対するポインターが繰り返し返されました。
