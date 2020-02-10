
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :group_members
- has_many :groups, through: :group_members

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|references :group|foreign_key: true|
|user_id|references :user|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :group_members
- has_many :users, through: :group_members

## group_membersテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|references :group|foreign_key: true|
|user_id|references :user|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group