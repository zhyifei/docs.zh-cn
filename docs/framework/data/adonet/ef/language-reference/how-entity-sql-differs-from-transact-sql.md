---
title: Entity SQL 与 Transact-SQL 有何不同
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: e0af0a415d812337d6abf449e9ee170526c3df0c
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833714"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Entity SQL 与 Transact-SQL 有何不同
本主题介绍和 transact-sql 之间[!INCLUDE[esql](../../../../../../includes/esql-md.md)]的差异。  
  
## <a name="inheritance-and-relationships-support"></a>继承和关系支持  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 直接使用概念实体架构并支持诸如继承和关系等概念模型功能。  
  
 使用继承时，从父类型实例集合中选择子类型的实例通常是有用的。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]中 的 [oftyp](oftype-entity-sql.md)e 运算符（类似于序列C#中的`oftype`）提供了此功能。  
  
## <a name="support-for-collections"></a>集合支持  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 将集合视为一类实体。 例如:  
  
- 集合表达式在 `from` 子句中有效。  
  
- `in` 和 `exists` 子查询已被一般化，以允许使用任何集合。  
  
     子查询是一种集合。 `e1 in e2` 和 `exists(e)` 是执行这些运算的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 构造。  
  
- 集运算（例如 `union`、`intersect` 和 `except`）现在对集合执行运算。  
  
- 联接对集合执行运算。  
  
## <a name="support-for-expressions"></a>对表达式的支持  
 Transact-sql 具有子查询（表）和表达式（行和列）。  
  
 为了支持集合和嵌套集合， [!INCLUDE[esql](../../../../../../includes/esql-md.md)]使所有内容成为表达式。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]比 Transact-sql 更具可组合，每个表达式都可在任何地方使用。 查询表达式总是产生投影类型的集合，并且可以在允许使用集合表达式的任何地方使用。 有关中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]不支持的 transact-sql 表达式的信息，请参阅不支持的[表达式](unsupported-expressions-entity-sql.md)。  
  
 下面是所有有效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询。  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>子查询统一处理  
 考虑到其对表的关注，Transact-sql 会对子查询执行上下文解释。 例如，`from` 子句中的子查询被视为多集（表）。 但是，`select` 子句中使用的同一子查询被视为标量子查询。 同样， `in`运算符左侧使用的子查询被视为标量子查询，而右侧应为多集子查询。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 消除了这些差异。 表达式具有不依赖于使用它的上下文的统一解释。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]将所有子查询视为多集子查询。 如果需要从子查询获取标量值，则 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 会提供对集合（在此情况下为子查询）进行运算的 `anyelement` 运算符，并从集合中提取单一实例值。  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>避免对子查询执行隐式强制转换  
 与统一处理子查询相关的一个副作用是将子查询隐式转换为标量值。 具体而言，在 Transact-sql 中，行的多集（具有单个字段）将隐式转换为其数据类型为该字段的数据类型的标量值。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持这种隐式强制。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 提供 ANYELEMENT 运算符从集合中提取单一实例值，并提供 `select value` 子句以避免在查询表达式中创建行包装。  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>选择值：避免隐式行包装器  
 Transact-sql 子查询中的 select 子句会在子句中的项的周围隐式创建行包装。 这意味着我们无法创建标量或对象的集合。 Transact-sql 允许在具有一个字段的 rowtype 与相同数据类型的单一实例值之间进行隐式强制转换。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 提供了 `select value` 子句，以跳过隐式行构建。 在 `select value` 子句中只能指定一个项。 在使用这样的子句时，不会对 `select` 子句中的项构造行包装，并且可生成所需形状的集合，例如：`select value a`。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 还提供了用于构造任意行的行构造函数。 `select` 接受投影中的一个或多个元素，并生成含有字段的数据记录，如下所示：  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>左相关与别名化  
 在 transact-sql 中，给定作用域（ `select`或`from`的单个子句）中的表达式无法引用前面在同一范围内定义的表达式。 SQL 的某些方言（包括 transact-sql）支持`from`子句中的有限形式。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 在 `from` 子句中对左相关进行了一般化，并且对它们进行了统一处理。 `from` 子句中的表达式无需使用额外的语法，即可引用同一子句中先前的定义（位于左侧的定义）。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 还对涉及 `group by` 子句的查询施加了额外的限制。 此类查询的 `select` 子句和 `having` 子句中的表达式只能通过其别名引用 `group by` 关键字。 以下构造在 Transact-sql 中有效，但不在中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]：  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 执行此操作  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>引用表（集合）的列（属性）  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的所有列引用都必须用表别名限定。 以下构造（假定`a`是表`T`的有效列）在 transact-sql 中有效，但在中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]无效。  
  
```sql  
SELECT a FROM T
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 形式为  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 表别名在 `from` 子句中是可选的。 表名称被用作隐式别名。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 还允许使用以下形式：  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>通过对象导航  
 Transact-sql 使用 "." 表示法来引用表的（某行的）列。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 扩展了这一表示法（借用自编程语言）为通过对象的属性导航提供支持。  
  
 例如，如果 `p` 是 Person 类型的表达式，则下面是用于引用此人地址所在城市的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 语法。  
  
```sql  
p.Address.City   
```  
  
## <a name="no-support-for-"></a>不支持 *  
 Transact-sql 支持将非限定的 * 语法作为整行的别名，并支持限定\*语法（t.\*）作为该表字段的快捷方式。 此外，transact-sql 允许使用特殊计数（\*）聚合，其中包括 null 值。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持 * 构造。 窗`select * from T`体的 transact-sql 查询， `select T1.* from T1, T2...`可以分别表示[!INCLUDE[esql](../../../../../../includes/esql-md.md)]为`select value t from T as t`和`select value t1 from T1 as t1, T2 as t2...`。 此外，这些构造还处理继承（值可替换性），同时将 `select *` 变体限制到所声明类型的顶级属性。  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持 `count(*)` 聚合。 请改用 `count(0)`。  
  
## <a name="changes-to-group-by"></a>对 Group By 的更改  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持 `group by` 关键字的别名化。 `select` 子句和 `having` 子句中的表达式必须通过这些别名引用 `group by` 关键字。 例如，以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 语法：  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ...等效于以下 Transact-sql：  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>基于集合的聚合  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持两种合计。  
  
 基于集合的合计对集合进行运算，并且产生合计结果。 它们可以出现在查询中的任何位置，并且不需要 `group by` 子句。 例如：  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 还支持 SQL 样式的合计。 例如:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>ORDER BY 子句用法  
Transact-sql 仅允许在最顶层的 @no__t 块中指定 @no__t 的子句。 在 @no__t 中，您可以使用嵌套的 @no__t 1 表达式，并将其放在查询中的任何位置，但不会保留在嵌套查询中的排序。  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a>标识符  
 在 Transact-sql 中，标识符比较基于当前数据库的排序规则。 在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中，标识符始终不区分大小写但区分重音（即，[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 区分重音字符和非重音字符；例如，“a”不等于“ấ”）。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 将看上去相同但来自不同代码页的字母视为不同的字符。 有关详细信息，请参阅[输入字符集](input-character-set-entity-sql.md)。  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Transact-SQL 功能在 Entity SQL 中不可用  
 以下 Transact-sql 功能在中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]不可用。  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 当前未提供对 DML 语句（insert、update、delete）的支持。  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 的当前版本未提供对 DDL 的支持。  
  
 命令式编程  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]不支持命令式编程，这与 Transact-sql 不同。 请改而使用编程语言。  
  
 分组函数  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 尚未提供对分组函数（例如，CUBE、ROLLUP 和 GROUPING_SET）的支持。  
  
 解析函数  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 尚未提供对解析函数的支持。  
  
 内置函数、运算符  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]支持 Transact-sql 的内置函数和运算符的子集。 这些运算符和函数可能受到主要存储提供程序的支持。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 使用在提供程序清单中声明的特定于存储的函数。 此外，实体框架允许声明内置的和用户定义的现有存储函数，以供[!INCLUDE[esql](../../../../../../includes/esql-md.md)]使用。  
  
 提示  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不提供查询提示机制。  
  
 查询结果批处理  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持查询结果批处理。 例如，下面是有效的 Transact-sql （以批处理的形式发送）：  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 但是，等效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不受支持：  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 仅支持在每个命令中使用一个由结果生成的查询语句。  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 概述](entity-sql-overview.md)
- [不支持的表达式](unsupported-expressions-entity-sql.md)
