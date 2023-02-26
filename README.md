# テーブル設計

## users テーブル

| Column             | Type   | Options                 |
| ------------------ | ------ | ----------------------- |
| nickname           | string | null: false             |
| email              | string | null: false unique:true |
| encrypted_password | string | null: false             |
| family_name        | string | null: false             |
| first_name         | string | null: false             |
| family_name_kana   | string | null: false             |
| first_name_kana    | string | null: false             |
| birthday           | date   | null: false             |

has_many :introduction

## 機能一覧 テーブル 
## introduction テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| function_name      | string     | null: false                    |
| category_id        | integer    | null: false                    |
| user               | references | null: false, foreign_key: true |

belongs_to :user