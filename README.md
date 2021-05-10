## ProtoSpaceのER図

### users テーブル
| Column     | Type   | Option   |
| ---------- | ------ | -------- |
| email      | string | NOT null |
| password   | string | NOT null |
| name       | string | NOT null |
| profile    | text   | NOT null |
| occupation | text   | NOT null |
| position   | text   | NOT null |

### Association

- has_many :prototypes
- has_many :comments


### prototypes テーブル
| Column     | Type       | Option   |
| ---------- | ---------- | -------- |
| title      | string     | NOT null |
| catch_copy | text       | NOT null |
| concept    | text       | NOT null |
| user       | references | NOT null |

### Association

- has_many :comments
- belongs_to :user


### comments テーブル
| Column     | Type       | Option   |
| ---------- | ---------- | -------- |
| text       | text       | NOT null |
| user       | references |          |
| prototype  | references |          |

### Association

- belongs_to :phototype
- belongs_to :user


