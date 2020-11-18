Git

リモートのdevelopを用意
ローカルのdevelopにpull
ローカルのトピックブランチに移動し作業
ローカルのトピックブランチでpush
トピックブランチからdevelopにプルリクエスト　
pushは全て上書きされるのでは無く、ノートに新しい記述を追加するイメージ

$ git init
$ git add .
$ git commit -m “[start]3-3“
$ git remote add origin リモートリポジトリのurl

fatal: remote origin already exists. 	
このエラーが出たら既に住所が登録されている（ここではorigin）　
一回住所を削除するコードを記述し再度、住所登録
MA4-0064:vagrant owner$ git remote rm origin

$ git remote add origin リモートリポジトリのurl
$ git push origin master

ファイルのコピー			$ git clone コピーしたコード

ブランチ					１つのプロジェクトから分岐させることにより、本体に影響を与えずに開発を行える機能のこと
ブランチを切る				ひとつのプロジェクトから枝分かれをさせ、別の作業を行うこと
統合ブランチ				いつでもリリースできる状態のブランチ。通常masterブランチを統合ブランチにするが、開発中は
						常にリリースできる状態ではないことが多いので、developブランチをmasterブランチの下に作成
						し、developブランチを統合ブランチとするケースも多い。
トピックブランチ			機能追加やバグ修正といった、あるタスクに関する作業を行うためのブランチ

デプロイ					使える状態にすること
プルリクエスト				他の開発メンバーに変更点を通知する機能
マージ					他のブランチの更新を取り込む処理
コンフリクト（競合）			更新前と更新後の
ステージングエリア			コミットするファイルを置いておくためのエリア

更新状況確認				insights → network
ブランチの確認				$ git branch
ブランチ移動				$ git checkout ブランチ名
ブランチの作成・移動			$ git checkout -b ブランチ名
リモートに反映				$ git push origin ブランチ名
コピー					$ git pull origin ブランチ名
マージ反映					$ git merge 統合したいブランチ名
トピックブランチ削除			$ git branch -D 削除したいブランチ

error: you need to resolve your current index firstとエラーが出る
コンフリクトの編集前			$ git merge --abort	
編集後					$ git reset --hard HEAD	

＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝
リモートブランチ			remote/origin/master	リモートにあるブランチ
リモート追跡ブランチ			origin/master　  		リモートリポジトリの master を追跡する追跡ブランチである。またローカルの上流ブランチ
ローカルブランチ			master		　		ローカルの master は origin/master を追跡する追跡ブランチである

★マージの流れ　　　　　　　　※マージは更新先のブランチに移動する必要がある
Git fetch					リモートの状態をリモート追跡ブランチにコピー
git merge origin/master 		リモート追跡ブランチからマージ。
git merge ブランチ名		ローカルブランチから自分のブランチにマージ
Git push origin 作業ブランチ	リモートの自分のブランチにも反映。Nerworkで右側に並ぶ

★トピックブランチ作成方法
ブランチ作成				$ git checkout -b ブランチ名
ステージングに追加			$ git add -A
ローカルに反映				$ git commit -m “名前”
=完成=
リモート反映　　　　			$ git push origin ブランチの名前

git pull origin ブランチ名  		git fetch +git merge origin/ブランチ名の合体コマンド
Git merge  				今いるブランチに別のブランチの内容を結合させるコマンド。
		  				リモートリポジトリにあるブランチや、ローカルの別のブランチをマージしたいときに使います。
Git merge ブランチ名		ローカルを更新する
git rebase				取り込みたいブランチの上に今のブランチの内容を乗せる
git pull 					git fetch と git merge をいっぺんに実行するコマンド

下のエラーが出たときはESCを押してQW同時押し
**~**

**~**

**~**

**~**

**~**

**~**

**~**

