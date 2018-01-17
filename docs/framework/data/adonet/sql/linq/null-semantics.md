---
title: "Null 语义"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6786c7ea4441b1a753d6f0b4213f40fa64dcb4ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="null-semantics"></a>Null 语义
下表提供了指向 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 文档中讨论 `null` （在`Nothing` 中为 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]）问题的各个部分的链接。  
  
|主题|描述|  
|-----------|-----------------|  
|[SQL-CLR 类型不匹配](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|本主题的“Null 语义”部分包括以下方面的讨论：三态 SQL Boolean 与两态公共语言运行库 (CLR) <xref:System.Boolean>的比较、文本 `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) 与 `null` (C#) 以及其他类似问题。|  
|[标准查询运算符转换](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|本主题的“Null 语义”部分介绍 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]中的 null 比较语义。|  
|[System.String 方法](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|本主题的“与 .NET 的差异”部分说明从 <xref:System.String.LastIndexOf%2A> 返回 0 为何意味着字符串为 null 或找到的位置为 0。|  
|[计算数值序列中值的和](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|说明使用 <xref:System.Linq.Enumerable.Sum%2A> 运算符计算只包含 null 的序列或空序列时，所得结果为何为 `null` （在`Nothing` 中为 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]）。|  
  
## <a name="see-also"></a>请参阅  
 [数据类型和函数](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
