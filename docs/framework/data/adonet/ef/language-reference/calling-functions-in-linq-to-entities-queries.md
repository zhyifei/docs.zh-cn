---
title: 在 LINQ to Entities 查询中调用函数
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 690f1a2cdcd8726d40a6627c1ceb05c9ae7e7fdd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760136"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>在 LINQ to Entities 查询中调用函数
本节中的主题说明如何调用 LINQ to Entities 查询中的函数。  
  
 <xref:System.Data.Objects.EntityFunctions> 和 <xref:System.Data.Objects.SqlClient.SqlFunctions> 类提供了对作为实体框架的一部分的规范函数和数据库函数的访问功能。 有关详细信息，请参阅[如何： 调用规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)和[如何： 调用数据库函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)。  
  
 调用自定义函数的过程需要三个基本步骤：  
  
1.  在概念模型中定义函数或在存储模型中声明函数。  
  
2.  将方法添加到应用程序并将其映射到具有 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> 的模型中的函数。  
  
3.  在 LINQ to Entities 查询中调用该函数。  
  
 有关更多信息，请参见本节中的各主题。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：调用 Canonical 函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [如何：调用数据库函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [如何：调用自定义数据库函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [如何：在查询中调用模型定义的函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [如何：调用模型定义的函数作为对象方法](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>请参阅  
 [LINQ to Entities 中的查询](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [.edmx 文件概述](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [如何： 在概念模型中定义自定义函数](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)
