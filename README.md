# Name（リポジトリ/プロジェクト/OSSなどの名前）
 
分かりやすくてカッコイイ名前をつける（今回は"hoge"という名前をつける）
 
"hoge"が何かを簡潔に紹介する
 
# DEMO
 
"hoge"の魅力が直感的に伝えわるデモ動画や図解を載せる
 
# Features
 
"hoge"のセールスポイントや差別化などを説明する
 
# Requirement
 
"hoge"を動かすのに必要なライブラリなどを列挙する
 
* huga 3.5.2
* hogehuga 1.0.2
 
# Installation
 
Requirementで列挙したライブラリなどのインストール方法を説明する
 
```bash
pip install huga_package
```
 
# Usage
 
DEMOの実行方法など、"hoge"の基本的な使い方を説明する
 
```bash
git clone https://github.com/hoge/~
cd examples
python demo.py
```
 
# Note
 
注意点などがあれば書く
 
# Author
 
作成情報を列挙する
 
* 作成者
* 所属
* E-mail
 
# License
ライセンスを明示する
 
"hoge" is under [MIT license](https://en.wikipedia.org/wiki/MIT_License).


いとエモし、

家にいながらエモい画像や写真をお互いが投稿し合う事を目的としたサイト、

会員登録をしなくても画像などを見るだけならできます、
会員登録をすると画像の投稿とマイページ閲覧ができるようになります、
会員登録は＠の入った適当な文　パスワードは６桁以上、

今後の実装予定、
いいね機能、
携帯でも見れるように調整、


DB設計
tweetテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|-------|
|image|text|-------|
|user_id|integer|null: false, foreign_key: true|

Association
belongs_to :user
has_many :comments


commentテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|
|text|text|null: false|

Association
belongs_to :tweet
belongs_to :user


userテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null:false|
|email|string|null:false|
|password|string|null:false|

Association
has_many :tweets
has_many :comments
