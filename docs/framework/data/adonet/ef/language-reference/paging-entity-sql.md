---
title: 分页 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 4c9a08604c90422ac461bdd7db895b18b633e87e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402080"
---
# <a name="paging-entity-sql"></a>分页 (Entity SQL)
可以使用执行物理分页[跳过](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)并[限制](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)中的子子句[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)子句。 若要以确定的方式执行物理分页，应使用 SKIP 和 LIMIT。 如果只想要限制非确定的方式中的结果中的行数，则应使用[顶部](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)。 TOP 和 SKIP/LIMIT 是互斥的。  
  
## <a name="top-overview"></a>TOP 概述  
 SELECT 子句可以在可选的 ALL/DISTINCT 修饰符之后具有可选的 TOP 子子句。 TOP 子子句指定查询结果中将只返回第一组行。 有关详细信息，请参阅[顶部](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)。  
  
## <a name="skip-and-limit-overview"></a>SKIP 和 LIMIT 概述  
 SKIP 和 LIMIT 是 ORDER BY 子句的组成部分。 如果 ORDER BY 子句中存在 SKIP 表达式子子句，则将根据排序规范对结果排序，结果集将包含从紧接着 SKIP 表达式之后的下一行开始的行。 例如，SKIP 5 将跳过前五行，并返回第六行以及后续行。 如果 ORDER BY 子句中存在 LIMIT 表达式子子句，则将根据排序规范对查询排序，并且结果行数将受到 LIMIT 表达式限制。 例如，LIMIT 5 将结果集限制为五个实例或行。 SKIP 和 LIMIT 不必一起使用，可以只将 SKIP 或 LIMIT 用于 ORDER BY 子句。 有关详细信息，请参阅下列主题：  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [如何： 查询结果分页](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
