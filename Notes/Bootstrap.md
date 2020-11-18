Bootstrap

https://qiita.com/akatsuki174/items/53b7367b04ed0b066bbf

col-xs-12		配置ルール　常に横並び

col-sm-12	配置ルール　既定の画面幅を下回ると縦並びになる
col-md-12
col-lg-12

**Bootstrap4でコンテンツのマージンやパディングを指定する ****http://info-i.net/bootstrap-spacing****
**

Col-4 Col-4 Col-4 　合計12になる
　↓

基本				container  row  col

テキスト位置の調整	その中にある要素に適用。なのでボタンなどを右寄せしたい場合親要素で囲む必要がある
				text-left
				text-center
				text-right

タグの位置の調整　　
margin: 0 auto; 	mx-auto
width: 200px;		width: 200px;

画像を親要素より大きくならないようにする設定　　img-fluid

mt・・・上マージン
mb・・・下マージン
ml・・・左マージン
mr・・・右マージン
mx・・・左右マージン
my・・・上下マージン
m・・・上下左右マージン
pt・・・上パディング
pb・・・下パディング
pl・・・左パディング
pr・・・右パディング
px・・・左右パディング
py・・・上下パディング
p・・・上下左右パディング

ボタン色
青　<button type="button" class="btn btn-primary">Primary</button>
灰色<button type="button" class="btn btn-secondary">Secondary</button>
緑　<button type="button" class="btn btn-success">Success</button>
赤　<button type="button" class="btn btn-danger">Danger</button>
黄色<button type="button" class="btn btn-warning">Warning</button>
水色<button type="button" class="btn btn-info">Info</button>
白　<button type="button" class="btn btn-light">Light</button>
黒　<button type="button" class="btn btn-dark">Dark</button>
透明<button type="button" class="btn btn-link">Link</button>

