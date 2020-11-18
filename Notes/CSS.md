CSS
**
**
複数選択	セレクタ1,セレクタ2	カンマ区切り
絞り込み　セレクタ1 セレクタ2	区切り文字が空白

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #6c6b6b;
}

の必要性

これを書かないとブラウザのデフォルトで
*p {*
*    display: block;*
*    margin-block-start: 1em;*
*    margin-block-end: 1em;*
*    margin-inline-start: 0px;*
*    margin-inline-end: 0px;*
*}*
*こんなんが反映される*

clearfixの使い方
先頭に壁を貼る	.clearfix::before

HTMLで右寄せ・中央寄せ・左寄せをする方法【初心者向け】 **https://techacademy.jp/magazine/12728**

