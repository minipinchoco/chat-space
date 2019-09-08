<!-- userテーブル -->

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|

- has_many :message
- has_many :group
- has_many :group_users

<!-- messageテーブル -->

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|

- belongs_to :user
- has_many :group
- has_many :group_users

<!-- groupテーブル -->

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

- has_many :message
- has_many :user, through: :group-users

<!-- group_users -->

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

- belongs_to :group
- belongs_to :user