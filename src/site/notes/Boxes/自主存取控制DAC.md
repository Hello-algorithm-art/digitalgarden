---
{"dg-publish":true,"permalink":"/Boxes/自主存取控制DAC/","dgPassFrontmatter":true,"created":"2025-05-18T19:38:12.589+08:00","updated":"2025-06-23T00:30:47.737+08:00"}
---

C2级
## 说明
用户对不同的数据库对象有不同的存取权限，
不同的用户对同一对象也有不同的权限，
而且用户还将其拥有的存取权限转授给其它用户
[[Boxes/用户权限组成要素\|用户权限组成要素]]
## 实现
#sql 
```sql
//1.创建登录用户
create user u1 identified by '123'
//2.删除用户
drop user u1
//3.查看当前用户
select user()
//4.查看所有
select * from mysql.user
```
#sql 
```sql
/*Grant 权限，，
on 对象类型，对象名
to 用户，，
with grant option(可再授予) */

grant all on *.* to u1
grant all on educ.student to u3
grant select on educ.student to u4

//查看权限，show grants for u1
```

```sql
revoke 权限，，
on 对象类型，对象名
from 用户

revoke all on *.* from u1
revoke select on educ.student from u4

grant select on educ.course to u4
grant update(cname) on educ.course to u4

grant insert on educ.sc to u4
grant select on educ.sc to u4
```
普通用户登录只能链接数据库，不能访问
- 缺点：可能存在数据的无意泄露
	- 数据本身无安全性标记