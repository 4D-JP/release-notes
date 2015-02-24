[4D v14.3 Hotfix 2](http://forums.4d.fr/Post/FR/15945962/1/15945963)
---
* ACI0091348 Windows版のみ，配列型のタブコントロールの最後の要素が選択されている場合，[DELETE FROM ARRAY](http://doc.4d.com/4Dv14/4D/14.3/DELETE-FROM-ARRAY.301-1697569.ja.html)でそのタブを削除するとアプリケーションがクラッシュしました。

* ACI0091172 [QUERY SELECTION](http://doc.4d.com/4Dv14/4D/14.3/QUERY-SELECTION.301-1697129.ja.html)で表示したクエリエディターのクエリタイプメニューは，デフォルトで「絞り込み」にセットされていませんでした。

* ACI0091143 コンポーネントメソッドSVG_SET_FONT_FAMILYを使用した場合，SVG_CLEARでメモリーが完全に解放されませんでした（メモリーリーク）がありました。

【参考】メモリーリークは[GET MEMORY STATISTICS](http://doc.4d.com/4Dv14/4D/14.3/GET-MEMORY-STATISTICS.301-1696594.ja.html)で確認することができます。

ACI0091090 Risk of division by zero while printing a variable size text
ACI0091086 Printing a list will show unexpected gray colored fields on Yosemite
ACI0091082 Design mode: Listbox with locked column crashes if shown in an subform
ACI0090990 The icons showing the sort order in the QR Editor are no more displayed
ACI0090951 SVG referenced by interface objects will be printed Black
ACI0090881 'Get External data path' for empty field return bad value
ACI0090865 Localization in Web area contextual menu is wrong
ACI0090853 Deployed dropdown list area is too small in v14
ACI0090847 In case of change of current tab, 4D does not always make it visible.
ACI0090828 Build Application very slow when copying files on mac
ACI0090753 'Get picture file name' fails under certain conditions
ACI0090654 Listbox: Default alignment is ignored when printing listbox for numeric column
ACI0090575 'MSG_EXTRACT' can't decode properly UTF8 encoded file names.
ACI0090567 Build Application: Master license column not updated when removing license
ACI0090556 Build Dialog: Master column is empty for expansion licences
ACI0090541 In client/server mode, "METHOD SET CODE" can unexpectedly quit 4D Server
ACI0090527 When editing form, 'undo' about font settings not working properly
ACI0090448 Copy/Past: 4D forms copied in clipboard
ACI0090378 Error #406 from Web server depending of http field "accept"
ACI0090364 Listbox: using Arrow Keys can make 4D to quit
ACI0090319 'SET WINDOW TITLE' doesn't work, depending the event where it is called
ACI0090259 Runtime Error "Invalid parameters" in Web Service method
ACI0090258 Program hangs after using SMTP_SEND without optional parameter
ACI0090116 Updating an application by itself : deletion of application
ACI0090115 Incomplete printing of a styled text with variable frame on Windows
ACI0090094 'SET PRINT OPTION' to a PDF not working
ACI0089899 After a signed merged application updated, Gatekeeper it not triggered
ACI0089704 Web Area doesn't work correctly when displayed in a form page that is not page 1
ACI0089335 PK Wizard not loading in C/S mode
ACI0089184 4D Write menu not shown with 'Movable dialog box' window type
ACI0089145 Remote 4D link proposed in the submenu local databases.
ACI0089113 '.4DC' does not open the adjacent '.4DD' by default
ACI0088790 Some strings cut in label editor in spanish version
ACI0088470 Blinking cursor becomes invisible because of a right justification
ACI0088360 Entering decimal separator does not work in a listbox
ACI0088262 External data path damaged for picture field.
ACI0087679 Listbox: column insertion position marker is badly calculated
ACI0087370 Using 'WEB SEND RAW DATA(data;*)' on a very bad network can hang 4D
ACI0087352 PRINT LABEL (l([table];>) or PRINT LABEL (>) : Syntax error
ACI0087312 Synchronous sorting of arrays object
ACI0087252 In 4D View tabulating from cell to cell does not work
ACI0086913 Quick Report: No numeric format for calculated column
ACI0082468 The type-ahead popup window too small in certain cases on Japanese system
ACI0080790 Bad copy/paste of apicture from 'Paint' application to 4D
ACI0080677 Undo/Redo of Japanese in Code Editor multiplies text
ACI0072111 Configuring IP port number for 4D engined client
