# このプログラムについて

Graph2chは、PHPで作られた2chの監視を目的としたプログラムです。  
主にcactiやmunin, MRTG等を使ってグラフ化することを目的として作られています。
板名やキーワードを指定して2chに接続し、対象となるスレッドの勢いを数値化して出力します。
実行環境にはLinux+PHP5.1以降を推奨しています。  

* @author 松井 健太郎 (Kentaro Matsui) <info@ke-tai.org>
* @copyright ke-tai.org
* @license BSD
* @link https://github.com/ketaiorg/Graph2ch
* @link http://info.2ch.net/wiki/index.php?%A4%C8%A4%AB%A4%B2%A4%CE%BF%AC%C8%F8%C0%DA%A4%EA%2F%A5%D0%A1%BC%A5%DC%A5%F3%A5%CF%A5%A6%A5%B9


# 実行方法

* サンプルのconfigをコピーして設定ファイルを作成します  
`$ cp sample.conf my_setting.conf`  
`$ vi my_setting.conf`  

* 設定項目は以下の通りです  
 - BoardName : URLに使われている板の識別名(http://\*.2ch.net/に続く文字)を設定します。（必須パラメータ）  
 - Keyword : 対象としたいスレ名を正規表現で指定します。対象が複数ある場合は一番勢いがあるスレが利用されます。（必須パラメータ）  
 - Period : 対象となる期間を秒で設定します。例えば過去30分にあった書き込みを元に勢いを算出する場合は1800と指定します。デフォルトは3600です。  
 - CacheDir : キャッシュを置く場所を指定します。デフォルトは実行プログラムと同じ階層に「.graph\_2ch\_cache」というディレクトリが作成されます。「/tmp/.graph\_2ch\_cache」と設定してもいいでしょう。書込権限が必要なことに注意してください。  
 - CacheExpire : キャッシュの最大有効期限を秒で指定します。デフォルトは86400です。通常変更の必要はありません。  
 - MenuListUrl : 板のメニューリストを取得するURLです。通常変更の必要はありません。  
 - DatCacheUrl : "http://bg20.2ch.net/test/r.so/" のように設定することで、キャッシュサーバを利用できバーボンハウス入りを避けることができます。  

* 次のように実行します  
`./graph_2ch my_setting.conf`  

勢いが数値で出力されます  

