# DB設計
## usersテーブル
|Column|Type|Option|
|------|----|------|
|username|string|null: false,index: true|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

## groupsテーブル
|Column|Type|Option|
|------|----|------|
|groupname|string|null: false|
- has_many :groups_users
- has_many :usres, through: :groups_users
- has_many :messages

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group