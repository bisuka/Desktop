DBとseedの使い方

モデル作成			$ rails g model モデル名　※モデル名は先頭大文字で
カラム同時作成　	$ rails g model モデル名 ○○:text ○○:string ○○:integer など

カラムの追加		2種類ある
				$ rails g migration Add追加するカラム名To追加したいテーブル名 カラム名:データ型
				$ rails g migration Add任意のファイル名To追加したいテーブル名 カラム名:データ型
				※テーブル名はマジレーションファイル名ではない

例				$ rails g migration AddNameToUsers  カラム名:型名
キャメルケース		内部的にはadd name to usersと書かれている
カラムの削除		

マイグレーションファイル削除https://qiita.com/ISSO33/items/33a935cb3255c269bef2

マイグレーションファイルがサーバーに上がっているか確認				rails db:migrate:status
指定したマイグレーションファイルをdownにする					rails db:migrate:down VERSION=20200409150025_create_as.rb
マイグレーションファイル削除									rm -rf db/migrate/マジレーションファイル名					

DBに反映			$ rails db:migrate  			反映されるのは最初の１回のみで２回目は反映されない
				$ rails db:migrate:reset		DBをリセットして最初からつくり直す
				$ rails db:rollback STEP=N	サーバーからローカルに戻す(N+1個前まで戻る)
				$ rails db:seed			seed反映

Models			Book.rb	# booksのテーブルに関連したこと書くファイル
Migrate   			create_books.rb   テーブルやカラムの設定を各ファイル
schemaに作るテーブルを定義する　create_tableは○○というテーブルを作りますという意味
Schema	        		作られたテーブルが記載

情報は、テーブルに保存されます。テーブルに保存された情報を引き出すのは、そのテーブルに対応するモデルです。
どのテーブルとモデルが関連付けられているかは、名前によって判断されます

★seedの使い方
モデル.create!{
	カラム: “値”,
	カラム: “値”
}
nilは入れられない

def order_count
    	sum = 0
    	# selfには呼び出し元のモデルが入る
    	self.order_items.each do |order_item|
    		sum += order_item.quantity
    	end
    	return sum
end

