# README
# テーブル設計

## usersテーブル

| Column             | Type     | Options                                |
| ------------------ |----------|--------------------------------------- |
| email              | string   | NOT NULL,unique: true                  |
| encrypted_password | string   | NOT NULL                               |
| name               | string   | NOT NULL                               |
| profile            | text     | NOT NULL                               |
| occupation         | text     | NOT NULL                               |
| position           | text     | NOT NULL                               |

## Association
- has_many :prototypes_users
- has_many :comments

## prototypesテーブル

| Column             | Type     | Options                                |
| ------------------ |----------|--------------------------------------- |
| title              | string   | NOT NULL                               |
| catch_copy         | text     | NOT NULL                               |
| concept            | text     | NOT NULL                               |
| user_id            | string   | NOT NULL,外部キー                       |

## Association
- has_many :prototypes_users
- has_many :users
- has_many :comments

## commentsテーブル

| Column             | Type       | Options                                |
| ------------------ |----------  |--------------------------------------- |
| content            | text       | NOT NULL                               |
| prototype_id       | references | NOT NULL                               |
| concept            | references | NOT NULL                               |

- belongs_to :prototype
- belongs_to :user
- belongs_to :