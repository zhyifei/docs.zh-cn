---
title: 如何：将列表示为允许 Null 值
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: e3bab3f307bcba77e0d311b96fa79d5a0d01e937
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169632"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="cd5b4-102">如何：将列表示为允许 Null 值</span><span class="sxs-lookup"><span data-stu-id="cd5b4-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="cd5b4-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>属性上的<xref:System.Data.Linq.Mapping.ColumnAttribute>属性指定关联的数据库列可以保存 null 值。</span><span class="sxs-lookup"><span data-stu-id="cd5b4-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="cd5b4-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>。</span><span class="sxs-lookup"><span data-stu-id="cd5b4-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="cd5b4-105">将列指定为允许 null 值</span><span class="sxs-lookup"><span data-stu-id="cd5b4-105">To designate a column as allowing null values</span></span>  
  
1.  <span data-ttu-id="cd5b4-106">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="cd5b4-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="cd5b4-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cd5b4-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5b4-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd5b4-108">See also</span></span>

- [<span data-ttu-id="cd5b4-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="cd5b4-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="cd5b4-110">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="cd5b4-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
