---
title: 如何：将列表示为数据库生成的
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: bb9510986581ad6d3bcd0711aed681ef3a7c4e45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781785"
---
# <a name="how-to-represent-columns-as-database-generated"></a>如何：将列表示为数据库生成的
使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 特性<xref:System.Data.Linq.Mapping.ColumnAttribute>上的<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>属性可将字段或属性指定为表示数据库生成的列。  
  
 有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>。  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>指定字段或属性表示数据库生成的列  
  
1. 将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。  
  
2. 将此属性 (Property) 的值设置为 `true`。  
  
## <a name="see-also"></a>请参阅

- [LINQ to SQL 对象模型](the-linq-to-sql-object-model.md)
- [如何：使用代码编辑器自定义实体类](how-to-customize-entity-classes-by-using-the-code-editor.md)
