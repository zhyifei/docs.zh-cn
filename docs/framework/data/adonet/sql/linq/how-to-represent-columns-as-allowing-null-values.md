---
title: 如何：将列表示为允许 Null 值
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781807"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>如何：将列表示为允许 Null 值
使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 特性<xref:System.Data.Linq.Mapping.ColumnAttribute>上的<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>属性可指定关联的数据库列可以包含 null 值。  
  
 有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>。  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>将列指定为允许 null 值  
  
1. 将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。  
  
2. 将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性值设置为 `true`。  
  
## <a name="see-also"></a>请参阅

- [LINQ to SQL 对象模型](the-linq-to-sql-object-model.md)
- [如何：使用代码编辑器自定义实体类](how-to-customize-entity-classes-by-using-the-code-editor.md)
