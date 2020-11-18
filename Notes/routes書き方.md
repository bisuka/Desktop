routes書き方

Railsのルーティングの種類と要点まとめ
https://qiita.com/senou/items/f1491e53450cb347606b

https://railsdoc.com/routes

resources		7つの基本アクションを使用できる
member  		resourcesの中で:idありのルーティングを記述する
collection		resourcesの中で:idなしのルーティングを記述する

|  **HTTP****リクエスト** | **URL****(パス)** | **コントローラ名****#****アクション名** |
|-----|-----|-----|

ルート指定		root 'books#top'
通常指定		get  "tweets/new"  => "tweets#new"

●rails routesの見方

Prefix				パスが入った変数のようなもの。resourcesメソッドを使ってルーティングを定義すると自動で作成されます。
VerbHTTP			メソッドを表します。URI Patternのパスにどのhttpリクエストでアクセスするかを示しています。
URI Pattern			ブラウザのURL（ルーティングのパスを表します）
Controller#Action		httpリクエストでパスが送られた際に処理が行われるコントローラとアクションを表します。#左がコントローラ名、右がアクション名を示します。

Prefix   		Verb  	 URI Pattern                       	 Controller#Action
new_tweet   	GET    	/tweets/new(.:format)      	 tweets#new

●URLの書き方		edit以外HTTPメソッドで使い分ける
Index	books			get
Create	books			post
Show	books/:id			get
Edit		books/:id/edit		get
Update	books/:id			patch
Delete	books/:id			destroy

