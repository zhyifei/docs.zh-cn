---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 8b55519b7f95deb6463af4c0a6a2a53975e5b5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248977"
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)

SELECT 子句可以在可选的 ALL/DISTINCT 修饰符之后具有可选的 TOP 子子句。 TOP 子子句指定查询结果中将只返回第一组行。

## <a name="syntax"></a>语法

```
[ TOP (n) ]
```

## <a name="arguments"></a>自变量

`n`指定要返回的行数的数值表达式。 `n` 可以是单个数值或单个参数。

## <a name="remarks"></a>备注

TOP 表达式必须是单个数值或单个参数。 如果使用一个常量文本，则该文本类型必须可隐式提升为 Edm.Int64（字节、int16、int32 或 int64，或映射到可提升为 Edm.Int64 的类型的任何提供程序类型），并且其值必须大于或等于零。 否则，将引发异常。 如果将一个参数用作表达式，则该参数类型也必须可隐式提升为 Edm.Int64，但由于参数值是后期绑定的，因此在编译过程中不会对实际参数值进行任何验证。

下面是常量 TOP 表达式的示例：

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

下面是参数化 TOP 表达式的示例：

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

除非对查询进行排序，否则 TOP 具有不确定性。 如果需要确定的结果，请在 [ORDER BY](skip-entity-sql.md) 子句中使用 [SKIP](limit-entity-sql.md) 和 [LIMIT](order-by-entity-sql.md) 子子句。 TOP 和 SKIP/LIMIT 是互斥的。

## <a name="example"></a>示例

以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 TOP 指定要从查询结果中返回的最上面一行。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：

1. [按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。

2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a>请参阅

- [SELECT](select-entity-sql.md)
- [SKIP](skip-entity-sql.md)
- [LIMIT](limit-entity-sql.md)
- [ORDER BY](order-by-entity-sql.md)
- [实体 SQL 引用](entity-sql-reference.md)
