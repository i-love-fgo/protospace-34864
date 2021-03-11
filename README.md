## usersテーブル

| Column     | Type   | Options          |
| ---------- | ------ | -----------------|
| email      | string | null: false      |
| password   | string | null: false      |
| name       | string | null: false      |
| profile    | text   | null: false      |
| occupation | text   | null: false      |
| position   | text   | null: false      |

### Association

- has_many :prototype
- has_many :comments

## prototypesテーブル

| Column     | Type       | Options           |
| ---------- | ---------- | ----------------- |
| title      | string     | null: false       |
| catch-copy | text       | null: false       |
| concept    | text       | null: false       |
| image      | (ActiveStorageで実装)           |
| user       | references | null: false       |

### Association

- has_many :comments
- belongs_to :user

## commentsテーブル

| Column     | Type        | Option           |
| ---------- | ----------- | ---------------- |
| text       | text        | null: false      |
| user       | references  | null: false      |
| prototype  | references  | null: false      |

### Association

- belongs_to :user
- belongs_to :prototype