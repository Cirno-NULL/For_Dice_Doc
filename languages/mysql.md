# Mysql
关于mysql的一些常见指令的记录和分析
## 创建表
```
create table 表名(
    键值 数据类型(),
    键值 数据类型()
);
```
## 数据类型
|数据类型|释义|
| ----| -----|
|int|整数类型 |
|varchar|变长字符串类型|
|date|日期类型|
|double|浮点数|
|char|定长字符串|
## 查看表结构
```
desc 表名;
```
## 修改表,增加字段
```
alter table 表名 add column 键值 数据类型()
```
## 修改表,改变字段属性
```
alter  table 表名 modify 键值名 数据类型
```
## 修改表,删除字段
```
alter table 表名 drop column 键值名
```
## 数据操作语言
  * insert
  * update
  * delete

## insert
```
#给所有字段插入数据
INSERT INTO emp VALUES(
    7934,'MILLER','办事员',7782,
    str_to_date(
        '1982-1-23','%Y-%m-%d'
        ),
    1300,NULL,10
);

#给指定的字段插入数据
insert into emp1(empid,ename) 
values(1234,'zhangsan');
```
## select 数据查询
```
#万物起源
select * from 表名

select deptno FROM emp
#单列查询

SELECT sal , comm from emp;
#多列查询
```

## update 更新数据
```
update  emp  set comm=300, deptno=50  where empid=7902;
```

## delete 删除数据
```
delete  from  emp  
where  ename='zhangsan';
```

## drop 删除表
```
drop table 表名
```

## 常见函数
* 字符拼接
  ```
  select CONCAT('asd','qwe','zxc') from dual;
  ```
* 获取系统当前时间
  ```
  select now() from dual;
  ```
* 替换字符串
  ```
  select replace('hellojava','java','python')   from dual;
  ```
* 转大写
  ```
  select UPPER('hellojava') from dual;
  ```
* 转小写
  ```
  select LOWER('HELLO') from dual;
  ```
* substr 截取字符串
  ```
  select SUBSTR('hellojava',3) from dual;
  select SUBSTR('hellojava',-3) from dual;
  select SUBSTR('hellojava',2,4) from dual;
  #字符分割
  ```
* max,min,avg,sum
  ```
  SELECT AVG(comm),sum(comm) from emp;
  #平均数和总数
  select max(sal),min(sal)from emp;
  #最大值最小值
  ```
* count 元素总数
  ```
  select count(*)from emp
  #元素总数
  ```
* ifnull null值替换
  ```text
  SELECT ifnull(comm,0) FROM emp;
  #替换null为第二个跟随的值

  SELECT ifnull(comm,0) FROM emp;
  #替换null为第二个跟随的值

  SELECT AVG(ifnull(comm,0)),sum(comm) from emp;
  #基于替换的查询，防止漏

  SELECT sal,comm,sal+ifnull(comm,0) from emp;
  #因为替换成0所以元素不会漏了
  ```
* date_format 日期格式化
  ```
  select DATE_FORMAT(now(),"%Y-%m-%d %H:%I:%s") from dual;

  SELECT DATE_FORMAT(now(),'%Y-%m:%I%s') from dual;

  select str_to_date('1980-12-17','%Y-%m-%d') from dual;
  #日期格式化
  ```
* like 模糊查询
  ```
  SELECT * from emp
  SELECT *from emp where ename like 'a%';
  SELECT *from emp where ename like '_a%';
  SELECT *from emp where ename like '%a%';
  SELECT *from emp where ename like '%n';
  SELECT *from emp where ename like '%n_';
  #模糊查询
  ```
* char_length 字符串长度
  ```
  SELECT CHAR_LENGTH("hello") from DUAL
  SELECT CHAR_LENGTH(ename),ename from emp
  #长度
  ```
* between 限定范围查询
  ```
  SELECT * from emp where sal BETWEEN 1500 and 3000
  #在xx之间
  ```
* as 重命名/重定向
  ```
  SELECT sal as text,
  comm as test,
  sal+ifnull(comm,0) as salcom;
  from emp
  #命名替换
  ```
* distinct 去重
  ```
  SELECT DISTINCT job from emp;
  SELECT DISTINCT deptno,job from emp;
  #去重，以组合计
  ```
* order by 排序
  ```
  SELECT DISTINCT deptno,job from emp ORDER BY job DESC,deptno ASC;
  SELECT * from emp order by sal desc;
  SELECT * from emp order by deptno ,sal;
  #排序，默认正序
  ```
* where 的比大小
  ```
  SELECT * from emp WHERE sal > 1000 
  #比大小
  ```
* 多条件查询
  ```
  SELECT * from emp WHERE sal > 1000 and job ='办事员' and deptno =10
  select * from emp where job in('办事员','salesman');
  #多条件查询

  SELECT * from emp WHERE sal > 1000 
  and job in('办事员','salesman') and deptno =10
  #in的多条件连接，and的多条件连接

  select * from emp where sal >1000 
  and (job='办事员' or job='salesman');
  #or的多条件连接（注：and是串联，or是并联）
  ```

* EXISTS 跳出
  ```
  SELECT * from dept where deptno in (
  SELECT deptno from emp);

  SELECT deptno , dname ,loc FROM dept d WHERE EXISTS 
  (SELECT * from emp e where e.deptno = d.deptno)
  #exits关键字后面的查询,用到了主查询的字段数据,
  #如果在子查询中查到一条结果,则整个子查询立马返回true,后面数据不再比较
  #如果没有查询到结果,则返回false
  ```

* LIMIT 分页
  ```
  select * from emp order by sal desc LIMIT 0,3;
  select * from emp order by sal desc LIMIT 3,3;
  select * from emp order by sal desc LIMIT 6,3;

  #select * from emp1 order by sal desc LIMIT (n-1)x pagesize ,pagesize;
  #(n-1) x pagesize
  #pagesize = 100
  #n =3
  # 200 ,100
  ```

## 聚合函数
* group by 成组查询
  ```
  SELECT max(sal),min(sal),deptno FROM emp GROUP BY deptno
  #聚合函数，统计结果用，这个结果是最大值和最小值

  select avg(sal),sum(sal),deptno from emp group by deptno;
  #聚合函数，统计结果用，这个结果是统计平均值和总数

  SELECT max(sal),min(sal),deptno,job from emp group by deptno,job;
  #select中的非聚合函数字段必须出现在group by中，否则毫无意义
  ```
*  having 结果筛选
  ```
  SELECT AVG(sal),deptno from emp GROUP BY deptno HAVING AVG(sal)>2000;
  SELECT AVG(sal),deptno from emp GROUP BY deptno; # HAVING AVG(sal)>2000
  #结果筛选

  SELECT min(sal),deptno from emp group by deptno
  having min(sal)>
  (SELECT min(sal) from 
  emp WHERE deptno =30);
  #查看部门最低薪资
  #高于30号部门最低薪资的部门
  ```

## 多表查询
  ```
  select * from emp;
  select * from dept;

  SELECT * FROM emp a ,dept b
  where a.deptno = b.deptno;
  #简单多表查询,如果有null会漏
  #必须添加一个连接用的,否则直接相乘

  SELECT * from emp e,dept d
  where e.ename ='克拉克' 
  and e.deptno = d.deptno;
  #多表查询，查到结果的时候顺便显示一下部门值

  SELECT e.empid ,e.ename ,d.* 
  from emp e,dept d
  where e.ename ='克拉克' 
  and e.deptno = d.deptno；
  #多表查询，可以结合单独列举使用，可以结合重定向命名使用
  #select+重定向后的东西+from+重定向+where+多条件查询

  SELECT * from emp e,dept d #WHERE e.ename =d .dname
  #关联的时候需要指定关联条件，否则会产生笛卡尔集
  #这是一个错误示例
  ```

* 自连接查询  
  可以结合其他的东西一起使用  
  适用范围为表内有内部相关联的数据  
  可以拿来做有向图  
    ```
    SELECT * from emp;

    SELECT * from emp e,emp m 
    WHERE e.ename ="克拉克" 
    and e.mgr = m.empid;

    SELECT e.empid,e.ename,
    e.job,e.mgr,e.hiredate,
    e.sal,e.deptno,m.ename,
    m.job,m.hiredate,m.sal 
    from emp e,emp m 
    WHERE e.ename ="克拉克" 
    and e.mgr = m.empid;
    #自连接查询
    ```

## join 多表连接
* inner 直接连接  
可以忽略inner这个控制字符  
默认是以直接连接算  
  ```
  SELECT * FROM emp e 
  #INNER 
  JOIN dept d on e.deptno = d.  deptno;
  #关联查询，依旧不能不加对应集，  否则依旧会产生笛卡尔积
  SELECT * FROM emp e
  JOIN dept d on e.deptno = d.deptno 
  AND e.ename = "克拉克";
  #多表关联查询一定要加对应关系，否则绝对会出问题
  ```
* left right 主表查询
  哪边是主表就用那边
  目前想到的适用方法是节约空间
  降低打表成本
  ```
  SELECT * from emp;
  SELECT * from dept;
  update emp set deptno =50 where empid =7902
  
  SELECT * from emp e LEFT JOIN dept d 
  on e.deptno = d.deptno;
  
  SELECT * from dept d  LEFT JOIN emp e
  on e.deptno = d.deptno;
  
  SELECT * from emp e right JOIN dept d 
  on e.deptno = d.deptno;
  #关联表的主附表查询,可以将不存在的记录以null显示,哪边主表就哪边连接
  SELECT * from 
  (SELECT ename,sal,deptno from emp where sal >=3000) e 
  left join dept d 
  on e.deptno = d.deptno
  ```

## 子查询
括号里的优先级比较高一点
所以可以当成是参数或者表格来使用
  ```
  SELECT * from emp where deptno = 
  (SELECT deptno from emp where ename='scott');
  #子查询,where后面的内容优先度较高
  #此条目的是为了获取'scott'的deptno
  #然后列出deptno相同的员工
  
  SELECT * from emp where sal > 
  (SELECT sal from emp WHERE ename = 'scott');
  #子查询,where后面的内容优先度较高
  #此条目的是为了获取'scott'的工资
  #然后列出比'scott'工资高的员工
  
  SELECT * from emp where deptno in
  (SELECT DISTINCT deptno 
  from emp where job = 'salesman');
  #多值查询其一,查询与salesman相同部门的员工都有谁
  
  SELECT * from dept where deptno in 
  (SELECT deptno from emp 
  where sal >=3000);
  #多值查询其二,查询工资大于三千的人部门和地址
  ```

## view 视图

```
CREATE view emp10 as 
SELECT empid,ename,deptno 
from emp WHERE deptno =10
select * from emp10
DROP view emp10;
select * from emp10
#视图创建之后不要修改也不要插入数据
#因为插入和修改的数据都会影响到原始表
#类似于映射
#如果是多张表的视图会直接报错
```

## 索引
```
CREATE INDEX idx_emp_ename on emp(ename);
drop index idx_emp_ename on emp;
#索引推荐在较为静态的数据库中使用
#频繁插入删除的数据库使用索引带来的消耗会更高
#索引会自行维护,只要创建和删除即可
```
## 主键和序列
```
INSERT into emp (ename,job,mgr,sal,comm,deptno) 
VALUES ('曹操','测试',8000,2000,60,20);
SELECT * from emp ORDER BY empid;
DELETE from emp WHERE ename = '曹操'
SELECT * from emp ORDER BY sal desc
#主键:
#用于标识数据的唯一性
#主键字段的参数值不能为空不能重复
#一般来说数据表里的第一个字段就是主键
#序列
#一般用于提供主键的参数值
#序列会自动递增不会重复
#如果一个序列永远自动递增那就永远不会重复
#最好不要允许空值
#一般来说两个都是结合在一起使用来防止数据重复的
```

## 导出
导出需要调整  
`show global variables like '%secure_file_priv%';`  
的位置  
否则会出现无权限的问题
```
select * from emp 
ORDER BY sal desc
INTO OUTFILE 'D:\me\\test.csv'
```




## 还没想好怎么分类的查询方法
```
SELECT * from emp where comm is null;
SELECT * from emp where comm is not null;
#is null 的各种用法

SELECT sal,comm,sal+ifnull(comm,0) from emp
SELECT *,(sal+IFNULL(comm,0))*12 as year from emp where (sal+IFNULL(comm,0))*12 >30000;
#运算查询

SELECT* from 
emp e1,
(SELECT AVG(sal) avgsal,deptno from emp GROUP BY deptno) e2
WHERE e1.deptno = e2.deptno
and e1.sal > e2.avgsal;
#查询高于部门平均工资的人
#重命名
#子查询*1
#多表查询*1
#连接*1
#对比*1
```