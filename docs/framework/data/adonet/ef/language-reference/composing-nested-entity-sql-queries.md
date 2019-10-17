---
title: 撰写嵌套的 Entity SQL 查询
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: cd41c36853f50597a32d511d455148d649d9eb64
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395556"
---
# <a name="composing-nested-entity-sql-queries"></a>撰写嵌套的 Entity SQL 查询
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 是一种功能丰富的语言。 @No__t 的构建基块是一个表达式。 与传统的 SQL 不同，[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不限于表格结果集： [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持组合复杂的表达式，这些表达式可以具有文本、参数或嵌套表达式。 表达式中的值可以是参数化的或由其他表达式组成。  
  
## <a name="nested-expressions"></a>嵌套表达式  
 嵌套表达式可以放置在任何可接受其返回类型值的位置。 例如:  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 嵌套查询可以放在投影子句中。 例如:  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中，嵌套查询必须括在括号中：  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 下面的示例演示如何在 @no__t 中正确嵌套表达式：[如何：对两个查询的并集进行排序](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))。  
  
## <a name="nested-queries-in-projection"></a>投影中的嵌套查询  
 投影子句中的嵌套查询可在服务器上转换为笛卡尔积查询。 在某些后端服务器（包括 SQL Server）中，这可能会导致 TempDB 表变得非常大，这可能会对服务器性能产生负面影响。  
  
 以下是这种查询的一个示例：  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a>嵌套查询排序  
 在实体框架中，嵌套表达式可置于查询中的任何位置。 Entity SQL 为编写查询提供了非常大的灵活性，可以在编写的查询中包含对嵌套查询的排序。 但是，将不保留嵌套查询的顺序。  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 概述](entity-sql-overview.md)
