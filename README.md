# アプリケーション名
BIKER SPACE

# アプリケーション概要
バイク乗りのための投稿シェアアプリ

# URL
https://bikerspace.herokuapp.com/

# テスト用アカウント

## 出品者用アカウント
メールアドレス sample@sample.com  
パスワード yuuki420968

## 購入者用アカウント
メールアドレス sample1@sample.com  
パスワード yuuki420968

# 利用方法
1.トップページのヘッダーからユーザー新規登録を行う  
2.新規投稿ボタンから各フォームに記述をした後新規投稿を行う。  

# アプリケーションを作成した背景
自分自身バイクが好きでバイクの情報などを共有して情報交換する場の一つになれば良いなと考え企画。

 # 洗い出した要件
 https://docs.google.com/spreadsheets/d/12UAjSP_gOKSy9mt7NRsRrddKjUFSyl0BqZsFo6Adavw/edit#gid=982722306

  # 実装予定の機能
  ビューの改革  
  いいね機能の実装

# データーベース設計
[![Image from Gyazo](https://i.gyazo.com/4a2ac98365291efcf2f31218bf247a24.png)](https://gyazo.com/4a2ac98365291efcf2f31218bf247a24)

# 開発環境
Ruby on rails  
Git Hub  
AWS  
Heroku

#  工夫したポイント
自分でわからないことはインターネット、過去の勉強内容、を駆使して自力で制作できたのが今後の開発現場で求められるであろう、自走力を養うことができたと感じております。


# DB 設計

## users table

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| email              | string              | null: false, unique: true |
| encrypted_password | string              | null: false               |
| name               | string              | null: false               |
| profile            | text                | null: false               |
| my_bike            | string              | null: false               |
| residence          | text                | null: false               |

### Association

* has_many :bikes
* has_many :comments

## bikes table

| Column             | Type       | Options                          |
|-----------------------------------------------------------------|
| title              | string     | null: false                   |
| catch_copy         | text       | null: false                   |
| concept            | text       | null: false                   |
| user               | references | null: false, foreign_key: true|

### Association

- belongs_to :user
- has_many :comments

## comments table

| Column      | Type       | Options                        |
|-------------|------------|--------------------------------|
| content     | text       | null: false                    |
| bike        | references | null: false, foreign_key: true |
| user        | references | null: false, foreign_key: true |

### Association…

- belongs_to :bikes
- belongs_to :user