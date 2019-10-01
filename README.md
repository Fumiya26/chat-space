## usersテーブル

|Column|Type|Options|
|------|----|-------|
| name |string|null: false, index: true, unique: true|
| mail |string|null: false, unique: true|

### Association
- has_many :groups,through::group_users
- has_many :group_users
- has_many :messages


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
| name |string|null: false, index: true, unique: true|

### Association
- has_many :users,through::group_users
- has_many :group_users
- has_many :messages

## group_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group |references|index:true,foreign_key:true,null:false|
| user |references|index:true,foreign_key:true,null:false|

### Association
- belongs_to :user
- belongs_to :group

## messageテーブル
|Column|Type|Options|
|------|----|-------|
| body |text|null:false|
|image |string|     |
|group |references|foreign_key:true|
| user |references|foreign_key:true|

### Association
- belongs_to :user
- belongs_to :group



