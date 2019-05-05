## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|group_id|integer|

### Association
- has_many :messeges
- has_many :groups, through: :member
- has_many :members

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|

### Association
- has_many :users, through: :member
- has_many :members

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|text|
|group_id|integer|
|user_id|integer|

### Association
- belongs_to :users
