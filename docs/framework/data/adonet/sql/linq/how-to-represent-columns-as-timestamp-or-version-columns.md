---
title: "如何：将列表示为时间戳列或版本列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2f97b87b2070ea39dbd16d03a967d80dcfc8f500
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>如何：将列表示为时间戳列或版本列
使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>属性<xref:System.Data.Linq.Mapping.ColumnAttribute>属性将字段或属性指定为表示保存数据库时间戳或版本号的数字的数据库列。  
  
 有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>。  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>将字段或属性指定为表示时间戳列或版本列  
  
1.  将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。  
  
2.  将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 属性值设置为 `true`。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [如何：指定针对并发冲突对哪些成员进行测试](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 [如何：通过使用代码编辑器自定义实体类](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
