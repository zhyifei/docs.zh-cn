---
title: 如何：将列表示为允许 Null 值
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 6700ee5d4de53dd82da29d48ca7c42785d52afc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355972"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="72194-102">如何：将列表示为允许 Null 值</span><span class="sxs-lookup"><span data-stu-id="72194-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="72194-103">使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>属性<xref:System.Data.Linq.Mapping.ColumnAttribute>属性用于指定关联的数据库列可以保存 null 值。</span><span class="sxs-lookup"><span data-stu-id="72194-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="72194-104">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>。</span><span class="sxs-lookup"><span data-stu-id="72194-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="72194-105">将列指定为允许 null 值</span><span class="sxs-lookup"><span data-stu-id="72194-105">To designate a column as allowing null values</span></span>  
  
1.  <span data-ttu-id="72194-106">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="72194-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="72194-107">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="72194-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72194-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="72194-108">See Also</span></span>  
 [<span data-ttu-id="72194-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="72194-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="72194-110">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="72194-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
