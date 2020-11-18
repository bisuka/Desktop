# Form_with

https://qiita.com/sew_sou19/items/e9944904b50899fbb4cf

form_withを使って作成したformがある場合、全てのformにlocal:trueオプションをつける必要があります。

<%= form_with model:@anime, url:users_anime_index_path, method: :post, local: true do |f| %>

model	controllerから受け取ったインスタンス変数が入っている。
url		飛ばしたい先のpath
method    httpメソッド

<%= form_with model: @user do |form| # modelを渡している %>
  <%= form.text_field :email %>
  <%= form.submit %>
<% end %>

Editアクション　インスタンスに値があればeditに飛ばす

<%= form_with model: @user do |form| # modelを渡している %>
  <%= form.text_field :email %>
  <%= form.submit %>
<% end %>

