**form_forの利用**
**
**
モデル.newはFormタグを使う時に利用。Formデータの送信はPOSTになる
Book.newと書いてあるのでBookモデルをfrom_forに渡す
@User = Book.new

from_forでは渡されたモデルに対し、Postメソッドでcreateアクションの送信が行われる
form_for(@User) do |f|

Urlの指定は飛ばしたいcreateアクションの先が決まっている時

viewでform_for  モデルのデータ全部を取り出す時に利用する
form_for(@モデル,[オプション]) do |f|
form_for(@list, url: '/todolists') **do** |f|	@listはList.newが入っている**
**
**
**
★投稿画像をupdateで表示
attachment_image_tag(@モデル名, :カラム名(末尾の_idは除く),format: '拡張子名', size: "横幅数値x高さ数値"

★投稿画像をリンクにする
link_to attachment_image_tag(@user, :profile_image,size:'50x50'), users_path
**
**
**
**
Createアクションに以下記述
   # １. データを新規登録するためのインスタンス作成
    @list = List.new(list_params)

    # ２. データをデータベースに保存するためのsaveメソッド実行
    list.save
    # ３. トップ画面へリダイレクト     redirect_to '/top'

Permitに利用するカラム記述
private
**def** list_params
	**params**.**require**(:モデル名).permit(:カラム名1, :カラム名2, ...)
**end**

deviseのform_for
form_for(resource, as: resource_name, url: session_path(resource_name)) do |f|
フォームに入力されたEmailアドレスとパスワードを、session_path（deviseのユーザ認証を行うコントローラ）に渡して、
認証を行っている

