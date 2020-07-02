# HTML CSS 編

## 6/30 学習内容

## レスポンシブウェブデザイン

### レスポンシブウエブデザインとは

- 1 つの HTML に対して様々なデバイスに対応した CSS をそれぞれ入力し適応させることによって管理すること

#### メリット

1. 1 つの HTML で管理するため、一回の更新で済む

2. ユーザーがシェアしやすい

3. 検索の上位に入りやすくなることがある

#### デメリット

1. 1 つのスタイルシートに入力した場合に個別に作るより CSS がやや複雑になる

2. 読み込みに時間がかかる

3. デザインに制限がかかる

## まずは viewport を設定しよう

1. HTML の head に`<meta name = "viewport" content ="whidth =device-whidth, initial-scale=1>`を入力する

## mediay

1. CSS に入力する方法

- スタイルシートに`@media(min-whidth:数値1) and (max-whidth:数値2){ }`と入力する

- 中央の and の前後には半角空白が必要

- ディスプレイが数値 1 以上数値 2 以下の時に{}ないの CSS が適応される

- これをスマホ用、タブレット用、パソコン用を作り適応させる CSS を振り分けることによって 1 つの HTML とスタイルシートで 3 種類のデバイスに対応した Web サイトが作れる

2. link 要素として指定する方法

- いつも通り`<link rel="stylesheet" href="./css/style.css">`と入力する 最後に空白を入れ`media ="screen and (max-whidth:数値)`を入力する

- `<link rel="stylesheet" href="./css/style.css" media ="screen and (max-whidth:数値)>`この形になったら数値以下の画面にはこの CSS が適応される

- それ以上は適応されないのでまた新しく`<link rel="stylesheet" href="./css/style.css" media ="screen and (min-whidth:数値1) and (max-whidth:数値2)>`を追加してそれ以上のサイズに適応したスタイルシートを作る

- 更新は複数必要だが一つ一つ分かれていて CSS が見やすい
