Selectとcollection_selectとenumの利用

Select					DBを介さないときやboolean型のときに利用
https://techacademy.jp/magazine/37096

<%= f.select 属性, 選択肢の集合, {オプション}, {HTMLオプション} %>

<span>販売ステータス
	<%=  ブロック変数.select :is_active, {‘値’: true, ‘値’: false}, { include_blank: '選択してください'}, { class: 'form-control' , required: true } %>
</span>

collection_select			DBを参照するときやenumを使っているときに利用
https://qiita.com/ohnitakahiro/items/c536fe65e37980e1087e

<%=  ブロック変数.collection_select(オブジェクト名, メソッド名, 要素の配列, value属性の項目, テキストの項目 [, オプション or HTML属性 or イベント属性])
 %>
クラスをつけたい場合
<%=  ブロック変数.collection_select :postage_player_id, PostagePlayer.all, :id, :name,{prompt: "選択してください"}, {class: ""} %>

1個目   	利用するカラム
2個目	とってきたいレコードの配列
３個目　　DBに引き渡す値
４個目　　viewで必要とされる値

★Enumの利用	https://atora1992.hatenablog.com/entry/2019/09/04/162433

enumの機能は、DBに保存されている数値を取り出した際に、対応する文字列に変換して扱うことができることだと思っていました。
しかし実際はモデルを介してデータのやり取りをする際に数値と、それに対応する文字列を変換することがenumの機能なのです。（日本語が分かり辛くてすいません。要は数値から文字列への変換を一方通行で行うわけじゃないよ、ということです。）
つまり、値がモデルクラスのインスタンスに代入される際も、enumで設定した値しか受け付けないと言うことです。と言うことはただ単に、フォームで設定するバリューをenumで設定している文字列に変えれば良いだけ。そもそもエラーを読んだ時点で認識を誤っていました。

viewの記述
<span>都道府県<%=  item.select :入れたいカラム, モデル.メソッド.keys, {}, {class: 'hoge'}%></span>

モデルの記述
enum メソッド:{　"---":0,北海道:1,青森県:2,岩手県:3,宮城県:4,秋田県:5,山形県:6,福島県:7　}
	 
Railsでformのセレクトボックス https://310nae.com/rails-selectbox/

f.select( プロパティ名, タグの情報, {オプション}, {HTMLオプション} )

