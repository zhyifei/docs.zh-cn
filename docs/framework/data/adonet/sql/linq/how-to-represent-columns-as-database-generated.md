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
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="8aba9-102">如何：将列表示为数据库生成的</span><span class="sxs-lookup"><span data-stu-id="8aba9-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="8aba9-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 特性<xref:System.Data.Linq.Mapping.ColumnAttribute>上的<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>属性可将字段或属性指定为表示数据库生成的列。</span><span class="sxs-lookup"><span data-stu-id="8aba9-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="8aba9-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>。</span><span class="sxs-lookup"><span data-stu-id="8aba9-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="8aba9-105">指定字段或属性表示数据库生成的列</span><span class="sxs-lookup"><span data-stu-id="8aba9-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="8aba9-106">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="8aba9-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="8aba9-107">将此属性 (Property) 的值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="8aba9-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aba9-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8aba9-108">See also</span></span>

- [<span data-ttu-id="8aba9-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="8aba9-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="8aba9-110">如何：使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="8aba9-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
