# explain

## 1概念    

explain模拟优化器执行SQL语句，在5.6以及以后的版本中，除过select，其他比如insert，update和delete均可以使用explain查看执行计划，从而知道mysql是如何处理sql语句，分析查询语句或者表结构的性能瓶颈。 
作用 
1、表的读取顺序 
2、数据读取操作的操作类型 
3、哪些索引可以使用 
4、哪些索引被实际使用 
5、表之间的引用 
6、每张表有多少行被优化器查询

## 2 explain用法

explain+SQL语句即可！ 
执行计划包含的信息如下

 

> ![1561642689507](C:\Users\ADMINI~1\AppData\Local\Temp\1561642689507.png)



## 3 SQL执行顺序

  想要优化SQL，必须清楚知道SQL的执行顺序，这样再配合explain才能事半功倍！ 

​	完整SQL语句

```
select distinct 
        <select_list>
from
    <left_table><join_type>
join <right_table> on <join_condition>
where
    <where_condition>
group by
    <group_by_list>
having
    <having_condition>
order by
    <order_by_condition>
limit <limit number>
```


 

  	SQL执行顺序

```
1、from <left_table><join_type>
2、on <join_condition>
3、<join_type> join <right_table>
4、where <where_condition>
5、group by <group_by_list>
6、having <having_condition>
7、select
8、distinct <select_list>
9、order by <order_by_condition>
10、limit <limit_number>
```


 

## 4 extend

    extended关键字：仅对select语句有效，在explain后使用extended关键字，可以显示filtered列显示了通过条件过滤出的行数的百分比估计值。 
    也可以通过show warnings显示扩展信息，输出中的 Message值SHOW WARNINGS显示优化程序如何限定SELECT语句 中的表名和列名， SELECT应用重写和优化规则后的外观，以及可能有关优化过程的其他说明。

总结
    本文主要是讲解如何看懂explain的分析结果，想要真正提升MySQL优化技能，还需要不断的练习！
--------------------- 
 