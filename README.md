## usersテーブル
| Column          | Type   | Options     |
| --------------- | ------ | ----------- |
| nickname        | string | null: false |
| first_name      | string | null: false |
| last_name       | string | null: false |
| first_name_kana | string | null: false |
| last_name_kana  | string | null: false |
| email           | string | null: false |
| password        | string | null: false |
| birthday        | date   | null: false |

### Association

- has_many : products
- has_many : comments
- has_many : purchasehistorys

## productsテーブル
| Column      | Type       | Options     |
| ----------- | ---------- | ----------- |
| name        | string     | null: false |
| price       | integer    | null: false |
| text        | text       | null: false |
| status_id   | integer    | null: false |
| category_id | integer    | null: false |
| burden_id   | integer    | null: false |
| area_id     | integer    | null: false |
| period_id   | integer    | null: false |
| user | references | null: false, foreign_key: true |

### Association

- has_many : comments
- belongs_to : user
- has_one : purchasehistory

## commentsテーブル
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| comment  | string | null: false |
### Association

- belongs_to : usre
- belongs_to : comment

## purchasehistoryテーブル

| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| user     | references | null: false, foreign_key: true |
| product  | references | null: false, foreign_key: true |

### Association

- belongs_to: user
- belongs_to: product
- has_one: address

## addresssテーブル

| Column         | Type    | Options     |
| -------------- | ------- | ----------- |
| postalcode     | string  | null: false |
| prefectures_id | integer | null: false |
| city           | string  | null: false |
| address        | string  | null: false |
| buildingname   | string  |             |
| tel            | string  | null: false |
| purchasehistory | references | null: false, foreign_key: true |

### Association
- belongs_to: purchasehistory

