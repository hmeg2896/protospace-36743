# README



##usersテーブル

| Column     | Type       | Options               |
| ---------- | ---------- | ----------------------|
| email      | string     | null: false           |
| password   | string     | null: false           |
| name       | string     | null: false           |
| profile    | text       | null: false           |
| occupation | text       | null: false           |
| position   | text       | null: false           |

###アソシエーション
has_many :prototype
has_many :comments




##prototypesテーブル

| column     | Type         | options               |
| ---------- | ------------ | ----------------------|
| title      | string       | null: false           |
| catch_copy | text         | null: false           |
| concept    | text         | null: false           |
| image      | ActiveStorage| null: false           |
| user       | references   | foreign_key: true     |  

###アソシエーション
belongs_to :user
has_many :comments




##commentsテーブル

| column     | Type         | options               |
| ---------- | ------------ | ----------------------|
| text       | text         | null: false           |
| user       | reference    | foreign_key: true     |
| prototype  | reference    | foreign_key: true     |

###アソシエーション
belongs_to :user
belongs_to :prototype
