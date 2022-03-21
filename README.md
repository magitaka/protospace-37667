# README

## usersテーブル

| Column                          | Type   | Options            |
| ------------------------------- | ------ | ------------------ |
| email                           | string | null: false, unique|
| encrypted_password              | string | null: false        |
| name                            | string | null: false        |
| profile                         | text   | null: false        |
| occupation                      | text   | null: false        |
| position                        | text   | null: false        |

### Association

- has_many :prototype
- has_many :comments

## prototypeテーブル

| Column                          | Type         | Options                        |
| ------------------------------- | ------------ | ------------------------------ |
| title                           | string       | null: false                    |
| catch_copy                      | text         | null: false                    |
| concept                         | text         | null: false                    |
| user                            | references   | null: false , foreign_key: true|

### Association

has_many :comments
belongs_to :users

## commentsテーブル

| Column                          | Type         | Options                        |
| ------------------------------- | ------------ | ------------------------------ |
| content                         | text         | null: false                    |
| prototype                       | references   | null: false , foreign_key: true|
| concept                         | references   | null: false , foreign_key: true|

### Association

- belongs_to :users
- belongs_to :prototype