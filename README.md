# README

## itemsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|price|integer|null: false|
|image|string|null: false, unique: true|
|condition|string|null: false|
|delivery_way|string|null: false|
|delivery_day|string|null: false|
|item_state|string|null: false|
|prefecture|string|null: false|
|size|string|null: false|
|brand_id|references|null: false, foreing_key: true|
|user_id|references|null: false, foreign_key: true|
|category_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many :categories
- has_many :brands


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false, unique: true|
|mail|string|null: false, unique: true|
|password|string|null: false, unique: true|
|tel|integer|null: false, unique: true|
|first_name|string|null: false|
|first_name_kana|string|null: false|
|last_name|string|null: false|
|last_name_kana|string|null: false|
|card_number|integer|null: false|
|expire_month|integer|null: false|
|expire_year|ingteger|null: false|
|security_code|integer|null: false|
|post_number|integer|null: false|
|prefecture_id|integer|null: false,foreign_key:true|
|city|string|null: false|
|address|string|null: false|
|building|string||
|building_tel|integer||
|avatar|string||
|birth_year|integer||
|birth_month|integer||
|birth_day|integer||


### Association
- has_many :items
- has_many :buyers, through::transaction
- has_many :transactions
- belongs_to :profile

## categoriesテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- belongs_to :item

## brandsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items
- has_many :categories

## transactionsテーブル

|Column|Type|Options|
|------|----|-------|
|state|string|null: false|
|like|integer|null: false|
|user_id|references|null: false, foreign_key:true|
|item_id|references|null: false, foreign_key:true|


### Association
- belongs_to :item
- belongs_to :user
- belongs_to :buyer

## profilesテーブル

|Column|Type|Options|
|------|----|-------|
|introduction|text||
|user_id|references|null: false, foreign_key:true|


### Association
- belongs_to :user
