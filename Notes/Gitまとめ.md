# Gitまとめ

現在のブランチを、あるブランチで上書きする
git fetch origin
git reset --hard origin/ブランチ名

Commitしないで作業ブランチを変えるときに利用
git stash

Mergeのやり方　取り込みを行いたい場所にいた上で、以下のコマンドを実行		
Git merge 取り込みたいブランチ

Git branch -a　でトラッキングブランチ確認するとこんなふうに出てくる

* admins/products/index
  admins/products/new
  develop
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/admins/products/new
  remotes/origin/develop
  remotes/origin/devise_customer

Git fetchは  remotes/origin/developをマージしてると思っていい　origin/developが更新される
Git merge origin/develop は origin/developをマージしている　 　developが更新される
Git merge develop は developをマージしている		             任意のディレクトリが更新される

エラー文
Your local changes to the following files would be overwritten by merge: 
「次のファイルに対するローカルの変更は、マージによって上書きされます」「マージする前に変更をコミットするか、隠してください」

you need to resolve your current index first

