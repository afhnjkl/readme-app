## userテーブル
|Column|Type|Options|
|------|----|------|
|id|intenger|null: false, primary_key: true|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has many :groups, throught: :groups_users
- has many :messages
- has many :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|id|intenger|null: false, primary_key: true|
|image|text||
|text|text||
|user|references|foreign_key: true|
|group|references|foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|id|intenger|null: false, primary_key: true|
|name|string|null: false|
### Association
- has many :users, through: groups_users
- has many :groups_users
- has many :messages

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user