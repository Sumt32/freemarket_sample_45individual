# README

## itemsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|price|integer|null: false|
|image|string|null: false, unique: true|
|like|integer|null: false|
|user_id|references|null: false, foreign_key: true|
|category_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :category

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
|mail|string|null: false, unique: true|
|password|string|null: false, unique: true|

### Association
- has_many :items

## categoriesテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items
