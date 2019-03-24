# Redis

## 基础部分

* Redis 有哪些数据结构

> 字符串、字典、列表、集合、有序集合

* Redis 的分布式锁如何使用

> 单 Redis 实例：SET resource_name my_random_value NX EX 5
>
> 分布式环境：Redlock 算法