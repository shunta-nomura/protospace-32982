# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| password   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments



## prototypes テーブル

| Column     | Type                 | Options     |
| ---------- | -------------------- | ----------- |
| title      | string               | null: false |
| catch_copy | string               | null: false |
| concept    | string               | null: false |
| image      | activeStorage        |             |
| user       | references           |             |

### Association

- belongs_to :users
- has_many   :comments


## comments テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| text    | string     | null: false                    |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

### Association

- belongs_to :users
- belongs_to :prototypes