---
title: "如何：将列表示为允许 Null 值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 509c0554c6ce2bd02f1294fe19b1138241864ca9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>如何：将列表示为允许 Null 值
使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>属性<xref:System.Data.Linq.Mapping.ColumnAttribute>属性用于指定关联的数据库列可以保存 null 值。  
  
 有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>。  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>将列指定为允许 null 值  
  
1.  将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。  
  
2.  将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性值设置为 `true`。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [如何：通过使用代码编辑器自定义实体类](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
