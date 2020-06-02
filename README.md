# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

いとエモし
家にいながらエモい画像や写真をお互いが投稿し合うサイト
会員登録をしなくても画像などを見るだけならできます
会員登録をすると画像の投稿とマイページ閲覧ができるようになります


エモい（えも－い）】 エモいとは、感情が高まって強く訴えかける心の動きを表す形容詞で、英語の「emotion」が形容詞化したものです。 一般に使われ始めたのはごく最近ですが、音楽シーンでは以前から使われていました。

いと
副詞
①大変。非常に。▽程度がはなはだしい。


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
