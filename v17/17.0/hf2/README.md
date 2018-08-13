4D v17.0 Hotfix 2
---

![jp](https://cloud.githubusercontent.com/assets/10509075/16182979/016305e0-36e7-11e6-816b-2335cc6f0abb.png)

---

* ACI0098518 ``FORM LOAD``コマンドでメモリにロードした4D Write Proエリアに対して``OBJECT Get font``を使用した場合，アプリケーションがクラッシュしました。

* ACI0098409 Windows 10 1803のみ。Acrobat Reader DC・ Office 365・Kyoceraのプリンタードライバをインストールし，デフォルトプリンターに設定した後，オペレーションシステムを再起動して，Microsoft Wordに続けて4Dを起動して``FONT STYLE LIST``を実行すると，しばらく後にアプリケーションがクラッシュしました。

* ACI0098547 クライアントサーバー版のみ。出力フォームにレコードを表示し，フォームをスクロールしたり，リサイズしたりするたびに，メモリーリークが発生しました。
