deviseの利用

Gem追加		Gemfileの下にgem ‘devise’を追記  コピーするとエラーになるので「’’」は手動で入力
インストール	$ bundle install
初期設定		$ rails g devise:install
モデル作成		$ rails g devise モデル名
view作成		$ rails g devise:views

userはdeviseを利用しているモデルになる。customerならcurrent_customer
current_user 		ログインユーザー情報
current_user.id  	ログインユーザーのID
current_user.name	ログインユーザーの名前

★複数のdeviseの利用
deviseがインストールが完了したら、/config/initializers/devise.rbの中のconfig.scoped_views = falseをconfig.scoped_views = trueに変更

confingの設定							/config/initializers/devise.rbの247行目のconfig.scoped_views = falseをtrueに変更
Deviseを利用したいmodelを全て記述			$ rails g devise モデル名
各modelに対応するcontrollerを生成　		$ rails g devise:controllers モデル名s
各modelに対応するviewを生成　　     		$ rails g devise:views モデル名s
routingを設定
使わないviewファイルを削除				$ rails d devise:views

●deviseのview内form_forについて
form_for(resource, as: resource_name, url: registration_path(resource_name))

resource, as: resource_name  作成したモデルを取得
urlは、form_forのオプション　<%= form.submit %>をクリックしたときのアクションを設定

●application_controller.rbファイルの修正について
deviseのコントローラは、ライブラリで用意されているので、直接修正できません。 今回は、初期設定では用意されていないカラム（name）を追加しているので修正を加えます。
deviseのコントローラに修正が必要なときは、application_controllerに記述します。

●deviseでログイン後の遷移先の指定		ApplicationController内で以下記述

sign_in後のリダイレクト先
	def after_sign_in_path_for(resource)
		user_path(resource.id)
	end

sign_out後のリダイレクト先
  	def after_sign_out_path_for(resource)
    		user_path(resource.id)
  	end

●deviseでログイン時のカラムの指定方	Keys:[]に追加
	def configure_permitted_parameters
		devise_parameter_sanitizer.permit(:sign_in, keys: [:name,:email])
	end

●ログインしていない状態でアクセス制限	Controller内で以下記述	except: [:top] top画面は除く
before_action :authenticate_user!, except: [:top,:about]

●devise ヘルパーメソッドhttps://qiita.com/k4ssyi/items/3edcd0e5373a41677dee

・deviseとはログイン機能やユーザ登録機能などを簡単に実装できるライブラリあらかじめ記述が決まっている
・モデル作成時には、app/models/モデル名.rbファイルにdeviseで利用する機能が自動記述される
・Rails routesで記載されているdevise/passwords#newのようなコードはdeviseという仮想のコントーラー
に飛んでいると考える

