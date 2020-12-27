# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| email    | string | not: full   |
| password | string | not: full   |
| name     | string | not: full   |
| profile  | text   | not: full   |
|occupation| text   | not: full   |
| position | text   | not: full   |

### Association

- has_many :prototypes_users
- has_many :prototypes, through: prototypes_users
- has_many :comments

## prototypes テーブル

| Column   | Type     | Options     |
| ------   | ------   | ----------- |
| title    | string   | not: full   |
|catch_copy| text     | not: full   |
| concept  | text     | not: full   |
| title    | string   |             |


### Association

- has_many :prototypes_users
- has_many :users, through: prototypes_users
- has_many :comments

## prototypes_users テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
|  user    | references | not: full   |
|prototypes| references | not: full   |

### Association

- belongs_to :prototypes
- belongs_to :user

## comments テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | not: full                      |
| room    | references | not: full                      |

### Association

- belongs_to :prototypes 
- belongs_to :user