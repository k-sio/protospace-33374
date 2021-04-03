# テーブル設計

## usersテーブル ##

| Column     | type   | option      |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments


## prototypeテーブル ##

| Column     | type       | option            |
| ---------- | ---------- | ----------------- |
| title      | string     | null: false       |
| catch_copy | text       | null: false       |
| concept    | text       | null: false       |
| user       | references | foreign_key: true |

## Association ##

- belongs_to :user
- has_many :comments


## comments table

| Colum    | Type       | Options           |
| -------- | ---------- | ----------------- |
| text     | text       | null: false       |
| prototype| references | foreign_key: true |
| user     | references | foreign_key: true |

### Association

- belongs_to :prototypes
- belongs_to :users
