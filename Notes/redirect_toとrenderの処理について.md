redirect_toとrenderの処理について

まとめ
index画面で投稿の一覧を表示したい場合、create内で@books = Book.allなどのように書かないとViewでエラーが生じる。
本来はindexアクションから取り出している為。

render action: :new				動いたアクションとは別のアクションのテンプレートを表示させます。
render :new					省略形
render template: "user/new"		違うコントローラー内のアクション呼び出

createアクションやdestroyアクション, updateアクションでは対応するviewファイルを作成しないことが多いため
新規投稿, 編集, 削除した際はredirect_toを用いてHTTPリクエストを行なうか、renderを用いてviewを表示します。

①controllerの処理でrenderを実行 ②renderのオプションで指定したviewファイルを表示する
【!!要注意!!】
renderを使用してviewファイルを表示したときにはactionを呼び出し処理をしているわけではありません。 上のapp/controllers/post_images_controller.rbのrenderの記述ではpost_images/new.html.erbを表示しているだけで、 newアクションを実行しているわけではありません。
原則、呼び出されるViewはアクション名.html.erbです。これはRailsの設計理念である「設定より規約」によるものです。 しかし、renderを使うことで明示的に他のViewを表示することができます。 この際、呼び出し先のviewでインスタンス変数が使われていると、呼び出し元のアクション内で定義されていなければエラーになるので注意が必要です。

【renderで記述していた時】
送信ボタンをクリックして保存に失敗しelseの分岐を通りrenderによりnew.html.erbを表示されます。 @post_imageの中にはエラーの内容が含まれ、その内容が表示されます。 また、createアクションの中でrenderして画面を表示しているのでURLも「http://localhost:3000/post_images」となります。

【redirect_toで記述していた時】
送信ボタンをクリックして保存に失敗しelseの分岐を通りredirect_toでhttp://localhost:3000/post_images/newへHTTPリクエストを送り、 ルーティングを介してapp/controllersフォルダのpost_images_controller.rbのnewアクションが実行されています。 newアクションが実行されることで@post_imageもnewされて新しいものとなっています。 このせいで保存に失敗した際に@post_imageに含まれていたエラーメッセージも、 新しくインスタンス変数を作成してnew.html.erbを表示しているのでエラーメッセージは表示されません。

