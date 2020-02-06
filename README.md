## user_テーブル

|Column|Type|Options|
|------|----|------|
|id|intenger|null: false, primary_key: true|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|

### Association
- has many :groups, throught: :groups_user
- has many :tweets

## tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|id|intenger|null: false, primary_key: true|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|id|intenger|null: false, primary_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- has_masny :users, through: groups_users
- has_masny :groups_users



## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user