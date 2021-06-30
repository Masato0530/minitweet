# README

# テーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| email     | string | null: false |
| password  | string | null: false |
| nickname  | string | null: false |

## Association

- has_many :tweets
- has_many :comments

## tweets テーブル

| Column      | Type    | Options                        |
| --------    | ------  | -----------                    |
| image       | text    |                                |
| text        | text    |                                |
| user_id     | integer | null: false, foreign_key: true |

## Association

- belongs_to :user
- has_many :comments

## comments テーブル

| Column      | Type    | Options                        |
| --------    | ------  | -----------                    |
| text        | text    | null: false                    |
| user_id     | integer | null: false, foreign_key: true |
| tweet_id    | integer | null: false, foreign_key: true |

## Association

- belongs_to :tweet
- belongs_to :user