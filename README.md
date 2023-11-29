## 本项目实现的最终作用是基于JSP在线地下停车场车库管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - IC卡信息管理
 - 临时车辆入库管理
 - 修改密码
 - 停车信息管理
 - 出入库管理
 - 添加用户信息
 - 添加角色信息
 - 管理员登录
 - 管理用户信息
 - 管理角色信息
 - 车位信息管理
 - 车辆出库管理
### 第2个角色为用户角色，实现了如下功能：
 - 临时车辆入库管理
 - 修改个人信息
 - 修改密码
 - 用户登录
 - 车辆出库管理
## 数据库设计如下：
# 数据库设计文档

**数据库名：** chekusys

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [card](#card) |  |
| [fixed](#fixed) |  |
| [role](#role) | 角色表 |
| [seat](#seat) |  |
| [temp](#temp) |  |
| [user](#user) | 用户表 |

**表名：** <a id="card">card</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | card_id |   varchar   | 255 |   0    |    N     |  Y   |       |   |
|  2   | seat_id |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | user_name |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |
|  4   | user_gender |   varchar   | 1 |   0    |    N     |  N   |       |   |
|  5   | user_addr |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  6   | car_num |   varchar   | 255 |   0    |    N     |  N   |       |   |

**表名：** <a id="fixed">fixed</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | fixed_id |   varchar   | 255 |   0    |    N     |  Y   |       |   |
|  2   | card_id |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | entry_date |   date   | 10 |   0    |    N     |  N   |       |   |
|  4   | entry_time |   time   | 8 |   0    |    N     |  N   |       |   |
|  5   | out_date |   date   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  6   | out_time |   time   | 8 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="role">role</a>

**说明：** 角色表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | role_id |   varchar   | 255 |   0    |    N     |  Y   |       | 角色ID  |
|  2   | role_name |   varchar   | 255 |   0    |    N     |  N   |       |   |

**表名：** <a id="seat">seat</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | seat_id |   varchar   | 255 |   0    |    N     |  Y   |       |   |
|  2   | seat_num |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | seat_section |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  4   | seat_state |   int   | 10 |   0    |    N     |  N   |       |   |
|  5   | seat_tag |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="temp">temp</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | temp_id |   varchar   | 255 |   0    |    N     |  Y   |       |   |
|  2   | card_id |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | car_num |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  4   | entry_date |   date   | 10 |   0    |    N     |  N   |       |   |
|  5   | entry_time |   time   | 8 |   0    |    N     |  N   |       |   |
|  6   | out_date |   date   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  7   | out_time |   time   | 8 |   0    |    Y     |  N   |   NULL    |   |
|  8   | temp_money |   float   | 13 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="user">user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | user_id |   varchar   | 255 |   0    |    N     |  Y   |       | 用户ID  |
|  2   | role_id |   varchar   | 255 |   0    |    N     |  N   |       | 角色ID  |
|  3   | user_name |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |
|  4   | real_name |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  5   | user_pwd |   varchar   | 255 |   0    |    N     |  N   |       | 用户密码  |
|  6   | user_phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 手机号码  |

**运行不出来可以微信 javape 我的公众号：源码码头**
