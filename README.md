
 messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text| foreign_key: true|
|image|string| foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|timestamp|timestamp||

### Association
- belongs_to :user_group
 



 membersテーブル

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


 groupテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|

### Association
- has_many :users_groups, dependent: :
- has_many :users, through: :users_groups



 userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|password|string|null: false, |
|email|string|null: false, Addindex|

### Association
- has_many :users_groups, dependent: :
- has_many :groups, through: :users_groups