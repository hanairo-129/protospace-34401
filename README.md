# README

# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototype
- has_many :comments

## prototypes テーブル

| Column    | Type          | Options                        |
| ------    | ------------- | ------------------------------ |
| title     | string        | null: false, foreign_key: true |
| catch     | text          | null: false, foreign_key: true |
| concept   | text          | null: false, foreign_key: true |
| image     | ActiveStorage |                                |
| user      | references    |                                |

### Association

- has_many :prototype
- has_many :comments

## comments テーブル

| Column       | Type       | Options     |
| ------------ | ---------- | ----------- |
| text         | string     | null: false |
| user         | references |             |
| prototype    | references |             |

### Association

- belongs_to :user
- belongs_to :prototype


