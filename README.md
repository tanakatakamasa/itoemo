# いとエモし
 
家にいながらエモい画像や写真をお互いが投稿し合う事を目的としたサイト、
 
# DEMO
 

 
# Features
 
* 会員登録をしなくても画像などを見るだけならできます、
* 会員登録をすると画像の投稿とマイページ閲覧ができるようになります、
* 会員登録は＠の入った適当な文　パスワードは６桁以上、
 
# Requirement
 
* ruby 2.5.1
* rails 5.2.3
* mysql2 0.5.3
  
# Note
 
今後の実装予定
 * いいね機能、
 * 携帯でも見れるように調整、
 
# Author
 
* 作成者   田中崇雅
* E-mail  73.tanaka.takamasa@gmail.com


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
