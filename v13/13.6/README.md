4D v13.6
---

* ACI0092648 4D Volume Deskopのビルド番号を特定することができませんでした。

**注記**: 通常，ビルド番号は，[Application version](http://doc.4d.com/4Dv13/4D/13.5/Application-version.301-1458428.ja.html)で特定することができますが，ビルドされたアプリケーションでは，Info.plistに記述された情報 (```CFBundleShortVersionString, CFBundleVersion```) を参照する必要があるかもしれません。今回の修正により，Info.plistファイルにビルド番号が反映されるようになりました。

* ACI0092730 Windows版のみ，[IT_Version](http://doc.4d.com/4Dv13/4D/13.2/IT-Version.301-1086826.ja.html)から返されるバージョン番号が正確ではありませんでした。

* ACI0092713 統合WebKit版，およびMac版システムWebエリアで[WA EXECUTE JAVASCRIPT FUNCTION](http://doc.4d.com/4Dv13/4D/13.5/WA-EXECUTE-JAVASCRIPT-FUNCTION.301-1457214.ja.html)または[WA Execute JavaScript](http://doc.4d.com/4Dv13/4D/13.5/WA-Execute-JavaScript.301-1457215.ja.html)でJavaScriptを実行することができませんでした。13.5では問題ありません。13.5HF1以降の問題です。
 
* ACI0091680 [XSLT GET ERROR](http://doc.4d.com/4Dv13/4D/13.5/XSLT-GET-ERROR.301-1457286.ja.html)を実行した後，```OK```変数に```1```が代入されませんでした。





Fixed bugs v13.5 build 186028(Released on 2015-05-30)
-----------------------------------------------------
ACI0090668 : [130510] FORM SCREEN CAPTURE PROBLEM
ACI0091680 : OK variable is not set to 1 after an correct execution of XSLT GET ERROR

Fixed bugs v13.5 build 185995 (Released on 2015-05-29)
-----------------------------------------------------
ACI0092244 : [131131] 4D crash if OS language is Luxembourgish

Fixed bugs v13.5 build 185736 (Released on 2015-05-26)
-----------------------------------------------------
ACI0091616 : [130902] http request (The PROFIND method is not set in the HTTP request)

Fixed bugs v13.5 build 185419 (Released on 2015-05-21)
-----------------------------------------------------
ACI0092077 : LOG EVENT no longer writes to Mac Console.LOG

Fixed bugs v13.5 build 184944 (Released on 2015-05-13)
-----------------------------------------------------
ACI0069136 : Import not seeing RTF files

Fixed bugs v13.5 build 184319 (Released on 2015-05-01)
-----------------------------------------------------
ACI0087028 : [128895] bug repeat lines and printing

Fixed bugs v13.5 build 184216 (Released on 2015-04-30)
-----------------------------------------------------
ACI0091207 : [130685] SQL LEFT JOIN
ACI0091687 : [130929] LEFT OUTER JOIN 2 criteria do not work
