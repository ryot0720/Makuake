# README

### User

| Column      | Type        | Options             |
|:-----------|------------:|:------------:|
| name        | string      | null :false         |
| email       | string      | null :false         |
| password    | string      | null :false         |

##### has_many projects, through users_projects
##### has_many products, through users_products

### User_Project

| Column       | Type        | Options           |
|:-----------|------------:|:------------:|
| user_id      | integer     | reference         |
| project_id   | integer     | reference         |

##### belongs_to user
##### belongs_to projects

### Project

| Column        | Type        | Options              |
|:-----------|------------:|:------------:|
| name          | string      | null :false          |
| explanation   | text        | null :false          |
| category      | string      | null :false          |
| image         | string      |                      |
| movie         | string      |                      |
| proposer      | string      | user_id?             |
| occation      | string      |                      |
| aim_money     | integer     | null :false          |
| collect_money | integer     | null :false          |
| archieve_rate | integer     | null :false          |
| supporter_num | integer     | null :false, user_id?|
| category      | string      |                      |

##### has_many users, through users_projects
##### has_many courses
##### has_many tags, through tags_projects
##### has_many posts, through posts_projects
##### has_many reports, through reports_projects
##### has_many comments, through comments_projects


### User_Product

| Column        | Type        | Options             |
|:-----------|------------:|:------------:|
| user_id       | integer     | reference           |
| product_id    | integer     | reference           |

##### belongs_to user
##### belongs_to products

### Product

| Column        | Type        | Options             |
|:-----------|------------:|:------------:|
| name          | string      | null :false         |
| image         | string      |                     |
| movie         | string      |                     |
| explanation   | text        | null :false         |
| price         | integer     | null :false         |
| pcs           | integer     |                     |
| delivery_day  | string      | null :false         |

##### has_many users, through users_products

### Course

| Column         | Type        | Options              |
|:-----------|------------:|:------------:|
| name           | string      | null :false          |
| pcs            | integer     | null :false          |
| price          | integer     | null :false         |
| explanation    | text        | null :false          |
| image          | string      |                      |
| movie          | string      |                      |
| deliver_address| string      |                      |
| delivery_day   | text        | null :false          |
| project_id     | integer     | reference            |

##### belongs_to project

### Tag

| Column        | Type        | Options             |
|:-----------|------------:|:------------:|
| name          | string      | null :false         |

##### has_many projects, through tags_projects

### Tag_Project

| Column       | Type        | Options           |
|:-----------|------------:|:------------:|
| tag_id       | integer     | reference         |
| project_id   | integer     | reference         |

### Post

| Column        | Type        | Options             |
|:-----------|------------:|:------------:|
| body          | text        | null :false         |

##### has_many projects, through posts_projects

### Post_Project

| Column       | Type        | Options           |
|:-----------|------------:|:------------:|
| post_id      | integer     | reference         |
| project_id   | integer     | reference         |

### Report

| Column        | Type        | Options             |
|:-----------|------------:|:------------:|
| body          | text        | null :false         |

##### has_many projects, through reports_projects

### Report_Project

| Column       | Type        | Options           |
|:-----------|------------:|:------------:|
| report_id    | integer     | reference         |
| project_id   | integer     | reference         |

### Comment

| Column        | Type        | Options             |
|:-----------|------------:|:------------:|
| body          | text        | null :false         |

##### has_many projects, through comments_projects

### Comment_Project

| Column       | Type        | Options           |
|:-----------|------------:|:------------:|
| comment_id   | integer     | reference         |
| project_id   | integer     | reference         |
