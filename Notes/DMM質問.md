DMM質問

１ヶ月目	何をしたいのか/何が分からないのか/試したことと結果/参考にしたサイト
２ヶ月目
タイトル	応用課題○	
1.何を(なぜ)したかったのか
2.何をしたのか(重要！)
3.どんな結果(問題)となったのか

文字入力　おかしい　
グーグルと入力するとグーグーググーグルとなる
sから始まる言葉を入力すると初めにsが入った状態で検索される

divとじ右に１つずれる問題   下の行が子要素にもかかわらずインデントされてないとおこる

_form画面のdivを１行に2つ書くのは美しいコード、読みやすいコードしてどうなのか？
ブロック要素を１行に2つ入れるのはよくいない？状況による？
インデントのルールみたいなものを知りたい

特定のトピックブランチを特定のトピックブランチにコピーしたい。
Index      ○○　→　Develop  ●●●　→　Show　●●●       
showをindexにしたい

new画面でプレビュー機能をつけたい

doについて

<% if @book.favorited_by?(current_user) %>
              <%= link_to book_favorites_path(@book), method: :delete do %>
                		<span class="glyphicon glyphicon-heart"><%= @book.favorites.count%></span>
              <% end %>
            <% else %>
              <%= link_to book_favorites_path(@book), method: :post do %>
                <span class="glyphicon glyphicon-heart-empty"><%= @book.favorites.count %></span>
              <% end %>
 <% end %>

