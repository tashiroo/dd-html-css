# HTML CSS 編

## 7/01 学習内容 フレックスボックス

### flexBox の準備

- flexBox を使うには親要素が必要、なければ親要素を作ってからはじめよう

### flax item と flex conteinar

| 名前           | 特徴                                                               | 定義するもの                                                |
| -------------- | ------------------------------------------------------------------ | ----------------------------------------------------------- |
| flax item      | flex Box で並べられた要素を flax item という                       | `要素{プロパティリスト flax item 参照}`                     |
| flex conteinar | flax item を収納する領域つまり親要素のことを flex conteinar という | `要素{ display:flex;+プロパティリスト flex conteinar 参照}` |

1. flex conteinar には主軸と交差軸がある

| 名前   | 特徴                                     |
| ------ | ---------------------------------------- |
| 主軸   | block や inline など要素が沿って並ぶ方向 |
| 交差軸 |                                          |

2. 補足 display の block と inline について

| 名前   | 例                    | 並び       | 特徴 1                           | 特徴 2                                   | 特徴 3                                                                  |
| ------ | --------------------- | ---------- | -------------------------------- | ---------------------------------------- | ----------------------------------------------------------------------- |
| block  | h1 タグや p タグなど  | 上から下へ | 要素の間に改行が入り縦に並ぶもの | 幅と高さを指定できる                     | 余白をつけることができる つまり padding と margin が指定できる          |
| inline | a タグや img タグなど | 左から右へ | 要素同士が横に並ぶもの           | img など一部を除き幅と高さを指定できない | 上下の余白をつけることができない margin の top と bottom が指定できない |

### プロパティリスト flex conteinar

1. flex-direction 主軸の向きを決めるプロパティ

- 例 `flex-direction:名前;`

| 名前           | 主軸の向き 並び | 交差軸の向き 並び | 特徴                                                           |
| -------------- | --------------- | ----------------- | -------------------------------------------------------------- |
| row            | 左から右へ並ぶ  | 上から下に並ぶ    | 特に指定がなければこれに設定される inline のような並び方になる |
| row-reverse    | 右から左へ並ぶ  | 上から下に並ぶ    | row から見て逆の方向になる                                     |
| column         | 上から下へ並ぶ  | 右から左に並ぶ    | 主軸が縦になり block のような並び方になる                      |
| column-reverse | 下から上へ並ぶ  | 右から左に並ぶ    | colmn から見て逆の方向になる                                   |

2. justify-content 主軸に対してどう並べるかを決めるプロパティ

- 例 `justify-content:名前;`

| 名前          | 主軸から見てどう並ぶか       | 特徴                                                      |
| ------------- | ---------------------------- | --------------------------------------------------------- |
| flex-start    | 主軸の向きに沿って並ぶ       | 特に指定がなければこれに設定される row なら左に詰めて並ぶ |
| flex-end      | 主軸の向きとは反対方向に並ぶ | start から見て逆の方向になる row なら右に詰めて並ぶ       |
| center        | 主軸の向きに沿って並ぶ       | start と同じ並びだが flax item が中央にくる               |
| space-between | 主軸の向きに沿って並ぶ       | start と同じ並びだが flax item に均等に余白が入る         |

3. align-itemes 交差軸に対してどう並べるかを決めるプロパティ

- 例 `align-itemes:名前;`

- 補足 1 交差軸に余裕があるときに有効

- 補足 2 align は揃えるという意味で flexbox で使用した場合交差軸に対して働くものを指す

| 名前       | 交差軸から見てどう並ぶか       | 特徴                                                      |
| ---------- | ------------------------------ | --------------------------------------------------------- |
| flex-start | 交差軸の向きに沿って並ぶ       | 特に指定がなければこれに設定される row なら上に詰めて並ぶ |
| flex-end   | 交差軸の向きとは反対方向に並ぶ | start から見て逆の方向になる row なら下に詰めて並ぶ       |
| center     | 交差軸の向きに沿って並ぶ       | start と同じ並びだが flax item が交差軸の中央にくる       |

4. flex-wrap flex conteinar 主軸からあふれた flexitem がどのように並ぶかを決めるプロパティ

- 例 `flex-wrap:名前;`

| 名前         | 主軸から見てどう並ぶか | 交差軸の向き 並び | 特徴                                                                                              |
| ------------ | ---------------------- | ----------------- | ------------------------------------------------------------------------------------------------- |
| nowrap       | 主軸の向きに沿って並ぶ | 上から下に並ぶ    | 特に指定がなければこれに設定される flex conteinar の主軸の長さに合わせて flex item が縮んで収まる |
| wrap         | 主軸の向きに沿って並ぶ | 上から下に並ぶ    | flex conteinar の主軸の長さを超えた場合、交差軸が下に一段落増えてそこに超えた分が並んでいく       |
| wrap-reverse | 主軸の向きに沿って並ぶ | 下から上に並ぶ    | 主軸に関しては wrap と同じ並びだが交差軸が逆さまになり上に一段落増えてそこに超えた分が並んでいく  |

5. align-content flex-wrap の並びを交差軸に対してどの位置づけにするかを決めるプロパティ

- 例 `align-content:名前;`

| 名前          | 交差軸から見てどう並ぶか | 特徴                                                                      |
| ------------- | ------------------------ | ------------------------------------------------------------------------- |
| flex-start    | 交差軸の向きに沿って並ぶ | 特に指定がなければこれに設定される 交差軸に対して上に詰めて並ぶ           |
| flex-end      | 交差軸の向きに沿って並ぶ | start と同じ形のまま交差軸に対して下に詰めて並ぶ                          |
| center        | 交差軸の向きに沿って並ぶ | start と同じ形のまま交差軸の中央に詰める                                  |
| space-between | 交差軸の向きに沿って並ぶ | start と同じ形のまま flax item の余白が交差軸に対して均等に振り分けられる |

### プロパティリスト flex item

1. align-self 交差軸に対してどの位置に flexitem を置くかを決めるプロパティ

- 例 `align-self:名前;`

| 名前       | 交差軸から見てどの位置になるか | 特徴                               |
| ---------- | ------------------------------ | ---------------------------------- |
| flex-start | 交差軸の一番上                 | 特に指定がなければこれに設定される |
| flex-end   | 交差軸の一番下                 |                                    |
| center     | 交差軸の真ん中                 |                                    |

2. order 並ぶ順番を決めるプロパティ

- 例 `order:数字;`

| 数字     | 一応    | 特徴                                                                     |
| -------- | ------- | ------------------------------------------------------------------------ |
| 0        | 0       | 特に指定がなければこれに設定される                                       |
| 0 < 数字 | 1 以上  | 数字の大きさが優先順位となり大きければ大きいほど主軸の先頭から並べられる |
| 数字 < 0 | -1 以下 | 数字の小ささが小さいほど主軸の最後から並べられる                         |

3. flex-basis 要素の長さを決めるプロパティ

- 例 `flex-basis:数値;`

- 補足 1 row の時は幅で column の時は高さになる

- 補足 2 主軸の長さに対してどれくらいの長さをとるかきめる

- 補足 3 row の時は max-whidth が column の時は max-higtht が指定されているとそれ以上の値を設定しても max のほうが優先される

| 数値    | 特徴                               |
| ------- | ---------------------------------- |
| auto    | 特に指定がなければこれに設定される |
| 数値 px | 指定した数値の長さになる           |

4. flex-grow flex flex-conteiner の余白の分配を決めるプロパティ

- 例 `flex-grow:数字;`

| 名前     | 一応   | 特徴                                                               |
| -------- | ------ | ------------------------------------------------------------------ |
| 0        | 0      | 特に指定がなければこれに設定される、その時は余白の分配は行われない |
| 0 < 数字 | 1 以上 | 指定した flexitem 全体で余白に対して指定した数字の比率が適応される |

5. flex-shrink flexitem をどのくらい縮めて flex-conteiner の長さを全ての flexitem に分配するプロパティ

- 例 `flex-shrink:名前;`

| 名前     | 交差軸から見てどう並ぶか | 特徴                                                                                 |
| -------- | ------------------------ | ------------------------------------------------------------------------------------ |
| 0        | 0                        | 特に指定がなければこれに設定される、その時は flexitem は縮まない                     |
| 0 < 数字 | 1 以上                   | 指定した flexitem 全全てが flex-conteiner の長さ対して指定した数字の比率が適応される |

#### 注意点 flex item のプロパティについて

- flex item に適応させるので一個一個の item に対してのみ対応するプロパティ
