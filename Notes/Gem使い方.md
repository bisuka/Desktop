Gem使い方

Gemfileにコードを記述　gem 'devise'

アプリケーションに読み込ませる		$ bundle install

初期設定を行う	$ rails g devise:install

★画像登録用gem　Refile

Gemfile追加
gem "refile", require: "refile/rails", github: 'manfe/refile'
gem "refile-mini_magick"

DBにimage_idカラムを追加する

attachmentメソッドを追加	これによりDBに存在する画像を取得したりアップロードが可能になる
モデルにattachment :imageを追記　このときidはつけない

Strong Parametersに追加　カラム にidはつけない

画像用のフィールドを追加
<%= f.attachment_field :image %>

viewで表示
<%= attachment_image_tag @product, :image, :fill, 300, 300, format: 'jpeg' %>	imageのidは抜く

**RuntimeError　**Refile.secret_key was not set.と出るので
Refile.secret_key = '313734ef8e4baaa4a5b94bed9df7877ad83970995584640f89528b02b0dcce476b61b15c647794a9beaf624d00c8cfaabf99199c3724cd7d9838cd1517cd9f30'
みたいなコードをconfig/initializersディレクトリにあるapplication_controller_renderer.rbファイルに貼り付け**
**

