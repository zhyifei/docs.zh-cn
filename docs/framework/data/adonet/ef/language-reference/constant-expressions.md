---
title: 常量表达式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: b31cd881f1307ec734c026d3c873d7a650e19a20
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251136"
---
# <a name="constant-expressions"></a>常量表达式
常量表达式由常量值组成。 常量值被直接转换为常量命令目录树表达式，而无需在客户端进行任何变换。 这包括产生常量值的表达式。 因此，所有涉及常量的表达式都应具有数据源行为。 这可能产生与 CLR 行为不同的行为。  
  
 下面的示例说明了一个在服务器上求值的常量表达式。  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 LINQ to Entities 不支持将用户类用作常量。 但是，用户类上的属性引用被视为常量，将转换为命令目录树常量表达式并在数据源上执行。  
  
## <a name="see-also"></a>请参阅

- [LINQ to Entities 查询中的表达式](expressions-in-linq-to-entities-queries.md)
