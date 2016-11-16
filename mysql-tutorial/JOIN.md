#JOIN 
##INNER JOIN
  内连接或等值连接：获取两个表中字段匹配的记录
## OUTER JOIN:
  LEFT OUTER JOIN OR LEFT JOIN
  1. 左连接从左表(A)产生一套完整的记录,与匹配的记录(右表(B))如果没有匹配,右侧将包含null。
  RGIHT OUTER JOIN OR RGIHT JOIN
  FULL OUTER JOIN OR FULL JOIN
## CROSS JOIN
  交叉连接，结果是两个表的笛卡尔积
  注：笛卡尔（Descartes）乘积又叫直积。假设集合A={a,b}，集合B={0,1,2}，则两个集合的笛卡尔积为
{(a,0),(a,1),(a,2),(b,0),(b,1), (b,2)}。可以扩展到多个集合的情况。类似的例子有，如果A表示某学
校学生的集合，B表示该学校所有课程的集合，则A与B的笛卡尔积表示所有可能的选课情况。
　实际上，在 MySQL 中（仅限于 MySQL） CROSS JOIN 与 INNER JOIN 的表现是一样的，在不指定 ON 条
件得到的结果都是笛卡尔积，反之取得两个表完全匹配的结果。INNER JOIN 与 CROSS JOIN 可以省略 INNER 或 CROSS 关键字。   

1. ON 条件（"A LEFT JOIN B ON"条件表达式中的ON）用来决定如何从 B 表中检索数据行。如果 B 表中没有任何一行数据匹配 ON 的条件,将会额外生成一行所有列为 NULL 的数据
在匹配阶段 WHERE 子句的条件都不会被使用。仅在匹配阶段完成以后，WHERE 子句条件才会被使用。它将从匹配阶段产生的数据中检索过滤。
    Reference: https://www.oschina.net/question/89964_65912
2. (1) 尽量用INNER JOIN，避免LEFT JOIN和NULL
   (2) 在使用LEFT(RIGHT) JOIN时，一定要给出尽可能多的匹配条件，减少Where的执行(尽可能满足ON的条件，而少用Where的条件)。
   (3) 尽量避免子查询，而用JOIN
   Reference: http://www.cnblogs.com/BeginMan/p/3754322.html