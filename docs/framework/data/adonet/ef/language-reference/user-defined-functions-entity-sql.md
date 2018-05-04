---
title: 用户定义的函数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: a3c9cda162e77517d480d9e48eb80fa62dd1c161
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="user-defined-functions-entity-sql"></a>用户定义的函数 (Entity SQL)
Entity SQL 支持在查询中调用用户定义函数。 你可以定义随查询一起这些函数的内联 (请参阅[如何： 调用用户定义函数](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) 或作为概念模型的一部分 (请参阅[如何： 在概念模型中定义自定义函数](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f))。 概念模型函数定义中的 Entity SQL 命令为[DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e)元素[函数](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134)概念模型中的元素。  
  
 通过 Entity SQL，您可以在查询命令自身中定义函数。 [函数](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)运算符定义内联函数。 您可以在单个命令中定义多个函数，这些函数可以具有相同的函数名称，只要函数签名是唯一的。 有关详细信息，请参阅 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)。  
  
## <a name="see-also"></a>请参阅  
 [函数](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
