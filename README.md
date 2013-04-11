# このプログラムについて

Graph2chは、PHPで作られた2chの監視を目的としたプログラムです。  
主にcactiやmunin, MRTG等を使ってグラフ化することを目的として作られています。
板名やキーワードを指定して2chに接続し、対象となるスレッドの勢いを数値化して出力します。
実行環境にはLinux+PHP5.1以降を推奨しています。  

* @author 松井 健太郎 (Kentaro Matsui) <info@ke-tai.org>
* @copyright ke-tai.org
* @license BSD


# 実行方法

* サンプルのconfigをコピーして設定ファイルを作成します  
`$ cp sample.conf my_setting.conf`  
`$ vi my_setting.conf`  

* 設定項目は以下の通りです  
 - BoardName : URLに使われている板の識別名(http://\*.2ch.net/に続く文字)を設定します  
 - Keyword : 対象としたいスレ名を正規表現で指定します（対象が複数ある場合は先に見つかったものを使用します）  
 - Period : 対象となる期間を秒で設定します。例えば過去30分にあった書き込みを元に勢いを算出する場合は1800と指定します  

* 次のように実行します  
`./graph_2ch my_setting.conf`  

勢いが数値で出力されます  

