
## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text| |
|image|string| |
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|timestamp|timestamp||

### Association
- belongs_to :members
 



## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_name|string|null: false, foreign_key: true|
|group_name|string|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
- has_many :messages, 


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|

### Association
- has_many :users_groups, dependent: :
- has_many :users, through: :users_groups
- belongs_to :users



## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|password|string|null: false, |
|email|string|null: false, Addindex|

### Association
- has_many :users_groups, dependent: :
- has_many :groups, through: :users_groups
- has_many :groups