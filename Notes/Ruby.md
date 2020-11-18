Ruby

★初回操作
Vagrant up 起動
Vagrant ssh ログイン

 PC上の共有フォルダは、Vagrantfileのある場所（~/Desktop/work/vagrant）にあります
仮想環境内の共有フォルダは、（/home/vagrant/work/）にあります

アプリ作成				$ rails new アプリケーション名
アプリ削除				$ rm -rf アプリケーション名
コントローラの作成		$ rails g controller コントローラ名
アクション同時作成		$ rails g controller コントローラ名 アクション名
コントローラー削除		$ rails d controller コントローラ名

サーバー起動			$ rails s -b 0.0.0.0

ルーティングの記述		HTTPメソッド 'URL' => 'コントローラ#アクション'
ルーティングエラーサーバー立ち上げ時	
/home/vagrant/work/sample_app/config/routes.rb:3: 	routes.rbの3行目に
syntax error									文法エラー
unexpected end-of-input, expecting keyword_end	予期せぬところでコードが終わっており、endが必要

