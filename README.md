# Mommy-book(母子手帳アプリ) <br>
http://mommy-book.herokuapp.com

- 製作者・担当箇所
- なぜ作ったのか
- 設計
- どういったページ（機能）があるのか
- 工夫・苦労した点
- 追加で実装したい機能
- まとめ

### 製作者 (STOチーム開発)<br>
https://github.com/ayk920kd<br>
https://github.com/sayuri-n<br>
https://github.com/Chiho99<br>

#### 担当箇所
https://github.com/ayk920kd<br>
（フロント）
ママ画面, 赤ちゃん画面<br>
（バック）
予防接種画面, 赤ちゃん健診画面, 妊婦健診画面(Update機能)<br>
（その他）
企画立案, 設計画面遷移図の製図, publicフォルダ整理<br>

https://github.com/sayuri-n<br>
（フロント）
サインアップ画面, サインイン画面, 赤ちゃん登録・登録確認画面<br>
（バック）
サインアップ画面, サインイン画面<br>
（その他）
企画立案, 設計画面遷移図の製図<br>

https://github.com/Chiho99<br>
（フロント）
妊婦健診画面, こどもの成長記録画面, 赤ちゃん健診画面, 予防接種画面<br>
（バック）
ママ画面, 赤ちゃん登録・登録確認画面, 赤ちゃん画面, こどもの成長記録画面, 妊婦健診画面(Create/Read/Delete機能)<br>
(その他)
（その他）
企画立案, 設計画面遷移図の製図, SlackとGithubの連携, マイグレーションファイル作成, usersテーブルテストデータ挿入, User機能の実装、デプロイ<br>

## なぜ作ったのか
私たちが生まれる前から存在する母子手帳。手帳のデザインは、年々新しくなり見た目は可愛くなっているが中身は昔ながらの手書き。
病院側が診察結果を記録しママに渡したり、ママが自分の体調の変化や子供の発育状況など記録し、次の診察で病院側に見せたりする。
ちょっとした時間に確認、記録したりすることができれば日々の忙しい時間に少し余裕ができる。
出かける時にたくさんの荷物の中から小さい母子手帳を探す一手間があれば、ひと休みにその時間を使って欲しい。
それが毎日使う携帯で簡単に見つけられ、簡単に操作ができればママ達に心の余裕ができ、少しでも心のケアの一部になって欲しいという強い思いから生まれた案。

## 設計

### 画面遷移図
<img src="https://user-images.githubusercontent.com/57189967/90416334-4d7b0400-e0ed-11ea-86b9-a77ede82c7f6.jpg">

### テーブル定義書
物理名（論理名）

Users(会員情報) テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414082-4bfc0c80-e0ea-11ea-9d3c-ed844c528f07.jpg">

Babies(赤ちゃん)テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414093-4e5e6680-e0ea-11ea-80d9-717c1ed33a97.jpg">

Vaccines(予防接種)テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414098-50282a00-e0ea-11ea-96ef-a19ec5491e50.jpg">

Baby_checkups(赤ちゃん健診）テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414106-51f1ed80-e0ea-11ea-8386-7663e572dfb8.jpg">

Baby_tooths(赤ちゃん健診(歯))テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414119-561e0b00-e0ea-11ea-8760-a35b7b1e712c.jpg">

Maternity_checkups(妊婦健診)テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414135-5a4a2880-e0ea-11ea-9b04-9781a8676b36.jpg">

Albums(こどもの成長)テーブル
<img src="https://user-images.githubusercontent.com/57189967/90414148-5f0edc80-e0ea-11ea-81d3-cf8ec1f32f02.jpg">

## どういったページ（機能）があるのか
#### サインイン・サインアップ画面 
<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90413995-2d961100-e0ea-11ea-8488-62d6b1eac78c.PNG" width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507633-2c6bef00-e191-11ea-8f64-8887de3943e7.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>


#### 赤ちゃん登録・登録確認画面 
<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507663-3b52a180-e191-11ea-9fb4-1951093032e9.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507676-3e4d9200-e191-11ea-8546-c8d9e37705e7.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>

#### ママ画面 
- 出産予定日をもとに、妊娠週数(出産前）と赤ちゃんの年齢（出産後）を逆算
- 予定日からズレが生じることなどを考慮し、ユーザーが「生まれたよ」ボタンを押すことで、出産後画面に切り替わる（「元に戻す」ボタンで戻すことも可能）
- 赤ちゃんが複数人いる場合を想定し、最新の赤ちゃん（最後に生まれる・生まれたこども）の情報を表示

出産前・出産後
<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507653-368ded80-e191-11ea-902b-7537d36ee4cd.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90414017-3686e280-e0ea-11ea-8895-520932a4cf48.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>

#### 妊婦健診画面 
- 妊婦健診に関するCRUD機能を実装

<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507640-2ece4900-e191-11ea-954c-66dbd2e04467.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507641-2f66df80-e191-11ea-9a00-52079e8fbc14.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>

最新の妊娠健診情報はママ画面で表示されるように実装
<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507644-30980c80-e191-11ea-8d25-4e87b992410a.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507647-34c42a00-e191-11ea-8851-4bc7b8da608c.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>

#### 赤ちゃん画面  
- ママ画面からの遷移後は、ママ画面で表示されていた最新の赤ちゃん情報（最後に生まれる・生まれたこども）を表示し、ママ画面の赤ちゃん情報と赤ちゃん画面の情報が一致する仕組み
- 「赤ちゃんの名前」をボタンクリックすると、その赤ちゃんの専用ページに切り替わる
- 「新規登録」ボタンを押すと、新たに赤ちゃんを登録できるよう実装

<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507689-43124600-e191-11ea-8130-00cdb1406056.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>

#### 赤ちゃん健診画面 ・　予防接種画面 ・ こどもの成長記録画面 
- 赤ちゃん健診・予防接種・こどもの成長記録それぞれに関するCRUD機能を実装
- 妊婦健診同様に、赤ちゃん健診と予防接種の最新データを赤ちゃん画面に表示
- こどもの成長記録画面では、Cloudinaryを用いた画像投稿機能を実装 https://cloudinary.com
<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507686-40afec00-e191-11ea-858c-4f59a63d8bc8.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507656-38f04780-e191-11ea-8575-d18224d32f1b.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507694-4574a000-e191-11ea-9c11-e4440a6cd0da.jpg" width = "300px" height = "400px">
    </td>
  </tr>
</table>

## 工夫・苦労した点

### 妊娠週数と赤ちゃんの年齢計算（ママ画面・赤ちゃん画面）
- 赤ちゃんの妊娠日や出産予定日は、不確実性の高いものが多く明確なデータの表示が困難であったこと

#### 解決策
1. 一般的に妊娠日は、出産予定日から280日前とされるため、以下のように立式
（妊娠日） = (出産予定日) - 280日<br>
（妊娠日数）= (今日の日付) - (妊娠日)<br>
（妊娠週数） = (妊娠日数)　÷　30日（1ヶ月） ×　4週（1ヶ月）<br>
（妊娠月数）=　(妊娠日数)　÷　30日（1ヶ月）<br>

2. データベースのstatusカラムの値が「生前」であれば「生まれたよ」ボタンとし、妊娠月数を表示
データベースのstatusカラムの値が「生後」であれば「元に戻す」ボタンとし、「出産おめでとう」と表示されるように条件分岐

3. 2の条件分岐に入れ子で月数・週数・日数表示が切り替わるようにif文で条件分岐を追加

☆赤ちゃんは予定日通りに生まれると限らないため、ユーザーの心的負担にならないようユーザー自身が出産前後を切り替えできるようにした

ママ画面出産前・出産後
<table>
  <tr>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90507653-368ded80-e191-11ea-902b-7537d36ee4cd.jpg"　width = "300px" height = "400px">
    </td>
    <td>
      <img src="https://user-images.githubusercontent.com/57189967/90414017-3686e280-e0ea-11ea-8895-520932a4cf48.jpg"　width = "300px" height = "400px">
    </td>
  </tr>
</table>

##### コード (MommyController)<br>
ママ画面での最新の赤ちゃん情報と妊娠歳月の算出、表示<br>
 <img src="https://user-images.githubusercontent.com/57189967/90488495-f752a300-e176-11ea-9ce6-3cdbe60f3e16.jpg">

ボタン選択時の条件分岐<br>
 <img src="https://user-images.githubusercontent.com/57189967/90488498-f883d000-e176-11ea-891f-18006acaf462.jpg">

 ##### コード (BabyController)<br>
 ママ画面同様の条件分岐を実装することで、それぞれの赤ちゃんの日齢・月齢・年齢を算出、表示
<img src="https://user-images.githubusercontent.com/57189967/90489479-4f3dd980-e178-11ea-9298-f47978d03455.jpg">


### 画像投稿機能
実際に行った手順 https://qiita.com/Chiho99/items/f68566425b116cfd3097
- 本番環境での画像投稿機能への初挑戦
- DB設計の段階では、ローカルでの画像保存処理用のカラムしか持たせていなかった
- テーブルのリレーションを組む際、Usersテーブルに外部キーを持たせてしまっていたため、特定のこどものページ表記が困難であった

#### 解決策
- Cloudinaryというサービスを使用し、本番環境での画像投稿処理に必要なカラムをテーブルに持たせた
- リレーションを組みなおし、Babiesテーブルに外部キーを持たせることで、自動的にUsersテーブルのidも定まり、解決

##### コード（AlbumController保存処理）
<img src="https://user-images.githubusercontent.com/57189967/90493898-e2c5d900-e17d-11ea-9de5-b0ccfbcb2ac0.png">

##### コード（AlbumController削除処理）
<img src="https://user-images.githubusercontent.com/57189967/90493900-e35e6f80-e17d-11ea-9fd4-d2c71c7e8f47.png">


## 追加で実装したい機能

- カレンダー通知機能
- ママページ（mommies.php）と赤ちゃんページ(babies.php)グラフ機能
- 子育て情報共有ページ
- ママ（ユーザー）と赤ちゃん情報の編集画面
- 子どもの食事をチェックボックスで取得可能にする
- 画像投稿での編集機能


## まとめ

今回はアジャイル開発を手法として用い、設計～開発まで2週間という短い期間だったが、
日々のデイリースクラムでお互いの進捗状況を確認しながら完成することができた。
また、これまでにGit管理/Github操作に力を入れて取り組んでいたことから、スムーズにチーム開発を行うことができたと思う。

そして、「ITを社会課題の解決に向けて役立たせたい」という想いから、このアプリケーションが生まれ、
実際に自身の経験やお母さんの目線を大切にすることで、UXを意識アプリ設計が経験できたのではないかと考える。

今までSTOで学んできたことに加え、画像投稿やUser機能といった
新たな機能の実装へ取り組むことができ、短期間ながらも多くのアウトプットができた。

将来的には、上記で述べたような機能も追加していきたいと考える。






