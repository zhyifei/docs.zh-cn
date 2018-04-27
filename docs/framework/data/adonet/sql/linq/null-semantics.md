---
title: Null 语义
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3c4daa5fd37158f1af31f33ba743a56cf76670d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="null-semantics"></a>Null 语义
下表提供指向各个部分的[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档其中`null`(`Nothing`在 Visual Basic 中) 问题进行讨论。  
  
|主题|描述|  
|-----------|-----------------|  
|[SQL-CLR 类型不匹配](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|本主题的"Null 语义"部分包括以下方面讨论的三态 SQL Boolean 与两态公共语言运行时 (CLR) <xref:System.Boolean>，文本`Nothing`(Visual Basic 中) 和`null`(C#) 以及其他类似问题。|  
|[标准查询运算符转换](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|本主题的“Null 语义”部分介绍 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]中的 null 比较语义。|  
|[System.String 方法](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|本主题的“与 .NET 的差异”部分说明从 <xref:System.String.LastIndexOf%2A> 返回 0 为何意味着字符串为 null 或找到的位置为 0。|  
|[计算数值序列中值的和](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|描述如何<xref:System.Linq.Enumerable.Sum%2A>运算符的计算结果为`null`(`Nothing`在 Visual Basic 中) 而不是 0 一个序列，其中只包含 null 或空序列。|  
  
## <a name="see-also"></a>请参阅  
 [数据类型和函数](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
