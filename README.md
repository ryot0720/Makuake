# README

| User        |             |                     |
| Column      | Type        | Options             |
| name        | string      | null :false         |
| email       | string      | null :false         |
| password    | string      | null :false         |

has_many projects, through users_projects
has_many products, through users_products

| User_Project |             |                   |
| Column       | Type        | Options           |
| user_id      | integer     | reference         |
| project_id   | integer     | reference         |

belongs_to user
belongs_to projects

| Project       |             |                     |
| Column        | Type        | Options             |
| name          | string      | null :false         |
| explanation   | text        | null :false         |
| category      | string      | null :false         |
| image         | string      |                     |
| movie         | string      |                     |

has_many users, through users_projects
has_many courses

| User_Product  |             |                     |
| Column        | Type        | Options             |
| user_id       | integer     | reference           |
| product_id    | integer     | reference           |

belongs_to user
belongs_to products

| Product       |             |                     |
| Column        | Type        | Options             |
| name          | string      | null :false         |
| explanation   | text        | null :false         |
| price         | integer     | null :false         |
| pcs           | integer     |                     |
| delivery_day  | string      | null :false         |

has_many users, through users_products

| Course        |             |                     |
| Column        | Type        | Options             |
| name          | string      | null :false         |
| pcs           | integer     | null :false         |
| explanation   | text        | null :false         |
| image         | string      |                     |
| supporter_num | integer     | null :false         |
| delivery_day  | text        | null :false         |
| project_id    | integer     | reference           |

belongs_to product
